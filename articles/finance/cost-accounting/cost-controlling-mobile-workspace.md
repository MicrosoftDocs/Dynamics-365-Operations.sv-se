---
title: Mobil arbetsyta för kostnadskontroll
description: Det här avsnittet innehåller information om Mobil arbetsyta för kostnadskontroll. Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 27381a408df64b8f11323b2f164d242bb2c4b6c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249711"
---
# <a name="cost-controlling-mobile-workspace"></a>Mobil arbetsyta för kostnadskontroll

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om den mobila arbetsytan **kostnadskontroll**. Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst.

Denna mobila arbetsyta är avsedd att användas med mobilappen Finance and Operations.

## <a name="overview"></a>Översikt
Mobil arbetsyta för **Kostnadskontroll** ger en omedelbar översikt över aktuell prestanda för kostnadsställen genom att jämföra faktiska kostnader mot budgeterade kostnader. Du kan gå ända ner till statusen för enskilda kostnadselement.

Till exempel en medarbetare får en inbjudan till en internationell konferens, men organisationen måste stå för alla resekostnader. Medarbetaren frågar sin chef om han kan delta i konferensen. Chefen öppnar den mobila arbetsytan för **kostnadskontroll** i sin mobiltelefon för att se om budgeten tillåter att medarbetaren deltar i konferensen.

### <a name="data-security"></a>Datasäkerhet
Datan i den mobila arbetsytan för **kostnadskontroll** skyddas av användarens autentiseringsuppgifter. Chefer för ett kostnadsställe får endast se data för eget kostnadsställe. Säkerheten för åtkomstnivå hanteras inom modulen **kostnadsredovisning**.

Kostnadsrevisorerna definierar konfigurationen för den mobila arbetsytan för **kostnadskontroll** i modulen **kostnadsredovisning**. När arbetsytan publiceras i mobilappen, blir den tillgänglig i appen. Detta säkerställer att alla chefer för kostnadsställen i organisationen ser data i samma format.

### <a name="actions-views-and-links"></a>Åtgärder, vyer och länkar
Den mobila arbetsytan **kostnadskontroll** innehåller följande åtgärder, vyer och länkar:

-   **Åtgärder:**

    -   Använd **Välj konfiguration** för att välja en layout.
    -   Använd **Välj kostnadsobjekt** för att välja kostnadsobjekt att filtrera data på.
    
        > [!NOTE]
        > Kostnadsställen som finns med i listan beror på den åtkomst som beviljas i modulen **kostnadsredovisning**.

-   **Vyer:** Baserat på de åtgärder som väljs och konfigurationen i modulen **Kostnadsredovisning** kan du visa följande information på korten.

    -   Utfall kontra budget (aktuell period)
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
    
    [![Kort för ett kostnadselement ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Förutsättningar
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Förutsättningar om du använder Microsoft Dynamics 365 Finance
Om Finance används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Kostnadskontroll**. Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Förutsättningar om du använder version 1611 med plattformsuppdateringen 3 eller senare
Om version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav.

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

<td>KB 4013633 är en X++ -uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>kostnadskontroll</strong>. Om du vill implementera KB 4013633 måste systemadministratören göra följande.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigeringar för metadata från Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>kostnaskontroll</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen
Hämta och installera mobilappen Finance and Operations:

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

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
