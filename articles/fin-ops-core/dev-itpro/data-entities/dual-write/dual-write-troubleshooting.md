---
title: Allmän felsökning
description: Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: bcedb9f6e8fb15210512ed6a376d4329759593e4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781184"
---
# <a name="general-troubleshooting"></a>Allmän felsökning

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation

**Nödvändig roll för att aktivera spårningsloggen och visa fel:** systemadministratör

Så här aktiverar du spårningslogg.

1. Logga in på kundengagemangsappen, öppna sidan **inställningar** och under **System**, välj **Administration**.
2. På sidan **Administration** väljer du **Systeminställningar**.
3. På fliken **Anpassning** i kolumnen **Plugin-program and aktivitetsspåring för anpassat arbetsflöde**, välj **Alla** för att aktivera spårningsloggen för plugin-program. Om du bara vill logga spårningsloggar när undantag inträffar kan du istället välja **undantag**.


Så här visar du spårningslogg.

1. Logga in på kundengagemangsappen, öppna sidan **inställningar** och under **Anpassning**, välj **Spårningslogg för plugin-program**.
2. Sök efter spårningsloggarna där kolumnen **Typnamn** anges till **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Dubbelklicka på ett objekt om du vill visa hela loggen och på snabbfliken **Körning**, granska texten **Meddelandeblock**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Aktivera felsökningsläget för att felsöka problem med direkt synkronisering i Finance and Operations-appar

**Den roll som krävs för att visa felen:** systemadministratör

Fel i dubbelriktad skrivning som har sitt ursprung i Dataverse kan visas i Finance and Operations-appen. Följ dessa steg om du vill aktivera detaljerad loggning för felen:

1. För samtliga projektkonfigurationer i Finance and Operations-appen finns en **IsDebugMode**-flagga i tabellen **DualWriteProjectConfiguration**.
2. Öppna **DualWriteProjectConfiguration** genom att använda Excel-tillägget. Aktivera designläget i Exce-tillägget för Finance and Operations och lägg till **DualWriteProjectConfiguration** i arket om du vill använda tillägget. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
3. Ange **IsDebugMode** som **Ja** i projektet.
4. Kör scenariot som genererar fel.
5. De detaljerade loggarna lagras i tabellen **DualWriteErrorLog**.
6. Om du vill söka efter data i en tabellwebläsare använder du följande länk: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog` och ersätter `999` efter behov.
7. Uppdatera igen efter [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), som är tillgängligt för uppdatering av plattform 37 och senare. Om du har den här korrigeringen installerad kommer felsökningsläget att samla in fler loggar.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Kontrollera synkroniseringsfel på den virtuella datorn för Finance and Operations-appen

**Den roll som krävs för att visa felen:** systemadministratör

1. Logga in på Microsoft Dynamics Lifecycle Services (LCS).
2. Öppna LCS-projektet som du valde att utföra testning av dubbelriktad skrivning för.
3. Välj panelen **Molnstyrda miljöer**.
4. Logga in på den virtuella datorn (VM) för Finance and Operations-appen med hjälp av fjärrskrivbord. Använd det lokala kontot som visas i LCS.
5. Öppna händelsevisningsprogrammet.
6. Välj **Program- och tjänstloggar \> Microsoft \> Dynamics \> AX-DualWriteSync \> Drift**.
7. Granska listan över de senaste felen.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Ta bort länken och länka en annan Dataverse-miljö från en Finance and Operations-app

**Nödvändiga autentiseringsuppgifter för ta bort länken till miljö**: systemadministratör för antingen Finance and Operations-appen eller Dataverse.

1. Logga in på Finance and Operations-appen.
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

### <a name="chrome"></a>Chrome

1. I den öppnade fliken trycker du på **F12** eller väljer **Utvecklarverktyg** om du vill öppna utvecklarverktygen.
2. Öppna fliken **Nätverk** och skriv in **integ** i filtertextrutan.
3. Kör ditt scenario och observera de förfrågningar som loggas.
4. Högerklicka på posterna och välj **Spara alla som en HAR med innehåll**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. I den öppnade fliken trycker du på **F12** eller väljer **Utvecklarverktyg** om du vill öppna utvecklarverktygen.
2. Öppna fliken **Nätverk**.
3. Kör ditt scenario.
4. Välj **Spara** för att exportera resultaten som HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
