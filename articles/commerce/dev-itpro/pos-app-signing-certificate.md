---
title: Signera MPOS med ett certifikat för kodsignering
description: I det här avsnittet beskrivs hur du signerar MPOS med ett kodsigneringscertifikat.
author: mugunthanm
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 28021
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-09-2019
ms.openlocfilehash: e45961cf1ddb385d914b700d03bc95d07de47b68
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741553"
---
# <a name="sign-mpos-appx-with-a-code-signing-certificate"></a>Signera MPOS appx med ett certifikat för kodsignering

[!include [banner](../includes/banner.md)]

Om du vill installera Modern POS (MPOS) måste du signera MPOS-programmet med ett kodsigneringscertifikat från en betrodd leverantör och installera samma certifikat på alla maskiner där MPOS installeras under den betrodda rotmappen för den aktuella användaren.

När du vill signera MPOS-programmet med ett certifikat använder du något av följande alternativ i filen **Retail SDK\\Build tool\\Customization.settings**:

- Lägg till uppgiftsdelen Säker fil i Azure DevOps-byggsteg och överför certifikatet för att säkra filuppgiften. Använd den Säker fil-uppgiftens utdatasökvägsvariabel som parameter i filen Customization.settings.

    > [!NOTE]
    > Uppgiften Säker fil har inte stöd för lösenordsskyddat certifikat. Du måste ta bort lösenordet innan du laddar upp den här uppgiften. Eftersom certifikatet laddas upp till systemuppgiften Säker fil i Azure kan du ta bort lösenordet enbart för det här steget. Du bör dock diskutera hur du tar bort lösenordet med dina säkerhets experter för att ta reda på om åtgärden är korrekt för ditt projekt. Ta inte bort certifikatets lösenord för andra scenarier.
- Använd ett certifikat som finns i filsystemet. Det gör du genom att ladda ned eller generera ett certifikat och placera det i filsystemet där bygget körs. Den Microsoft-värdbaserade agenten eller byggvändaren bör ha åtkomst till den här sökvägen och filen.
- Använd tumavtryck för att söka efter certifikatet på lagringsplatsen och logga in med det certifikatet.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Använda uppgiften Säker fil för Universal Windows Platform-appsignering

> [!NOTE]
> Du kan också använda Azure Key Vault om du vill lagra certifikatet och använda Azure-teckenverktyget för att signera Modern POS.appx-filen och installationsprogrammet med självbetjäning. Exempel på pipelineskript och ytterligare information finns i [Konfigurera en bygg-pipeline i Azure DevOps för att generera Retail-självbetjäningspaket](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

Att använda uppgiften Säker fil är det rekommenderade tillvägagångssättet för appsignering i Universal Windows Platform (UWP). Mer information om paketsignering finns i [Konfigurera paketsignering](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Processen visas i följande bild.

![MPOS-appsigneringsflöde.](media/POSSigningFlow.png)

> [!NOTE]
> För närvarande stöder OOB-paketeringen bara signeringen av appx-filen. De olika självbetjäningsinstallationsprogrammen som MPOIS, RSSU och HWS signeras inte av den här processen. Du måste signera det manuellt med hjälp av SignTool eller andra signeringsverktyg. Certifikatet som används för att signera appx-filen måste installeras i maskinen där Modern POS är installerat.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Steg för att konfigurera certifikatet för signering i Azure Pipelines

### <a name="certificate-in-the-file-systemsecure-location"></a>Certifikat i filsystemet/säker plats

Ladda ned [uppgiften DownloadFile](/visualstudio/msbuild/downloadfile-task) och lägg till den som ett första steg i byggprocessen. Fördelen med att använda uppgiften Säker fil är att filen är krypterad och placeras på disken under bygget oavsett om bygg-pipelinen lyckas, misslyckas eller avbryts. Filen tas bort från nedladdningsplatsen när byggprocessen är klar.

1. Ladda ned och lägg till uppgiften Säker fil som ett första steg i Azure-bygg-pipelinen. Du kan ladda ned uppgiften Säker fil från [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
2. Ladda upp certifikatet till uppgiften Säker fil och ställ in referensnamnet under Utdatavariabler, enligt bilden nedan.
    > [!div class="mx-imgBorder"]
    > ![Uppgiften Säker fil.](media/SecureFile.png)
3. Skapa en ny variabel i Azure Pipelines genom att välja **Ny variabel** på fliken **Variabler**.
4. Ange ett namn på variabeln i värdefältet, t.ex. **MySigningCert**.
5. Spara variabeln.
6. Öppna filen **Customization.settings** från **RetailSDK\\BuildTools** och uppdatera **ModernPOSPackageCertificateKeyFile** med variabelnamnet som skapades i pipelinen (steg 3). Exempel:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Det här steget är obligatoriskt om certifikatet inte är lösenordsskyddat. Om certifikatet är lösenordsskyddat fortsätter du med följande steg.
 
7. Lägg till en ny variabel med säker test på fliken **Variabler** i pipelinen. Ange namnet som **MySigningCert.secret** och ställ in värdet på lösenordet för certifikatet. Välj låsikonen för att säkra variabeln.
8. Lägg till uppgiften **Powershell-skript** i pipelinen (efter Ladda ned Säker fil och före Bygg-steget). Ange **Visning**-namn och ange Typ som **Infogat**. Kopiera och klistra in följande i skriptavsnittet.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

9. Öppna filen **Customization.settings** från **RetailSDK\\BuildTools** och uppdatera **ModernPOSPackageCertificateThumbprint** med certifikatets tumavtrycksvärde.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Information om hur du hämtar tumavtrycket för ett certifikat finns i [Hämta ett certifikats tumavtryck](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

 
## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Ladda ned eller generera ett certifikat för att signera MPOS-appen manuellt med msbuild i SDK

Om ett nedladdat eller genererat certifikat används för att signera MPOS-appen uppdaterar du noden **ModernPOSPackageCertificateKeyFile** i filen **BuildTools\\Customization.settings** så att den pekar på pfx-filplatsen (**$(SdkReferencesPath)\\appxsignkey.pfx**). Exempel:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

I det här fallet är namnet på certifikatfilen **appxsignkey.pfx**, som finns i mappen **Retail SDK\\Reference**.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Använda tumavtryck för att signera MPOS-appen

Om du använder tumavtryck för att signera MPOS-appen ska du installera certifikatet lokalt. Uppdatera tumavtrycksvärdet i noden **ModernPOSPackageCertificateThumbprint** i filen **BuildTools\\Customization.settings**.

Det här alternativet fungerar om bygganvändaren är en lokal användare. Men om du använder Azure DevOps-agenter för att generera bygget kanske agenten inte har behörighet att få åtkomst till certifikatarkivet för att använda certifikatet för signering, eller så kommer byggdatorn inte få certifikatet installerat. I detta fall är lösningen att ändra bygganvändaren till lokal användare och installera certifikatet i rutan. Detta alternativ fungerar dock inte om du inte har admin-åtkomst till rutan.

> [!NOTE]
> Om alternativet för .pfx-fil eller uppgiften Säker fil används för att signera appen ska du låta noden **ModernPOSPackageCertificateThumbprint** i **Customization.settings** vara tom. Om tumavtrycksalternativet har använts ska du lämna **ModernPOSPackageCertificateKeyFile** tomt. Om båda värdena uppdateras misslyckas bygget.

### <a name="certification-renewal"></a>Förnyelse av certifiering

### <a name="renew-a-certificate-from-trusted-ca"></a>Förnya ett certifikat från en betrodd certifikatutfärdare

Kontakta din certifikatutfärdare (CA, certifying authority) för att förnya certifikatet. För ett betrott certifikat krävs inga åtgärder på MPOS-sidan.

### <a name="renew-a-self-signed-certificate"></a>Förnya ett självsignerat certifikat

Använd inte exempelcertifikatet som är tillgängligt i Retail SDK för produktion. Det kan bara användas utveckling. Contoso-exemplet kan inte förnyas och exempelcertifikatet som ingår i Retail SDK-version 10.0.16 eller tidigare upphör att gälla den 31 december 2020. Om det här certifikatet, eller ett självsignerat certifikat, har använts för att signera en anpassad Modern POS finns det en stor risk för att Modern POS inte fungerar som det ska efter detta datum.
 
### <a name="impact"></a>Effekt
 
Om ovanstående stämmer för dig är problemet som du kommer att stöta på att installationsprogrammet inte kommer att kunna köras efter 31 december 2020. Beroende på vilken företags-IT-policy som används, kanske Modern POS inte kan fungera. Det är mycket viktigt att du testar det här genom att ändra datumet tillfälligt till ett framtida datum för att bestämma effekten för din organisation.
 
### <a name="steps-to-determine-the-issue"></a>Steg för att fastställa problemet
 
1.  Använd Windows-inställningar för att ändra datorns klocka till ett datum och tid under år 2021.
2.  Kontrollera att Modern POS kan öppnas, inloggning fungerar och en transaktion kan slutföras.
3.  Kontrollera att Modern POS självbetjäningsinstallationsprogrammet kan köras, och i så fall att installation kan slutföras.
4.  Returnera Windows-klockinställningarna till korrekt datum och tid.
 
Om du kan utföra alla de här stegen utan problem kommer du att kunna arbeta med aktuellt certifikat efter den 31 december 2020.  
 
### <a name="steps-going-forward"></a>Framtida steg 

Vi rekommenderar att du förnyar det tidigare använda certifikatet. Vi rekommenderar starkt att du skaffar ett nytt certifikat. För att göra det måste du utföra någon av följande åtgärder:
 
- **Prioriterad** – Skaffa ett kodsigneringscertifikat från en betrodd certifikatutfärdare.

- **Ej prioriterat** – Generera ett självsignerat kodsigneringscertifikat att använda. Detta används normalt bara för utvecklingssyften inom en domän och rekommenderas inte för produktion. 

- **Tillgängligt som tillfällig lösning** – Använd det förnyade Contoso-kodsigneringscertifikatet. Detta används vanligtvis för testsyften, så du rekommenderas inte att distribuera den i produktion.
 
Nu ska du generera ett nytt anpassat Modern POS-paket som har signerats med det här certifikatet som erhållits från någon av åtgärderna ovan. Beroende på certifikatet måste något av stegen nedan följas:
 
- Om du använder ett nytt, betrott certifikat (eller ett nytt, självsignerat certifikat) måste du installera ett nytt certifikat på alla enheter. Därefter måste du ta det nya Modern POS-paketet (installationsprogrammet), avinstallera det befintliga programmet och sedan installera om det nya Modern POS-paketet. Du måste utföra en enhetsaktivering av Modern POS på alla enheter.

- Om du använder det förnyade Contoso-certifikatet måste du installera det nya certifikatet på alla enheter och installera Modern POS-paketet (installationsprogrammet). Du måste inte avinstallera, men du måste installera om enheten. Observera att enhetsaktivering av Modern POS inte krävs. Det här alternativet är en tillfällig lösning. Använd bara det här alternativet om du vill undvika att återaktivera och för att lösa problemet innan du får ett nytt, betrott certifikat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
