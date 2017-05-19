---
title: "Mobil arbetsyta för inventering av lagerbehållning"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för inventering av lagerbehållning som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Denna arbetsyta ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e703ae80800b993ebca1c7bee455af1be41c7d5f
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Mobil arbetsyta för inventering av lagerbehållning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om den mobila arbetsytan för inventering av lagerbehållning som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Denna arbetsyta ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Översikt över Mobil arbetsyta för inventering av lagerbehållning
--------------------------------------------------

Normalt har företag flera in- och flera utleveranser av lager varje dag. Dessa transporter ändrar konstant tillgänglig lagerstatus. **Den mobila arbetsytan för inventering av lagerbehållning** låter dig se tillgänglig lagerstatus för hela företaget, vilket ger dig senaste information om lagerdata på valfri mobil enhet. Oavsett om du arbetar i på lagerstället, inom inköp, försäljning, tillverkning, administration eller har andra roller, kan du använda datan för tillgängligt lager när som helst och var som helst. Den mobila arbetsytan för inventering av lagerbehållning ger en översikt över lagerbehållningsstatus över lokaler. Där kan du visa lagerbehållning över lokaler, aktuella reservationer och oreserverad lagerbehållning. Du kan också ange artikelnummer till en förfrågan om lagerbehållning och söka filtrerat efter produkter i lager eller varianter. Närmare bestämt erbjuder den mobila arbetsytan följande funktioner:

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
Innan du kan använda **Mobil arbetsyta för tillgängligt lager** ska du se till att systemadministratören har följande förutsättningar på plats.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Roll</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare måste genomföras.</td>
<td>Systemadministratör</td>
<td>Om du inte redan använder Dynamics 365 for Operations i din organisation kan systemadministratören se <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Distribuera en demomiljö för Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4013633 måste genomföras.</td>
<td>Systemadministratör</td>
<td>KB 4013633 (X++ uppdatering eller snabbkorrigering av metadata) innehåller fyra mobila arbetsytor för hantering av leveranskedjan. Om du vill implementera KB 4013633 måste systemadministratören göra följande:
<ol>
<li>Hämta KB 4013633 från Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Snabbkorrigering av metadata</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Koppla det driftfärdiga paketet</a> till Dynamics 365 for Operations-systemet.</li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Mobil arbetsyta för tillgängligt lager</strong> måste publiceras i mobilappen för Dynamics 365 for Operations.</td>
<td>Systemadministratör</td>
<td><ol>
<li>Starta Dynamics 365 for Operations i din webbläsare.</li>
<li>På sidan <strong>systemparametrar</strong> anger du <strong>Hantera mobila arbetsområden</strong>.</li>
<li>Välj <strong>arbetsyta för inventering av lagerbehållning</strong></li>
<li>Klicka på <strong>Publicera mobil arbetsyta</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Hämta och installera mobilappen Dynamics 365 for Operation.
Hämta och installera mobilappen Dynamics 365 for Operation från din mobilappsbutik.

-   För Android - [Dynamics 365 for Operations i Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   För iPhone: [Dynamics 365 for Operations iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Logga in på mobilappen Dynamics 365 for Operations
1.  Starta appen i din mobila enhet.
2.  Ange URL för Dynamics 365 for Operations
3.  Ange ett företag att logga in på. Ange till exempel **USMF**.
4.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter.
5.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor. 

    [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Visa lagerbehållningen för en produkt med hjälp av Mobil arbetsyta för inventering av lagerbehållning
1.  På din mobila enhet väljer du arbetsytan **Lagerbehållning**.
2.  Välj **Kontrollera lagerbehållning för en artikel**. Du kan se en lista över de produkter som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/).
3.  Om objektet inte finns i listan väljer du **Sök fler** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter produktnummer eller växla till en sökning efter produktnamn.
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






