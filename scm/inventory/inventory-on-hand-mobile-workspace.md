---
title: "Mobil arbetsyta för inventering av lagerbehållning"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för lagerbehållning. Denna arbetsyta ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst."
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: d14f3510df45169e3b77ee9c4f3d0d9d389e6036
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Mobil arbetsyta för inventering av lagerbehållning

[!include[banner](../includes/banner.md)]

Det här avsnittet innehåller information om den mobila arbetsytan för **Lagerbehållning**. Denna arbetsyta ger dig insyn i reserverat och lagerbehållning, när som helst och var som helst.

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>Översikt
Normalt har företag flera in- och flera utleveranser av lager varje dag. Dessa transporter ändrar konstant tillgänglig lagerstatus. Den mobila arbetsytan för **Lagerbehållning** låter dig se tillgänglig lagerstatus för hela företaget, vilket ger dig den senaste informationen om lagerdata på valfri mobil enhet. Oavsett om du arbetar i på lagerstället, inom inköp, försäljning, tillverkning, administration eller har andra roller, kan du använda datan för tillgängligt lager när som helst och var som helst. 

Den mobila arbetsytan för inventering av lagerbehållning ger en översikt över lagerbehållningsstatus över lokaler. Där kan du visa lagerbehållning över lokaler, aktuella reservationer och oreserverad lagerbehållning. Du kan också ange artikelnummer till en förfrågan om lagerbehållning och söka filtrerat efter produkter i lager eller varianter. 

Närmare bestämt erbjuder den mobila arbetsytan följande funktioner:

-   Du kan söka efter produktnummer och produktnamn för att hitta produkter att visa lagerbehållningsstatusen för.
-   Du kan visa följande information för valda produkter:

    -   Lagerbehållning efter plats
    -   Lagerbehållning efter lagerställe
    -   Lagerbehållning efter plats
    -   Lagerbehållningen per batch (för batchstyrda produkter)
    -   Lagerbehållning efter lagerstatus
    
-   Lagerbehållning för produkt visas på följande sätt:

    -   Genom fysiskt lager (denna vy representerar den totala mängden.)
    -   Genom fysiskt reserverat (denna vy representerar den reserverade mängden.)
    -   Genom fysiskt disponibelt (den här vyn representerar tillgänglig mängd utan reservationer.)

## <a name="prerequisites"></a>Förutsättningar
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update"></a>Kraven om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 uppdatering 
Om Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017-uppdateringen) har implementerats för din organisation, måste systemadministratören publicera den mobila arbetsytan **Lagerbehållning**. Instruktioner finns i [Publicera en mobil arbetsyta](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare
Om Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav. 

<table>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Roll</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementera KB 4013633.</td>
<td>Systemadministratör</td>

<td>KB 4013633 är en X++ -uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>lagerbehållning</strong>. Om du vill implementera KB 4013633 måste systemadministratören göra följande.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Lagerbehållning</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Hämta och installera mobilappen Dynamics 365 for Unified Operations:

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Visa lagerbehållningen för en produkt med hjälp av den mobila arbetsytan för lagerbehållning

1.  På din mobila enhet väljer du arbetsytan **Lagerbehållning**.

2.  Välj **Kontrollera lagerbehållning för en artikel**. Du kan se en lista över de produkter som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform).
3.  Om objektet inte finns i listan väljer du **Sök fler**. Sök efter produktnummer eller växla till en sökning efter produktnamn.

4.  Välj en produkt. Om artikeln har en bild, visas bilden.
5.  Välj ett av följande alternativ för att visa lagerbehållningens status:

    -   Visa lagerbehållning per plats
    -   Visa lagerbehållning per lagerställe
    -   Visa lagerbehållning efter plats
    -   Visa lagerbehållning per batch (för batchstyrda produkter)
    -   Visa lagerbehållning per lagerstatus

    Lagerbehållning för produkt visas på följande sätt:
    -   Genom fysiskt lager (denna vy representerar den totala mängden.)
    -   Genom fysiskt reserverat (denna vy representerar den reserverade mängden.)
    -   Genom fysiskt disponibelt (den här vyn representerar tillgänglig mängd utan reservationer.)

