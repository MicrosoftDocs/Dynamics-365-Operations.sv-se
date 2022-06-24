---
title: Intrastat – översikt
description: Det här ämnet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU).
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9360f97506ac7bdf67bb2f1b296f01b6ed49b39f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894786"
---
# <a name="intrastat-overview"></a>Intrastat – översikt

[!include [banner](../includes/banner.md)]

Det här ämnet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU). Detta ämne ger också en översikt över rapporteringsprocessen och beskriver nödvändiga inställningar och förutsättningar.

Intrastat är systemet för att samla information och skapa statistik över handeln med varor mellan länder/regioner i den Europeiska unionen (EU). Intrastat-rapportering krävs när en produkt korsar gränsen till ett annat EU-land eller en annan EU-region. I flera länder/regioner gäller Intrastat-rapportering även för tjänster. Obligatoriska och valfria element kan samlas in i Intrastat-rapportering. Följande element är obligatoriska: momsnumret för parten som ansvarar för att ge information, referensperioden, flödet (införsel eller utförsel), den åttasiffriga artikelkoden, partnerns medlemsstat (medlemsstaten för försändelsen vid införsel och medlemsstaten för målen vid utförsel), värdet på varorna, varornas kvantitet (nettomassa och fyllnadsenhet) och transaktionens natur. Länder/regioner kan också samla in valfria element under olika omständigheter. Exempel på valfria element är ursprungsland/ursprungsregion, leveransvillkor, transportsätt, en mer detaljerad artikelkod än CN8, ursprungsregionen vid utförsel och målmålen vid införsel, den statistiska proceduren, det statistiska värdet, en beskrivning av varorna och hamn/flygplats för lastning/avlastning.

## <a name="overview-of-the-intrastat-reporting-process"></a>Översikt över processen vid Intrastat-rapportering
Följande avsnitt beskriver det generella flödet av information som används för Intrastat-rapportering.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Ange en transaktion som korsar gränsen till ett annat EU-land eller en annan EU-region

En kundfaktura, fritextfaktura, inköpsfaktura, projektfaktura, kundföljesedel, produktinleverans för leverantör eller överföringsorder överförs bara till Intrastat-journalen om landet/regionen för målen (vid utförsel) eller försändelsen (vid införsel) är **EU**. Denna funktion har utökats för Microsoft Dynamics 365 for Operations (1611) och låter dig ange fraktadresser för en transaktion inom gemenskapen. Om en fraktadress skiljer sig åt från en leverantörsföretagsadress (eller en kunderföretagsadress för returorder), fungerar Intrastat-rapporteringen med den här informationen. När du skapar en försäljningsorder, fritextfaktura, inköpsorder, leverantörsfaktura, projektfaktura eller överföringsorder har vissa fält som är relaterade till utländsk handel standardvärden i dokumenthuvudet eller på raden. Standardtransaktionskoden hämtas från motsvarande fält på sidan **Utländska handelsparametrar**. Standardartikelkoden, ursprungsland/ursprungsregion och ursprungsstat/ursprungsprovins hämtas från artikeln. Du kan ändra standardvärdena och du kan även fylla i annan utländsk handelsrelaterad information: statistikprocedur, transportmetod och hamn.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Använd Intrastat-journalen för att skapa information om handel mellan EU-länder/EU-regioner

För statistiska ändamål skapar du information om handeln mellan EU-länder/EU-regioner varje månad. Du kan överföra transaktioner från en fritextfaktura, kundfaktura, kundföljesedel, leverantörsfaktura, leverantörföljesedel, projektfaktura eller överföringsorder enligt överföringsvillkoren som har ställts in på sidan **Utländska handelsparametrar**. Alternativt kan du ange transaktioner manuellt. Du kan uppdatera överförda transaktioner manuellt i Intrastat-journalen om uppdateringar krävs. Under vissa förhållanden som ställs in på sidan **Komprimering av Intrastat** kan du komprimera transaktionerna i Intrastat-journalen. Vissa länder/regioner låter dig tillämpa en liten transaktionströskel. Du kan då rapportera transaktioner som är under det tröskelvärdet under den angivna artikelkoden. Du kan uppdatera artikelkoden på motsvarande Intrastat-journalrader baserat på inställningen **Minimigräns** på sidan **Utländska handelsparametrar**. Du kan också komprimera dessa transaktioner baserat på inställningen **Komprimering av Intrastat**. Du kan validera fullständigheten för transaktionerna i Intrastat-journalen baserat på inställningen **Checkinställningar** på sidan **Utländska handelsparametrar**. Data i motsvarande fält kan valideras för fullständighet: land/region, delstat eller provins, vikt, artikelkod, transaktionskod, fyllnadsenhet, hamn, ursprung, leveransvillkor, transportmetod och momsregistreringsnummer. Transaktioner som inte är kompletta markeras som inte giltiga.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Använd Intrastat-journalen för att rapportera information om handel mellan EU-länder/EU-regioner

För statistiska ändamål rapporterar du information om handeln mellan EU-länder/EU-regioner varje månad. Du kan skriva ut Intrastat-rapporten baserat på inställningarna för **Mappning av rapportformat** på sidan **Utländska handelsparametrar**. Du kan även skapa en elektronisk fil baserat på inställningarna för **Mappning av filformat** på sidan **Utländska handelsparametrar**. Se uppgiftsinspelningar för Intrastat-rapportering om du vill ha mer information om Intrastat-rapportering:

  - Skapa en EU Intrastat-deklaration,
  - Överföra transaktioner till Intrastat,
  - Ange fraktadressen för en inomeuropeisk transaktion.

## <a name="prerequisites"></a>Förutsättningar
Följande tabell anger förutsättningarna för Intrastat-rapportering.

|  Förutsättning  |  Beskrivning  |
|-------------------------|-------------------------|
| Adressinställning | Ställ in ISO-koder (International Organization for Standardization) för länder/regioner. |
| Juridisk person | Ställ in momsregistreringsnummer för import/export, filialnummertillägg för import/export och Intrastat-koden som tilldelas den juridiska personen. |
| Produktkategorihierarki (försäljningshierarki, anskaffningshierarki) | Tilldela Intrastat-artikelkoderna till kategorinoder på fliken **Artikelkoder** på sidan **Kategorihierarki**. När du tilldelar en artikelkod till en överordnad kategorinod gäller den koden för alla underordnade kategorinoder. De valda artikelkoderna är tillgängliga i vyn **Markerade** när du väljer en varukod i produktinformationen samt på försäljningsorder-, inköpsorder- och överföringsorderrader. |
| Information om frisläppt produkt | Ställ in följande information om utrikeshandel för frisläppta produkter:<ul><li>**Artikelkod** – Välj från listan över valda varor som hämtas från tilldelade produktkategorier eller från hela listan med Intrastat-artikelkoder.</li><li>**Procent för statistiska avgifter**</li><li>**Ursprungsland/ursprungsregion** – Välj standardlandet/standardregionen där varorna erhölls helt eller tillverkades.</li><li>**Delstat/provins för ursprung/mål** – Välj den förvalda delstaten/provinsen för målen för införsel och ursprungsdelstaten/ursprungsprovinsen för utförsel.</li><li>**Nettovikt i kg**</li><li>**Exkludera** - Aktivera den här parametern om du inte vill överföra transaktioner med den här produkten till Intrastat</li></ul> |
| Kunder | Ställ in kundens leveransadress i EU-landet/EU-regionen. |
| Leverantörer | Ställ in leverantörens adress i EU-landet/EU-regionen. |
| Övriga avgifter | Ställ in tilläggskoden som ska tas med i fakturabeloppet, det statistiska beloppet eller båda. På sidan **Avgiftskoder** på fliken **Utländsk handel** aktiverar du **Intrastat-fakturavärde** om du vill inkludera avgiftsbeloppen i fakturavärdet och aktiverar **Intrastat-statistikvärde** om du vill ta med avgiftsbeloppet i det statistiska värdet.</br>Mer information finns i exempel [transaktionskoder och tillägg](#transaction-codes-and-miscellaneous-charges). |
| Elektronisk rapportering | Ställ in konfigurationer för elektronisk rapportering när du vill exportera Intrastat-data i en elektronisk fil som har formatet som krävs av relevanta myndigheter och för att granska Intrastat-data i ett användarvänligt, läsbart format (exempelvis i Microsoft Excel). |
| Lagerförvaring | Associera leverantörskonton med lagerkoder för att ange mombefrielsenummer när du överför överföringsorder.</br>Mer information finns i exemplet [överföringsorder](#transfer-order).|

## <a name="setup"></a>Inställningar
Följande avsnitt beskriver de inställningar som krävs för Intrastat-rapportering.

### <a name="set-up-all-required-intrastat-related-lists"></a>Ställ in alla nödvändiga Intrastat-relaterade listor

|   Lista   |   Ytterligare information   |
|-------------------------|-------------------------|
| Artikelkoder | Ställ in en kategorihierarki av typen **Artikelkod** och ange alla artikelkoder enligt den kombinerade nomenklaturlistan. För varje vara ställer du in följande information:<ul><li>Namnet på varan och artikelkoden</li><li>Det egna namnet och/eller det översatta namnet</li><li>Inställningar för att rapportera ytterligare (kompletterande) enheter på fliken **Utrikeshandel**. Du kan välja ytterligare enheter i enhetslistan. Du kan även ange om vikten av varorna måste rapporteras utöver den valda ytterligare enheten.</li></ul>Mer information finns i exemplet [Ytterligare enheter](#additional-units).|
| Transaktionskoder | Ställ in transaktionens natur enligt landets/regionens krav. För varje transaktionskod som du anger måste du ställa in reglerna för att beräkna fakturabelopp och statistiska belopp för överföringsorder och försäljnings-/inköpsorder.<ul><li>För överföringsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:<ul><li>**Tom** – Beloppet kommer att vara 0 (noll).</li><li>**Ekonomiskt självkostnadsbelopp** – Beloppet kommer att vara lika med den ekonomiska kostnaden.</li><li>**Total kostnad** – Beloppet kommer att vara lika med totalkostnaden för transaktionen.</li><li>**Manuellt** – Beloppet kommer att vara samma som det belopp som angetts manuellt på överföringsorderraden.</li></ul></li><li>För försäljnings- och inköpsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:<ul><li>**Tom** – Beloppet kommer att vara 0 (noll).</li><li>**Fakturabelopp** – Beloppet kommer att vara samma som det fakturerade beloppet för varan.</li><li>**Basbelopp** – Beloppet kommer att vara samma som det fakturerade beloppet före en eventuell rabatt.</li></ul></ul>Mer information finns i exempel [transaktionskoder och tillägg](#transaction-codes-and-miscellaneous-charges). |
| Transportmetoder | Ställ in transportsätt enligt landets/regionens krav. För varje leveranssätt kan du ställa in en standardtransportmetod på fliken **Utländsk handel**. |
| Hamnar | Ställ in hamnen/flygplatsen för lastning/avlastning om denna information samlas in av ditt land/din region. |
| Statistikprocedurer | Ställ in statistikproceduren om denna information samlas in av ditt land/din region. |



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

## <a name="example"></a>Exempel

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a>Transaktionskoder och tillägg

Det här ämnet omfattar ett scenario där ett företag i Tyskland måste köpa varor från ett företag i Italien. För att kunna göra detta inköp måste det tyska företaget ställa in nya transaktionskoder och konfigurera beräkningsregler för fakturabeloppet och det statistiska beloppet för dessa transaktionskoder. När företaget skapar en faktura, måste det dessutom ange tillägg och deras procentsatser. Dessa värden beaktas när det statistiska värdet beräknas.

Detta scenario använder den juridiska personen **DEMF**.

#### <a name="preliminary-setup"></a>Preliminär inställning

1. Gå till **Organisationsadministration** > **Organisation** > **Juridiska personer** och välj **DEMF**.
2. På snabbfliken **Adresser** på fältet **land/region** till **DEU (Tyskland)**.
3. Gå till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer**.
4. Välj **DE-001** i rutnätet.
5. På snabbfliken **Adress** väljer du **Registrera**.
6. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **ITA**.
7. Välj **OK** för att stänga dialogrutan.

#### <a name="set-up-transaction-codes"></a>Ställ in transaktionskoder

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
2. Välj **11** i rutnätet. Välj sedan **Ta bort** i åtgärdsfönstret.
3. Klicka på **Ny** i åtgärdsfönstret.
4. På snabbfliken **Transaktionskoder** i fältet **Transaktion** **kod** ange **11**.
5. I fältet **Namn** anger du **Direkt köp/försäljning**.
6. I avsnittet **Försäljning och inköp** i fältet **Fakturabelopp**, välj **Fakturabelopp**.
7. I fältet **Statistiskt belopp**, välj **Fakturabelopp**.
8. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="set-up-miscellaneous-charges"></a>Ställa in tillägg

1. Gå till **Kundreskontra** > **Ställa in avgifter** > **Avgiftskod**.
2. Välj **Frakt** i rutnätet.
3. I åtgärdsfönstret väljer du **Redigera**.
4. På snabbfliken **Utländsk handel**, ange alternativen **Intrastat fakturavärde** och **Intrastat statistikvärde** till **Ja**.

#### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
2. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **11**.
3. På snabbfliken **Artikelkodhierarki** bekräftar du att fältet **Kategorihierarki** är inställt på **Intrastat**.

#### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa inköpsorder**, i fältet **Leverantörskonto**, väljer du **DE-001**.
4. Välj **OK**.
5. I fliken **Rubrik**, på snabbfliken **Handel med** **utlandet**, bekräftar du att fältet **Transaktionskod** angetts som **11**.
6. På fliken **Rader** > snabbfliken **Inköpsorderrader** > fältet **Artikelnummer** väljer du **D0003**. I fältet **Kvantitet**, ange **10**.
7. På snabbfliken **Raddetaljer** på fliken **Handel med utlandet** i avsnittet **Utländsk handel**, verifiera att fältet **Transaktionskod** har ställts in automatiskt.
8. På snabbfliken **Inköpsorderrader** på menyn **Ekonomi** i avsnittet **Tillägg** väljer du **Underhåll avgifter**.
9. I fältet **Kod för avgifter** välj **FRAKT**.
10. I fältet **Avgiftsvärde** ange **30**.
11. Klicka på **Spara** i åtgärdsfönstret. Stäng sidan.
12. I Åtgärdsfönstret > på fliken **Inköp** > i gruppen **Åtgärd** markerar du **Bekräfta**.
13. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
14. I åtgärdsfönstret väljer du **Standard från**. I fältet **Standardkvantiteter för rader** väljer du **Beställd kvantitet**. Välj sedan **OK**.
15. På snabbfliken **Sidhuvud i leverantörsfaktura** i avsnittet **Fakturaidentifiering** i fältet **Nummer** anger du **00100**.
16. I avsnittet **Fakturadatum** > fältet **Fakturadatum** väljer du **11/24/2021** (24 november 2021).
17. Om du vill bokföra fakturan väljer du **Bokför** i åtgärdsfönstret.

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Överför leverantörsfakturan till Intrastat-journalen

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Leverantörsfaktura** som **Ja**.
4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

   ![Rad som representerar inköpsordern med diverse avgifter på Intrastat-sidan](media/intrastat_overview_1.png)

5. Granska fliken **Allmänt** för inköpsordern. Lägg märke till att fältet **Fakturavärde** visar summan av fälten **Fakturabelopp** and **Fakturaavgiftsbelopp** och fältet **Statistiskt värde** visar summan av fälten **Statistiskt belopp** och **Statistiskt tilläggsbelopp**.

   ![Inköpsorderdetaljer med diverse avgifter på fliken Allmänt på Intrastat-sidan](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Överföringsorder

I det här exemplet måste ett företag i Tyskland flytta två enheter varor från ett lagerställe i Tyskland till ett lagerställe i Italien. Tillägg med en sats på 20 procent måste också anges för denna produkt för redovisning i fältet **Statistiskt värde**. I exemplet används den juridiska personen **DEMF**.

#### <a name="preliminary-setup"></a>Preliminär inställning

1. Gå till **Organisationsadministration** > **Organisation** > **Juridiska personer** och välj **DEMF**.
2. På snabbfliken **Adresser** på fältet **land/region** till **DEU (Tyskland)**.
3. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
4. På snabbfliken **Artikelkodhierarki** bekräftar du att fältet **Kategorihierarki** är inställt på **Intrastat**.
5. Gå till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer**.
6. Välj **DE-001** i rutnätet.
7. På snabbfliken **Adress** väljer du **Registrera**.
8. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **ITA**.
9. Välj **OK** för att stänga dialogrutan.

#### <a name="set-up-transaction-codes"></a>Ställ in transaktionskoder

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
2. Välj **11** i rutnätet. Välj sedan **Ta bort** i åtgärdsfönstret.
3. Klicka på **Ny** i åtgärdsfönstret.
4. På snabbfliken **Transaktionskoder** i fältet **Transaktion** **kod** ange **11**.
5. I fältet **Namn** anger du **Direkt köp/försäljning**.
6. I avsnittet **Överföringsorder** i fältet **Fakturabelopp** välj **Total kostnad**.
7. I fältet **Statistiskt belopp** välj **Total kostnad**.
8. Klicka på **Spara** i åtgärdsfönstret.
9. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
10. På fliken **Intrastat** på fliken **Allmänt** i fältet **Överföringsorder**, välj **11**.

#### <a name="set-up-charges-for-an-item"></a>Ställa in tillägg för ett objekt

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. Välj **D0001** i rutnätet.
3. På snabbfliken **Handel med utlandet** i avsnittet **Intrastat** i fältet **Avgiftsprocent** ange **20**.

#### <a name="change-the-site-address"></a>Ändra platsens adress

1. Gå till **Lagerstyrning** > **Konfiguration** > **Distributionslager** > **Platser**.
2. Välj **1** i rutnätet.
3. På snabbfliken **Adresser** väljer du **Registrera**.
4. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **DEU**.
5. Välj **OK**.
6. Välj **2** i rutnätet.
7. På snabbfliken **Adresser** väljer du **Registrera**.
8. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **ITA**.
9. Välj **OK**.
10. Gå till **Lagerstyrning** > **Inställningar** > **Lagerställe** > **Lagerställen**.
11. Välj **21** i rutnätet.
12. På snabbfliken **Allmänt** i avsnittet **Referens** i fältet **Leverantörskonto**, välj **DE-001**.

#### <a name="create-a-transfer-order"></a>Skapa en överföringsorder

1. Gå till **Lagerhantering** > **Utgående order** > **Överföringsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. På fliken **Rader** på snabbfliken **Överföringsorderrubrik** i avsnittet **Översikt** i fältet **Från lagerställe** välj **11**. I fältet **Till lagerställe** väljer du **21**.
4. På fliken **Rader** på snabbfliken **Överföringsorderrader**, välj **Lägg till**.
5. I fältet **Artikelnummer**, välj **D0001**. I fältet **Överföringsmängd**, ange **2**.
6. På snabbfliken **Raddetaljer** på fliken **Handel med utlandet** i avsnittet **Utländsk handel**, verifiera att fältet **Transaktionskod** har ställts in automatiskt.
7. I åtgärdsfönstret på fliken **Leverera** i gruppen **Åtgärder** väljer du **Leverera överföringsorder**.
8. I dialogrutan **Leverans** på fliken **Översikt** i fältet **Uppdatera** välj **Alla**.
9. Välj **OK** för att leverera ordern.
10. I åtgärdsfönstret, på fliken **Inleverera** i gruppen **Åtgärder**, markerar du **Inleverera**.
11. I dialogrutan **Inleverera** på fliken **Översikt** i fältet **Uppdatera** välj **Alla**.
12. Välj **OK** för att leverera ordern.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Överför överföringsordern till Intrastat-journalen

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (Transfer)** ange alternativet **Överföringsorder** till **Ja** och alla andra alternativ till **Nej**.
4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

   ![Rad som representerar överföringsordern på Intrastat-sidan](media/intrastat_overview_3.png)

5.  Granska fliken **Allmänt** för överföringsordern.

    Observera att fälten i avsnitten **Fakturavärde** och **Statistiskt värde** ställs in automatiskt. Värdena i fälten **Fakturabelopp** och **Statistiskt belopp** baseras på inställningarna på sidan **Transaktionskoder**. Värdet **20** i fältet **Avgiftsprocent** är värdet som ställs in på sidan **Frisläppt produkt**. Värdet i fältet **Statistiskt tilläggsbelopp** är ett kvantitativt uttryck för avgifterna (eftersom 107,24 är lika med 20 procent av 536,18). Värdet i fältet **Statistiskt värde** är summan av värdena i fälten **Statistiskt belopp** och **Statistiskt tilläggsbelopp**.

  ![Överföringsorderdetaljer på fliken Allmänt på Intrastat-sidan](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Ytterligare enheter

I det här exemplet måste ett företag i Tyskland köpa 10 enheter varor från ett företag i Italien. Utöver artikelkoder måste ytterligare enheter anges för dessa varor. I exemplet visas hur du skapar nya måttenheter, tilldelar ytterligare enheter till Intrastat-artikelkoden, bokför transaktioner som har ytterligare enheter och granskar Intrastat-journalen där fältet för de ytterligare enheterna är inställt.

#### <a name="preliminary-setup"></a>Preliminär inställning

1. Gå till **Organisationsadministration** > **Organisation** > **Juridiska personer** och välj **DEMF**.
2. På snabbfliken **Adresser** på fältet **land/region** till **DEU (Tyskland)**.
3. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
4. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **11**.
5. På snabbfliken **Artikelkodhierarki** bekräftar du att fältet **Kategorihierarki** är inställt på **Intrastat**.
6. Gå till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer**.
7. Välj **DE-001** i rutnätet.
8. På snabbfliken **Adress** väljer du **Registrera**.
9. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **ITA**.
10. Välj **OK** för att stänga dialogrutan.

#### <a name="create-a-unit-of-measure"></a>Skapa en måttenhet

1. Gå till **Organisationsadministration** > **Inställningar** > **Enheter** > **Enheter**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Enhet** ange ett namn för måttenheten. Ange **GRM** i det här exemplet.
4. På snabbfliken **Allmänt** i avsnittet **Klassificering** i fältet **Enhetsklass**, välj den egenskap som enheten mäter. Välj **Mass** i det här exemplet.
5. I **System med enheter**, välj det mätsystem som enheten tillhör. Välj till exempel **måttenheter**.

#### <a name="set-up-unit-conversions"></a>Ställ in konverteringar

1. Gå till **Organisationsadministration** > **Inställningar** > **Enheter** > **Enhetskonverteringar**.
2. På fliken **Konverteringar mellan klasser**, välj **Ny**.
3. I dialogrutan **Enhetskonvertering** i fältet **Produkt** väljer du **F00007**.
4. Välj **Från enhet** i fältet **Enhet**.
5. Välj **Till enhet** i fältet **GRM**.
6. Kontrollera att konverteringskursen är **1 = 1**.
7. Välj **OK**.
8. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
9. Välj **F00007** i rutnätet.
10. På snabbfliken **Hantera lager** > avsnittet **Lager** > fältet **Enhet** väljer du **GRM**.
11. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="set-up-product-information"></a>Konfigurera produktinformation

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. Välj **F00007** i rutnätet.
3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **920 20 34**.
4. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>Tilldela ytterligare enhet till en Intrastat artikelkod

1. Gå till **Produktinformationshantering** > **Inställningar** > **Kategorier och attribut** > **Kategorihierarkier**.
2. Välj **Intrastat** i listan.
3. Välj **Högtalare** i rutnätet.
4. På snabbfliken **Handel med utlandet**, i fältet **Ytterligare enheter**, väljer du **GRM**.
5. Klicka på **Spara** i åtgärdsfönstret.

   Mer information finns i [Hantera måttenheter](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa inköpsorder**, i fältet **Leverantörskonto**, väljer du **DE-001**.
4. Välj **OK**.
5. I fliken **Rubrik**, på snabbfliken **Handel med** **utlandet**, bekräftar du att fältet **Transaktionskod** angetts som **11**.
6. På fliken **Rader** > snabbfliken **Inköpsorderrader** > fältet **Artikelnummer** väljer du **F00007**. I fältet **Kvantitet**, ange **10**.
7. På snabbfliken **Raddetaljer** på fliken **Handel med utlandet** i avsnittet **Utländsk handel** verifiera att fälten **Transaktionskod** och **Artikel** har ställts in automatiskt.
8. I Åtgärdsfönstret > på fliken **Inköp** > i gruppen **Åtgärd** markerar du **Bekräfta**.
9. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
10. I åtgärdsfönstret väljer du **Standard från**. I fältet **Standardkvantiteter för rader** väljer du **Beställd kvantitet**. Välj sedan **OK**.
11. På snabbfliken **Sidhuvud i leverantörsfaktura** > avsnittet **Fakturaidentifiering** > fältet **Nummer** anger du **VE-0010**.
12. I avsnittet **Fakturadatum** fältet **Fakturadatum** väljer du **10/5/2021** (5 oktober 2021).
13. Om du vill bokföra fakturan väljer du **Bokför** i åtgärdsfönstret.

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Överför leverantörsfakturan till Intrastat-journalen

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Leverantörsfaktura** som **Ja**.
4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

   ![Rad som representerar inköpsordern på Intrastat-sidan](media/intrastat_overview_5.png)

5. Granska fliken **Allmänt** för inköpsordern. Lägg märke till **Kvantiteten för ytterligare enheter** och **Ytterligare enheter** i avsnittet **Enhet** ställs in automatiskt.

   ![Inköpsorderdetaljer på fliken Allmänt på Intrastat-sidan](media/intrastat_overview_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
