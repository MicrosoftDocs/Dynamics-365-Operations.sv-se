---
title: Allmän felsökning
description: Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 779cc80d4cb510e79885919f1c705824ab6ad58b3e2fe1bab7bbec0511d08951
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736312"
---
# <a name="general-troubleshooting"></a>Allmän felsökning

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>När du försöker installera paketet för dubbelriktad skrivning visas med hjälp av verktyget package deployer inga tillgängliga lösningar

Vissa versioner av verktyget package deployer är inte kompatibla med lösningspaketet för dubbelriktad skrivning. Om du vill installera paketet måste du först använda [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) eller senare av verktyget package deployer.

När du har installerat verktyget package deployer installerar du lösningspaketet genom att följa stegen nedan.

1. Hämta den senaste lösningspaketfilen från Yammer. com. När paketets zip-fil har hämtats högerklickar du på den och väljer **egenskaper**. Markera kryssrutan **Avblockera** och välj sedan **Använd**. Om du inte ser kryssrutan **Avblockera** är zip-filen redan avblockerad och du kan hoppa över det här steget.

    ![Dialogrutan Egenskaper.](media/unblock_option.png)

2. Extrahera paketets zip-fil och kopiera alla filer i mappen **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.43**.

    ![Innehåll i mappen Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438.](media/extract_package.png)

3. Klistra in alla kopierade filer i mappen **Verktyg** i verktyget package deployer. 
4. Kör **PackageDeployer. exe** för att välja Dataverse-miljön och installera lösningarna.

    ![Innehåll i mappen Verktyg.](media/paste_copied_files.png)

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

**Den roll som krävs för att visa felet:** systemadministratören Fel i dubbelriktad skrivning som har sitt ursprung i Dataverse kan visas i Finance and Operations-appen. I vissa fall är den fullständiga texten i felmeddelandet inte tillgänglig eftersom meddelandet är för långt eller innehåller personligt identifierande information (PII). Du kan aktivera detaljerad loggning för fel genom att följa stegen nedan.

1. Alla projektkonfigurationer i Finance and Operations-appar har en **IsDebugMode**-egenskap i kolumnen **DualWriteProjectConfiguration**. Öppna kolumnen **DualWriteProjectConfiguration** genom att använda Excel-tillägget.

    > [!TIP]
    > Ett enkelt sätt att öppna tabellen är att aktivera **design**-läget i Excel-tillägget och sedan lägga till **DualWriteProjectConfigurationEntity** i kalkylbladet. För mer information, se [Öppna tabelldata i Excel och uppdatera den med hjälp av Excel-tillägget](../../office-integration/use-excel-add-in.md).

2. Ställ in egenskapen **IsDebugMode** på **ja** för projektet.
3. Kör scenariot som genererar fel.
4. De detaljerade loggarna finns i registret DualWriteErrorLog. Om du vill söka efter data i en registerläsare använder du följande URL (ersätt **XXX** efter behov):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]