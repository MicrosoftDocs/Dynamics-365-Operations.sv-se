---
title: EU-mottagningskvitton
description: "Det här avsnittet innehåller information om mottagningskvitton för Europeiska unionen (EU)."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e066bd2adbb9f27f3b0850ca25978d0777590d2
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="eu-entry-certificates"></a>Mottagningskvitton för EU

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om mottagningskvitton för Europeiska unionen (EU).

Du kan utföra följande uppgifter för ett EU-mottagningskvitto:

-   Skapa och skicka ett EU-mottagningskvitto tillsammans med en följesedel eller kundfaktura för leverans av artiklar och tjänster till EU-länder/områden.
-   Ta emot det EU-mottagningskvitto som har signerats av en EU-kund.
-   Överför det signerade EU-mottagningskvittot som tas emot antingen från kunden eller från en tredje part, som ansvarar för att leverera artiklar till kunden.
-   Associera det överförda EU-mottagningskvittot med en kundfaktura.
-   Uppdatera statusen för det överförda EU-mottagningskvittot.

## <a name="prerequisites"></a>Krav
Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

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
<td>Land/region</td>
<td>Den primära adressen för den juridiska personen måste ligga i ett EU-land.</td>
</tr>
<tr class="even">
<td>Relaterade inställningsuppgifter</td>
<td><ul>
<li>Välj alternativen <strong>Aktivera hantering av mottagningskvitton</strong> och <strong>Aktivera utfärdande av mottagningskvitton</strong> på sidan <strong>Parametrar för kundreskontra</strong>.</li>
<li>Välj <strong>Mottagningskvitto krävs</strong> på snabbfliken <strong>Faktura och leverans</strong> på sidan <strong>Kunder</strong> för att ange om ett EU-mottagningskvitto är obligatoriskt för kunden. Markera kryssrutan <strong>Utfärda mottagningskvitto</strong> om du vill utfärda ett EU-mottagningskvitto för kundens juridiska person.</li>
<li>Välj en nummerseriekod för <strong>Postcertifikat</strong> på sidan <strong>Parametrar för kundreskontra</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Relaterade transaktioner</td>
<td><ul>
<li>Skapa ett kundkonto.</li>
<li>Skapa en försäljningsorder.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a>Skapa och registrera och överföra ett EU-mottagningskvitto
Du kan skapa ett EU-postcertifikat automatiskt eller manuellt. Ett EU-mottagningskvitto skapas och skrivs ut automatiskt när du bokför en följesedel eller en faktura för en kund via sidan **Bokför med följesedel** eller sidan **Bokför med faktura**. Skapa ett EU-mottagningskvitto manuellt eller skriv ut det på nytt för en kundfaktura via sidan **Fakturajournal**. Du kan även ange information om ett EU-mottagningskvitto som utfärdats av en tredje part på sidan **Mottagningskvittojournal**.

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a>Skapa ett EU-mottagningskvitto automatiskt eller manuellt.

Du kan skapa ett EU-mottagningskvitto automatiskt, med hjälp av en följesedel på sidan **Alla försäljningsorder** eller genom att använda en faktura på sidan **Försäljningsorder** sidan. Skapa ett EU-mottagningskvitto manuellt med en faktura på sidan **Fakturajournal**. Du måste dock ändra kvittostatusen för en faktura innan du skapar ett EU-mottagningskvitto manuellt.

### <a name="registering-an-eu-entry-certificate"></a>Registrera ett EU-mottagningskvitto

Om registrering krävs kan även registrera ett EU-mottagningskvitto som utfärdats av tredje part på sidan **Mottagningskvittojournal**.

### <a name="uploading-a-received-eu-entry-certificate"></a>Överföra ett mottaget EU-mottagningskvitto

Använd sidan **Bilagor** för att överföra ett mottaget EU-mottagningskvitto som har signerats av en EU-kund. När kvittot har överförts kan du associera det med en faktura som bevis på att artiklarna har levererats. Det här beviset krävs om du måste utfärda en faktura som inte inkluderar mervärdesskatt (moms) och den även används vid granskning.

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a>Valfritt: Uppdatera mottagningskvittots status och skriv ut status för en faktura

Du kan uppdatera mottagningskvittostatusen och skriva ut status för en kundfaktura på sidan **Fakturajournal**.

## <a name="technical-information-for-system-administrators"></a>Teknisk information för systemadministratörer
Om du inte har åtkomst till de sidor som används för att slutföra den här uppgiften, kontakta systemadministratören och ange information som visas i följande tabell.

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
<td>Säkerhetsroller och behörigheter</td>
<td>Om du vill ställa in och skapa ut EU-mottagningskvitton för artiklar eller tjänster måste du vara medlem i en säkerhetsroll som innehåller följande behörigheter:
<ul>
<li><strong>Kundreskontraansvarig</strong> (CustInvoiceAccountsReceivableClerk)</li>
<li><strong>Kundtjänstrepresentant</strong> (TradeCustomerServiceRepresentative)</li>
<li><strong>Försäljningsansvarig</strong> (TradeSalesClerk)</li>
<li><strong>Leveransansvarig</strong> (InventShippingClerk)</li>
</ul></td>
</tr>
</tbody>
</table>






