---
title: Spåra provisioner i kassan (POS) med hjälp av försäljningsgrupper
description: Det är vanligt att spåra försäljningen per den medarbetare som arbetade med kunden – och ge hjälp, ökad försäljning, korsförsäljning och bearbetar transaktionen.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: afbf69c072ae205e973203d97a5fbca7504ae04f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415717"
---
# <a name="track-commissions-in-the-point-of-sale-pos-by-using-sales-groups"></a>Spåra provisioner i kassan (POS) med hjälp av försäljningsgrupper

[!include [banner](includes/banner.md)]

Det är vanligt att spåra försäljningen per den medarbetare som arbetade med kunden – och ge hjälp, ökad försäljning, korsförsäljning och bearbetar transaktionen.

Spåra försäljning per säljare är ett mått på medarbetarnas säljfärdigheter, medan försäljning per kassör ett mått på hastigheten och effektiviteten. Försäljning spårad per säljare används också ofta för att beräkna provision eller andra ersättningar.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Konfigurera en arbetare för att vara en försäljare i kassan

När arbetare har lagts till en försäljningsgrupp kan de bli berättigade till provision och kan identifieras i systemet som en säljare. En arbetare som inte finns i en försäljningsgrupp är inte berättigad till provision och anges inte som säljare i kassaprogrammet. I kassan hämtas listan över säljare från alla försäljningsgrupper som innehåller minst en arbetare som har tilldelats till butiken. Listan visas i kassan som en kombination av försäljningsgrupp-ID och namn (ID : Namn). En standardgrupp för försäljning kan tilldelas arbetare för att ge stöd för scenarier där återförsäljaren väljer att ange säljaren automatiskt på kassaraderna. Användarna kan välja från valfri försäljningsgrupp som arbetaren tillhör.

## <a name="functionality-profile-settings"></a>Inställningar för funktionsprofil

Det finns ett antal inställningar för funktionsprofil för en butik som bestämmer det flöde och den process i kassan som berör säljare.

<table>
<thead>
<tr>
<th>Profil</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Återgå till kassör om tillgänglig</td>
<td>Om det här alternativet är aktiverat fyller kassan automatiskt i transaktionsrader med den aktuella kassörens standardgrupp för försäljning. Om en kassör saknar standardförsäljningsgrupp anges värdet inte. En användare kan manuellt ange försäljningsgruppen genom att använda kassaknappen i knappsatsen.</td>
</tr>
<tr>
<td>Fråga efter säljare</td>
<td>Det här alternativet har tre möjliga värden:
<ul>
<li><strong>Nej</strong> – Om det här alternativet väljs ombeds användaren inte att välja en försäljningsgrupp. Värdet kan fortfarande anges med en kassörs standardgrupp för försäljning eller manuellt genom att använda en kassaknapp i knappsatsen.</li>
<li><strong>Transaktionens början</strong> - Om det här alternativet väljs och antingen alternativet <strong>Återgå till kassör</strong> inte har aktiverats eller den aktuella kassören inte har en standardgrupp för försäljning, uppmanas användaren att välja en försäljningsgrupp i början av varje transaktion. Välja en försäljningsgrupp vid den här uppmaningen visar som standard alla efterföljande rader från den valda försäljningsgruppen. En användare kan manuellt ange försäljningsgruppen genom att använda kassaknappen i knappsatsen.</li>
<li><strong>För varje rad</strong> - Om det här alternativet väljs och antingen alternativet <strong>Återgå till kassör</strong> inte har aktiverats eller den aktuella kassören inte har en standardgrupp för försäljning, uppmanas användaren att välja en försäljningsgrupp när varje rad har lagts till. En användare kan fortfarande manuellt ange försäljningsgruppen genom att använda kassaknappen i knappsatsen.</li>
</ul>
</td>
</tr>
<tr>
<td>Kräv</td>
<td>Det här alternativet gäller endast om kassan har konfigurerats för att fråga efter säljare. Om aktiverat uppmanas användaren att välja en försäljningsgrupp innan du fortsätter. Annars uppmanas användaren, men kan avbryta och fortsätta utan att göra ett val. När raden har lagts till kan en användare med tillräcklig behörighet dock ta bort försäljningsgruppen från raden. "Kräv säljare" används inte i den situationen.</td>
</tr>
</tbody>
</table>

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Visa informationen om säljare på skärmen med kassatransaktioner

Skärmens layout och innehållet för kassatransaktionen kan konfigureras med hjälp av skärmlayoutdesignern och tilldelade skärmlayouter för butiker, kassor eller arbetare. Fältet **Försäljningsrepresentant** kan läggas till på fliken Rader i kvittofönstret.  Då visas ID för den angivna försäljningsgruppen för varje rad på transaktionsskärmen.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Lägga till säljaråtgärder i kassaknappsatser

I kassan kan användare konfigurera knappsatser som ingår på skärmar för att komma åt kassaåtgärder. Följande kassaåtgärder kan tilldelas knappar i knappsatsen som tillhör säljare.

| Åtgärd                                 | beskrivning |
|-------------------------------------------|-------------|
| Ange säljare på rad          | Den här kassaåtgärden visar en lista över berättigade försäljningsgrupper (ID : Namn) för butiken. Om du väljer en försäljningsgrupp i listan ställs värdet in på den aktuella transaktionsraden. |
| Rensa säljare på rad        | Kassaåtgärden tar bort aktuellt försäljningsgruppsvärde från den aktuella transaktionsraden. |
| Ställ in säljare på transaktion   | Den här kassaåtgärden visar en lista över berättigade försäljningsgrupper (ID : Namn) för butiken. Om du väljer en försäljningsgrupp i listan ställs standardvärdet in på den aktuella transaktionen. Alla befintliga rader utan försäljningsgrupp tilldelad ställs in, samt alla rader som läggs till i efterhand. |
| Rensa säljare på transaktion | Kassaåtgärden tar bort aktuellt standardförsäljningsgruppvärde från den aktuella transaktionen. Det påverkar inte de rader som redan finns i transaktionen. |

## <a name="calculating-commissions"></a>Beräkna provisioner

Provisionen beräknas för arbetare inom angivna försäljningsgrupper vid tidpunkten för bokföring av utdrag eller försäljningsorder. Provisionsbeloppet bestäms utifrån arbetarens provisionsandel, enligt definitionen i försäljningsgruppen och tillhörande provisionsberäkningsinställningar för kund och/eller produkter för transaktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]