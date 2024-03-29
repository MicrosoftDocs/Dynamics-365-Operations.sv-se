---
title: Startsida för mobilapp
description: Den här artikeln beskriver mobilappen för ekonomi och drift (Dynamics 365) och ger länkar till resurser som kan hjälpa dig att implementera den i din organisation.
author: sericks007
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-02-28
ms.dyn365.ops.version: Platform update 4
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.openlocfilehash: a0979df7c0cd685f810c0ab743fbede740e7aacb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284081"
---
# <a name="mobile-app-home-page"></a>Startsida för mobilapp

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Den här artikeln beskriver mobilappen **Ekonomi och drift (Dynamics 365)** och ger länkar till resurser som kan hjälpa dig att implementera den i din organisation.

## <a name="overview"></a>Översikt

Mobilappen låter din organisation sina dess affärsprocesser tillgängliga på mobila enheter. När din IT-administratör aktiverar funktionen för mobila arbetsytor för organisationen, kan användare logga in på appen och omedelbart börja köra affärsprocesser från sina mobila enheter. Mobilappen innehåller följande funktioner som hjälper dig att öka produktiviteten:

- Användare kan visa, redigera och arbeta med affärsdata, även om de har en opålitlig nätverksanslutning eller om deras mobila enheter är helt offline. När en enhet återupprättar en nätverksanslutning, synkroniseras offline dataågärder automatiskt.
- IT-administratörer och utvecklare kan bygga och publicera mobila arbetsytor som har anpassats till organisationen. Appen använder befintliga kodtillgångar. Det innebär inte du inte behöver återimplementera dina valideringsförfaranden, affärslogik eller säkerhetskonfiguration.
- IT-administratörer och utvecklare kan enkelt utforma mobila arbetsytor genom att använda arbetsytedesignern med peka-och-klicka som ingår i webbklienten.
- IT-administratörer och utvecklare kan även optimera arbetsytornas offlinekapacitet med hjälp av ramverket för Business logic utbyggbarhet. Eftersom data fortfarande bearbetas när en enhet är offline, förblir dina mobila scenarier omfattande eller flytande, även om enheterna inte har fasta nätverksanslutningar.

## <a name="elements-of-the-mobile-app"></a>Delar av mobilappen
Navigering i mobilappen består av fyra grundläggande begrepp: instrumentpanel, arbetsytor, sidor och åtgärder. 

[![Navigeringsbegrepp i mobilappen.](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. När du startar programmet kan du gå till **instrumentpanelen**.
2. På instrumentpanelen visas en lista över **arbetsytor** som har publicerats.
3. I varje arbetsyta visas en lista över **sidor** som är tillgängliga för arbetsytan.
4. När du befinner dig på en sida kan du utföra flera åtgärder. Nedan följer några exempel:

    - Visa detaljerad information.
    - Navigera till andra sidor för relaterade data, till exempel enhetsinformation eller -rader.
    - Visa en lista över **åtgärder** som är tillgängliga för den aktuella sidan. Åtgärder låter dig skapa och redigera befintliga data.

## <a name="implementation-process"></a>Implementeringsprocess
Följande illustration visar processen för implementering av såväl mobila arbetsytor som tillhandahålls av Microsoft, som anpassade mobila arbetsytor. 

[![Implementeringsprocess för mobilappar.](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

Följande tabell innehåller länkar till resurser som hjälper dig att implementera såväl mobila arbetsytor som tillhandahålls av Microsoft, som anpassade mobila arbetsytor. Siffrorna i den första kolumnen visar de numrerade stegen i illustrationen.

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
<td>Implementera appen för ekonomi och drift i din organisation.</td>
<td><ul><li>Om du ännu inte har installerat en version av Microsoft Dynamics 365, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö</a>.</li><li>En lista över de mobila arbetsytor som kan användas finns i <a href="mobile-workspaces-released.md">Mobila arbetsytor som nyligen lanserats</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Systemadministratör</td>
<td><strong>Om du använder Microsoft Dynamics 365 for Operations version 1611:</strong>  Hämta och installera KBs som gör det möjligt för mobila arbetsytor som tillhandahålls av Microsoft.</td>
<td>Se följande avsnitt för mer information:
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Mobil arbetsyta för kostnadskontroll</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Mobil arbetsyta för inventering av lagerbehållning</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Mobil arbetsyta för arbetsplatser</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Mobil arbetsyta för leverantörssamarbete</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">Mobil arbetsyta för projekttidangivelse</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">Mobil arbetsyta för utläggshantering</a></li>

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
<td>Använd mobila plattformen om du vill skapa anpassade mobila arbetsytor.</td>
<td><a href="platform/mobile-platform-home-page.md">Mobilplattform</a></td>
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
<td>Tillämpa det driftfärdiga paketet som innehåller de anpassade arbetsytor som tillhandahålls av den oberoende programvaruleverantören (ISV).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Systemadministratör</td>
<td>Publicera anpassade mobila arbetsytor som tillhandahålls av ISV.</td>
<td><a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Användare</td>
<td>Hämta och installera mobilappen.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Appen Ekonomi och drift för Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Appen Ekonomi och drift för iOS</a><BR/>
(Windows Phone stöds inte)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Användare</td>
<td>Logga in och använd mobilappen. Appen inkluderar de mobila arbetsytor som har publicerats av systemadministratören.</td>
<td>En lista över de mobila arbetsytor som tillhandahålls av Microsoft finns i <a href="mobile-workspaces-released.md">Mobila arbetsytor som nyligen lanserats</a>.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>Felsökning
[Mobila plattformsresurser](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

