---
title: "Mobil arbetsyta för kostnadskontroll"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för kostnadskontroll som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 31a9650774b2ddb70827ffa210154ca10c761236
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Mobil arbetsyta för kostnadskontroll

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om den mobila arbetsytan för kostnadskontroll som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Översikt över Mobil arbetsyta för kostnaskontroll
-------------------------------------------------

Mobil arbetsyta för **Kostnadskontroll** ger en omedelbar översikt över aktuell prestanda för kostnadsställen genom att jämföra faktiska kostnader mot budgeterade kostnader. Du kan gå ända ner till statusen för enskilda kostnadselement. Till exempel en medarbetare får en inbjudan till en internationell konferens, men organisationen måste stå för alla resekostnader. Medarbetaren frågar sin chef om han kan delta i konferensen. Chefen öppnar den mobila arbetsytan för **kostnadskontroll** i sin mobiltelefon för att se om budgeten tillåter att medarbetaren deltar i konferensen.

### <a name="data-security"></a>Datasäkerhet

Datan i den mobila arbetsytan för **kostnadskontroll** skyddas av användarens autentiseringsuppgifter. Chefer för ett kostnadsställe får endast se data för eget kostnadsställe. Säkerheten för åtkomstnivå hanteras inom modulen **kostnadsredovisning**. Kostnadsrevisorerna definierar konfigurationen för den mobila arbetsytan för **kostnadskontroll** i modulen **kostnadsredovisning**. När arbetsytan publiceras i mobilappen Microsoft Dynamics 365 for Operations, blir den tillgänglig i appen. Detta säkerställer att alla chefer för kostnadsställen i organisationen ser data i samma format.

### <a name="actions-views-and-links"></a>Åtgärder, vyer och länkar

Den mobila arbetsytan för **kostnadskontroll** för appen Dynamics 365 for Operations innehåller följande åtgärder, vyer och länkar:

-   **Åtgärder:**
    -   Använd **Välj konfiguration** för att välja en layout.
    -   Använd **Välj kostnadsobjekt** för att välja kostnadsobjekt att filtrera data på. **Anmärkning:** kostnadsställen som finns med i listan beror på den åtkomst som beviljas i modulen **kostnadsredovisning**.
-   **Vyer:** Baserat på de åtgärder som väljs och konfigurationen i modulen **Kostnadsredovisning** kan du visa följande information på korten.
    -   Utfall kontra Budget (aktuell period)
    -   Utfall kontra reviderad budget (aktuell period)
    -   Utfall kontra Budget (föregående period)
    -   Utfall kontra reviderad budget (föregående period)
    -   Utfall kontra budget (hittills i år)
    -   Utfall kontra reviderad budget (hittills i år)

    Följande belopp på varje kort: Utfall, Budget, Avvikelse och Avvikelse i %.
-   **Länkar:**
    -   Information om aktuell period.
    -   Information om föregående period.
    -   Information om hittillsvarande år.

    När du väljer en länk visas ett kort för varje kostnadselement. Följande belopp visas på varhje kort: Utfall, Budget, Budgetavvikelse, Budgetavvikelseprocent, Reviderad budget, Reviderad budgetavvikelse samt Reviderad budgetavvikelseprocent. 
    
    [![Kort för ett kostnadselement ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Förutsättningar
Innan du kan använda mobil arbetsyta för **kostnadskontroll** ska du se till att systemadministratören har följande förutsättningar på plats.

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
<td>Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare måste genomföras.</td>
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
<td><strong>Mobil arbetsyta för kostnadskontroll</strong> måste publiceras i mobilappen för Dynamics 365 for Operations.</td>
<td>Systemadministratör</td>
<td><ol>
<li>Starta Dynamics 365 for Operations i din webbläsare.</li>
<li>På sidan <strong>systemparametrar</strong> anger du <strong>Hantera mobila arbetsområden</strong>.</li>
<li>Välj arbetsytan <strong>översikt över kostnadsobjekt</strong>.</li>
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

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Visa prestanda för ditt kostnadsställe med hjälp av den mobila arbetsytan för kostnadskontroll
1.  På din mobila enhet väljer du arbetsytan **Kostnadsstyrning**.
2.  Välj **Styrning av kostnadsobjekt**.
3.  Välj **Åtgärder**.
4.  Välj **Välj konfiguration** för att välja en layout för kostnadsstyrning.
5.  Välj **Klar**.
6.  Välj **Åtgärder**.
7.  Välj **Välj kostnadsobjekt** för att välja de kostnadsställen för vilka du har beviljats åtkomst till.
8.  Välj **Klar**.
9.  Visa total prestanda för ditt kostnadsställe.
10. Välj länken **detaljer för aktuell period**.
11. Visa prestandan för enskilda kostnadselement.
12. Du kan också söka efter specifika kostnadselement.





