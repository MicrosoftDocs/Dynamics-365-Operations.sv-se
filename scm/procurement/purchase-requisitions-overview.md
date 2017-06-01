---
title: "Översikt över inköpsrekvisition"
description: "Den här artikeln beskriver arbetsflödet för inköpsrekvisition och de olika statusar en inköpsrekvisition kan ha."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2174
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 38e7fba3fbd12de3a1cd9ac7b1c627834978ba30
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-requisition-overview"></a>Översikt över inköpsrekvisition

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver arbetsflödet för inköpsrekvisition och de olika statusar en inköpsrekvisition kan ha.

Beroende på hur din organisation är inställd kan du skapa inköpsrekvisitioner för produkter som används i organisationen. En inköpsrekvisition är ett internt dokument som ger inköpsavdelningen behörighet att köpa dessa artiklar eller tjänster.  

När en inköpsrekvisition har godkänts kan den användas för att skapa inköpsordern. Inköpsorder är de externa dokument som inköpsavdelningen skickar till leverantörer.

## <a name="creating-purchase-requisitions"></a>Skapa inköpsrekvisitioner
Du kan skapa en inköpsrekvisition på sidan **Mina inköpsrekvisitioner** och väljer de artiklar och tjänster som du behöver. Du kan välja artiklar från en anskaffningskatalog som din organisation har skapat, eller så kan du begära, artiklar som inte finns i en katalog, genom att välja en anskaffningskategori och ange produktdetaljerna.  

Innan du kan skicka en inköpsrekvisition för granskning måste arbetsflödena konfigureras i Microsoft Dynamics 365 for Operations. Du använder ett arbetsflöde för att flytta en inköpsrekvisition genom granskningsprocessen, från den ursprungliga statusen **Utkast** till den slutliga statusen **godkänd**.

### <a name="purchase-requisition-statuses"></a>Status för inköpsrekvisitioner

När du skapar en ny inköpsrekvisition sätts tilldelas den en status. En status tilldelats också varje rad som du lägger till en inköpsrekvisition. När du skickar in en inköpsrekvisition till ett arbetsflöde för granskning, uppdateras statusvärdet för inköpsrekvisitionen och statusen för varje rad som raderna går igenom arbetsflödesprocessen.  

Du kan konfigurera arbetsflödesprocessen för inköpsrekvisitionen att flöda en inköpsrekvisition genom granskningsprocessen som ett enskilt dokument. Alternativt kan raderna på inköpsrekvisitionen dirigeras separat till lämpliga granskare. Om inköpsrekvisitionsraderna granskas individuellt, kan statusen för varje inköpsrekvisitionsrad uppdateras allt eftersom raderna flyttas genom granskningsprocessen. När rader har slutfört granskningsprocessen och det inte finns några granskningssteg kvar för inköpsrekvisitionen uppdateras övergripande status för inköpsrekvisitionen.

### <a name="purchase-requisition-workflow"></a>Arbetsflöde för inköpsrekvisitioner

Följande diagram visar status som har tilldelats en inköpsrekvisition och en inköpsrekvisitionsrad allt eftersom de går igenom arbetsflödesprocessen.  

[![Status för rubrik och rad för inköpsrekvisition](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Statusrelation för rubrik och rad för inköpsrekvisition

Den övergripande statusen på inköpsrekvisitionen bestäms av statusen på inköpsrekvisitionsraderna. Därför måste granskningsprocessen slutföras för alla inköpsrekvisitionsraderna innan granskningen för hela inköpsrekvisitionen kan slutföras. Följande tabell beskriver status som har tilldelats en inköpsrekvisition och en inköpsrekvisitionsrubrik och -rader allt eftersom inköpsrekvisitionen går igenom arbetsflödesprocessen.

<table>
<thead>
<tr class="header">
<th>Status för inköpsrekvisition</th>
<th>Status för inköpsrekvisitionsrad</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utkast</td>
<td>Utkast</td>
<td>Inköpsrekvisitionen och inköpsorderraden har skapats, men de har inte skickats in för granskning. Inköpsrekvisitioner och inköpsrekvisitionsrader som har statusen <strong>Utkast</strong> kan ändras. En inköpsrekvisition eller en inköpsrekvisitionsrad har också statusen <strong>Utkast</strong> om den har återkallats men inte har skickats tillbaka för granskning.<strong>Obs!</strong> Du kan skicka in eller återkalla en inköpsrekvisition på dokumentnivån. Du kan dock inte skicka in eller återkalla en enskild inköpsrekvisitionsrad.</td>
</tr>
<tr class="even">
<td>Under granskning</td>
<td><ul>
<li>Under granskning</li>
<li>Avvisad</li>
</ul></td>
<td>Om arbetsflödet har konfigurerats för att skicka inköpsrekvisitionsrader till enskilda granskare, kan varje rad ha statusvärdet <strong>Under granskning</strong> eller <strong>Avvisad</strong> Inköpsrekvisitionsstatus uppdateras när granskningsprocessen har slutförts för alla inköpsrekvisitionsrader och inga granskningssteg är kvar för inköpsrekvisitionen.
<ul>
<li><strong>Under granskning</strong> – Inköpsrekvisitionsraderna har skickats in för granskning. När arbetsflödesprocessen har avslutats för en inköpsrekvisitionsrad, förblir status för den raden <strong>Under granskning</strong> tills alla återstående inköpsrekvisitionsrader har granskats.</li>
<li><strong>Avvisad</strong> – En inköpsrekvisitionsrad har avvisats. Inköpsrekvisitionsrader som har avvisats kan ändras och skickas in igen.</li>
</ul>
Om du skickar tillbaka en inköpsrekvisitionsrad som har avvisats, startar granskningen om för alla rader i inköpsrekvisitionen som fortfarande är under granskning. <strong>Obs!</strong> Du kan sedan återkalla en inköpsrekvisition som redan har skickats in. När du återkallar en inköpsrekvisition, återkallas alla andra inköpsrekvisitionsrader också. Inköpsrekvisitionrader, som har återkallats, kan tas bort.</td>
</tr>
<tr class="odd">
<td>Avvisad</td>
<td>Avvisad</td>
<td>Den valda inköpsrekvisitionen och alla inköpsrekvisitionsrader har avvisats. Inköpsrekvisitionen och inköpsrekvisitionsrader som avvisats kan skickas in igen.</td>
</tr>
<tr class="even">
<td>Godkända</td>
<td><ul>
<li>Godkända</li>
<li>Annullerad</li>
<li>Stängt</li>
</ul></td>
<td>Alla inköpsrekvisitionsrader har slutfört granskningsprocessen och det inte finns några granskningssteg kvar för inköpsrekvisitionen.
<ul>
<li><strong>Godkänd</strong> – Granskningprocessen för en inköpsrekvisitionsrad har slutförts och raden är godkänd.</li>
<li><strong>Avbruten</strong> - Inköpsrekvisitionsraden godkändes, men har annullerats, eftersom den inte längre är obligatorisk. Endats inköpsrekvisitionsrader, som har godkänts kan avbrytas.</li>
<li><strong>Stängd</strong> - Inköpsrekvisitionsraden godkändes och dokumentet har skapats, beroende på rekvisitionssyftet.
<ul>
<li>Om syftet med rekvisitionsraden är förbrukning skapas en inköpsorder för inköpsrekvisitionsraden.</li>
<li>Om inköpsrekvisitionens syfte är återanskaffning, har en eller flera uppfyllelsedokument har skapats.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Annullerad</td>
<td>Annullerad</td>
<td>Inköpsrekvisitionen och alla inköpsrekvisitionsrader har annullerats.<strong>Obs!</strong> Om du inte längre behöver en artikel på en inköpsrekvisitionsrad, måste du avbryta inköpsrekvisitionsraden om den redan har godkänts. Endats inköpsrekvisitionsrader, som har godkänts kan avbrytas. Om alla inköpsrekvisitionsrader är under granskning har inköpsrekvisitionen statusvärdet. <strong>Under granskning</strong> Du får återkalla inköpsrekvisitionen och ta bort den lämpliga inköpsrekvisitionsraden.</td>
</tr>
<tr class="even">
<td>Stängt</td>
<td><ul>
<li>Stängt</li>
<li>Annullerad</li>
</ul></td>
<td>Inköpsrekvisitionen är stängd och en eller flera uppfyllelsedokument har skapats.
<ul>
<li><strong>Stängd</strong> - Inköpsrekvisitionsraden godkändes och dokumentet har skapats, beroende på rekvisitionssyftet.
<ul>
<li>Om syftet med rekvisitionsraden är förbrukning skapas en inköpsorder för inköpsrekvisitionsraden.</li>
<li>Om inköpsrekvisitionens syfte är återanskaffning, har en eller flera uppfyllelsedokument har skapats.</li>
</ul></li>
<li><strong>Avbruten</strong> - Inköpsrekvisitionsraden godkändes, men har annullerats, eftersom den inte längre är obligatorisk. Endats inköpsrekvisitionsrader, som har godkänts kan avbrytas.</li>
</ul>
<strong>Obs!</strong> Om du inte längre behöver en artikel på en inköpsrekvisitionsrad som har stängts, måste du avbryta raden på uppfyllelsedokumentet som har skapats för inköpsrekvisitionsraden.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Fördela kostnader till flera affärsredovisningskonton
Du kan fördela kostnaderna i en produkt som är inkluderade i en inköpsrekvisition till flera affärsredovisningskonton. Om din organisation använder dimensioner, till exempel kostnadsställen och avdelningar, kan du fördela kostnaden för en produkt till dimensioner för affärsredovisningskonton.

## <a name="requisition-purposes"></a>Rekvisitionssyften
Rekvisitionsyften gör att processen att uppfylla rekvisitionsbegäran blir mer flexibel. När du skapar en rekvisition kan du tilldela ett av två syften till den: förbrukning eller påfyllnad. Beroende på rekvisitionssyftet och hur din organisation är konfigurerad kan rekvisitionsbegäran fyllas på av en inköpsorder, överföringsorder, tillverkningsorder eller kanban.  

I anskaffningspolicyerna kan du kontrollera rekvisitionssyftena som är tillgängliga, när en rekvisition skapas för din organisation.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Rekvisitioner med förbrukningssyfte

En rekvisition med förbrukningssyfte representerar en efterfrågan på artiklar eller tjänster som ska användas internt i organisationen. En begäran som har skapats av den här sortens rekvisition uppfylls alltid av en inköpsorder. Om Microsoft Dynamics 365 for Operations ställs in på att automatiskt skapa inköpsorder, skapas inköpsorder när inköpsrekvisitionen har godkänts.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Rekvisitioner som har ett syfte med påfyllnad

En rekvisition som har ett syfte med påfyllnad representerar en begäran att fylla på lagret. Till exempel vill du kanske skapa en rekvisition för att fylla på artiklar så att de kan säljas i en viss butik vid en viss tidpunkt. Begäran som skapas av denna sorts rekvisitionens kan uppfyllas av en inköpsorder, överföringsorder, tillverkningsorder eller kanban.  

När rekvisitionssyftet är påfyllnad uttrycks behovet som en kvantitet i stället för ett monetärt belopp. Därför används inte reservredovisning, budgetkontroll, affärsregler för bestämning av anläggningstillgångar (BRAD), projektredovisning och relaterade regler. Endast produkter som lagerförs och frisläpps till den angivna juridiska personen kan uppfylla en begäran om påfyllningsrekvisition. Använd sidan **Policyregel för påfyllnad kategoriåtkomst** för att definiera produkterna som är tillgängliga när rekvisitionsyftet är påfyllnad.  

Om du vill använda inköpsrekvisitioner som har ett syfte med lagerpåfyllnad måste ställas in för att inkludera rekvisitionsbegäran i huvudplaneringen. När detta är gjort bestäms uppfyllelsemetoden för en begäran som har skapats av denna typ av rekvisition med påfyllnadssyfte automatiskt av tillförselpolicyerna som har ställts in för artiklarna i organisationen och planerats med hjälp av huvudplaneringen.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Inköpsrekvisitioner: och anbudsförfrågan
I vissa fall måste du starta en anbudsförfrågan (RFQ)-process för att identifiera leverantören och priset för produkter som begärs i en inköpsrekvisition. En anbudsförfrågan kan skapas när inköpsrekvisitionen är under granskning. När du accepterar ett bud, överförs information om leverantör, pris, och så vidare till inköpsrekvisitionen.  

Du kan spärra en inköpsrekvisition genom att välja kryssrutan **Spärrad** på sidan **Information om inköpsrekvisition**. Bearbetningen av inköpsrekvisitionen kan fortsätta först när du har tagit bort spärren genom att avmarkera kryssrutan.  

**Obs!** I eProcurement kan anbudsförfrågan för din inköpsrekvisition tillåta leverantörer lägga till alternativrader. I detta fall kommer din inköpsrekvisition att återspegla godkända alternativ.

## <a name="demand-consolidation"></a>Efterfråganskonsolidering
Genom att konsolidera inköpsrekvisitionsrader från flera inköpsrekvisitioner kan du öka din förhandlingskraft hos leverantörerna och få bättre priser, lägre leverans- och hanteringskostnader och lägre omkostnader.  

Inköpsrekvisitionsrader är bara valbara för efterfrågekonsolidering om följande utdrag är uppfyllda:

-   Inköpsrekvisitionen har godkänts.
-   Inköpsrekvisitionen uppfyller inköpspolicyregelvillkoren för manuell bearbetning och efterfråganskonsolidering.

Bokför godkända inköpsrekvisitionsrader, som uppfyller villkoren för manuellt bearbetningar på sidan **Bokför godkända inköpsrekvisitioner**. Om inköpsrekvisitionsraden också uppfyller villkoren för begärandekonsolidering kan raden läggas till i en konsolideringsmöjlighet.  

En konsolideringsmöjlighet är en uppsättning inköpsrekvisitionsrader som grupperas tillsammans så att inköpare kan förhandla fram bästa möjliga avtal med leverantörer. Inköpsrekvisitionrader som du väljer för en konsolideringsmöjlighet visas på sidan **Inköpsrekvisitionkonsolidering**. Du kan ändra raderna på den här sidan om ändringar krävs. Du kan också lägga till nya rader till konsolideringsmöjligheten eller ta bort befintliga rader.  

När du har lagt till rekvisitionsrader i konsolideringsmöjligheten och gör de ändringar som du vill, kan du skapa en inköpsorder för konsoliderade inköpsrekvisitionsrader.  

**Obs!** De ändringar som du gör på en inköpsrekvisitionsrad på sidan **Konsolidering i inköpsrekvisition** visas även i inköpsordern som du skapar. I inköpsrekvisitionen förblir raden oförändrad, så att dess historik bevaras.  

Om du vill skapa en inköpsorder för inköpsrekvisitionsrader som inte är valbara för efterfrågekonsolidering eller som inte väljs för en konsolideringsmöjlighet, måste du bearbeta raderna manuellt.

### <a name="consolidating-purchase-requisition-lines"></a>Konsolidering av inköpsrekvisitionsrader

Processen för efterfråganskonsolidering börjar när en inköpsrekvisition har godkänts i arbetsflödet och budgetreservationer och förinteckningar har registrerats, om budgetkontroll har konfigurerats för din organisation. Följande diagram visar processflödet för begärandekonsolidering.  

[![Processflöde för efterfråganskonsolidering](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Om du vill konsolidera godkända inköpsrekvisitionsrader, följ dessa steg:

1.  Granska godkända rekvisitionsrader som har spärrats för manuell bearbetning och som är berättigad till efterfrågekonsolidering.
2.  Välj rader som ska läggas till i konsolideringsmöjligheten.
3.  Skapa en ny konsolideringsmöjlighet eller lägg till rekvisitionrader i en befintlig konsolideringsmöjlighet.
4.  Tillämpa ändringarna som du vill göra i rekvisitionsraderna och ta bort de rekvisitionsradartiklar som du inte längre vill ska inkluderas i konsolideringsmöjligheten.
5.  Skapa inköpsorder för konsoliderade rekvisitionrader eller för inköpsrekvisitionsrader i en konsolideringsmöjlighet.


<a name="see-also"></a>Se även
--------

[Skapa en rekvisition för förbrukning (uppgiftsguide)](https://ax.help.dynamics.com/en/wiki/create-a-requisition-for-consumption/)

[Arbetsflöde för inköpsrekvisitioner](purchase-requisitions-workflow.md)




