---
title: Konfigurera elektroniska meddelanden
description: I detta ämne finns information om hur du konfigurerar in funktioner för elektroniska meddelanden (EM).
author: liza-golub
ms.date: 11/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a9d623c712de34afd1b38dbc6a8738ebf9613d49
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860568"
---
# <a name="set-up-electronic-messages"></a>Konfigurera elektroniska meddelanden

[!include [banner](../includes/banner.md)]

Funktionen **Elektroniska meddelanden** (EM) hjälper dig att underhålla olika processer för elektronisk rapportering för olika typer av dokument. I vissa komplexa scenarier som stöder [landsspecifika rapporteringsfunktioner](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality) konfigureras EM-funktionen på så sätt att den erhåller en kombination av många olika typer av meddelandestatus, status för meddelandeartiklar, ytterligare fält samt körbara klasser. För dessa scenarier finns paket med datatabeller tillgängliga för import. Om du använder dessa paket med datatabeller bör du importera dem till en juridisk person med hjälp av verktyget för datahantering. Mer information om hur du använder verktyget för datahantering finns i [Datahantering](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Om du inte importerar ett paket för datatabeller kan du konfigurera funktionen för elektroniska meddelanden manuellt. I detta fall måste du ställa in följande element:

- [Nummerserier](#sequences)
- [Artikeltyper för meddelande](#types)
- [Status för meddelandeartikel](#item)
- [Meddelandestatus](#statuses)
- [Ytterligare fält](#additional)
- [Körbara klassinställningar](#executable)
- [Fyll i poster, åtgärder](#populate)
- [Fylla i poster från flera företag](#multiple-companies-populate)
- [Webbprogram](#applications)
- [Inställningar för webbtjänst](#settings)
- [Åtgärder för meddelandebearbetning](#actions)
- [Elektronisk meddelandebearbetning](#processing)

Följande avsnitt innehåller mer information om varje element.

## <a name="number-sequences"></a><a id="sequences"></a>Nummerserier

Ställ in nummerserier för både meddelanden och meddelandeartiklar. Nummerserierna används sedan för att automatiskt numrera meddelanden och meddelandeartiklar. De nummer som tilldelas används som unika identifierare för meddelanden och meddelandeartiklar i systemet. Du kan ställa in nummerserier för elektroniska meddelanden på sidan **Redovisning** \> **Redovisningskonfiguration** \> **Allmänna redovisningsparametrar**.

## <a name="message-item-types"></a><a id="types"></a>Artikeltyper för meddelande

Artikeltyper för meddelanden identifierar de typer av poster som används i elektroniska meddelanden. Du kan ställa in artikeltyper för meddelanden genom att gå till sidan **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Artikeltyper för meddelanden**.

## <a name="message-item-statuses"></a><a id="item"></a>Status för meddelandeartikel

Artikelstatus för meddelanden identifierar den status gäller meddelandeartiklar i den bearbetning som du konfigurerar. Du kan ställa in artikelstatusen för meddelanden genom att gå till sidan **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Artikelstatus för meddelanden**.

Parametern **Tillåt borttagning** för en meddelandeartikelstatus anger huruvida du kan ta bort meddelandeartiklar som har denna status på sidan **Elektroniska meddelanden** eller sidan **Elektroniska meddelandeartiklar**.

## <a name="message-statuses"></a><a id="statuses"></a>Meddelandestatus

Ställ in artikelstatus för meddelanden som ska vara tillgänglig i meddelandebearbetning. Du kan ställa in meddelandestatusen genom att gå till sidan **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Meddelandestatus**.

I följande tabell beskrivs fälten på sidan **Meddelandestatusar**.

| Fältnamn          | Beskrivning |
|---------------------|-------------|
| Meddelandestatus      | Ange ett unikt namn för meddelandestatus. Meddelandestatusar används för att beskriva tillståndet i ett elektroniskt meddelande vid varje tidpunkt. Namnet som du anger visas på sidan **elektroniska meddelanden** och i en logg som är relaterad till elektroniska meddelanden. |
| Beskrivning         | Ange en beskrivning av meddelandestatusen. |
| Svarstyp       | Välj svarstyp för meddelandestatusen. Vissa åtgärder i en bearbetning kan ge mer än en svarstyp. En åtgärd av typen **Webbtjänst** kan exempelvis generera svar av antingen typen typen **Har körts** eller **Tekniskt fel** beroende på resultatet av körningen. I det här fallet måste meddelandestatus för båda svarstyper definieras. För mer information om åtgärdstyper och de typer av svar som är relaterade till dessa, se avsnittet [Åtgärdstyper för meddelandebearbetning](#action-types). |
| Status för meddelandeartikel | Status för ett elektroniskt meddelande måste påverka status för relaterad meddelandeartikel. Välj en meddelandeartikelstatus i detta fält för att associera den med meddelandestatus. |
| Tillåt borttagning        | Markera denna kryssruta om användare ska kunna ta bort elektroniska meddelanden som har denna status på sidan **elektroniska meddelanden**. |

## <a name="additional-fields"></a><a id="additional"></a>Ytterligare fält

Med hjälp av EM-funktionen kan du samla in poster från transaktionsregister i Microsoft Dynamics 365 Finance som meddelandeartiklar. På så sätt kan du förbereda posterna för rapportering och sedan rapportera dem. Transaktionsregister har ibland dock inte tillräckligt med information för att fylla i poster på ett sätt som uppfyller rapporteringskraven. Du kan fylla i all information som ska rapporteras för en post genom att ställa in ytterligare fält. Ytterligare fält kan associeras med meddelanden och meddelandeartiklar. Du kan ställa in ytterligare fält genom att gå till sidan **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Ytterligare fält**.

I följande tabell beskrivs i allmänna fälten på sidan **Ytterligare fält**.

| Fält       | beskrivning |
|-------------|-------------|
| Fältnamn  | Ange namnet på ett ytterligare fält för elektroniska meddelanden eller meddelandeartiklar relaterade till processen. Detta namn visas i användargränssnittet när du arbetar med processen. Namnet kan också användas i ER-konfigurationer som är relaterade till processen. |
| beskrivning | Ange en beskrivning av det ytterligare fältet. |
| Användarredigering   | Ange detta alternativ som **Ja** om användare ska kunna ändra värdet för ytterligare fält i användargränssnittet. |
| Räknare     | Ange detta alternativ till **Ja** om det ytterligare fältet ska innehålla en nummersekvens i ett elektroniskt meddelande. Värdet för ytterligare fält fylls i automatiskt när en åtgärd av typen **Export av elektronisk rapportering** körs. |
| Dolt      | Ange detta alternativ som **Ja** om det ytterligare fältet ska döljas i användargränssnittet på sidan **Elektroniska meddelanden** eller på sidan **Elektroniska meddelandeartiklar**. |

På snabbfliken **Värden** kan du fördefiniera värden som ytterligare ett fält kan ha. Därefter blir dessa värden tillgängliga för användarna att välja. Därför behöver de inte fyllas i manuellt under bearbetningen. Följande register beskriver fälten.

| Fält                | beskrivning |
|----------------------|-------------|
| Fältvärde          | Ange fältvärdet som ska användas till ett meddelande eller meddelandeartikel under rapportering. |
| Beskrivning          | Ange en beskrivning av fältvärdet. |
| Kontotyp         | Vissa fältvärden kan begränsas till särskilda kontotyper. Välj ett av följande värden: **Alla**, **Kunden**, eller **Leverantör**. |
| Kontokod         | Om du har valt **Kund** eller **Leverantör** i fältet **Kontotyp** kan du begränsa användningen av fältvärdet ytterligare till en viss grupp eller tabell. |
| Konto-/gruppnummer | Om du har valt **Kund** eller **Leverantör** i fältet **Kontotyp** och om du anger en grupp eller en tabell i fältet **Kontokod** kan du ange en viss grupp eller utländskt ombud i det här fältet. |
| Giltighet            | Ange datum då värdet bör börja övervägas. |
| Utgång           | Ange datum då värdet bör sluta övervägas. |

Som standard definieras kombinationer av villkor av fälten **Konto-/ gruppnummer**, **Kontokod**, **Giltighet** och **Utgång** påverkar inte valet av värdena för ytterligare fält. Men dessa kombinationer kan användas i en körbar klass för att genomföra särskild affärslogik som beräknar värden för ytterligare fält.

## <a name="executable-class-settings"></a><a id="executable"></a>Körbara klassinställningar

En körbar klass är en X++-metod eller klass som bearbetning av elektroniska meddelanden kan anropa i relation till en åtgärd om viss utvärdering krävs för processen.

Du kan manuellt ställa in en körbar klass som måste anropas under bearbetningen genom att gå till inställningarna för **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Inställningar för körbar klass**. Skapa en rad på sidan **Inställningar för körbar klass** och ställ in följande fält:

| Fält                 | beskrivning |
|-----------------------|-------------|
| Körbar klass      | Ange namnet som ska användas vid installationen av en åtgärd för meddelandebearbetning som denna klass anropas i relation till. |
| beskrivning           | Ange en beskrivning av den körbara klassen. |
| Körbart klassnamn | Välj en X++ körbar klass. |
| Körningsnivå       | Detta fältet anges automatiskt eftersom värdet fördefinieras för den markerade körbara klassen. Detta fält begränsar nivån som den relaterade utvärderingen körs på. |
| Klassbeskrivning     | Detta fältet anges automatiskt eftersom värdet fördefinieras för den markerade körbara klassen. |
| Åtgärdstyp           | Detta fält är tillgängligt när funktionen **\[EM\] Körbar klassåtgärdstyp** aktiveras i arbetsytan för **Funktionshantering**. Använd det här fältet om du vill ange åtgärdstypen för den körbara klassen. Det här fältet ger en mer exakt kontroll över nästa åtgärder som är tillgängliga för det elektroniska meddelandet på sidan **Elektroniska meddelanden**. |

Vissa körbara klasser kan ha obligatoriska parametrar som måste anges innan den körbara klassen körs för första gången. Du definierar dessa parametrar genom att välja **Parametrar** i åtgärdsfönstret. I dialogrutan som visas anger fälten och väljer sedan **OK**. Det är viktigt att du väljer **OK**. Annars sparas inte parametrarna i databasen och den körbara klassen anropas inte korrekt.

## <a name="populate-records-actions"></a><a id="populate"></a>Fyll i poster, åtgärder

Du använder åtgärder för ifyllda poster för att konfigurera åtgärder som lägger till poster i artikelregistret för meddelanden, detta så att dessa kan läggas till i ett elektroniskt meddelande. Till exempel om elektroniska meddelandet måste rapportera kundfakturor, måste du ställa in åtgärden Fylla i poster som kopplas fältet **Datakälla** i registret Kundfakturajournal.

Du kan ange åtgärder för att fylla i poster genom att gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Åtgärder för ifyllande av poster**. Skapa en ny post för varje åtgärd som ska lägga till poster i tabellen och ange följande fält.

| Fält       | Beskrivning |
|-------------|-------------|
| Namn        | Ange ett namn för åtgärden som fyller i poster i din process. |
| Beskrivning | Ange en beskrivning av åtgärden Fyll i poster. |

På snabbfliken **Inställningar för datakällor**, lägg till en rad för varje datakälla som används för processen och ange följande fält.

| Fält                  | beskrivning |
|------------------------|-------------|
| Namn                   | Ange namnet på datakällan. |
| Meddelandets artikeltyp      | Välj den typ av meddelandeartikel som ska användas när poster skapas för datakällan. |
| Kontotyp           | Välj den typ av konto som ska associeras med poster från datakällan. |
| Namn på huvudregister      | Välj den tabell som ska vara en datakälla. |
| Dokumentnummerfält  | Markera det fält som dokumentnumret ska tas från i den valda huvudtabellen. Värdet i det här fältet används som värde i fältet **Dokumentnummer** för meddelandeartikeln. |
| Dokumentdatumfält    | Markera det fält som dokumentdatumet ska tas från i den valda huvudtabellen. Värdet i det här fältet används som värde i fältet **Datum för meddelandeartikel** för meddelandeartikeln. |
| Dokumentkontofält | Markera det fält som dokumentkontot ska tas från i den valda huvudtabellen. Värdet i det här fältet används som värde i fältet **Kontonummer** för meddelandeartikeln. |
| Företag                | Detta fält blir tillgängligt när funktionen **Frågor mellan företag för åtgärder för ifyllande av poster** aktiveras i arbetsytan **Funktionshantering**. Använd den här funktionen när du vill ställa in datakällor mellan företag för åtgärder för postifyllande. Data kan hämtas från flera olika företag. |
| Användarfråga             | <p>Om du ställer in en sökning genom att välja **Redigera sökning** ovanför rutnätet och du anger de kriterier som måste tillämpas på den valda huvudtabell som data fylls i ifrån, markeras denna kryssruta automatiskt. I annat fall fylls alla poster i från den valda huvudtabellkällan.</p><p>När funktionen **Frågor mellan företag för åtgärder för postifyllnad** har aktiverats i arbetsytan **Funktionshantering** och poster måste samlas in från flera olika företag, lägger du till en rad för varje ytterligare juridisk person som måste inkluderas i rapporteringen. För varje ny rad väljer du **Redigera sökning** och anger sedan ett relaterat kriterium som är specifikt för den juridiska personen som angetts i fältet **Företag** på raden. När du är klar innehåller rutnätet **Konfiguration av datakällor** rader för alla juridiska personer som måste inkluderas i rapporten.</p> |

## <a name="populate-records-from-multiple-companies"></a><a id="multiple-companies-populate"></a>Fylla i poster från flera företag

Om ditt företag måste rapportera från flera juridiska personer i samma Finance-databas ställer du in [ifyllda poståtgärder](#populate) för alla juridiska personer som data måste inkluderas från i rapporteringen.

Följ dessa steg för att aktivera denna funktion i din Finance-miljö. 

1. Gå till **Arbetsytor** \> **Funktionshantering**.
2. Sök efter och välj funktionen **Frågor mellan företag för åtgärd för postifyllande** i listan.
3. Välj **Aktivera nu**. 

Om du vill ställa [åtgärder för ifyllande av poster](#populate) för flera företag som data måste inkluderas i rapporteringen från följer du dessa steg.

1. Gå till **Moms** \> **Inställningar** \> **Elektroniska meddelanden** \> **Fyll i poståtgärder**.

    När funktionen **Frågor mellan företag för åtgärd för postifyllande** är aktiverad, rutnätet **Konfiguration av datakällor** på sidan **Fyll i poster, åtgärd** inkluderar fältet **företag**. För befintliga poster som skapades under de allmänna inställningarna för [åtgärderna för ifyllda poster](#populate) visar det här fältet identifieraren för den aktuella juridiska personen.

2. I rutnätet **Konfiguration för datakällor** lägger du till en rad för varje dotterbolag som juridisk person som måste inkluderas i rapporten .

    | Fältnamn             | Värde |
    |------------------------|-------|
    | Namn                   | Ange ett textvärde som hjälper dig att förstå varifrån den här posten kommer. För exempel, ange **Datakällans namn - dotterbolag 1**. |
    | Meddelandets artikeltyp      | Välj den meddelandeartikeltyp som krävs för din EM-bearbetning. |
    | Kontotyp           | Ange kontotyp som krävs för din EM-bearbetning. Om din EM-bearbetning inte har några specifika kontotyper väljer du **Alla**. |
    | Namn på huvudregister      | Ange namnet på huvudregistret som krävs för din EM-bearbetning. |
    | Dokumentnummerfält  | Ange fältet som innehåller dokumentnumret i posterna för din EM-bearbetning. |
    | Dokumentdatumfält    | Ange fältet som innehåller dokumentdatum i posterna för din EM-bearbetning. |
    | Dokumentkontofält | Ange fältet som innehåller dokumentkonto i posterna för din EM-bearbetning. |
    | Företag                | Välj ID för dotterbolag för juridiska personen. |
    | Användarfråga             | Kryssrutan väljs automatiskt när du definierar kriterier genom att välja **Redigera fråga**. |

3. För varje ny rad väljer du **Redigera sökning** och anger sedan en kriterier för den juridiska person som angetts i fältet **Företag** på raden.

## <a name="web-applications"></a><a id="applications"></a>Webbprogram

Använd inställningar för webbprogram för att ställa in ett webbprogram så att detta stöder öppen auktorisering (OAuth) 2.0. OAuth är en öppen standard som ger användarna ”säker delegerad åtkomst” till programmet för deras räkning, utan att dela sina autentiseringsuppgifter. Du kan också gå igenom auktoriseringsprocessen genom att få en auktoriseringsskod och åtkomsttoken. Du kan konfigurera inställningar för webbappar genom att gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Webbappar**.

I följande tabell beskrivs fälten på sidan **Webbprogram**.

| Fält                        | Beskrivning |
|------------------------------|-------------|
| Programnamn             | Skriv ett namn på webbprogrammet. |
| Beskrivning                  | Ange en beskrivning för webbprogrammet. |
| Bas-URL                     | Ange basinternetadressen till webbprogrammet. |
| URL-sökväg för auktorisering       | Ange sökvägen om används för att skapa URL för auktorisering. |
| URL-sökväg för token               | Ange sökvägen om används för att skapa URL för token. |
| Omdirigerings-URL                 | Ange omdirigerings-URL |
| Klient-ID                    | Ange klient-ID för webbprogrammet. |
| Klienthemlighet                | Ange klienthemlighet för webbprogrammet. |
| Servertoken                 | Ange servertoken för webbprogrammet. |
| Mappning av auktoriseringsformat | Välj ER-format som används för att generera en begäran om godkännande. |
| Modellmappning för importtoken   | Välj en modellmappning för ER-import som används för att lagra åtkomsttoken. |
| Beviljat område                | Omfattningen beviljas för begäran till programmet. Det här fältet uppdateras automatiskt. |
| Åtkomsttoken upphör att gälla om  | Återstående tid innan åtkomsttoken upphör att gälla. Det här fältet uppdateras automatiskt. | 
| Godkänn                       | Ange egenskap för **godkännande** av webbegäran. ange t-ex **application/vnd.hmrc.1.0+json**. |
| Innehållstyp                 | Ange innehållstyp. Ange t.ex. **application/json**. |

Dessutom är följande knappar tillgängliga i åtgärdsfönstret för sidan **webbprogram** för att ge stöd till auktoriseringsprocessen:

- **Hämta auktoriseringskod** – initiera auktorisering av webbprogrammet. Den här funktionen använder det ER-format som anges i fältet **Mappning av auktoriseringsformat** i syfte att generera en auktoriseringsbegäran.
- **Hämta ett åtkomsttoken** – initiera processen för att hämta ett åtkomsttoken.
- **Uppdatera åtkomsttoken** – uppdatera ett åtkomsttoken. Denna funktion använder det ER-format som anges i fältet **Importera mappning av tokenmodell** om du vill importera information om mottagen åtkomsttoken.

När ett åtkomsttoken till ett webbprogram som lagras i systemets databas är i krypterat format kan det användas för begäran till en webbtjänst. I säkerhetssyfte måste åtkomsten till åtkomsttoken begränsas till de säkerhetsroller som får hantera dessa begäranden. Om någon utanför säkerhetsgruppen försöker hantera en begäran får de ett felmeddelande som anger att de inte är behöriga att interagera via det valda webbprogrammet. Om du vill konfigurera vilka säkerhetsroller som har tillgång till åtkomsttoken använd er du snabbfliken **Säkerhetsroller** på sidan **Webbprogram**. Om säkerhetsroller inte definieras för ett webbprogram kan endast en systemadministratör interagera via webbprogrammet.

För varje åtgärd med det valda webbprogrammet sparar snabbfliken **Åtgärdslogg** information om användaren samt datum och tid.

Vissa webbtjänster kanske kräver att olika rubriker ingår i begärandena. Systemadministratören kan ställa in ytterligare sidhuvuden och dessas värden på snabbfliken **Fyllnadssidhuvuden** och sedan använda dessa under generering av förfrågningar.

## <a name="web-service-settings"></a><a id="settings"></a>Inställningar för webbtjänst

Använd inställningar för webbtjänst för att konfigurera dataöverföring direkt till en webbtjänst. Du kan konfigurera inställningar för webbtjänster genom att gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Inställningar för webbtjänst**.

I följande tabell beskrivs fälten på sidan **Inställningar för webbtjänst**.

| Fält                          | beskrivning |
|--------------------------------|-------------|
| Webbtjänst                    | Skriv ett namn på webbtjänsten. |
| beskrivning                    | Ange en beskrivning för webbtjänsten. |
| Internet-adress               | <p>Ange internetadressen till webbtjänsten. Om ett webbprogram anges för webbtjänsten, och om internetadressen för webbtjänsten är densamma som internetadressen som definierats för det webbprogrammet, väljer du **Kopiera bas-URL**. Bas-URL:en för webbprogrammet kopieras sedan till det här fältet.</p><p>**Varning:** Tjänster från tredje part eller andra tjänster som du konfigurerar här kräver ingen certifiering och kanske inte uppfyller Microsofts sekretesstandarder. Du bör granska varje tjänsts sekretessdokumentation och arbeta tillsammans med respektive serviceleverantör för att ta reda på vilken nivå av regelefterlevnad som respektive tjänst tillhandahåller. Du ansvarar för att dessa tjänster uppfyller dina säkerhets-, integritets- och juridiska standarder. Du bär själv ansvaret för allt användande av tjänsterna. Microsoft gör inga uttryckliga utfästelser om garantier eller villkor. Vi rekommenderar starkt att du bara använder tjänster som tillhandahåller säkra och auktoriserade anslutningar, till exempel HTTPS.</p> |
| Certifikat                    | Välj ett Azure Key Vault-certifikat som tidigare har konfigurerats. |
| Webbprogram                | Välj en webapp som tidigare har konfigurerats. |
| Svarstyp – XML        | Ange det här alternativet till **Ja** om svarstypen är XML. |
| Metod för begäran                 | Ange vilken metod för begäran. HTTP definierar en uppsättning metodbegäran som anger vilken åtgärd som ska utföras av en viss resurs. Den begärda metoden kan vara **HÄMTA**, **BOKFÖR**, eller någon annan HTTP-metod. |
| Rubrik för begäran                | Ange rubrik för begäran. Ett begärandesidhuvud är ett HTTP-sidhuvud som kan användas i en HTTP-begäran. Det är inte relaterat till meddelandets innehåll. |
| Godkänn                         | Ange godkännandeegenskap för webbegäran. |
| Godkänn kodning                | Ange värdet för Godkänn kodning. HTTP-huvudet för begäran att acceptera-kodning meddelar innehålllskodning som klienten kan förstå. Den här innehållskodningen är vanligtvis en komprimeringsalgoritm. |
| Innehållstyp                   | Ange innehållstyp. Entitets-HTTP-rubriken innehållstyp anger medietypen för resursen. |
| Svarskod för genomförd åtgärd       | Ange den HTTP-statuskod som indikerar att begäran beviljades. |
| Formatmappning av rubrik för begäran | Välj ER-format som används för att generera rubriker för webbegäran. |

## <a name="message-processing-actions"></a><a id="actions"></a>Åtgärder för meddelandebearbetning

Du använder åtgärder för meddelandebearbetning om du vill skapa åtgärder för dina processer och ställa in parametrarna. Du kan konfigurera åtgärder för meddelandebearbetning genom att gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Åtgärder för meddelandebearbetning**.

I följande tabell beskrivs fälten på sidan **Åtgärder för meddelandebearbetning**.

### <a name="general-fasttab"></a>Snabbfliken Allmänt

| Fält                                     | beskrivning |
|-------------------------------------------|-------------|
| Åtgärdstyp                               | Välj typ av åtgärd Mer information om alternativen finns i [Åtgärdstyper för meddelandebearbetning](#action-types) längre fram i detta ämne. |
| Mappning av format                            | Välj ER-format som ska anropas för åtgärden. Det här fältet är endast tillgängligt för åtgärder av typerna **Export av elektronisk rapportering**, **Import av elektronisk rapportering** och **Meddelande om export av elektronisk rapportering**. |
| Formatmappning för URL-sökväg               | Välj ER-format som ska anropas för åtgärden. Detta format används för att skriva sökvägen till den URL-adress som ska läggas till i den grundläggande internetadress som har angetts för den markerade webbservern. Det här fältet är endast tillgängligt för åtgärder av typen **Webbtjänst**. |
| Meddelandets artikeltyp                         | Välj typ av poster som åtgärden ska utvärderas för. Detta fält är endast tillgängligt för åtgärder av typerna **Körningsnivå för meddelandeartikel**, **Export av elektronisk rapportering**, **Import av elektronisk rapportering** samt **Webbtjänst**, och även andra typer. Om du lämnar fältet tomt beräknas alla meddelandeobjekttyper som har definierats för meddelandebehandling. |
| Körbar klass                          | Välj en befintlig körbar klassinställning. Det här fältet är bara tillgängligt för åtgärder av typerna **Körningsnivå för meddelandeartikel** och **Körningsnivå för meddelandeartikel**. |
| Fyll i poster, åtgärd                   | Välj en befintlig åtgärd för postifyllande. Det här fältet är endast tillgängligt för åtgärder av typen **fylla i poster**. |
| Webbtjänst                               | Välj en befintlig webbtjänst. Det här fältet är endast tillgängligt för åtgärder av typen **Webbtjänst**. |
| Filnamn att skicka                         | Ange namnet på bilagan till ett elektroniskt meddelande som måste skickas med den här åtgärden. Om flera bilagor har samma ursprungliga filnamn skickas den senaste. Om det inte finns någon bilaga med det angivna ursprungliga filnamnet skickas begäran utan innehåll. Det här fältet är endast tillgängligt för åtgärder av typen **Webbtjänst**. |
| Filnamn                                 | Ange namnet på den fil som blir resultatet av åtgärden. Den här filen kan vara svaret från webbservern eller den rapport som genereras. Det här fältet är endast tillgängligt för åtgärder av typerna **webbtjänst** och **meddelande om export av elektronisk rapportering**. |
| Bifoga filer till källdokument          | Markera den här kryssrutan om du vill koppla genererade filer till poster i ett refererat huvudregister för EM-artiklar. Det här fältet är endast tillgängligt för åtgärder av typerna **Elektronisk rapporteringsexport** och **Webbtjänst**. |
| Bifoga filer från utdataarkiv till artiklar | Markera den här kryssrutan om du vill ta fram separata XML-filer från utdataarkivfilen och koppla dessa till motsvarande objekt i det elektroniska meddelandet. Detta fält är endast tillgängligt för åtgärder av typen **Meddelande om export av elektronisk rapportering**. |
| Antal meddelandeartiklar per export        | Ange gränsen för antalet meddelandeartiklar som måste inkluderas i en fil (meddelande). Detta fält är endast tillgängligt för åtgärder av typen **Meddelande om export av elektronisk rapportering**. |
| Använd ER-källa                             | Markera den här kryssrutan om du vill använda ER-källparametrar för import. I annat fall används bilagan från det elektroniska meddelandet. Detta fält är endast tillgängligt för åtgärder av typen **Meddelande om import av elektronisk rapportering**. |
| Visa dialogruta                               | Ange det här alternativet som **Ja** om en dialogruta måste visas för användare innan rapporten genereras. Det här fältet är endast tillgängligt för åtgärder av typen **meddelande om export av elektronisk rapportering**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Åtgärdstyper för meddelandebearbetning

Följande alternativ finns tillgängliga **Åtgärdstyp**:

- **Skapa meddelande** – Använd denna åtgärdstyp för att låta användarna manuellt skapa meddelanden på sidan **elektroniskt meddelande**. En inledande status kan inte ställas in för en åtgärd av den här typen.
- **Fyll i poster** – Åtgärdstypen måste redan ha konfigurerats. För att göra det möjligt för åtgärden att inkluderas i bearbetning associerar du den med en åtgärd för postifyllnad. Det antas att denna åtgärdstyp används för den första åtgärden i meddelandebearbetningen (när inget elektroniskt meddelande skapas i förväg) eller för en åtgärd som lägger till meddelandeartiklar i ett meddelande som skapats tidigare av åtgärdstypen **Skapa ett meddelande**. För åtgärder av den här typen kan resultatstatus endast ställas in för meddelandeartiklar. En inledande status kan inte anges endast för meddelanden.
- **Körningsnivå för meddelandeartikel** – Använd den här åtgärdstypen om du vill ställa in en körbar klass som ska utvärderas på meddelandeartikelnivå visas.
- **Körningsnivå för meddelande** – Använd den här åtgärdstypen om du vill ställa in en körbar klass som ska utvärderas på nivån visas.
- **Export av elektronisk rapportering** – Använd denna åtgärdstyp för åtgärder som ska generera en rapport baserad på en ER-konfiguration på meddelandeartikelnivå.
- **Meddelande om export av elektronisk rapportering** – Använd den här åtgärdstypen för åtgärder som ska generera en rapport baserad på en ER-konfiguration på meddelandeartikelnivå (till exempel när ett meddelande inte har några meddelandeartiklar).
- **Import av elektronisk rapportering** – Använd den här åtgärdstypen för åtgärder som ska generera en rapport baserad på import av en ER-konfiguration.
- **Användares bearbetning på meddelandenivå** – Använd den här åtgärdstypen för åtgärder som antar någon manuell åtgärd av användaren på meddelandennivån. Användaren kan till exempel uppdatera status för meddelanden.
- **Användarbearbetning** – Använd den här åtgärdstypen för åtgärder som antar någon manuell åtgärd av användaren på meddelandeartikelnivån. Användaren kan till exempel uppdatera status för meddelandeartiklar.
- **Webbtjänst** – Använd den här åtgärdstypen för åtgärder som ska överföra en genererad rapport till en webbtjänst. Den här åtgärdstypen används inte för italienska kommunikationsrapporter för inköps och försäljningsfakturor. För denna åtgärdstyp inkluderar sidan **Åtgärder för meddelandebearbetning** snabbfliken **Diverse detaljer** där du kan ange en bekräftelsetext. Denna bekräftelsetext visas för användare innan begäranden skickas till vald webbtjänst.
- **Begära verifiering** – Använd den här åtgärdstypen till begäran av verifiering från en server.

### <a name="initial-statuses-fasttab"></a>Snabbfliken Ursprunglig status

> [!NOTE]
> Snabbfliken **inledande status** är inte tillgänglig för åtgärder som har en inledande åtgärdstyp av **Skapa ett meddelande**.

| Fält               | Beskrivning |
|---------------------|-------------|
| Status för meddelandeartikel | Välj meddelandeartikelstatus som den vald meddelandebearbetningsåtgärden ska utvärderas för. |
| beskrivning         | En beskrivning av den valda meddelandeartikelstatusen. |

### <a name="result-statuses-fasttab"></a>Snabbfliken Status för resultat

| Fält               | beskrivning |
|---------------------|-------------|
| Meddelandestatus      | Välj meddelandestatus som den vald meddelandebearbetningsåtgärden ska utvärderas för. Det här fältet är endast tillgängligt för åtgärder för meddelandebearbetning som utvärderas på meddelandenivå. Är till exempel tillgänglig för åtgärder av typen **Export av elektronisk rapportering** och **Import av elektronisk rapportering**, men är inte tillgänglig efter åtgärder av typen **Användarbearbetning** och **Körningsnivå för meddelandeartikel**. |
| beskrivning         | En beskrivning av den valda meddelandestatusen. |
| Svarstyp       | Svarstyp för den valda meddelandestatusen. |
| Status för meddelandeartikel | Välj resulterande status som ska vara tillgänglig efter att meddelandebearbetningsåtgärden utvärderas. Det här fältet är endast tillgängligt för åtgärder för meddelandebearbetning som utvärderas på meddelandeartikelnivå. Den är till exempel tillgänglig för åtgärder av typen **Användarbearbetning** och **Körningsnivå för meddelandeartikel**. För meddelandebearbetningsåtgärder som utvärderas på meddelandenivån visar det här fältet statusen för meddelandetypen som ställdes in för den valda meddelandestatusen. |

Följande register visar resultatstatus som måste ställas in för olika åtgärdstyper och svarstyper.

| Elektroniskt meddelande åtgärdstyp/svarstyp | Har utförts | Verksamhetsfel | Tekniskt fel | Användardefinierat | Avbryt |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Skapa ett meddelande                               | X                     |                |                 |              |        |
| Export av elektronisk rapportering                  | X                     |                |                 |              |        |
| Import av elektronisk rapportering                  |                       |                |                 |              |        |
| Webbtjänst                                  | X                     |                | X               |              |        |
| Användarbearbetning                              |                       |                |                 |              |        |
| Körningsnivå för meddelande                      |                       |                |                 |              |        |
| Fyll i poster                             |                       |                |                 |              |        |
| Körningsnivå för meddelandeartikel                 |                       |                |                 |              |        |
| Verifiering av begäran                         | X                     | X              | X               |              |        |
| Meddelande om export av elektronisk rapportering          | X                     |                |                 |              |        |
| Användares bearbetning på meddelandenivå                |                       |                |                 |              |        |

## <a name="electronic-message-processing"></a><a id="processing"></a>Elektronisk meddelandebearbetning

Elektronisk meddelandebearbetning är ett grundläggande begrepp för EM-funktionen. Den sammanställer åtgärder som ska utvärderas för det elektroniska meddelandet. Åtgärderna kan länkas med hjälp av en inledande status och en resulterande status. Alternativt kan åtgärder av typen **Användarbearbetning** startas oberoende av varandra. Om du vill konfigurera bearbetning av elektroniska meddelanden går du till **Skatt** \> **Konfiguration** \> **Bearbetning av elektroniska meddelanden** \> **Bearbetning av elektroniska meddelanden**.

Snabbfliken **Åtgärd** låter dig lägga till fördefinierade åtgärder till bearbetningen. Du kan ange om en åtgärd måste köras separat, eller om den kan startas av bearbetningen. Om vill ange att en åtgärd i bearbetningen endast kan initieras av en användare anger du **kör separat** till **Ja** för åtgärden. Om en åtgärd bör startas av behandlingen för meddelanden eller meddelandeposter som är i status som definieras som den ursprungliga statusen för åtgärden, ställer du in **Kör separat** till **Nej**. Åtgärder av typen **Användaråtgärd** måste alltid köras separat.

Ibland måste flera åtgärder samlas i en sekvens, trots att den första åtgärden har ställts in att köras separat. En användare måste till exempel initiera genereringen av rapporter. Omedelbart efter det att rapporten har genererats måste den emellertid skickas till en webbtjänst, och svaret från webbtjänsten måste återspeglas i systemet. I detta fall kan du skapa en oskiljaktig sekvens för de åtgärder som alltid måste köras tillsammans. På snabbfliken **åtgärd**, välj **Oskiljaktig sekvenser** ovanför rutnätet och skapa en sekvens. För alla åtgärder som därefter måste köras tillsammans i en och samma sekvens väljer du fältet **Oskiljaktig sekvens**. För detta exempel kan fältet **Kör separat** ställas in som **Ja** för den första åtgärden i sekvensen och **Nej** för alla andra åtgärder.

Åtgärder av typen **Export av elektronisk rapportering** och **Exportmeddelanden för elektronisk rapportering** kör ett ER-format med indataparametrar. Om den elektroniska meddelandebearbetningen omfattar åtgärder av någon av dessa typer måste du ange värdena för indataparametrarna innan du genererar rapporter. På det här sättet kan systemet använda en batchordning för att generera rapporten. Du kan välja **Parametrar** ovanför rutnätet för att konfigurera parametrarna för vald åtgärdstyp (**Export av elektronisk rapportering** eller **Exportmeddelande för elektronisk rapportering**). Markera kryssrutan **Använd parametrar** för den åtgärd som måste köras med de angivna parametrarna i ett batch-schema.

Använd snabbfliken **Ytterligare fält för meddelandeartikel** för att lägga till fördefinierade ytterligare fält som är relaterade till meddelandeartikeln. Du måste lägga till ytterligare fält för varje typ av meddelandeobjekt som hör till fälten. Du kan ange ett standardvärde som tilldelas ytterligare fält under bearbetningen.

Använd snabbfliken **Ytterligare fält för meddelanden** för att lägga till fördefinierade ytterligare fält som är relaterade till meddelanden. Du kan ange ett standardvärde som tilldelas ytterligare fält under bearbetningen.

Använd snabbfliken **Säkerhetsroller** för att konfigurera de säkerhetsroller som fördefinierats i systemet för viss bearbetning. Användare som har en viss roll ser endast den bearbetning som har definierats för rollen.

Använd snabbfliken **Batch** för att ställa in bearbetning att arbeta i ett system för batchordning. Vi rekommenderar att du ställer in en batch- eller bearbetningstid direkt på sidan **Elektroniska meddelanden** eller **Artiklar i elektroniska meddelanden** när du väljer **Kör bearbetning** i åtgärdsfönstret i syfte att inleda bearbetningen.
