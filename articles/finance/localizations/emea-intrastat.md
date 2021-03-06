---
title: Intrastat – översikt
description: Det här ämnet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU). Det ger en översikt över rapporteringsprocessen och beskriver nödvändiga inställningar och förutsättningar.
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bafbb908531e003d2184409bf5d09ed5848fc474
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216794"
---
# <a name="intrastat-overview"></a>Intrastat – översikt

[!include [banner](../includes/banner.md)]

Det här ämnet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU). Det ger en översikt över rapporteringsprocessen och beskriver nödvändiga inställningar och förutsättningar.

Intrastat är systemet för att samla information och skapa statistik över handeln med varor mellan länder/regioner i den Europeiska unionen (EU). Intrastat-rapportering krävs när en produkt korsar gränsen till ett annat EU-land eller en annan EU-region. I flera länder/regioner gäller Intrastat-rapportering även för tjänster. Obligatoriska och valfria element kan samlas in i Intrastat-rapportering. Följande element är obligatoriska: momsnumret för parten som ansvarar för att ge information, referensperioden, flödet (införsel eller utförsel), den åttasiffriga artikelkoden, partnerns medlemsstat (medlemsstaten för försändelsen vid införsel och medlemsstaten för målen vid utförsel), värdet på varorna, varornas kvantitet (nettomassa och fyllnadsenhet) och transaktionens natur. Länder/regioner kan också samla in valfria element under olika omständigheter. Exempel på valfria element är ursprungsland/ursprungsregion, leveransvillkor, transportsätt, en mer detaljerad artikelkod än CN8, ursprungsregionen vid utförsel och målmålen vid införsel, den statistiska proceduren, det statistiska värdet, en beskrivning av varorna och hamn/flygplats för lastning/avlastning.

## <a name="overview-of-the-intrastat-reporting-process"></a>Översikt över processen vid Intrastat-rapportering
Följande avsnitt beskriver det generella flödet av information som används för Intrastat-rapportering.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Ange en transaktion som korsar gränsen till ett annat EU-land eller en annan EU-region

En kundfaktura, fritextfaktura, inköpsfaktura, projektfaktura, kundföljesedel, produktinleverans för leverantör eller överföringsorder överförs bara till Intrastat-journalen om landet/regionen för målen (vid utförsel) eller försändelsen (vid införsel) är **EU**. Denna funktion har utökats för Microsoft Dynamics 365 for Operations (1611) och låter dig ange fraktadresser för en transaktion inom gemenskapen. Om en fraktadress skiljer sig åt från en leverantörsföretagsadress (eller en kunderföretagsadress för returorder), fungerar Intrastat-rapporteringen med den här informationen. När du skapar en försäljningsorder, fritextfaktura, inköpsorder, leverantörsfaktura, projektfaktura eller överföringsorder har vissa fält som är relaterade till utländsk handel standardvärden i dokumenthuvudet eller på raden. Standardtransaktionskoden hämtas från motsvarande fält på sidan **Utländska handelsparametrar**. Standardartikelkoden, ursprungsland/ursprungsregion och ursprungsstat/ursprungsprovins hämtas från artikeln. Du kan ändra standardvärdena och du kan även fylla i annan utländsk handelsrelaterad information: statistikprocedur, transportmetod och hamn.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Använd Intrastat-journalen för att skapa information om handel mellan EU-länder/EU-regioner

För statistiska ändamål skapar du information om handeln mellan EU-länder/EU-regioner varje månad. Du kan överföra transaktioner från en fritextfaktura, kundfaktura, kundföljesedel, leverantörsfaktura, leverantörföljesedel, projektfaktura eller överföringsorder enligt överföringsvillkoren som har ställts in på sidan **Utländska handelsparametrar**. Alternativt kan du ange transaktioner manuellt. Du kan uppdatera överförda transaktioner manuellt i Intrastat-journalen om uppdateringar krävs. Under vissa förhållanden som ställs in på sidan **Komprimering av Intrastat** kan du komprimera transaktionerna i Intrastat-journalen. Vissa länder/regioner låter dig tillämpa en liten transaktionströskel. Du kan då rapportera transaktioner som är under det tröskelvärdet under den angivna artikelkoden. Du kan uppdatera artikelkoden på motsvarande Intrastat-journalrader baserat på inställningen **Minimigräns** på sidan **Utländska handelsparametrar**. Du kan också komprimera dessa transaktioner baserat på inställningen **Komprimering av Intrastat**. Du kan validera fullständigheten för transaktionerna i Intrastat-journalen baserat på inställningen **Checkinställningar** på sidan **Utländska handelsparametrar**. Data i motsvarande fält kan valideras för fullständighet: land/region, delstat eller provins, vikt, artikelkod, transaktionskod, fyllnadsenhet, hamn, ursprung, leveransvillkor, transportmetod och momsregistreringsnummer. Transaktioner som inte är kompletta markeras som inte giltiga.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Använd Intrastat-journalen för att rapportera information om handel mellan EU-länder/EU-regioner

För statistiska ändamål rapporterar du information om handeln mellan EU-länder/EU-regioner varje månad. Du kan skriva ut Intrastat-rapporten baserat på inställningarna för **Mappning av rapportformat** på sidan **Utländska handelsparametrar**. Du kan även skapa en elektronisk fil baserat på inställningarna för **Mappning av filformat** på sidan **Utländska handelsparametrar**. Se uppgiftsinspelningar för Intrastat-rapportering om du vill ha mer information om Intrastat-rapportering:

-   Skapa en EU Intrastat-deklaration,
-   Överföra transaktioner till Intrastat,
-   Ange fraktadressen för en inomeuropeisk transaktion.

## <a name="prerequisites"></a>Förutsättningar
Följande tabell anger förutsättningarna för Intrastat-rapportering.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Adressinställning</td>
<td>Ställ in ISO-koder (International Organization for Standardization) för länder/regioner.</td>
</tr>
<tr class="even">
<td>Juridisk person</td>
<td>Ställ in momsregistreringsnummer för import/export, filialnummertillägg för import/export och Intrastat-koden som tilldelas den juridiska personen.</td>
</tr>
<tr class="odd">
<td>Produktkategorihierarki (försäljningshierarki, anskaffningshierarki)</td>
<td>Tilldela Intrastat-artikelkoderna till kategorinoder på fliken <strong>Artikelkoder</strong> på sidan <strong>Kategorihierarki</strong>. När du tilldelar en artikelkod till en överordnad kategorinod gäller den koden för alla underordnade kategorinoder. De valda artikelkoderna är tillgängliga i vyn <strong>Markerade</strong> när du väljer en varukod i produktinformationen samt på försäljningsorder-, inköpsorder- och överföringsorderrader.</td>
</tr>
<tr class="even">
<td>Information om frisläppt produkt</td>
<td>Ställ in följande information om utrikeshandel för frisläppta produkter:
<ul>
<li><strong>Artikelkod</strong> – Välj från listan över valda varor som hämtas från tilldelade produktkategorier eller från hela listan med Intrastat-artikelkoder.</li>
<li><strong>Procent för statistiska avgifter</strong></li>
<li><strong>Ursprungsland/ursprungsregion</strong> – Välj standardlandet/standardregionen där varorna erhölls helt eller tillverkades.</li>
<li><strong>Delstat/provins för ursprung/mål</strong> – Välj den förvalda delstaten/provinsen för målen för införsel och ursprungsdelstaten/ursprungsprovinsen för utförsel.</li>
<li><strong>Nettovikt i kg</strong></li>
<li><strong>Exkludera</strong> - Aktivera den här parametern om du inte vill överföra transaktioner med den här produkten till Intrastat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kunder</td>
<td>Ställ in kundens leveransadress i EU-landet/EU-regionen.</td>
</tr>
<tr class="even">
<td>Leverantörer</td>
<td>Ställ in leverantörens adress i EU-landet/EU-regionen.</td>
</tr>
<tr class="odd">
<td>Övriga avgifter</td>
<td>Ställ in tilläggskoden som ska tas med i fakturabeloppet, det statistiska beloppet eller båda. På sidan <strong>Avgiftskoder</strong> på fliken <strong>Utländsk handel</strong> aktiverar du <strong>Intrastat-fakturavärde</strong> om du vill inkludera avgiftsbeloppen i fakturavärdet och aktiverar <strong>Intrastat-statistikvärde</strong> om du vill ta med avgiftsbeloppet i det statistiska värdet.</td>
</tr>
<tr class="even">
<td>Elektronisk rapportering</td>
<td>Ställ in konfigurationer för elektronisk rapportering när du vill exportera Intrastat-data i en elektronisk fil som har formatet som krävs av relevanta myndigheter och för att granska Intrastat-data i ett användarvänligt, läsbart format (exempelvis i Microsoft Excel).</td>
</tr>
<tr class="even">
<td>Lagerförvaring</td>
<td>Associera leverantörskonton med lagerkoder för att ange mombefrielsenummer när du överför överföringsorder.</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Inställningar
Följande avsnitt beskriver de inställningar som krävs för Intrastat-rapportering.

### <a name="set-up-all-required-intrastat-related-lists"></a>Ställ in alla nödvändiga Intrastat-relaterade listor

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista</th>
<th>Ytterligare information</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Artikelkoder</td>
<td>Ställ in en kategorihierarki av typen <strong>Artikelkod</strong> och ange alla artikelkoder enligt den kombinerade nomenklaturlistan. För varje vara ställer du in följande information:
<ul>
<li>Namnet på varan och artikelkoden</li>
<li>Det egna namnet och/eller det översatta namnet</li>
<li>Inställningar för att rapportera ytterligare (kompletterande) enheter på fliken <strong>Utrikeshandel</strong>. Du kan välja ytterligare enheter i enhetslistan. Du kan även ange om vikten av varorna måste rapporteras utöver den valda ytterligare enheten.</li>
</ul></td>
</tr>
<tr class="even">
<td>Transaktionskoder</td>
<td>Ställ in transaktionens natur enligt landets/regionens krav. För varje transaktionskod som du anger måste du ställa in reglerna för att beräkna fakturabelopp och statistiska belopp för överföringsorder och försäljnings-/inköpsorder.
<ul>
<li>För överföringsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:
<ul>
<li><strong>Tom</strong> – Beloppet kommer att vara 0 (noll).</li>
<li><strong>Ekonomiskt självkostnadsbelopp</strong> – Beloppet kommer att vara lika med den ekonomiska kostnaden.</li>
<li><strong>Total kostnad</strong> – Beloppet kommer att vara lika med totalkostnaden för transaktionen.</li>
<li><strong>Manuellt</strong> – Beloppet kommer att vara samma som det belopp som angetts manuellt på överföringsorderraden.</li>
</ul></li>
<li>För försäljnings- och inköpsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:
<ul>
<li><strong>Tom</strong> – Beloppet kommer att vara 0 (noll).</li>
<li><strong>Fakturabelopp</strong> – Beloppet kommer att vara samma som det fakturerade beloppet för varan.</li>
<li><strong>Basbelopp</strong> – Beloppet kommer att vara samma som det fakturerade beloppet före en eventuell rabatt.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Transportmetoder</td>
<td>Ställ in transportsätt enligt landets/regionens krav. För varje leveranssätt kan du ställa in en standardtransportmetod på fliken <strong>Utländsk handel</strong>.</td>
</tr>
<tr class="even">
<td>Hamnar</td>
<td>Ställ in hamnen/flygplatsen för lastning/avlastning om denna information samlas in av ditt land/din region.</td>
</tr>
<tr class="odd">
<td>Statistikprocedurer</td>
<td>Ställ in statistikproceduren om denna information samlas in av ditt land/din region.</td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Ställ in regler för komprimeringen av Intrastat-transaktioner

På sidan **Komprimering av Intrastat** kan du välja vilka fält du vill använda för komprimering. Alla transaktioner som har samma kombination av värden för de valda fälten i Intrastat-journalen komprimeras till en enda transaktion när du kör funktionen Komprimera i Intrastat-journalen.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

Använd sidan **Utländska handelsparametrar** för att ställa in parametrarna i följande tabell.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Flik</th>
<th>Parametrar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Allmänt</td>
<td><ul>
<li><strong>Allmänt</strong> – Ange följande information:
<ul>
<li>Standardtransaktionskoder för försäljningsorder, inköpsorder, kreditfakturor och överföringsorder. Transaktionskoden som har ställts in för kreditfakturor används också som koden för fysiska varureturer och används för att avvika fysiska returer jämfört med korrigeringskreditfakturor. Returer av fysiska varor rapporteras i Intrastat-överföring med en annan riktning. Införselsretur rapporteras som utförsel, och utförselsretur rapporteras som införsel.</li>
<li>Medarbetaren som ansvarar för att förbereda Intrastat-rapporter.</li>
</ul></li>
<li><strong>Minimigräns</strong> – Ange inställningarna för att uppdatera transaktioner som är under tröskeln:
<ul>
<li>Tröskelbeloppet och vikten</li>
<li>Varukoden som ska användas för transaktioner som är under tröskeln</li>
</ul></li>
<li><strong>Överför</strong> – Ange villkoren för överföring av transaktioner till Intrastat-journalen. Du kan ange att transaktionerna bara överförs när artiklarna uppfyller något eller alla av följande villkor:
<ul>
<li>Artiklarna är inte serviceartiklar.</li>
<li>Artiklarna har en varukod.</li>
<li>Artiklarna har en vikt.</li>
<li>Artiklarna har ytterligare enheter.</li>
</ul></li>
<li><strong>Checkinställningar</strong> – Ange reglerna för att validera fullständigheten av Intrastat-data. Du kan välja vilka data som valideras.</li>
<li><strong>Avrundningsregler</strong> – Ange följande inställningar för avrundningsbelopp och vikter i Intrastat-rapportering:
<ul>
<li>Avrundningsregeln (precision)</li>
<li>Avrundningsmetod: upp, ned eller normal</li>
<li>Antal decimaler för belopp och vikter</li>
<li>Instruktioner för att avrunda vikter som är mindre än 1 kilo (kg): upp till 1 kg, normal eller ingen avrundning</li>
</ul></li>
<li><strong>Elektronisk rapportering</strong> – Ange referenser till elektroniska rapporteringskonfigurationer så att du kan skapa en elektronisk fil och en rapport.</li>
<li><strong>Artikelkodhierarki</strong> – Ange kategorihierarkin för typen <strong>Artikelkod</strong> som representerar Intrastat-artikelkoden CN8.</li>
  <li> <strong>Valutakurstyp</strong> – Alternativt kan du ange en valutakurs som används för att rapportera Intrastat försäljnings- och inköpstransaktioner i utländska valutor. Detta används om hastigheten skiljer sig från den som tillämpas när du bokför transaktionen.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Kontaktinformation för agent</td>
<td>Ange agentens namn, adress, momsregistreringsnummer, telefonnummer och faxnummer.</td>
</tr>
<tr class="odd">
<td>Egenskaper för land/region</td>
<td>Ange ursprungsland/ursprungsregion för den aktuella juridiska personen till <strong>Inrikes</strong>. Ange ursprungsland/ursprungsregion för EU-länder/EU-regioner som deltar i EU-handel med den aktuella juridiska personen till <strong>EU</strong>. För varje land/region identifierar du också lands-/regionskoden för utrikeshandelsyften.</td>
</tr>
<tr class="even">
<td>Nummerserie</td>
<td>Ange nummerserien för Intrastat-journalen.</td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
