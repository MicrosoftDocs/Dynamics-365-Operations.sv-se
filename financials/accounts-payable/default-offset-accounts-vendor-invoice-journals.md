---
title: "Standardmotkonton för leverantörsfakturajournaler och fakturagodkännandejournaler"
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4691ac4456b08084bcd93f7a8447719a15299c93
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a>Standardmotkonton för leverantörsfakturajournaler och fakturagodkännandejournaler

[!include[banner](../includes/banner.md)]




Standardmotkonton används på följande sidor för leverantörsfakturajournaler:

-   Fakturajournal
-   Fakturagodkännandejournal

Använd följande register som hjälper dig att bestämma var du bör tilldela standardkonton och motkonton för fakturajournaler.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ställ in standardkonton här</th>
<th>Där standardkonton tillhandahålls</th>
<th>Hur detta alternativ påverkar bearbetning</th>
<th>När du ska använda det här alternativet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Leverantörsgrupp</strong> – Ställ in standardmotkonton för leverantörsgrupper på sidan <strong>Standardkontoinställning</strong>  som du öppnar från sidan <strong>Leverantörsgrupper</strong>.</td>
<td><ul>
<li>Leverantörskonto</li>
<li>Journalposter för leverantörskonton i leverantörsgruppen, om standardkonton inte anges för leverantörskonton</li>
</ul></td>
<td>Standardmotkontona för leverantörsgrupper visas som standardmotkonton för leverantörer på sidan <strong>Standardkontoinställning</strong>. Du kan öppna den här sidan från listsidan <strong>Alla leverantörer</strong>.</td>
<td>Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörsgrupperna över tid.</td>
</tr>
<tr class="even">
<td><strong>Leverantörskonto</strong> – Ställ in standardmotkonton för leverantörskonton på sidan <strong>Standardkontoinställning</strong> som du öppnar från sidan <strong>Leverantörer</strong>.</td>
<td>Journalposter för leverantörskontot</td>
<td>Standardmotkontona för leverantörskonton visas som standardmotkonton för journalposter för leverantörskontot.</td>
<td>Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörer över tid.</td>
</tr>
<tr class="odd">
<td><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>. Välj alternativet <strong>Fast motkonto</strong>. Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</td>
<td><ul>
<li>Journalrubrik som använder journalnamnet</li>
<li>Journalposter i journaler som använder journalnamn</li>
</ul></td>
<td>Om alternativet <strong>Fast motkonto</strong> på sidan <strong>Journalnamn</strong> har markerats, åsidosätter motkontot för journalnamnet standardmotkontot för leverantören eller leverantörsgruppen.</td>
<td>Använd det här alternativet om du vill ställa in journaler för specifika kostnader och utgifter som debiteras specifika konton, oavsett vem leverantören eller leverantörsgruppen som de tillhör.</td>
</tr>
<tr class="even">
<td><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>. Ta bort alternativet <strong>Fast motkonto</strong>. Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</td>
<td><ul>
<li>Journalrubrik</li>
<li>Journalposter i journaler som använder journalnamn</li>
</ul></td>
<td>Dessa standardvärden används på sidor för journalrubriker och motkontot på sidan för journalrubriker används som en standardinställning på sidan för bokföringsorder. Standardkonton från sidan <strong>Journalnamn</strong> används bara om standardkonton inte har ställts in för leverantörskontot.</td>
<td>Använd det här alternativet om du vill ställa in standardkonton som ska användas när en standardleverantörmotkonto inte tilldelas.</td>
</tr>
<tr class="odd">
<td><strong>Journalrubrik</strong> – Ställa in ett standardmotkonto för en journal som ska användas som ett standardvärde på sidan för bokföringsorder. Observera att du kan inte kan ange standardmotkonton för journalrubrik om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</td>
<td>Journalposter i journalen</td>
<td>Standardmotkontot för en journal används som standardposten på sidan för bokföringsordern.</td>
<td>Använd det här alternativet för att göra dataregistreringen snabbare, om de flesta poster i en journal har samma motkonto.</td>
</tr>
</tbody>
</table>






