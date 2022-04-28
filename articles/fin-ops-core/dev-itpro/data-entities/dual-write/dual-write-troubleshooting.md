---
title: Allmän felsökning
description: Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Ekonomi och Drift-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/07/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 8b5951f9f40179ca0bf31f5cccf1f05a0f968213
ms.sourcegitcommit: 1843235766b6f8cf950a13a310e9f4f2f53c59a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2022
ms.locfileid: "8554611"
---
# <a name="general-troubleshooting"></a>Allmän felsökning

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Ekonomi och Drift-appar och Dataverse.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation

Spårningsloggar kan vara användbara när du felsöker problem med direktsynkronisering mellan Finance & Operations och Dataverse. Loggarna kan innehålla specifik information avsedd för de team som ger teknisk och teknisk support för Dynamics 365. I den här artikeln beskrivs hur du aktiverar spårningsloggar och hur du visar dem. Spårningsloggar hanteras på inställningssidan för Dynamics 365 och kräver behörighet på administratörsnivå för att ändra och visa. 

**Nödvändig roll för att aktivera spårningsloggen och visa fel:** systemadministratör

### <a name="turn-on-the-trace-log"></a>Aktivera spårningsloggen
Så här aktiverar du spårningslogg.

1.  Logga in i Dynamics 365 och välj sedan **Inställningar** i det övre navigeringsfältet. På sidan System klickar du på **Administration**.
2.  På sidan Administration klickar du på **Systeminställningar**.
3.  Markera fliken och insticksmodulen **Anpassning** innan du ändrar listrutan till **Alla** i avsnittet för aktivitetsspårning av anpassat arbetsflöde. Då spåras alla aktiviteter, samntidigt som en omfattande uppsättning data tillhandahålls till de team som måste granska potentiella problem.

> [!NOTE]
> Om du ställer in listrutan till **Undantag** kommer spårningsinformation endast att tillhandahållas när undantag (fel) förekommer.

När de har aktiverats fortsätter loggarna för inloggningsspårning att samlas in tills de stängs av manuellt genom att gå tillbaka till den här platsen och välja **Av**.

### <a name="view-the-trace-log"></a>Visa spårningsloggen
Så här visar du spårningslogg.

1. På inställningssidan för Dynamics 365 väljer du **Inställningar** högst upp i navigeringsfältet. 
2. Välj **Spårningslogg för insticksprogram** i avnittet **Anpassningar** på sidan.
3. Posterna i listan med spårningsloggar baseras på typen av namn och/eller meddelandenamn.
4. Öppna önskad post för att visa hela loggen. Meddelandeblocket i körningsavsnittet ger tillgänglig information för insticksmodulen. Om tillgänglig anges även undantagsinformation. 

Du kan kopiera innehållet i spårningsloggar och klistra in dem i ett annat program som exempelvis Anteckningar eller andra verktyg om du vill visa loggar eller textfiler för att lättare kunna se allt innehåll. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Aktivera felsökningsläget för att felsöka problem med direkt synkronisering i Ekonomi och Drift-appar

**Den roll som krävs för att visa felen:** systemadministratör

Fel i dubbelriktad skrivning som har sitt ursprung i Dataverse kan visas i Ekonomi och Drift-appen. Följ dessa steg om du vill aktivera detaljerad loggning för felen:

1. För samtliga projektkonfigurationer i Ekonomi och Drift-appen finns en **IsDebugMode**-flagga i tabellen **DualWriteProjectConfiguration**.
2. Öppna **DualWriteProjectConfiguration** genom att använda Excel-tillägget. Aktivera designläget i Excel-tillägget för Ekonomi och Drift och lägg till **DualWriteProjectConfiguration** i arket om du vill använda tillägget. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
3. Ange **IsDebugMode** som **Ja** i projektet.
4. Kör scenariot som genererar fel.
5. De detaljerade loggarna lagras i tabellen **DualWriteErrorLog**.
6. Om du vill söka efter data i en tabellwebläsare använder du följande länk: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog` och ersätter `999` efter behov.
7. Uppdatera igen efter [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), som är tillgängligt för uppdatering av plattform 37 och senare. Om du har den här korrigeringen installerad kommer felsökningsläget att samla in fler loggar.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Kontrollera synkroniseringsfel på den virtuella datorn för Ekonomi och Drift-appen

**Den roll som krävs för att visa felen:** systemadministratör

1. Logga in på Microsoft Dynamics Lifecycle Services (LCS).
2. Öppna LCS-projektet som du valde att utföra testning av dubbelriktad skrivning för.
3. Välj panelen **Molnstyrda miljöer**.
4. Logga in på den virtuella datorn (VM) för Ekonomi och Drift-appen med hjälp av fjärrskrivbord. Använd det lokala kontot som visas i LCS.
5. Öppna händelsevisningsprogrammet.
6. Välj **Program- och tjänstloggar \> Microsoft \> Dynamics \> AX-DualWriteSync \> Drift**.
7. Granska listan över de senaste felen.

## <a name="dual-write-ui-landing-page-showing-blank"></a>UI-landningssida för dubbelriktad skrivning som är tom
När du öppnar sidan för dubbel skrivning i webbläsarna Microsoft Edge eller Google Chrome läses startsidan inte in, och du ser en tom sida eller ett fel, exmepelvis "Något gick fel".
I Devtools visas ett fel i konsolloggarna:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: Det gick inte att läsa egenskapen "sessionStorage" från "Fönster": Åtkomst nekas för det här dokumentet. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) på ny t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) på ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) på Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) på jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) på Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) på Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) på Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) på vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) på hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

Användargränssnittet använder webbläsarens "sessionslagring" för att spara vissa egenskapsvärden för inläsning av startsidan. För att detta ska fungera måste tredjepartscookies tillåtas i webbläsaren för webbplatsen. Felet indikerar att användargränssnittet inte kan komma åt sessionslagringen. Det finns två scenarier där det här problemet uppstår:

1.  Du öppnar användargränssnittet i inkognitoläget för Edge/Chrome och tredjepartscookies i inkognito har spärrats.
2.  Du har helt blockerat tredjepartscookies i Edge/Chrome.

### <a name="mitigation"></a>Minskning
Tredjepartscookies måste tillåtas i webbläsarinställningarna.

### <a name="google-chrome-browser"></a>Webbläsaren Google Chrome
Första alternativ:
1.  Gå till inställningarna genom att gå till chrome://settings/ i adressfältet och sedan navigera till Säkerhet > Cookies och andra webbplatsdata.
2.  Välj "Tillåt alla cookies". Om du inte vill göra detta går du vidare till det andra alternativet.

Andra alternativet:
1.  Gå till inställningarna genom att gå till chrome://settings/ i adressfältet och sedan navigera till Säkerhet > Cookies och andra webbplatsdata.
2.  Om du har valt "Spärra tredjepartscookies i Inkognito" eller "Blockera tredjepartscookies" går du till "Webbplatser som alltid kan använda cookies" och klickar på **Lägg till**. 
3.  Lägg till webbplatsnamnet för Finance & Operations-appar – https://<your_FinOp_instance>.cloudax.dynamics.com. Se till att du markerar kryssrutan för "Alla cookies, endast på den här webbplatsen". 

### <a name="microsoft-edge-browser"></a>Webbläsaren Microsoft Edge
1.  Navigera till Inställningar -> Webbplatsbehörigheter -> Cookies och webbplatsdata.
2.  Stäng av "Blockera tredjepartscookies".  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Ta bort länken till och länka en annan Dataverse-miljö från Ekonomi och Drift-app

**Nödvändiga autentiseringsuppgifter för ta bort länken till miljö**: systemadministratör för antingen Ekonomi och Drift-appen eller Dataverse.

1. Logga in på Ekonomi och Drift-appen.
2. Gå till **Arbetsytor \> Datahantering** och välj panelen **Dubbelriktad skrivning**.
3. Markera alla mappningar och sedan **stoppa**.
4. Välj **Ta bort länk till miljö**.
5. Välj **Ja** för att bekräfta åtgärden.

Nu kan du länka en ny miljö.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Det går inte att visa formuläret information om försäljningsorderrad 

När du skapar en försäljningsorder i Dynamics 365 Sales kan du om du klickar på **+ Lägg till produkter** omdirigeras till formuläret för orderrad i Dynamics 365 Project Operations. Från det formuläret finns det inget sätt att visa formuläret för försäljningsorderrad **Information**. Alternativet för **information** visas inte i listrutan under **Ny orderrad**. Detta inträffar eftersom projektåtgärder har installerats i din miljö.

Så här aktiverar du alternativet för formuläret **informations** igen:

1. Navigera till tabellen **orderrad**.
2. Hitta formuläret **Information** under formulärnoden.
3. Markera formuläret **Information** och klicka på **aktivera säkerhetsroller**.
4. Ändra säkerhetsinställningarna till **Visa för alla**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Så här aktiverar och sparar du nätverksspårning så att spårningar kan kopplas till supportbegäranden

Supportteamet kanske måste granska nätverksspårningar för att felsöka vissa problem. Följ dessa steg för att skapa en nätverksspårning:

### <a name="google-chrome-browser"></a>Webbläsaren Google Chrome

1. I den öppnade fliken trycker du på **F12** eller väljer **Utvecklarverktyg** om du vill öppna utvecklarverktygen.
2. Öppna fliken **Nätverk** och skriv in **integ** i filtertextrutan.
3. Kör ditt scenario och observera de förfrågningar som loggas.
4. Högerklicka på posterna och välj **Spara alla som en HAR med innehåll**.

### <a name="microsoft-edge-browser"></a>Webbläsaren Microsoft Edge

1. I den öppnade fliken trycker du på **F12** eller väljer **Utvecklarverktyg** om du vill öppna utvecklarverktygen.
2. Öppna fliken **Nätverk**.
3. Kör ditt scenario.
4. Välj **Spara** för att exportera resultaten som HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
