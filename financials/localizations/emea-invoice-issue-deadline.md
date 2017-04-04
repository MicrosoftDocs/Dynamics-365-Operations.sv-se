---
title: "Tidsgräns för fakturautfärdande"
description: "Den här artikeln innehåller information om hur du ställer in parametrar för att beräkna förfallodatum för utfärdande av kundfakturor och leverantörsfakturor i EU."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10923
ms.assetid: 64ea3343-df94-4a52-b839-6328c8a282bd
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 6121be0dd02659e4e8466b0c1381678be64fefc2
ms.lasthandoff: 03/31/2017


---

# <a name="invoice-issue-deadline"></a>Tidsgräns för fakturautfärdande

Den här artikeln innehåller information om hur du ställer in parametrar för att beräkna förfallodatum för utfärdande av kundfakturor och leverantörsfakturor i EU.

Europeiska unionens direktiv 45/2010 och andra direktiv kräver att försändelser inom EU måste faktureras på eller före den femtonde dagen i månaden efter leverans. Samtidigt kan olika EU-länder ha olika fakturaregler för inhemska leveranser. Funktionen för fakturautfärdande gör att du kan anpassa datumen till landet eller regionen. Sedan beräknas förfallodatumet för fakturautfärdandet för alla leveranser till och från ett land/en region av en viss typ med hjälp av regler som gäller för det angivna datumintervallet. Dessutom kan du få alla följesedlar som har ett specifikt förfallodatum för fakturautfärdande, filtrera efter fakturautleveransförfallodatumet under periodisk försäljningsfakturering och kontrollera försäljningsfakturautleveransdatumet under fakturabokföring. Du kan ställa in en datumintervallkod och sedan ställa in en beräkningsregel för förfallodatum för fakturautfärdande genom att tilldela en datumintervallkod till en lands- eller regiontyp. Beräkningsregeln används för att beräkna förfallodatumet för utfärdande av fakturor för följande transaktioner:

-   Försändelser inom EU
-   Lokala försändelser inom en EU-medlemsstat

Du kan även ställa in datumkontroller som används för att se till att kundfakturor och kreditnotor för kundtransaktioner genereras inom den angivna tidsperioden efter att leveransen har gjorts.

## <a name="prerequisites"></a>Krav
Följande tabell visar förutsättningarna som krävs innan du kan använda denna funktion för fakturautleveransförfallodatumet.

| Kategori            | Förutsättning                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Land/region      | Den primära adressen för den juridiska personen måste ligga i ett EU-land.                                                                                                                                                                                                                                                                                                                    |
| Relaterade inställningsuppgifter | På sidan **Datumintervall** ställer du in ett datumintervall som används för att beräkna fakturautleveransförfallodatumet. (Klicka på **redovisning**&gt;**Redovisningsinställningar**&gt;**datumintervall**.) I den **Utländska handelsparametrar** sida, ställa in egenskaper för utländsk handel för olika länder/regioner. (Klicka på **skattemässiga**&gt;**inställningar**&gt;**Utlandshandel**&gt;**Utländska handelsparametrar**.) |

## <a name="invoice-issue-due-date-calculation-rule"></a>Regel för beräkning av förfallodatum för fakturautfärdande
Använd sidan **Ställ in beräkning för förfallodatum för fakturautfärdande** när du ställer in en beräkningsregel för förfallodatumet för fakturautfärdandet. Koppla en datumintervallskod till en lands- eller regiontyp.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Datumkontrollparametrar för kundfakturor och kreditnotor
Du kan ställa in kontrollparametrar som används för att se till att kundfakturor och kreditnotor för kundtransaktioner genereras inom den angivna tidsperioden efter att leveransen har gjorts. Du kan hitta dessa parametrar i området **Datumkontroll för faktura** på sidan **Parametrar för kundreskontra**.

## <a name="example"></a>Exempel
Du ställer in Microsoft Dynamics 365 att beräkna fakturan problemet förfallodatum för leveranser inom EU den femtonde dagen i månaden när tillgången levereras, skapa en datum intervallet kod- och regel som har följande inställningar.

### <a name="date-interval-code"></a>Datumintervallkod

| Fält                                                           | Värde                           |
|-----------------------------------------------------------------|---------------------------------|
| Datumintervallkod                                              | 15-NM                           |
| Beskrivning                                                     | 15:e dagen i nästa månad |
| Före (i fältgruppen **Till datum**)                         | Månad                           |
| Start/Slut (i fältgruppen **Till datum**)                      | Slut                             |
| +/- (i fältgruppen **Till datum**)                            | 15                              |
| Dagar, månader, år eller perioder (i fältgruppen **Till datum**) | Dagar                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Regel för beräkning av förfallodatum för fakturautfärdande

| Fält               | Värde                                                     |
|---------------------|-----------------------------------------------------------|
| Lands-/regiontyp | **EU**                                                    |
| Startdatum          | Ange det datum när den aktuella inställningsraden blir giltig. |
| Datumintervallkod  | **15-NM**                                                 |

## <a name="next-steps"></a>Nästa steg
När du har avslutat inställningen av parametrarna för att beräkna förfallodatum för fakturautfärdande kan du skapa och bokföra följande transaktioner för att automatiskt beräkna och uppdatera förfallodatum för att utfärda fakturor:

-   **Försäljningsorder** – När du skapar en försäljningsorder och bokför en följesedel beräknas och uppdateras förfallodatumet för utfärdande av fakturan på följesedeln. Förfallodatumet beräknas utifrån det datumintervall som associeras med det land/den region som anges i leveransadressen för försäljningsordern. Du kan kontrollera fakturan utleverans när du bokför följesedeln förfallodatumet i den **fakturerar du utleveransen förfallodatum** på de **Följesedelsjournal** sida. (Klicka på **försäljnings- och**&gt;**försäljningsorder**&gt;**Order leverans**&gt;**följesedeln**.) Du kan visa alla följesedlar som inte har fakturerats och utfärdandet av fakturan förfallodatum, i den **följesedlar som inte har fakturerats** sida. (Klicka på **försäljnings- och**&gt;**försäljningsorder**&gt;**beställa leverans**&gt;**inte fakturerats följesedlar**.)
-   **Inköpsorder** – När du skapar en inköpsorder och bokför en produktinleverans beräknas och uppdateras förfallodatumet för utfärdande av fakturan på produktinleveransen. Förfallodatumet beräknas baserat på det datumintervall som associeras med det land/den region som anges i den primära adressen för leverantören. När du har bokfört produktinleveransen, kan du kontrollera fakturautleveransförfallodatumet i fältet **Förfallodatum för fakturautfärdande** på sidan **Produktinleveransjournal**. (Klicka på **anskaffning och källa**&gt;**inköpsorder**&gt;**ta emot produkter**&gt;**produktinleverans**.) Du kan visa alla produktinleveranser som inte har fakturerats och utfärdandet av fakturan förfallodatum, på den **produktinleveranser inte fakturerats** sida. (Klicka på **anskaffning och källa**&gt;**inköpsorder**&gt;**ta emot produkter**&gt;**produktinleveranser inte fakturerats**.)

## <a name="technical-information-for-system-administrators"></a>Teknisk information för systemadministratörer
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
<td>Klickar du på <strong>systemadministration</strong>&gt;<strong>inställningar</strong>&gt;<strong>licensiering</strong>&gt;<strong>Licenskonfiguration</strong>. Klicka på konfigurationsnyckeln <strong>Redovisning</strong>.</td>
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



