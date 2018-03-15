---
title: "Kundbokföringsprofiler"
description: "Bokföringsprofiler för kund styr bokföringen av kundtransaktionerna i redovisningen.kundpool"
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: d0795a9cb1839c45cf264b0d0f7cffacdc01ea9d
ms.contentlocale: sv-se
ms.lasthandoff: 02/23/2018

---

# <a name="customer-posting-profiles"></a>Kundbokföringsprofiler

[!include[banner](../includes/banner.md)]


Bokföringsprofiler för kund styr bokföringen av kundtransaktionerna i redovisningen.kundpool

<a name="customer-posting-profiles"></a>Kundbokföringsprofiler
-------------------------

Kundbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar för alla kunder, en grupp av kunder eller en enskild kund. Dessa inställningar kommer att användas när du skapar försäljningsorder, fritextfakturor, kontantbetalningar, kravbrev samt räntefakturor. För en del transaktioner kan du markera en bokföringsprofil som skiljer sig från och har företräde framför de bokföringsprofiler som har ställts in för transaktioner på den här sidan. 

Standardbokföringsprofilen definieras på snabbfliken Redovisning och moms på parametersidan Kundreskontra. Standardbokföringsprofilen inkluderas sedan automatiskt i rubriken för nya dokument som du kan ändra den till en annan bokföringsprofil, om det behövs.

Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan Bokföringsdefinitioner för transaktioner. Bokföringsprofiler styr bokföringen av kundtransaktionerna i redovisningen istället för bokföringsprofiler.

## <a name="creating-a-posting-profile"></a>Skapa en bokföringsprofil.
Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen. Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen. Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:

| Fältvärde **Kontokod** | Fältvärde **Konto-/gruppnummer**            | Sökprioritet |
|------------------------------|-------------------------------------------------|-----------------|
| **Register**                    | Specifikt kundkonto                       | 1               |
| **Grupp**                    | Kundgrupp som kunden är kopplad till. | 2               |
| **Alla**                      | Tom                                           | 3               |

Om du vill att alla kundtransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja Alla i fältet Kontokod. Ange följande värden om du vill ställa in din bokföringsprofil:

<table>
<thead>
<tr class="header">
<th>Fält</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Bokföringsprofil</strong></td>
<td>Ange en kod för bokföringsprofilen. Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för kundsaldon i den nationella valutan och ett annat för kundsaldon i en utländsk valuta. Du kan kalla en för Nationell och den andra för Utländsk.</td>
</tr>
<tr class="even">
<td><strong>Beskrivning</strong></td>
<td>Ange en beskrivning av bokföringsprofilen. Detta används endast för att bättre identifiera bokföringsprofilen när du visar den på den här sidan.</td>
</tr>
<tr class="odd">
<td><strong>Kontokod</strong></td>
<td>Ange om bokföringsprofilen gäller för en enda kund, en grupp kunder eller alla kunder:
<ul>
<li><strong>Tabell</strong> – Bokföringsprofilen gäller för en enskild kund. Välj kundkontot i fältet Konto-/gruppnummer.</li>
<li><strong>Grupp</strong> – Bokföringsprofilen gäller för en kundgrupp. Välj kundgruppen i fältet Konto-/gruppnummer.</li>
<li><strong>Alla</strong> – Bokföringsprofilen gäller för alla kunder. Lämna fältet Konto-/gruppnummer tomt.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Konto-/gruppnummer</strong></td>
<td>Om du har valt Tabell i fältet Kontokod anger du kontonumret för kunden som är associerad med bokföringsprofilen. Om du väljer Grupp ska du välja kundgruppen. Om du har valt Alla lämnar du det här fältet tomt.</td>
</tr>
<tr class="odd">
<td><strong>Samlingskonto</strong></td>
<td>Välj det redovisningskonto som används som kundsamlingskonto för kunderna som är associerade med bokföringsprofilen.</td>
</tr>
<tr class="even">
<td><strong>Kvittningskonto</strong></td>
<td>Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser. Det här fältet visas bara om kassaflödesprognoser aktiveras.</td>
</tr>
<tr class="odd">
<td><strong>Förskottsbetalningar av moms</strong></td>
<td>Välj momskontonumret för betalningar som mottas i förskott.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Obs!" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Obs!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Använd parametersidan Kundreskontra för att ange bokföringsprofilen som används när en betalning markeras som förskottsbetalning.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Skulder för diskonteringskonto</strong></td>
<td>Välj huvudbokskontot för diskonterade skulder.</td>
</tr>
<tr class="odd">
<td><strong>Kravbrevsserie</strong></td>
<td>Välj identifieraren för kravbrevsserien som används för kunder som tilldelas bokföringsprofilen.</td>
</tr>
<tr class="even">
<td><strong>Räntekod</strong></td>
<td>Välj räntekoden för beräkning av ränta för kunder som tilldelas bokföringsprofilen.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Registerbegränsningar**

Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen. Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.

Ange följande värden om du vill ställa in din bokföringsprofil:

| Fält                 | Beskrivning                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Kvittning**        | Markera den här växlingsknappen för automatisk kvittning av transaktioner som har denna bokföringsprofil. Om den här växlingsknappen avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan Kvitta öppna transaktioner eller sidan Ange kundbetalningar. |
| **Intresse**          | Markera den här växlingsknappen om ränta ska beräknas på utestående saldon för kundkonton som använder den här profilen. Om växlingsknappen är avmarkerad beräknas ingen ränta för dessa kunder.                                           |
| **Kravbrev** | Markera den här växlingsknappen om kravbrev ska skapas för kundkonton som använder den här profilen. Om växlingsknappen är avmarkerad skapas inga kravbrev för dessa kunder.                                                 |
| **Stäng**             | Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs. En transaktion betraktas som stängd när den har kvittats helt.                                                                           |



Mer information finns i [Översikt över kundbetalning](../cash-bank-management/tasks/customer-payment-overview.md).


