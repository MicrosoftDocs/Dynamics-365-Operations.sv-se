---
title: "Startsida för mobillappen Dynamics 365 for Operations"
description: "Det här avsnittet beskriver mobilappen Microsoft Dynamics 365 for Operations och ger länkar till resurser som kan hjälpa dig att genomföra den i din organisation."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5962fa36b061382e7f0ad55c08c81ac2cebc047d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Startsida för mobillappen Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver mobilappen Microsoft Dynamics 365 for Operations och ger länkar till resurser som kan hjälpa dig att genomföra den i din organisation.

<a name="overview"></a>Översikt
--------

Mobilappen Microsoft Dynamics 365 for Operations låter din organisation göra dess affärsprocesser tillgängliga på mobila enheter. När din IT-administratör aktiverar funktionen för mobila arbetsytor för organisationen kan användare logga in på appen och omedelbart börja köra affärsprocesser från sina mobila enheter. Mobilappen Dynamics 365 for Operations innehåller följande funktioner som hjälper dig att öka produktiviteten:

-   Användare kan visa, redigera och arbeta med affärsdata, även om de har en opålitlig nätverksanslutning eller om deras mobila enheter är helt offline. När en enhet återupprättar en nätverksanslutning, synkroniseras offline dataågärder automatiskt med Dynamics 365 for Operations.
-   IT-administratörer och utvecklare kan bygga och publicera mobila arbetsytor som har anpassats till organisationen. Appen använder befintliga kodtillgångar. Det innebär inte du inte behöver återimplementera dina valideringsförfaranden, affärslogik eller säkerhetskonfiguration.
-   IT-administratörer och utvecklare utformar enkelt mobila arbetsytor med arbetsytedesignern med peka och klicka som ingår i webbklienten för Dynamics 365 for Operations.
-   IT-administratörer och utvecklare kan även optimera arbetsytornas offlinekapacitet med hjälp av ramverket för Business logic utbyggbarhet. Eftersom data fortfarande bearbetas när en enhet är offline, förblir dina mobila scenarier omfattande eller flytande, även om enheterna inte har fasta nätverksanslutningar.

## <a name="elements-of-the-mobile-app"></a>Delar av mobilappen
Navigera i mobilappen består av fyra enkla begrepp: instrumentpanelen, arbetsytor, sidor och åtgärder. 

[![Navigeringsbegrepp i mobilappen](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   När du startar programmet kan du gå till **instrumentpanelen**.
-   På den här instrumentpanelen visas en lista över **arbetsytor** som publiceras i Dynamics 365 for Operations-miljön.
-   I varje arbetsyta visas en lista över **sidor** som är tillgängliga för arbetsytan.
-   Du kan visa data som hämtas från en eller flera sidor i Dynamics 365 for Operations.
-   Du kan navigera till sidor med relaterade data, till exempel information om enhet eller rader.
-   På sidan kan du även se en lista över **åtgärder** som är tillgängliga för den aktuella sidan.
-   Åtgärder låter dig skapa och redigera befintliga data.

## <a name="implementation-process"></a>Implementeringsprocess
Följande bild visar hur för implementering av mobilappen Dynamics 365 for Operations inom din organisation. 

![Implementeringsprocess för mobila program](./media/mobile-implementation-process_4.png)

Följande tabell inkluderar länkar till resurser som kan hjälpa dig att inkludera mobilappen Dynamics 365 for Operations i din organisation. Siffrorna i den första kolumnen visar de numrerade stegen i illustrationen.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Steg</th>
<th>Roll</th>
<th>Åtgärd</th>
<th>Resurser som hjälper dig att slutföra åtgärden</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Systemadministratör</td>
<td>Implementera Dynamics 365 for Operations i organisationen.</td>
<td>Om du inte redan använder Dynamics 365 for Operations i din organisation, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö för Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Systemadministratör</td>
<td>Hämta och installera KBs som gör det möjligt för mobila arbetsytor som tillhandahålls av Microsoft.</td>
<td>Se delen om &quot;förutsättningar&quot; i avsnittet om den mobila arbetsyta som din organisation vill använda:
<ul>
<li><a href="/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Mobil arbetsyta för kostnadskontroll</a></li>
<li><a href="/dynamics365/operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Mobil arbetsyta för inventering av lagerbehållning</a></li>
<li><a href="/dynamics365/operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Mobil arbetsyta för arbetsplatser</a></li>
<li><a href="/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Mobil arbetsyta för leverantörssamarbete</a></li>
<li><a href="/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Mobil arbetsyta för projekttidangivelse</a></li>
<li><a href="/dynamics365/operations/financials/expense-management/expense-management-mobile-workspace">Mobil arbetsyta för utgiftshantering</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Systemadministratör</td>
<td>Publicera mobila arbetsytor som tillhandahålls av Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publicera mobil arbetsyta</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Utvecklare eller oberoende programvaruleverantör (ISV)</td>
<td>Använd Dynamics 365 for Operations mobila ramverk om du vill skapa egna mobila arbetsytor.</td>
<td><ul>
<li><a href="mobile-platform.md">Det mobila ramverket för Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">Arbetsyta för Dynamics 365 for Operation X++ API:er</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Skapa driftfärdiga paket som innehåller anpassade mobila arbetsytor och överför paketet till Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Systemadministratör</td>
<td>Tillämpa det driftfärdiga paketet som innehåller egna arbetsytor som tillhandahålls av ISV.</td>
<td><a href="../deployment/apply-deployable-package-system.md">Koppla det driftfärdiga paketet till ett Microsoft Dynamics 365 for Operations-system</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Systemadministratör</td>
<td>Publicera anpassade mobila arbetsytor som tillhandahålls av ISV.</td>
<td><a href="publish-mobile-workspace.md">Publicera mobil arbetsyta</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Användare</td>
<td>Hämta och installera mobilappen Dynamics 365 for Operation.</td>
<td><ul>
<li>För Android - <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations i Google Play Store</a></li>
<li>För iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations iTunes apps store</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Användare</td>
<td>Logga in på mobilappen Dynamics 365 for Operations Appen inkluderar mobila arbetsytor som har publicerats.</td>
<td>Om du vill se en lista över mobila arbetsytor som tillhandahålls av Microsoft, se då <a href="mobile-workspaces-released.md">nyligen lanserade mobila arbetsytor för mobilappen Dynamics 365 for Operations</a>
</td>
</tr>
</tbody>
</table>






