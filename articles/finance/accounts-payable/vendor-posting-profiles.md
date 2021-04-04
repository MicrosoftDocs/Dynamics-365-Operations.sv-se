---
title: Bokföringsprofiler för leverantörer
description: Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.
author: abruer
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022e7d979ca7572bb824bc5248fec8c0b3c283d0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248169"
---
# <a name="vendor-posting-profiles"></a>Bokföringsprofiler för leverantörer

[!include [banner](../includes/banner.md)]

Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.

<a name="vendor-posting-profiles"></a>Bokföringsprofiler för leverantörer
-----------------------

Leverantörsbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar till alla leverantörer, en grupp leverantörer eller en enskild leverantörer. De här inställningarna kan användas när inköpsorder leverantörsfakturor och kontantbetalningar skapas. För en del transaktioner kan du markera en bokföringsprofil som skiljer sig från och har företräde framför de bokföringsprofiler som har ställts in för transaktioner på den här sidan. Standardbokföringsprofilen definieras på snabbfliken **Redovisning och moms** på parametersidan **Leverantörsreskontra**. Standardbokföringsprofilen inkluderas sedan automatiskt i rubriken för nya dokument som du kan ändra den till en annan bokföringsprofil, om det behövs.

Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan **Bokföringsdefinitioner för transaktioner**. Bokföringsprofiler styr bokföringen av leverantörstransaktionerna i redovisningen istället för bokföringsprofiler.

## <a name="creating-a-posting-profile"></a>Skapa en bokföringsprofil.
### <a name="setup"></a>**Inställningar**

Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen. Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen. Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:

| Fältvärde **Kontokod** | Fältvärde **Konto-/gruppnummer**        | Sökprioritet |
|------------------------------|---------------------------------------------|-----------------|
| **Register**                    | Specifikt leverantörskonto.                     | 1               |
| **Grupp**                    | Leverantörsgrupp som är kopplad till leverantören | 2               |
| **Allt**                      | Tom                                       | 3               |

Om du vill att alla leverantörstransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja **Alla** i fältet **Kontokod**. Ange följande värden om du vill ställa in din bokföringsprofil.

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
<td>Ange en kod för bokföringsprofilen. Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för leverantörssaldon i den nationella valutan och ett annat för leverantörssaldon i en utländsk valuta. Du kan kalla en för Nationell och den andra för Utländsk.</td>
</tr>
<tr class="even">
<td><strong>Beskrivning</strong></td>
<td>Ange en beskrivning av bokföringsprofilen.</td>
</tr>
<tr class="odd">
<td><strong>Kontokod</strong></td>
<td>Ange om bokföringsprofilen gäller för en specifik leverantör, en grupp leverantörer eller alla leverantörer:
<ul>
<li><strong>Tabell</strong> – Bokföringsprofilen gäller för en enskild leverantör. Välj leverantörskontot i fältet <strong>Konto-/gruppnummer</strong>.</li>
<li><strong>Grupp</strong> – Bokföringsprofilen gäller för en leverantörsgrupp. Välj leverantörsgruppen i fältet <strong>Konto-/gruppnummer</strong>.</li>
<li><strong>Alla</strong> – Bokföringsprofilen gäller för alla leverantörer. Lämna fältet <strong>Konto-/gruppnummer</strong> tomt.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Konto-/gruppnummer</strong></td>
<td>Om du har valt <strong>Tabell</strong> i fältet <strong>Kontokod</strong> anger du kontonumret för leverantören som är associerad med bokföringsprofilen. Om <strong>Grupp</strong> är markerat markerar du en leverantörsgrupp. Om du har valt <strong>Alla</strong> lämnar du det här fältet tomt.</td>
</tr>
<tr class="odd">
<td><strong>Samlingskonto</strong></td>
<td>Välj det redovisningskonto som används som samlingskonto för den/de leverantör(er) bokföringsprofilen gäller. Parametern <strong>Tillåt inte manuell inmatning</strong> för det här huvudkontot kommer att markeras. Om du senare tar bort det här kontot från bokföringsprofilen validerar inställningen <strong>Tillåt inte manuell inmatning</strong> på sidan <strong>Huvudkonto</strong>. 
<p><strong>OBS!</strong> Om alternativet <strong>Använd bokföringsdefinitioner</strong> valts på sidan <strong>Allmänna huvudboksparametrar</strong>, används transaktionsbokföringsdefinitionen för leverantörsfakturor i stället för samlingskontot.</p>
</td>
</tr>
<tr class="even">
<td><strong>Kvittningskonto</strong></td>
<td>Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser. Detta fält är endast tillgängligt när kassaflödesprognoser aktiveras.</td>
</tr>
<tr class="odd">
<td><strong>Förskottsbetalningar av moms</strong></td>
<td>Välj kontonumret för momsbetalningar som mottas i förskott.
<p><strong>OBS!</strong> Bokföringsprofilen som används när betalningen markeras som en förskottsbetalning väljs i profilen <strong>Bokföringsprofil</strong> med fältet <strong>förskottsbetalningsjournal</strong> i området <strong>Redovisning och moms</strong> på sidan <strong>Parametrar för leverantörsreskontra</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>Införsel</strong></td>
<td>Markera redovisningskontot där information om ej godkända fakturor registreras. Informationen registreras i Fakturaregisterjournal. Till exempel anger en användare mycket grundläggande information om leverantörsfakturor när de tas emot i fakturaregistret. När fakturaregistret bokförs, bokförs transaktionerna på det konto som har angetts här och i fältet <strong>Motkonto</strong>. När fakturorna godkänns överförs skulden från kontot Införselkonto till leverantörens samlingskonto.</td>
</tr>
<tr class="odd">
<td><strong>Motkonto</strong></td>
<td>Markera det redovisningskontonummer som används för motbokning av ej godkända fakturor som uppdateras med fakturaregistret. Motkontot fungerar som motkonto för transaktioner som bokförts till införselkonton. Därför innehåller kontot leverantörsinköp som ännu inte har godkänts.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Registerbegränsningar**

Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen. Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.

Ange följande värden om du vill ställa in din bokföringsprofil.

| Fält          | Beskrivning                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Kvittning** | Välj det här alternativet för att aktivera automatisk kvittning av transaktioner som har denna bokföringsprofil. Om det här alternativet avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan **Kvitta öppna transaktioner**. |
| **Avbryt**     | Välj det här alternativet för möjlighet att avbryta transaktioner som har denna bokföringsprofil.                                                                                                               |
| **Stäng**      | Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs. En transaktion betraktas som stängd när den har kvittats helt.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]