---
title: Kundbokföringsprofiler
description: Det här avsnittet beskriver kundbokföringsprofiler som styr bokföringen av kundtransaktioner till huvudboken.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91432a401a8f8a499e9f5e2bbe7157408faac822
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952581"
---
# <a name="customer-posting-profiles"></a>Kundbokföringsprofiler

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver kundbokföringsprofiler som styr bokföringen av kundtransaktioner till huvudboken.

## <a name="customer-posting-profiles"></a>Kundbokföringsprofiler

Kundbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar för alla kunder, en grupp av kunder eller en enskild kund. Dessa inställningar kommer att användas när du skapar försäljningsorderfakturor, fritextfakturor, projektfakturor, betalningsjournaler, inkassobrev och räntefakturor. 

Standardbokföringsprofilen definieras på fliken **Redovisning och moms** på sida **Parametrar för kundreskontra**. Den inkluderas sedan automatiskt i rubriken på nya dokument. Du kan ändra den där om en annan bokföringsprofil krävs. 

Organisationer som accepterar förskottsbetalningar från kunder konfigurerar ofta en andra bokföringsprofil för förskottsbetalningar och kopplar den till parametrarna som standardbokföringsprofil för förskottsbetalningar. Mer information finns i [Kundförbetalningar](customer-prepayments.md).

Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan **Bokföringsdefinitioner för transaktioner**. Bokningsdefinitioner används istället för bokföringsprofiler för att styra bokföringen av kundtransaktioner till huvudboken. Mer information finns i [Bokföringsdefinitioner](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Skapa en bokföringsprofil.
Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen. Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen. Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:

| Fältvärde Kontokod | Fältvärde Konto-/gruppnummer                | Sökprioritet |
|--------------------------|-------------------------------------------------|-----------------|
| Register                    | Specifikt kundkonto                       | 1               |
| Grupp                    | Kundgrupp som kunden är kopplad till. | 2               |
| Alla                      | Tom                                           | 3               |

Om du vill att alla kundtransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja **Alla** i fältet **Kontokod**. Ange följande värden om du vill ställa in din bokföringsprofil.

<table>
<thead>
<tr>
<th>Fält</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bokföringsprofil</td>
<td>Ange en kod för bokföringsprofilen. Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för kundsaldon i den nationella valutan och ett annat för kundsaldon i en utländsk valuta. Du kan kalla en för Nationell och den andra för Utländsk.</td>
</tr>
<tr>
<td>Beskrivning</td>
<td>Ange en beskrivning av bokföringsprofilen. Detta används endast för att bättre identifiera bokföringsprofilen när du visar den på den här sidan.</td>
</tr>
<tr>
<td>Kontokod</td>
<td>Ange om bokföringsprofilen gäller för en enda kund, en grupp kunder eller alla kunder:
<ul>
<li><b>Tabell</b> – Bokföringsprofilen gäller för en enskild kund. Välj kundkontot i fältet <b>Konto-/gruppnummer</b>.</li>
<li><b>Grupp</b> – Bokföringsprofilen gäller för en kundgrupp. Välj kundgruppen i fältet <b>Konto-/gruppnummer</b>.</li>
<li><b>Alla</b> – Bokföringsprofilen gäller för alla kunder. Lämna fältet <b>Konto-/gruppnummer</b> tomt.</li>
</ul>
</td>
</tr>
<tr>
<td>Konto-/gruppnummer</td>
<td>Om du har valt <b>Tabell</b> i fältet <b>Kontokod</b> anger du kontonumret för kunden som är associerad med bokföringsprofilen. Om du väljer <b>Grupp</b> ska du välja kundgruppen. Om du har valt <b>Alla</b> lämnar du det här fältet tomt.</td>
</tr>
<tr>
<td>Samlingskonto</td>
<td>Välj det huvudkonto som används som kundreskontra handel för kunderna som är associerade med bokföringsprofilen. Detta konto är kontot för bokföringstypen <b>Kundsaldo</b>.</td>
</tr>
<tr>
<td>Likviditetskonto för betalningar</td>
<td>Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser. Det här fältet visas bara om kassaflödesprognoser aktiveras.</td>
</tr>
<tr>
<td>Förskottsbetalningar av moms</td>
<td><p>Välj momskontonumret för betalningar som mottas i förskott.</p>
<p><strong>Obs!</strong> Använd sidan <b>Parametrar för kundreskontra</b> för att ange postningsprofilen som används när en betalning markeras som en förskottsbetalning.</p>
</td>
</tr>
<tr>
<td>Skulder för diskonteringskonto</td>
<td>Välj huvudbokskontot för diskonterade skulder.</td>
</tr>
<tr>
<td>Kravbrevsserie</td>
<td>Välj identifieraren för kravbrevsserien som används för kunder som tilldelas bokföringsprofilen.</td>
</tr>
<tr>
<td>Räntekod</td>
<td>Välj räntekoden för beräkning av ränta för kunder som tilldelas bokföringsprofilen.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Bokföringsexempel

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar. **Debet/kredit**-kolumnen anger om transaktionen vanligtvis debet- eller kredit, eller i vissa fall kan bokföra. Kolumnen **Clearingkonto** visar att bokföringstypen är ett clearingkonto. Det innebär att det belopp som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs. 

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | D/K | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Kundsaldo | 130100 | Kundfordringar | Tillgång | Båda | Nej | Ange kontot i **Sammanfattning**.|
| Inget | 110110 | Bankkonto | Tillgång | Båda | Nej | Ange huvudkontot i fältet **likviditetskontot för betalning**. Detta konto används inte för bokföring. Den används bara för kassaflödesprognoser. |
| Förskottsbetalningar av moms | 202900 | Avräkning av moms | Skulder | Båda | Ja | Välj momskontonumret för betalningar som mottas i förskott. |
| Skulder för diskonteringskonto | 250600 | Uppskjuten intäkt och rabatter | Skulder | Båda | Ja | Välj huvudbokskontot för diskonterade skulder.|     

### <a name="table-restrictions"></a>Registerbegränsningar

Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen. Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.

Ange följande värden om du vill ställa in din bokföringsprofil:

| Fält                 | Beskrivning                                           |
|-----------------------|-------------------------------------------------------|
| Bostadsområde        | Markera den här växlingsknappen för automatisk kvittning av transaktioner som har denna bokföringsprofil. Om den här växlingsknappen avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan **Kvitta öppna transaktioner** eller sidan **Ange kundbetalningar**. |
| Intresse          | Markera den här växlingsknappen om ränta ska beräknas på utestående saldon för kundkonton som använder den här profilen. Om växlingsknappen är avmarkerad beräknas ingen ränta för dessa kunder.                                           |
| Kravbrev | Markera den här växlingsknappen om kravbrev ska skapas för kundkonton som använder den här profilen. Om växlingsknappen är avmarkerad skapas inga kravbrev för dessa kunder.                                                 |
| Stäng             | Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs. En transaktion betraktas som stängd när den har kvittats helt.             |



Mer information finns i [Översikt över kundbetalning](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
