---
title: Mobil arbetsyta för inventering av lagerbehållning
description: Denna artikel innehåller information om den mobila arbetsytan för lagerbehållning. Denna arbetsyta ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst.
author: yufeihuang
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 640a45e29627ffe56535c7d05419309688e8ecb6
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069829"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Mobil arbetsyta för inventering av lagerbehållning

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Denna artikel innehåller information om den mobila arbetsytan för **lagerbehållning**. Denna arbetsyta ger dig insyn i reserverat och lagerbehållning, när som helst och var som helst.

Denna mobila arbetsyta är avsedd att användas med mobilappen Ekonomi och drift (Dynamics 365).

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
Förutsättningarna varierar baserat på vilken version av Supply Chain Management som har distribuerats inom organisationen.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Förutsättningar om du använder Supply Chain Management
Om Supply Chain Management används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Lagerbehållning**. Instruktioner finns i [Publicera en mobil arbetsyta](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>Förutsättningar om du använder plattformsuppdatering 3 eller senare 
Om plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav. 

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
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigeringar för metadata från Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Lagerbehållning</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Ladda ner och installera mobilappen för Ekonomi och drift (Dynamics 365):

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    [![Dra nedåt för att uppdatera.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Visa lagerbehållningen för en produkt med hjälp av den mobila arbetsytan för lagerbehållning

1.  På din mobila enhet väljer du arbetsytan **Lagerbehållning**.

2.  Välj **Kontrollera lagerbehållning för en artikel**. Du kan se en lista över de produkter som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

