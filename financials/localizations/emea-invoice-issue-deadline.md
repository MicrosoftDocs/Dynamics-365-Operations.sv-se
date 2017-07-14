---
title: "Tidsgräns för fakturautfärdande"
description: "Den här artikeln innehåller information om hur du ställer in parametrar för att beräkna förfallodatum för utfärdande av kundfakturor och leverantörsfakturor i EU."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10923
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 3fdd9f21964ae6d0c12225feebb6d73e852dc50e
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Tidsgräns för fakturautfärdande
<a id="invoice-issue-deadline" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om hur du ställer in parametrar för att beräkna förfallodatum för utfärdande av kundfakturor och leverantörsfakturor i EU.

Europeiska unionens direktiv 45/2010 och andra direktiv kräver att försändelser inom EU måste faktureras på eller före den femtonde dagen i månaden efter leverans. Samtidigt kan olika EU-länder ha olika fakturaregler för inhemska leveranser. Funktionen för fakturautfärdande gör att du kan anpassa datumen till landet eller regionen. Sedan beräknas förfallodatumet för fakturautfärdandet för alla leveranser till och från ett land/en region av en viss typ med hjälp av regler som gäller för det angivna datumintervallet. Dessutom kan du få alla följesedlar som har ett specifikt förfallodatum för fakturautfärdande, filtrera efter fakturautleveransförfallodatumet under periodisk försäljningsfakturering och kontrollera försäljningsfakturautleveransdatumet under fakturabokföring. Du kan ställa in en datumintervallkod och sedan ställa in en beräkningsregel för förfallodatum för fakturautfärdande genom att tilldela en datumintervallkod till en lands- eller regiontyp. Beräkningsregeln används för att beräkna förfallodatumet för utfärdande av fakturor för följande transaktioner:

-   Försändelser inom EU
-   Lokala försändelser inom en EU-medlemsstat

Du kan även ställa in datumkontroller som används för att se till att kundfakturor och kreditnotor för kundtransaktioner genereras inom den angivna tidsperioden efter att leveransen har gjorts.

## Krav
<a id="prerequisites" class="xliff"></a>
Följande tabell visar förutsättningarna som krävs innan du kan använda denna funktion för fakturautleveransförfallodatumet.

| Kategori            | Förutsättning                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Land/region      | Den primära adressen för den juridiska personen måste ligga i ett EU-land.                                                                                                                                                                                                                                                                                                                    |
| Relaterade inställningsuppgifter | På sidan **Datumintervall** ställer du in ett datumintervall som används för att beräkna fakturautleveransförfallodatumet. (Klicka på **Redovisning** &gt; **Redovisningsinställningar** &gt; **Datumintervall**.) På sidan **Utländska handelsparametrar** ställer du in egenskaper för utländsk handel för olika länder/regioner. (Klicka **Moms** &gt; **Inställningar** &gt; **Utländsk handel** &gt; **Utländska handelsparametrar**.) |

## Regel för beräkning av förfallodatum för fakturautfärdande
<a id="invoice-issue-due-date-calculation-rule" class="xliff"></a>
Använd sidan **Ställ in beräkning för förfallodatum för fakturautfärdande** när du ställer in en beräkningsregel för förfallodatumet för fakturautfärdandet. Koppla en datumintervallskod till en lands- eller regiontyp.

## Datumkontrollparametrar för kundfakturor och kreditnotor
<a id="date-control-parameters-for-customer-invoices-and-credit-notes" class="xliff"></a>
Du kan ställa in kontrollparametrar som används för att se till att kundfakturor och kreditnotor för kundtransaktioner genereras inom den angivna tidsperioden efter att leveransen har gjorts. Du kan hitta dessa parametrar i området **Datumkontroll för faktura** på sidan **Parametrar för kundreskontra**.

## Exempel
<a id="example" class="xliff"></a>
Skapa en datumintervallkod och en beräkningsregel med följande inställningar för att ställa in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för att beräkna förfallodatum för fakturautfärdande på inomeuropeiska (EU) leveranser planerade på den 15:e dagen i månaden efter det att artiklarna har levererats.

### Datumintervallkod
<a id="date-interval-code" class="xliff"></a>

| Fält                                                           | Värde                           |
|-----------------------------------------------------------------|---------------------------------|
| Datumintervallkod                                              | 15-NM                           |
| Beskrivning                                                     | 15:e dagen i nästa månad |
| Före (i fältgruppen **Till datum**)                         | Månad                           |
| Start/Slut (i fältgruppen **Till datum**)                      | Slut                             |
| +/- (i fältgruppen **Till datum**)                            | 15                              |
| Dagar, månader, år eller perioder (i fältgruppen **Till datum**) | Dagar                            |

### Regel för beräkning av förfallodatum för fakturautfärdande
<a id="invoice-issue-due-date-calculation-rule" class="xliff"></a>

| Fält               | Värde                                                     |
|---------------------|-----------------------------------------------------------|
| Lands-/regiontyp | **EU**                                                    |
| Startdatum          | Ange det datum när den aktuella inställningsraden blir giltig. |
| Datumintervallkod  | **15-NM**                                                 |

## Nästa steg
<a id="next-steps" class="xliff"></a>
När du har avslutat inställningen av parametrarna för att beräkna förfallodatum för fakturautfärdande kan du skapa och bokföra följande transaktioner för att automatiskt beräkna och uppdatera förfallodatum för att utfärda fakturor:

-   **Försäljningsorder** – När du skapar en försäljningsorder och bokför en följesedel beräknas och uppdateras förfallodatumet för utfärdande av fakturan på följesedeln. Förfallodatumet beräknas baserat på det datumintervall som associeras med det land/den region som anges i leveransadressen för försäljningsordern. När du har bokfört följesedeln kan du bekräfta fakturautleveransförfallodatumet i fältet **Förfallodatum för fakturautfärdande** på sidan **Följesedelsjournal**. (Klicka på **Försäljning och marknadsföring** &gt; **Försäljningsorder** &gt; **Orderleverans** &gt; **Följesedel**.) Du kan visa alla följesedlar som inte har fakturerats samt förfallodatum för fakturautfärdande på sidan **Icke-fakturerade följesedlar**. (Klicka på **Försäljning och marknadsföring** &gt; **Försäljningsorder** &gt; **Orderleverans** &gt; **Icke-fakturerade följesedlar**.)
-   **Inköpsorder** – När du skapar en inköpsorder och bokför en produktinleverans beräknas och uppdateras förfallodatumet för utfärdande av fakturan på produktinleveransen. Förfallodatumet beräknas baserat på det datumintervall som associeras med det land/den region som anges i den primära adressen för leverantören. När du har bokfört produktinleveransen, kan du kontrollera fakturautleveransförfallodatumet i fältet **Förfallodatum för fakturautfärdande** på sidan **Produktinleveransjournal**. (Klicka på **Anskaffning och källa** &gt; **Inköpsorder** &gt; **Ta emot produkter** &gt; **Produktinleverans**.) Du kan visa alla produktinleveranser som inte har fakturerats samt förfallodatum för fakturautfärdande på sidan **Icke-fakturerade produktinleveranser**. (Klicka på **Anskaffning och källa** &gt; **Inköpsorder** &gt; **Ta emot produkter** &gt; **Icke-fakturerade produktinleveranser**.)

## Teknisk information för systemadministratörer
<a id="technical-information-for-system-administrators" class="xliff"></a>
Om du inte har åtkomst till de sidor som används för att slutföra uppgifter som nämns i den här artikeln, kontakta systemadministratören och ange information som visas i följande tabell.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategori</th>
<th>Förutsättning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurationsnycklar</td>
<td>Klicka på <strong>Systemadministration</strong> &gt; <strong>Inställningar</strong> &gt; <strong>Licensiering</strong> &gt; <strong>Licenskonfiguration</strong>. Klicka på konfigurationsnyckeln <strong>Redovisning</strong>.</td>
</tr>
<tr class="even">
<td>Säkerhetsroller och behörigheter</td>
<td>Om du vill utföra uppgiften måste du vara medlem i en säkerhetsroll som innehåller följande behörigheter:
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (Aktivera faktura- och kassaprocess)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (Aktivera faktura- och betalningsprocess)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Säkerhetsroller och privilegier</td>
<td>Om du vill utföra uppgiften måste du vara medlem i en säkerhetsroll som innehåller följandeprivilegier:
<ul>
<li><strong>CustPackingSlipJournalView</strong> (Visa försäljningsföljesedlar)</li>
<li><strong>VendPackingSlipJournalView</strong> (Visa produktinleveransjournal från inköpsorder)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (Beräkna förfallodatum för fakturautfärdande)</li>
</ul></td>
</tr>
</tbody>
</table>






