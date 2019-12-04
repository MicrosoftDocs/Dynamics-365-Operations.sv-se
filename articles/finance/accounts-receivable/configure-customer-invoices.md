---
title: Skapa en kundfaktura
description: En **kundfaktura för en försäljningsorder** är en faktura som är relaterad till en försäljning och som en organisation skickar till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f5b9866fc7afba205b84b372c6a204ec4c8f64d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772730"
---
# <a name="create-a-customer-invoice"></a>Skapa en kundfaktura

[!include [banner](../includes/banner.md)]

En **kundfaktura för en försäljningsorder** är en faktura som är relaterad till en försäljning och som en organisation skickar till en kund. Den här typen av kundfaktura skapas baserad på en försäljningsorder, vilken inkluderar orderrader och artikelnummer. Artikelnummer specificeras och bokförs i redovisningen. Poster i redovisningsjournalen är inte tillgängliga för en kundfaktura för en försäljningsorder. Mer information finns i [Skapa försäljningsorderfakturor](tasks/create-sales-order-invoices.md).

En **fritextfaktura** har inget samband med en försäljningsorder. Den innehåller orderrader som inkluderar redovisningskonton, fritextbeskrivningar och en försäljningssumma som du anger. Du kan inte ange ett artikelnummer på den här sortens faktura. Du måste ange korrekt momsinformation. En huvudkonto för försäljningen anges på varje fakturarad, som du kan fördela till flera huvudbokskonton genom att klicka på **Fördela belopp** på sidan **Fritextfaktura** . Dessutom bokförs kundsaldot till det samlingskonto från bokföringsprofilen som används för fritextfakturan.

Mer information finns i 

[Skapa fritextfakturor](../accounts-receivable/create-free-text-invoice-new.md)

[Skapa en mall för fritextfaktura](../accounts-receivable/create-free-text-invoice-template-new.md)

[Tilldela en fritextfakturamall till en kund](tasks/assign-free-text-invoice-template-customer.md)

[Generera och bokför återkommande fritextfakturor](tasks/post-recurring-free-text-invoices.md)


En **proformafaktura** är en faktura som förbereds som en uppskattning av de faktiska fakturabeloppen innan fakturan bokförs. Du kan skriva ut en proformafaktura för antingen en kundfaktura för en försäljningsfaktura eller för en fritextfaktura.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Bokför och skriv ut enskilda kundfakturor baserade på försäljningsorder
Använd den här processen för att skapa en faktura baserat på en försäljningsorder. Du kan göra detta om du väljer att fakturera kunden innan du levererar varor eller tjänster. 

När du bokför en faktura uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de fakturerade kvantiteterna från vald försäljningsorder. Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**. Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den.

Du kan visa status för försäljningsorder på listsidan **Alla försäljningsorder**. Använd listsidan **Öppna kundfakturor** om du vill visa fakturor som du har bokfört.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Bokför och skriv ut individuella kundfakturor baserade på följesedlar och datumet
Använd den här processen när en eller flera följesedlar har bokförts för försäljningsordern. Kundfakturan baseras på dessa följesedlar och återspeglar kvantiteterna från dem. Den ekonomiska informationen för fakturan baseras på informationen som registreras när du bokför fakturan. 

Du kan skapa en kundfaktura som baseras på de artiklar på följesedeln som har levererats hittills, även om alla artiklar för en viss försäljningsorder ännu inte har levererats. Det kanske du vill göra om den juridiska personen utfärdar en faktura per kund och månad som täcker alla leveranser som har gjorts den månaden. Varje följesedel representerar en del av eller hela leveransen av artiklarna på försäljningsordern. 

När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de levererade kvantiteterna från de valda följesedlarna. Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**. Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den. 

Lagertransaktioner uppdateras med fakturanumret och statusen i fältet **Radstatus** på försäljningsordern ändras till **Fakturerad**. 

Visa status för försäljningsorder på listsidan **Alla försäljningsorder**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Konsolidera försäljningsorder och följesedlar för bokföring
Använd den här processen när en eller flera försäljningsorder är klara att fakturera och du vill konsolidera dem till en enda faktura. 

Du kan markera flera fakturor på listsidan **Försäljningsorder** och sedan använda **Skapa fakturor** för att konsolidera dem. På sidan **Bokföring av faktura** kan du ändra inställningen **Samlingsorder** att sammanställa efter ordernummer (där flera olika följesedlar finns för en enda försäljningsorder) eller per fakturakonto (där det finns flera olika försäljningsorder för ett enda fakturakonto). Använd knappen **Ordna** för att konsolidera försäljningsorder till enskilda fakturor som baseras på inställningarna för **Samlingsorder**.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Ytterligare inställningar som ändrar bokföringsbeteendet
Följande fält ändrar beteendet för bokföringsprocessen.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fält</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kvantitet</td>
<td>Välj de kvantiteter som bokföringen av dokumentet baseras på. Vilka alternativ som finns tillgängliga beror på vilken typ av dokument du bokför, exempelvis följesedel eller faktura.
<ul>
<li><strong>Leverera nu</strong> – Välj alla kvantiteter som anges i fältet <strong>Leverera nu</strong>. Används om du vill bekräfta eller leverera en delorder.</li>
<li><strong>Plockad</strong> – Välj alla kvantiteter som har plockats.</li>
<li><strong>Alla</strong> – Välj alla försäljningsorderkvantiteter som ännu inte uppdaterats för den aktuella dokumenttypen.</li>
<li><strong>Följesedel</strong> – Välj alla kvantiteter som har uppdaterats av en följesedel.</li>
<li><strong>Plockad kvantitet och produkter som inte finns i lager</strong> – Välj alla kvantiteter som har plockats och alla produktkvantiteter som inte finns i lager.</li>
</ul></td>
</tr>
<tr class="even">
<td>Bokför</td>
<td><ul>
<li>Välj det här alternativet för att journalföra försäljningsordern.</li>
<li>Avmarkera det här alternativet om du vill skriva ut en proformasäljorder. <strong>Anm.:</strong> Om du har ingått ett avtal om en betalningsplan visas inte betalningsplanen på proformasäljordern. Betalningsplanen visas bara på en faktisk försäljningsorder.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sent urval</td>
<td>Välj det här alternativet om du vill köra den aktuella frågan senare. Detta alternativ används för batchjobb. Frågan körs när batchjobbet körs.</td>
</tr>
<tr class="even">
<td>Minska kvantiteten</td>
<td>Välj det här alternativet för att automatiskt reducera den levererade kvantiteten, när dokumentet bokförs, så att den levererade kvantiteten är lika med det tillgängliga lagret.</td>
</tr>
<tr class="odd">
<td>Skriv ut</td>
<td>Välj när du vill skriva ut dokument:
<ul>
<li><strong>Aktuellt</strong> – Skriv ut dokument när varje faktura har uppdaterats.</li>
<li><strong>Efter</strong> – Skriv ut dokument när alla fakturor har uppdaterats.</li>
</ul>
<strong>Anm.:</strong> Fältet <strong>Skriv ut</strong> är bara tillgängligt om du väljer alternativet <strong>Skriv ut faktura</strong>, <strong>Skriv ut bekräftelse</strong>, <strong>Skriv ut plocklista</strong> eller <strong>Skriv ut följesedel</strong>. Anta att du har konfigurerat sidan <strong>Formulärsortering</strong> till att sortera informationen efter fakturakonto. Du kan sedan välja <strong>Efter</strong> för att skriva ut dokument i en bunt sorterad efter fakturakonto. Annars skrivas ut dokumenten ut innan du bearbetningen slutförs och dokumenten sorteras inte i den ordning som anges på sidan <strong>Formulärsortering</strong>.</td>
</tr>
<tr class="even">
<td>Skriv ut faktura</td>
<td>Markera det här alternativet om du vill skriva ut fakturan. Om det här alternativet är inaktiverat kan du bokföra en faktura utan att skriva ut den.</td>
</tr>
<tr class="odd">
<td>Skicka e-post</td>
<td>Markera det här alternativet för att skicka fakturan för en försäljningsorder till kunden som en e-postbilaga efter att fakturan bokförs. Bilagor skickas som PDF och XML-filer. Det här alternativet är tillgängligt om du väljer alternativet <strong>Aktivera CFD (elektroniska fakturor)</strong> på sidan <strong>Elektroniska fakturaparametrar</strong>. <strong>Anm.:</strong> (MEX) Den här kontrollen är bara tillgänglig för juridiska personer som har den primära adressen i Mexiko.</td>
</tr>
<tr class="even">
<td>Använd destination för utskriftshantering</td>
<td>Markera det här alternativet för att använda utskriftsinställningarna som har angetts för transaktionen, dokumentet eller modulen på sidan <strong>Inställning för utskriftshantering</strong>.</td>
</tr>
<tr class="odd">
<td>Kontrollera kreditgräns</td>
<td>Välj informationen som ska analyseras när en kreditgränskontroll utförs.
<ul>
<li><strong>Ingen</strong> – Det finns inga krav för kreditgränskontrollen.</li>
<li><strong>Saldo</strong> – Kreditgränsen kontrolleras mot kundsaldot.</li>
<li><strong>Saldo+följesedel eller produktinleverans</strong> – Kreditgränsen kontrolleras mot kundsaldot och leveranserna.</li>
<li><strong>Saldo+Alla</strong> – Kreditgränsen kontrolleras mot kundsaldot, leveranser och öppna order.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kreditkorrigering</td>
<td>Välj det här alternativet om du vill visa en kreditfaktura som debet i verifikationstransaktionerna.</td>
</tr>
<tr class="odd">
<td>Kreditrestkvantitet</td>
<td>Om du bokför en kreditfaktura väljer du det här alternativet för att behålla den resterande kvantiteten i ordern. Om alternativet avmarkeras anges resterande kvantitet till 0 (noll).</td>
</tr>
<tr class="even">
<td>Samlingsuppdatering för</td>
<td>Välj hur flera olika försäljningsorder ska summeras:
<ul>
<li><strong>Ingen</strong> – Summera inte försäljningsorder. Skapa till exempel en separat faktura för varje försäljningsorder.</li>
<li><strong>Fakturakonto</strong> – Alla valda order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</li>
<li><strong>Order</strong> – Summera ett angett intervall av order till en order som du anger. Dessa order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>. Om detta alternativ är valt måste du välja ett värde i fältet <strong>Försäljningsorder</strong>.</li>
<li><strong>Automatisk sammanfattning</strong> – Om samlingsuppdateringar har angetts på sidan <strong>Samlingsuppdatera</strong>, sammanfatta alla valda order, baserat på villkoren som har ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>. Om samlingsuppdateringar inte anges, bokförs ordern separat.</li>
<li><strong>Följesedel</strong> – Summera ett valt intervall av order till en faktura per följesedel. Det här alternativet är endast tillgängligt om <strong>Följesedel</strong> har valts i fältet <strong>Kvantitet</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>





