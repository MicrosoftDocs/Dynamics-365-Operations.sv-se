---
title: Ställa in farliga material
description: I det här avsnittet beskrivs hur du ställer in de data som krävs för att klassificera artiklar som farligt material. När du skapar en försäljningsorder som innehåller en artikel som klassificeras som ett farligt material genererar systemet information om farligt material för försäljningsordern när den har levererats.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: c360d6a0fd5ffb65d1ea50d50e1ea5de00c84abe72e83c72b9bc4d6826cb41d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712992"
---
# <a name="set-up-hazardous-materials"></a>Ställa in farliga material

[!include [banner](../includes/banner.md)]

Om du vill använda funktionen för farliga material måste du först ställa in de data som krävs för att klassificera artiklar som farligt material. Sedan när du skapar en försäljningsorder som innehåller en artikel som klassificeras som ett farligt material genererar systemet information om farligt material för försäljningsordern när den har levererats.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Aktivera funktionen för farliga material för ditt system

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Produktinformationshantering*
- **Funktionsnamn:** *Information om produkter för farligt material och leveransdokumentation*

## <a name="hazardous-material-regulations"></a>Regler om farliga material

Om du vill använda processerna för farliga material måste du först skapa regler. Regler definierar hur den utskrivna leveranstexten ska skapas för en artikel. De definierar också de relaterade leveranssätten.

Nedan följer några gemensamma regler:

- **ADR** – förordningar som rör internationell transport av farligt gods på väg
- **CFR 49** – förordningar i USA för transport av farligt gods
- **IMDG** – internationella koden för sjötransport av farligt gods (IMDG)
- **IATA** – reglerna för farligt gods i IATA (International Air Transport Association)

Dessa regler hjälper till att fastställa vilken information som ska visas när du skriver ut leveranstexten för en artikel. Du kan definiera så många regler som du måste följa.

> [!IMPORTANT]
> Funktionen för att ställa in informationskoder som rör farliga material gör inte ditt företag kompatibelt med regler. Det är bara ett verktyg som hjälper dig att skapa processer för ditt företag.

Normalt är en förordning tillgänglig för ett särskilt transportsätt, sjötransporterna, vägtransport eller flygtransport. Därför kan du koppla varje regel till ett leveranssätt. Leveranssättet kommer att användas när specifika dokument skrivs ut i lagerstyrning. I lagerstyrning är varje leverans kopplad till ett transportföretag och transportföretagstjänst som har ställts in i modulen **transport**. Leveranssättet är kopplat till transportföretaget och transporttjänsten. När du kör en rapport används leveranssättet för att hitta leveransens tryckta text som är kopplad till en frisläppt artikel.

Dessa inställningsdata är inte specifika för varje juridisk person (företag). Därför kan du ha en gemensam uppsättning information om farligt material som delas mellan alla dina juridiska personer.

För varje förordning kan du definiera en materiallista och använda den som en mallista som är kopplad till frisläppta artiklar. För varje förordning kan du även definiera en skrivarinställning. Med en skrivarinställning kan du definiera hur leveranstexten för en artikel ska skapas. Skrivarinställningen används för att skapa leveransens tryckta text för en frisläppt artikel.

Om du vill ställa in regler för farliga material går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Regler för farligt material**. På sidan för **regler för farliga material** kan du skapa ett valfritt antal regler och konfigurera var och en med hjälp av fälten som beskrivs i följande underavsnitt.

### <a name="hazardous-material-regulation-header"></a>Rubrik för regler om farliga material

Varje regel har en kod och en beskrivning. Följande register beskriver de fält som är tillgängliga i rubriken.

| Fält | beskrivning |
|---|---|
| Kod för föreskrift | Ange en kod för att identifiera posten för posten för farliga material. |
| beskrivning | Ange en beskrivning för regler för farliga material. |

### <a name="print-setup-fasttab"></a>Snabbfliken Utskriftsinställningar

Varje regel kan ha ett obegränsat antal utskriftsinställningar. Du definierar utskriftsinställningarna på snabbfliken **skrivarinställning**. Följande register beskriver de fält som är tillgängliga för varje utskriftsinställning.

| Fält | beskrivning |
|---|---|
| Sekvens | Definiera i vilken ordning fälten ska refereras i leveranstexten. |
| Skriv ut fält | Välj det fält som ska inkluderas i leveranstexten. Alla fält för det farliga materialet kommer inte att vara tillgängliga för utskrift. Endast de gemensamma fält som används för att definiera leveranstext i de olika reglerna kommer att vara tillgängliga. Du bör definiera det första utskriftsfältet som en fältavgränsare som har värdet **sekvens** på *0* (noll), så att det kan användas som avgränsare mellan andra fält. Det krävs bara en referens till fältavgränsaren.<p>Följande värden finns:</p><ul></li><li>**Fältseparator** – det här utskriftsfältet används som fältseparator för texten. Endast en fältseparator krävs i sekvensen. Vanligt vis ställer du in värdet **sekvens** för det här utskriftsfältet på *0* (noll). Systemet söker efter en fältavgränsare och använder det första som finns i listan. Det textvärde som används i strängen kommer från fältet **Skriv ut efter**.</li><li>**Identifiering** – i det här utskriftsfältet placeras [Identifieringskoden och/eller beskrivningen](#identification) i utskriftstexten.</li><li>**Klass** – i det här utskriftsfältet placeras [Klasskoden och/eller beskrivningen](#classes) i utskriftstexten.</li><li>**Indelning** – i det här utskriftsfältet placeras [Indelningskoden och/eller beskrivningen](#divisions) i utskriftstexten.</li><li>**Förpackningsgrupp** – i det här utskriftsfältet placeras [Förpackningsgruppkod och/eller beskrivningen](#packing-group) i utskriftstexten.</li><li>**Tunnelkod och/eller beskrivning** – i det här utskriftsfältet placeras [tunnelkoden och/eller beskrivningen](#tunnel) i utskriftstexten.</li><li>**Korrekt leveransnamn** – i det här fältet placeras det [korrekta leveransnamnet](hazmat-items.md#hazmat-description) i utskriftstexten.</li><li>**Tekniskt namn** – i det här utskriftsfältet placeras [Tekniskt namn och/eller beskrivningen](#technical-name) i utskriftstexten.</li><li>**Transportkategori** – i det här utskriftsfältet placeras [Transportkategorikoden och/eller beskrivningen](#transport-category) i utskriftstexten.</li><li>**Förvaring** – i det här utskriftsfältet placeras [förvaringskoden och/eller beskrivningen](#stowage) i utskriftstexten.</li><li>**Fast text** – det här utskriftsfältet anger den text som är definierad i fältet **fast text** för den här raden.</li><li>**Etikettkod och/eller beskrivning** – i det här utskriftsfältet placeras [Etikettkod och/eller beskrivningen](#label) i utskriftstexten.</li><li>**Flygplansförpackning** – i det här utskriftsfältet placeras [Flygplansförpackningskod och/eller beskrivningen](#packing-instruction) i utskriftstexten.</li><li>**Begränsad kvantitet** – i det här utskriftsfältet kontrolleras om artikeln är markerad som en [artikel med begränsad kvantitet](hazmat-items.md#material-management) och om den är den text som är definierad i fältet **fast text** för den här raden.</li><li>**Förpackningsbeskrivning** – i det här utskriftsfältet placeras [Förpackningsbeskrivning och/eller beskrivningen](#packing-description) i utskriftstexten.</li></ul> |
| Skriv ut före | Ange den text som ska skrivas ut före innehållet som definieras av inställningen för **utskriftsfält**. |
| Skriv ut efter | Ange den text som ska skrivas ut efter innehållet som definieras av inställningen för **utskriftsfält**. |
| Skriv ut med föregående | Markera den här kryssrutan om du vill förhindra att fält avgränsaren skrivs ut mellan det föregående fältet och det här fältet. Använd den här kryssrutan för att skriva ut fält som är valfria eller inkluderade i ett annat utskriftsfält. |
| Fast text | Om du ställer in fältet **Utskriftsfält** till **Fast text** eller **Begränsad kvantitet** anger du den text som ska skrivas ut. |
| Inkludera i utskrift | Välj vilket värde eller värden från det valda utskriftsfältet som ska skrivas ut för den här raden. Du kan skriva ut koden, beskrivningen eller både koden och beskrivningen. |

### <a name="mode-of-delivery-fasttab"></a>Snabbfliken Leveranssätt

Regeln är en delad tabell och är inte specifik för varje juridisk person. Leveranssätten är dock specifika för juridiska enheter. När du ställer in ett leverans sätt måste du därför välja relationen mellan regeln, den juridiska personen och leveranssättet.

Följande register beskriver de fält som är tillgängliga i snabbfliken **Leveranssätt**.

| Fält | beskrivning |
|---|---|
| Företag | Välj en juridisk person som ska associeras med denna regel. |
| Leveranssätt | Välj det leveranssätt som ska associeras med regel, baserat på den valda juridiska personen. |

### <a name="country-fasttab"></a>Snabbfliken land

I referenssyfte kan du ange vilka länder eller regioner som regeln är relevant för. När leveransrapporter körs används emellertid bara leveranssättet för att fastställa regeln. När du granskar en lagerutleverans, finns det ingen direkt länk till leveranssättet. Leveransen kan kopplas till transportföretaget och transporttjänsten. När du definierar en transportföretagstjänsten måste du associera den med ett leveranssätt. Den här relationen används på leveransrapporter, t.ex. fraktsedel för att hitta leveransens tryckta text för en artikel.

Följande register beskriver de fält som är tillgängliga i snabbfliken **Land**.

| Fält | beskrivning |
|---|---|
| Land/region | Välj land/region som ska associeras med den här regeln. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Materialkoder

Materialkoder skapar inställningar som är relaterade till en viss farlig komponent som kan ingå i en frisläppt produkt. Varje materialkod tillhör en specifik farligt materialregel och dess definition måste överensstämma med den regeln. När du kopplar en materialkod till en frisläppt produkt med hjälp av fältet **materialkod** används alla materialkod inställningar för farligt material automatiskt för den produkten. Därför är processen för att ställa in frisläppta produkter snabbare och mindre känslig för felet.

Hantera dina farliga material definitioner enligt följande instruktioner.

1. Gå till **Produktinformationshantering management \> Konfigurera \> Dokumentation för leverans av farligt material \> Regler för farligt material**.
2. Välj regeln för att ställa in en definition för farligt material för.
3. Välj **Försäljningsorderursprung** på fliken **Farliga material** i åtgärdsfönstret.
4. I fältet **Materialkod** ange en materialkod för definitionen av farligt material i fältet materialkod. Du väljer det här värdet när du använder materialkoden för en frisläppt produkt.

    Fältet **Regelkod** är skrivskyddat och visar den regel som du valde i steg 2.

5. Använd de återstående fälten på den här sidan om du vill skapa och ställa in varje farligt material som gäller för den valda regeln. Tillgängliga fält är en delmängd av de farliga material fält som är tillgängliga för enskilda frisläppta produkter. För mer information, se [Farliga material i produkter, order, leveranser och laster](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Klassificeringsgrupper för farligt material

Varje klassificeringsgrupp för farligt material definierar en grupp av fältvärden som skapar en mall. Du kan använda den här mallen senare när du ställer in information om farligt material för en frisläppt artikel.

När du tilldelar koden för en anslagen material klassificeringsgrupp till en frisläppt artikel, kopieras den information som är kopplad till klassificeringsgruppen till rätt fält för artikeln. Därför kan du förenkla inställningsprocesserna genom att skapa en uppsättning relaterade fältvärden som du ofta använder tillsammans.

Dessa inställningsdata är inte specifika för varje juridisk person. Därför kan du ha en gemensam uppsättning information om farligt material som delas mellan alla dina juridiska personer.

Om du vill ställa in klassificeringsgrupper för farliga material går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Klassificeringsgrupper för farliga material**. På sidan för **klassificeringsgrupper för farliga material** kan du skapa ett valfritt antal grupper och konfigurera var och en med hjälp av fälten som beskrivs i följande tabell.

| Fält | beskrivning |
|---|---|
| Gruppkod | Ange en kod för att identifiera gruppen. |
| beskrivning | Ange en beskrivning för gruppen. |
| Klasskod | Associera en [klasskod](#classes) för farligt material med gruppen. |
| Indelningskod | Associera en [Indelningskod](#divisions) för farligt material med gruppen. |
| Förpackningsgruppskod | Associera en [förpackningsgruppkod](#packing-group) med gruppen. |
| Kod för transportkategori | Associera en [Transportkategorikod](#transport-category) med gruppen. |
| Multiplikator | Ange den multiplikator för farligt material som gäller för den valda klassen och fördelningen av farliga material enligt tillämplig regel. Denna multiplikator används som en del av formeln för att beräkna de totala *punkter med farligt material* som ingår i en last eller leverans. Mer information om farliga materialpunkter och den här multiplikatorn finns i [snabbfliken materialhantering](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Klasser för farliga material

En klass för farligt material mappas vanligen till listan över klasser som finns i den förordning som du följer. Exempelvis amerikanska förordning CFR 49 listorna "klass 3" som brandfarliga och brännbara vätskor. Du kan ställa in vilka klasser som är relevanta för det material som du måste klassificera.

Varje klass tilldelas en materialinställning i materiallistan som hör till förordningen. Du ska tilldela varje frisläppt artikel en klass för att beskriva den farliga karaktären hos en produkt.

Dessa inställningsdata är inte specifika för varje juridisk person. Därför kan du ha en gemensam uppsättning information om farligt material som delas mellan alla dina juridiska personer.

Klasser för farliga material arbetar tillsammans med avdelningar, grupper och samhanteringsgrupp på följande sätt:

- När du tilldelar en klass för farligt material till en frisläppt artikel måste du även tilldela en [avdelning för farligt material](#divisions).
- Du kan använda farliga materialklasser tillsammans med [klassificeringsgrupper för farliga material](#classification-groups) att skapa en mall för koder för inställning av artiklar.
- Du kan använda [samhanteringsgrupp för farliga material](#compatibility-groups) för att fastställa vilka klasser och avdelningar för farligt material som kan skickas tillsammans.

Om du vill ställa in klasser för farliga material går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> klasser för farligt material**. På sidan för **klass för farliga material** kan du skapa ett valfritt antal klasser och konfigurera var och en med hjälp av fälten som beskrivs i följande tabell.

| Fält | beskrivning |
|---|---|
| Klasskod | Ange en kod för att identifiera den här klassen. Du definierar den här koden för artikeln. Den kommer sedan att användas i uppslagslistor när du tilldelar en frisläppt artikelklass för farligt material. |
| beskrivning | Ange en beskrivning av den klassen. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Avdelningar om farliga material

En avdelning för farligt material är en del uppsättning av en klass för farligt material. Du måste tilldela både en avdelning och en klass till varje produkt som innehåller farligt material.

För klasser som inte har några avdelningar skapar du en avdelningar där koden är *0*. I IATA-förordningen har klass 7 radioaktiva material t.ex. inga underavdelningar. I det här fallet ska du skapa en *0* avdelning som du kan koppla till en frisläppt produkt när du tilldelar klassen.

Dessa inställningsdata är inte specifika för varje juridisk person. Därför kan du ha en gemensam uppsättning information om farligt material som delas mellan alla dina juridiska personer.

Avdelningar för farliga material arbetar tillsammans med klasser, grupper och samhanteringsgrupp på följande sätt:

- När du tilldelar en frisläppt artikel för frisläppt, måste du även tilldela en [klass för farligt material](#classes).
- Du kan använda avdelningar för farliga material tillsammans med [klassificeringsgrupper för farliga material](#classification-groups) att skapa en mall för koder för inställning av artiklar.
- Du kan använda [samhanteringsgrupp för farliga material](#compatibility-groups) för att fastställa vilka klasser och avdelningar för farligt material som kan skickas tillsammans.

Om du vill ställa in avdelningar för farliga material går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Avdelningar för farligt material**. På sidan för **Avdelningar för farliga material** kan du skapa ett valfritt antal avdelningar och konfigurera var och en med hjälp av fälten som beskrivs i följande tabell.

| Fält | beskrivning |
|---|---|
| Indelning | Ange en kod som ska användas som referensnummer för avdelningar. |
| beskrivning | Ange en beskrivning av avdelningar. |
| Klass | Slå upp och tilldela klassen som avdelningar hör till. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Samhanteringsgrupp för farligt material

Samhanteringsgrupp för farliga material för att fastställa vilka klasser och avdelningar för farligt material som kan skickas tillsammans. När operatörer skapar laster eller leveranser för distributionslager kan de köra en kompatibilitetskontroll som ger en varning om lasten eller leveransen inkluderar artiklar som inte tillhör samma samhanteringsgrupp.

Dessa inställningsdata är inte specifika för varje juridisk person. Därför kan du ha en gemensam uppsättning information om farligt material som delas mellan alla dina juridiska personer.

Om du vill ställa in samhanteringsgrupper för farliga material går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Samhanteringsgrupp för farliga material**. På sidan för **Samhanteringsgrupp för farliga material** kan du skapa ett valfritt antal samhanteringsgrupper och konfigurera var och en med hjälp av fälten som beskrivs i följande underavsnitt.

### <a name="hazardous-material-compatibility-group-header"></a>Rubrik för samhanteringsgrupp för farligt material

Varje samhanteringsgrupp har en kod och en beskrivning. Följande register beskriver de fält som är tillgängliga i rubriken.

| Fält | beskrivning |
|---|---|
| Kompatibilitetsgrupp | Ange en kod för att identifiera samhanteringsgruppen. |
| beskrivning | Ange en beskrivning av samhanteringsgruppen. |

### <a name="compatibility-group-details"></a>Information om kompatibilitetsgrupp

Varje kompatibilitetsgrupp upprättar en lista över klasser och indelningar av farliga material som kan transporteras tillsammans.

| Fält | beskrivning |
|---|---|
| Klass | Välj en klass för farligt material som är kompatibel med alla andra klasser i gruppen. |
| Indelning | Välj en avdelning för farligt material som tillhör den valda klassen. |

## <a name="hazardous-material-specification-values"></a>Specifikationsvärden för farligt material

Microsoft Dynamics 365 Supply Chain Management tillhandahåller flera typer av specifikationer för farliga material. För varje typ måste du skapa en centraliserad uppsättning med värden för varje relevant fält. Användarna kan sedan välja bland dessa värden när de konfigurerar farliga material definitioner eller frisläppta produkter. Supply Chain Management finns en samling sidor där du kan upprätta värdena. Varje sida är dedicerad till en typ av specifikation. En beskrivning av varje tillgänglig specifikation och information om hur du upprättar tillgängliga värden för den finns i följande underavsnitt.

Ett exempel på specifikation av farligt material är _förvaringskoden_, som anger hur ett visst material kan lagras under transporten. Genom att använda informationen i det här avsnittet skapar du en central samling av koder för förvaring. Den här samlingen visas sedan för användarna i en nedrullningsbar lista när de anger förvaringskod för en frisläppt produkt.

Dessa specifikationsvärden för farligt material är inte specifika för varje juridisk person. därför kan du ha en uppsättning gemensamma värden som delas mellan alla juridiska personer.

Du kommer att använda [materialkoder](#hazmat-codes) för att upprätta gemensamma uppsättningar av inställningar för varje specifikation som gäller för en viss förordning. Du kan sedan tillämpa lämplig kod på varje frisläppt produkt om det behövs. Information om hur du tillämpar en kod för farligt material på en specifik frisläppt produkt, och hur du konfigurerar enskilda inställningar för den produkten för någon specifikation som beskrivs här, finns i [Farligt material i produkter, order, leverans och laster](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Beredskap för farligt material

Specifikationen *beredskapsprogram för farliga material* anger vad som ska göras om något blir fel medan en produkt som innehåller ett visst farligt material transporteras.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Beredskapsprogram för farliga material**. På sidan **Beredskapsprogram för farliga material** kan du skapa ett valfritt antal värden och konfigurera var och en med en klassificeringskod och en kort beskrivning.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Identifiering för farligt material

Specifikationen *identifiering av farligt material* identifierar ett farligt materialsklass eller karaktär. Värdet är vanligtvis en kod som baseras på en FN-standard (FN). Varje klass identifieras med en kod och en beskrivning och den kan också ange gränser för transportmetoder. Om du till exempel vill identifiera ett brandfarligt objekt eller material skapar du en klass för farligt material som använder koden *FL* och beskrivningen *brandfarligt*. Du anger även att klassen inte får transporteras med flyg.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Identifiering av farliga material**. På sidan för **Identifiering för farliga material** kan du skapa ett valfritt antal värden och konfigurera var och en med hjälp av fälten som beskrivs i följande tabell.

| Fält | beskrivning |
|---|---|
| Identifiering | Ange en kod som ska användas som referensnummer som identifierar denna klass av farligt material. |
| beskrivning | Ange en beskrivning av denna klass. |
| Begränsa från flygtransport | Markera den här kryssrutan om du vill ange att denna klass av farligt material inte bör transporteras med flyg. |
| Begränsa från sjötransport | Markera den här kryssrutan om du vill ange att denna klass av farligt material inte bör transporteras till havs. |

### <a name="hazardous-material-label"></a><a name="label"></a>Etikett för farligt material

Specifikationen *Etikett för farligt material* identifierar etiketten för farligt gods som måste användas på relevanta frisläppta produkter. Etiketterna beskriver hur produkten ska hanteras. Du har till exempel en produkt som innehåller en giftig gas. I det här fallet skapar du en etikettkod som representerar den giftiga gasens etikett. Du skapar också affärsprocessen så att den slår upp det här värdet när du levererar produkter.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Etikett för farliga material**. På sidan **Etikett för farliga material** kan du skapa ett valfritt antal etiketter och konfigurera var och en med en identifieringskod och en kort beskrivning.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Förpackningsbeskrivningar för farligt material

Specifikationen *Förpackningsbeskrivningar av farligt material* anger hur en farligt artikel måste packas. Den kan till exempel behöva förpackas i en viss typ av ståltrumma eller någon annan typ av speciell förpackning.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Förpackningsbeskrivningar av farligt material**. På sidan **Förpackningsbeskrivningar av farligt material** kan du skapa ett valfritt antal förpackningsbeskrivningar och konfigurera var och en med en identifieringskod och en kort beskrivning.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Förpackningsgrupp för farligt material

Specifikationen *Förpackningsgrupp för farliga material* identifierar förpackningsgruppen för en farlig artikel. I förpackningsgruppen kan du definiera en kod och en beskrivning som anger hur farliga materialartiklar måste packas under transport eller leverans. Förpackningsgruppen tilldelas artikeln via sidan **artikel för farligt material**.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Förpackningsgrupp för farliga material**. På sidan **Förpackningsgrupp för farligt material** kan du skapa ett valfritt antal förpackningsgrupper och konfigurera var och en med en identifieringskod och en kort beskrivning.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Förpackningsinstruktion för farligt material

Specifikationen *Förpackningsanvisning för farligt material* beskriver de förpackningsanvisningar som måste följas när en viss farlig artikel förbereds för flygtransport.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Förpackningsanvisningar för farligt material**. På sidan **Förpackningsanvisningar av farligt material** kan du skapa ett valfritt antal förpackningsidentifierare och konfigurera var och en med en identifieringskod och en kort beskrivning.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Stuvning av farligt material

Specifikationen *Lagring av farligt material* anger hur en produkt måste lagras på ett fartyg när den transporteras med sjötransport.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Lagring av farliga material**. På sidan **Lagring av farliga material** kan du skapa ett valfritt antal lagringsidentifierare och konfigurera var och en med en identifieringskod och en kort beskrivning.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Transportkategori för farligt material

Specifikationen *transportkategorier för farliga material* används vanligtvis för att gruppera likadana farliga produkter i rapporter. Transportkategorier används t.ex. i rapporten **Leveranssammanfattning** som du kan skriva ut från lagerleveransposten.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Transportkategori för farliga material**. På sidan **Transportkategori för farliga material** kan du skapa ett valfritt antal transportkategori och konfigurera var och en med ett visningsnamn och en kort beskrivning.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Tekniskt namn på farligt material

Specifikationen *Tekniskt namn för farliga material* kan användas för att ge ett vanligt eller internt företagsnamn som beskriver varje material.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Tekniskt namn för farliga material**. På sidan **Tekniskt namn för farliga material** kan du skapa ett valfritt antal tekniska namn och konfigurera var och en med ett visningsnamn och en kort beskrivning.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Tunnel för farligt material

Specifikationen *Tunnel för farligt material* begränsar vilka typer av tunnlar som ett farligt material kan transporteras genom att identifiera vilka typer av tunnlar som måste användas. Tunnelkategorier fastställs i tillämpliga förordningar för transport av farligt material. Denna specifikation gäller vanligtvis endast för vägtransporter.

Om du vill ställa in värden för denna specifikation går du till **Produktinformationshantering \> Konfigurera \> Dokumentation för leverans av farligt material \> Tunnel för farliga material**. På sidan **Tunnel för farliga material** kan du skapa ett valfritt antal tunnelidentifierare och konfigurera var och en med en identifieringskod och en kort beskrivning.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]