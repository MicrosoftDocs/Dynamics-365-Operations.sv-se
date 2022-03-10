---
title: Inställning av automatiska kostnader
description: I det här avsnittet beskrivs hur du ställer in kostnadsregler för olika inkommande färdnivåer. Baserat på dessa regler beräknar systemet kostnaderna och lägger automatiskt till dem. Därför behöver användarna inte lägga till kostnaderna manuellt.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0fe795127300ac99c3f5ee65cb1f6e0841ad4d95
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575810"
---
# <a name="auto-costs-setup"></a>Inställning av automatiska kostnader

[!include [banner](../../includes/banner.md)]

Du kan använda sidan **Automatiska kostnader** för att ställa in kostnadsregler för olika kostnadsområden (såsom färder, leveransbehållare, folio, inköpsorder, artiklar eller överföringsorderrader). Baserat på reglerna och de fält som användarna väljer när de skapar poster för ett av kostnadsområdena, beräknar systemet kostnaderna och lägger automatiskt till dem. Därför behöver användarna inte lägga till kostnaderna manuellt.

Om du vill arbeta med automatiska kostnader, gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Automatiska kostnader**. Ställ sedan in regler för automatiska kostnader på det sätt som beskrivs i resten av det här avsnittet.

## <a name="work-with-cost-areas"></a>Arbeta med kostnadsområden

Automatiska kostnader fungerar som handelsavtal eller automatiska tillägg. Varje post för automatisk kostnad hör till en viss kostnadsnivå. Använd fältet **Kostnadsområde** i listrutan på sidan **Automatiska kostnader** för att välja det kostnadsområde som du vill arbeta med. I listfönstret visas endast automatiska kostnader som tillhör det för tillfället valda kostnadsområdet. Alla automatiska kostnader som du skapar tillhör det för tillfället valda kostnadsområdet.

Med kostnadsområden kan systemet fördela kostnader över inköpsorderraderna i ett kostnadsområde. En kostnad för en leveransbehållare fördelas till exempel värdet av alla produkter i den leveransbehållaren. Om det finns två eller flera leveransbehållare kan samma kostnadstyp anges för varje leveransbehållare. Därför kan behållartypen användas för att hitta rätt automatisk kostnad.

## <a name="buttons-on-the-action-pane"></a>Knappar i åtgärdsfönstret

I följande tabell beskrivs de knappar som finns tillgängliga på fliken åtgärdsfönstret för **Automatiska kostnader**.

| Knapp | beskrivning |
|---|---|
| Redigera | Redigera en befintlig automatisk kostnad. |
| Nytt | Skapa en automatisk kostnad. |
| Radera | Ta bort en automatisk kostnad. |
| Kopiera från | Skapa en ny automatisk kostnad utifrån en befintlig arbetspost. Du kan sedan redigera den nya posten fritt. Med den här knappen kan du snabbt skapa nya automatiska kostnader. |
| Visa dimensioner | Öppna en dialogruta där du kan välja lagerdimensionerna som visas för de kostnadstransaktioner som du visar. Om du avmarkerar kryssrutorna visas färre lagerdimensioner för kostnadstransaktionerna. Mindre detaljer visas därför för transaktionen. Om en lagerdimension har angetts för en automatisk kostnad används automatiska kostnaden bara när den angivna lagerdimensionen används för artikeln på en lagerinventering. |

## <a name="settings-on-the-header"></a>Inställningar i rubriken

Kombinationen av inställningar i rubrikavsnittet avgör när och hur en viss automatisk kostnad läggs till i en färd. En automatisk kostnad tillämpas endast på en färd, leveransbehållare eller folio när detaljerna i automatiska kostnaden matchar uppgifterna i sidhuvudet i kostnadsområdet. Summan av alla matchande automatiska kostnader avgör den uppskattade hemtagningskostnaden för en färd. Denna kostnad fördelas på alla artiklar på fartyget eller färden.

Följande register beskriver alla fält som kan visas i rubriken. Vilka fält som finns tillgängliga varierar emellertid beroende på kostnadsområde och visningsdimensioner som för närvarande är valda.

| Fält | beskrivning |
|---|---|
| **Kontokod** | <p>Välj ett av följande värden:</p><ul><li>**Tabell** – Kostnadsregeln gäller endast en specifik leverantör.</li><li>**Grupp** – Kostnadsregeln gäller en specifik leverantörsgrupp. Systemet söker efter den [kostnadstypgrupp för leverantör](costing-parameters-setup.md) som är associerad med leverantörsposten.</li><li>**Alla** – Kostnadsregeln gäller för alla leverantörer. |
| **Speditör** | Välj den leverantör eller leverantörsgrupp som kostnadsregeln gäller. Det här fältet är endast tillgängligt om du väljer antingen *Tabell* eller *Grupp* i fältet **Kontokod**. |
| **Tullmäklare** | Välj den leverantör eller leverantörsgrupp som kostnadsregeln gäller. Det här fältet är endast tillgängligt om du väljer antingen *Tabell* eller *Grupp* i fältet **Kontokod**. |
| **Artikelkod** | <p>Välj ett av följande värden:</p><ul><li>**Tabell** – Kostnadsregeln gäller endast en specifik artikel.</li><li>**Grupp** – Kostnadsregeln gäller en specifik artikelgrupp. Systemet söker efter den [kostnadstypgrupp för artikel](costing-parameters-setup.md) som är associerad med artikelposten.</li><li>**Alla** – Kostnadsregeln gäller för alla artiklar.|
| **Artikelrelation** | Välj den artikel eller artikelgrupp som kostnadsregeln gäller. Det här fältet är endast tillgängligt om du väljer antingen *Tabell* eller *Grupp* i fältet **Artikelkod**. |
| **Leveranssätt** | Välj det leveranssätt (t.ex. flyg eller båt) som kostnadsregeln gäller för. |
| **Behållartyp** | Den typ av leveransbehållare som varorna ska skeppas i. En automatisk kostnad kan endast användas för en sådan om behållartyp i inställning av automatisk kostnad matchar färdens behållartyp. |
| **Från port** och **Till port** | Källporten ("från")-porten och destinationen ("till")-porten för företaget. (Vissa leveransbehållare kan ha olika "till"-portar, eftersom den kan stoppas vid flera portar.) En automatisk kostnad kan endast användas för en automatisk kostnad om portarna "från" och "till" i inställningarna för automatisk kostnad matchar portarna "från" och "till" för företaget. |
| **Automatiskt kostnadsnummer** | Unik identifierare för regeln för automatisk kostnad. Värdet i det här fältet genereras automatiskt baserat på nummerserien som ställs in på sidan **Parametrar för hemtagningskostnad**. |
| **Lagerdimensioner** | I vissa kostnadsområden kan du inkludera en eller flera artikeldimensioner i rubriken (till exempel storlek, färg, lagerställe och batchnummer). Välj **Visa dimensioner** i åtgärdsfönstret för att välja vilka dimensioner som ska inkluderas. |

## <a name="settings-on-the-lines-fasttab"></a>Inställningar på snabbfliken Rader

På snabbflikarna **Rader** lägger du till en rad för varje valuta som kan användas när en kostnad används på en inköpsorderrad i en färd. 

För artiklar och inköpsorder matchar systemet valutan för varje inköpsorderrad mot valutorna som anges på snabbflikarna **rader**. Den gäller endast det kostnadsvärde som har angetts för matchningsraden eller artikeln. Om ingen rad har angetts för valutan för raden eller artikeln används inte automatiska kostnaden på raden eller artikeln.

För andra typer av kostnadsområden, alla rader på snabbfliken **rader** gäller för varje färd, leveransbehållare, folio eller överföringsorderrad som matchar värdena som anges i rubriken.

Följande register beskriver alla fält som kan visas på varje rad. Vilka fält som finns tillgängliga varierar emellertid beroende på kostnadsområde som för närvarande är valda.

| Fält | beskrivning |
|---|---|
| **Valuta** | Välj valuta som raden gäller för. Den här valutan är relaterad till inköpsordern. När systemet försöker hitta de autokostnader som ska tillämpas på en rad och dess rader, väljer den raden som har samma valuta som inköpsordern. Det här fältet är endast tillgängligt om fältet **Kostnadsområde** är inställt på *Inköpsorder* eller *Artikel*. |
| **Kod för kostnadstyp** | Kostnadstypen. |
| **Fördelningsmetod** | <p>Den metod som används för att fördela kostnader på rader. Följande alternativ är tillgängliga:</p><ul><li><p>**Procent** – Värdet i fältet **Kostnadsvärde** är en procentsats som gäller för det totala värdet av varor.</p><p>Om till exempel fältet **Kostnadsvärde** är inställt på *10* och det totala värdet av varor är $800, är kostnadsvärdet $80 (= $800 × 10 procent).</p></li><li>**Kvantitet** – Kostnaden fördelas utifrån varukvantiteten.</li><li>**Belopp** – Kostnaden fördelas utifrån varans värde.</li><li>**Volym** – Kostnaden fördelas utifrån varans volym. Volym anges i artikelns huvudpost.</li><li>**Vikt** – Kostnaden fördelas utifrån varans vikt. Vikt anges i artikelns huvudpost.</li><li>**Volymmetod** – Kostnaden fördelas utifrån volymetrisk mätning av varor.</li><li><p>**Mått** – Det här alternativet gör att en mätning kan anges i modulen **Hemtagningskostnad**. Den används ofta av organisationer som inte känner till den individuella volymen eller vikten av varorna, men som kräver en mer korrekt fördelning än alternativen för **belopp** och **kvantitet**. Fraktspeditören eller agenten förser organisationen med vikt- eller mätning av mätning av mått, antingen på artikel- eller inköpsordernivå.</p><p>Till exempel är frakt till sjöss lika med $900. Artikel A har en vikt på 800 kilo (kg) och en volym på 2 m kubikmeter (m³). Artikel B har en vikt på 100 kg och en volym på 1 m³. Här är resultaten när kostnaderna fördelas efter vikt:</p><ul><li>Artikel A = $800</li><li>Artikel B = $100</li></ul><p>Här är resultaten när kostnaderna fördelas efter volym:</p><ul><li>Artikel A = $600</li><li>Artikel B = $300</li></ul><p>**Obs!** När fältet **Fördelningsmetod** anges till *Mått* använder systemet de mått som anges för både kostnadsområdet (leveransbehållare) och raderna. Dessa mått behöver inte nödvändigtvis summera till den förväntade summan. Om du däremot kräver att de summerar det förväntade beloppet kan du göra en kontroll med hjälp av statistiken för att granska den totala mätningen. Inställning av mätningsuppmaning och automatisk uppdatering av mått på leverans- eller behållarnivå ställs in i färdens sidhuvud.</p></li></ul> |
| **Från-datum** | Ange början på datumintervallet för kostnadsredovisning om det finns ett datumintervall. Detta är det första datum då automatiska kostnaden används. |
| **Till-datum** | Ange slutet på datumintervallet för kostnadsredovisning om det finns ett datumintervall. Detta är det sista datum då automatiska kostnaden används. |
| **Kategori** | <p>Välj den metod som används för att beräkna kostnaden. Följande alternativ är tillgängliga:</p><ul><li>**Fast** – Kostnaden fördelas utifrån fördelningsmetoden.</li><li>**Stycken** - Kostnaden fördelas per styck. Därför används inte fördelningsmetoden.</li><li>**Procent** – En procent av varornas värde läggs till. Därför används inte fördelningsmetoden.</li><li>**Kurs** – Välj det här alternativet om det finns kvantitetsuppdelningar. Fältet **fördelningsmetoden** för raden måste ställas in på *Mått*.</li><ul> |
| **Uppdelat efter kvantitet** | <p>Markera den här kryssrutan om du vill göra knappen **kvantitetsavbrott** tillgänglig på snabbfliken **Rader**. Kvantitetsavbrott gör att kostnaden kan brytas ned och de olika kostnaderna varierar beroende på kvantiteten på inköpsorderraden i färden. Den här funktionen används ofta när leveranssättet är flyg. Fältet **Kategori** för raden måste ställas in på *Kurs*.</p><p>Kvantiteten avser alternativet som väljs i fältet **fördelningsmetoden**. Kostnadsvärdet kommer att vara upp till den kvantitet som har angetts i fältet **Kostnadsvärde**.<p>Exempelvis kan kvantiteter på 45–100 kg producera en kostnad $6,00 per mått (t.ex. kg/m³). Kvantiteter som överskrider 100 kg producera en kostnad $5,50 per mått (t.ex. kg/m³).</p> |
| **Kostnadsvärde** | Ange värdet för kostnaden. |
| **Valutakod för kostnad** | Välj valuta för kostnaden. |
| **Artikelmomsgrupp** | Välj momskod för kostnaden. |
| **Minimikostnad** | <p>Det här fältet gäller bara om kryssrutan **Bruten efter kvantitet** har markerats. Om mätningen inte når detta värde väljs minimivärdet, oavsett vilka kostnader som har angetts på sidan **Kvantitetsbrytningar**.<p>Exempelvis kan kvantiteter på 0–45 kg producera en kostnad $6 per mått (kg/m³). Kvantiteter på 46–100 kg producerar en kostnad $5,50 per mått (kg/m³). Om 2 kg levereras skapar kvantitetsbrytningen ett kostnadsvärde på $12. Om fältet **minimikostnad** är inställt på *$100*, blir dock den slutliga kostnaden $100.</p> |
| **Sammansättning** | Markera den här kryssrutan om du vill tillåta användare att flytta denna kostnad från nivån för leveransbehållare till den sista färdnivån. I detta fall kan kostnader beräknas automatiskt på leveransbehållarnivå. De kan emellertid även kombineras och fördelas mellan alla artiklar i alla behållare i en behållare i en färd, i stället för alla artiklar i de enskilda leveransbehållarna. |
| **Länkad kostnadstyp** | <p>Länka den aktuella raden till en annan rad i samma post för automatisk kostnad genom att ange värdet **kostnadstypskod** för raden som du vill länka till. Den här funktionen är bara tillgänglig om fältet **kategori** för den aktuella raden är inställt på *Procent*. När den aktuella raden är länkad till en annan rad, baseras kostnaden för den aktuella raden på kostnaden för den andra raden.</p><p>Frakt beräknas till $1000 du vill att bränsletillägget ska vara 10 procent av fraktkostnaden. I det här fallet måste raden ha värdet **Kategori** för *Procent*, ett värde **kostnadsvärde** på *10 %* och **kopplad kostnadstyp** på *frakt*.</p> |
| **Värdejustering** och **Justeringsbelopp** | <p>Använd dessa fält om du vill justera värde och belopp för olika procentvärden. De är endast tillgängliga om fältet **Kostnadsområde** har angetts som *Artikel*.</p><p>Olika kostnadsredovisningar kan ställas in för olika komponenter i en artikel. En komponent av en artikel kan ha en annan kostnadsprocent än övriga komponenter i artikeln. Det här arbetssättet krävs ibland för att värdera en viss del av varorna till olika satser.</p><p>Avgifter för en användare beräknas till exempel med två satser: en komponent i satsen har 10 procents tullsats och en andra komponent har en 2-procents tullsats. I det här fallet delas kostnadsredovisningen upp mellan de två komponenterna.</p><p>Kostnaden beräknas för artikeln, men kostnadsvärdet justeras med värdet för de komponenter som har den olika kostnadskategorin. Kostnaden för övriga komponenter kan sedan beräknas med det belopp som den föregående beräkningen justerades med.</p><p>Till exempel har komponent A i programmet en kostnad $9,50 och en avgift på 10 procent, och komponent B har en kostnad $0,50 och en avgift på 2 procent. Därför är totala kostnaden $10,00. Den första posten gäller 10-procentsraden. Det har följande värden:</p><ul><li>**Kategori:** *procent*</li><li>**Kostnadsvärde:** *10*</li><li>**Värde justerat:** *Justera med*</li><li>**Justerat värde:** *-0,50*</li></ul><p>Den här inställningen anger att kostnaden för artikeln (10 USD) måste minskas med $0,50 (priset på komponent B) innan en avgift på 10 procent beräknas. Därför används 10 procent för $9,50.</p><p>Den andra posten gäller för 2-procentsraden ($0,50 som den föregående posten justerades med). Det har följande värden:</p><ul><li>**Kategori:** *procent*</li><li>**Kostnadsvärde:** *2*</li><li>**Justerat värde:** *Använd*</li><li>**Justering:** *0,50*</li></ul><p>I den här inställningen beräknas resterande avgift som ska betalas för komponent B.</p> |
