---
title: Elektroniska meddelanden
description: "Det här avsnittet innehåller översikt och inställningsinformation för elektroniska meddelanden i Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: 232398a6c4193d0074881e26fff361deb9784bf2
ms.openlocfilehash: 082ad886f40a52457900523f44158da3ed939458
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="electronic-messaging"></a>Elektroniska meddelanden

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller översikt och inställningsinformation för elektroniska meddelanden i Microsoft Dynamics 365 for Finance and Operations.

Myndigheter och rättsliga myndigheter i olika länder och regioner i världen har nyligen implementerat rapporteringskraven för företag som är registrerade i dessa länder eller regioner. Syftet med kraven är att tillåta hämta data från dessa företag i elektroniskt format direkt från systemen där den bokfördes, lagrades och bearbetades.

Funktionen för elektroniska meddelanden i Finance and Operations stöder olika processer för elektroniska driftskompatibilitet mellan Finance and Operations och de system som myndigheter och rättsliga myndigheter för rapportering, avsändning och mottagning av officiell information.

Funktionen för elektroniska meddelanden ingår i modulen **elektronisk rapportering** (ER). Därför kan du ställa in ER-format för elektroniska meddelanden. Mer information finns i [Elektronisk rapportering (ER)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

Elektroniska meddelanden utifrån följande enheter:

- **Elektroniskt meddelande** – en rapport eller deklaration som ska rapporteras och/eller överföras internt. Ett exempel är en rapport som skickas till ett skattekontor.
- **Elektroniska meddelandeartiklar** - poster som ska tas med i meddelandet som rapporteras.
- **Elektronisk meddelandebehandling** – en åtgärdskedja, antingen länkad eller ej länkad, som bör köras för att samla in nödvändiga uppgifter, generera rapporter, lagra data i Microsoft Azure Blob-lagring, överföra rapporter från utanför systemet, få svar från utanför systemet och uppdatera databasen baserat på den information som tas emot.

Följande illustration visar flödet av data för elektroniska meddelanden.

![Dataflöde i elektroniska meddelanden](media/electronic-messaging-data-flow.png)

Funktionen för elektroniska meddelanden stöder följande scenarier:

- Manuellt skapa meddelanden och generera rapporter utifrån associerade ER-exportformat för olika typer: Microsoft Excel XML, JavaScript Object Notation (JSON), PDF, text och Microsoft Word.
- Automatiskt skapa och bearbeta meddelanden som baseras på information som har begärs och erhållits från en myndighet via ett associerat ER-importformat.
- Samla in och bearbeta information från en datakälla (Finance and Operations-tabell) som meddelandeartiklar.
- Lagra ytterligare information och utvärdera olika värden genom att uttryckligen anropa definierade körbara klasser i förhållande till meddelanden eller meddelandeartiklar.
- Sätta samman information som samlas in i en meddelandeartikel, dela upp den informationen per meddelande och generera rapporter med tillhörande ER-exportformat.
- Skicka rapporter som genererats till en webbtjänst med hjälp av säkerhetsinformation som lagras i Azure Key Vault.
- Få ett svar från en webbtjänst, tolka svaret och uppdatera data i Finance and Operations enligt önskemål.
- Spara och granska alla rapporter som skapas.
- Spara och granska all logginformation som är relaterad till åtgärder som körs för ett meddelande eller en meddelandeartikel.
- Kontrollera bearbetning genom olika meddelandestatus och status för meddelandeartikel.

## <a name="set-up-electronic-messaging"></a>Ställa in elektroniska meddelanden

Elektroniska meddelanden kan hjälpa dig att underhålla olika processer för elektronisk rapportering för olika typer av dokument. I vissa komplexa scenarier ställs elektroniska meddelanden in med en kombination av många meddelandestatus, status för meddelandeartiklar, åtgärder. extra, fält och körbara klasser. För dessa scenarier finns paket med datatabeller tillgängliga för import. Om du använder dessa paket med datatabeller bör du importera dem till en juridisk person med hjälp av verktyget för datahantering. Mer information om hur du använder verktyget för datahantering finns i [Datahantering](../../dev-itpro/data-entities/data-entities-data-packages.md).

Om du inte importerar ett paket för datatabeller kan du manuellt ställa in funktionen för elektroniska meddelanden. I detta fall måste du ställa in följande element: 

- [Nummerserier](#number-sequences)
- [Artikeltyper och status för meddelande](#message-item-types-and-statuses)
- [Meddelandestatus](#message-statuses)
- [Ytterligare fält](#additional-fields)
- [Körbara klassinställningar](#executable-class-settings)
- [Fyll i poster, åtgärder](#populate-records-actions)
- [Inställningar för webbtjänst](#web-service-settings)
- [Åtgärder för meddelandebearbetning](#message-processing-actions)
- [Elektronisk meddelandebearbetning](#electronic-message-processing)

Följande avsnitt innehåller mer information om varje element.

### <a name="number-sequences"></a>Nummerserier

Ställ in nummerserier för både meddelanden och meddelandeartiklar. Nummerserierna används för att automatiskt numrera meddelandena och meddelandeartiklarna och de nummer som tilldelas används som unika identifierare för meddelanden och meddelandeartiklar i systemet. Du kan ställa in nummerserier för elektroniska meddelanden på sidan **Redovisningsparametrar** (**Redovisning** \> **Redovisningsinställningar** \> **Redovisningsparametrar**).

### <a name="message-item-types-and-statuses"></a>Artikeltyper och status för meddelande

Artikeltyper för meddelanden identifierar de typer av poster som kommer att användas i elektroniska meddelanden. Du kan ställa in artikeltyper för meddelanden på sidan **Artikeltyper för meddelanden** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Artikeltyper för meddelanden**).

Artikelstatus för meddelanden identifierar den status som ska tillämpas på meddelandeartiklar i bearbetningen som du konfigurerar. Du kan ställa in artikeltyper för meddelanden på sidan **Artikelstatus för meddelanden** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Artikelstatus för meddelanden**).

### <a name="message-statuses"></a>Meddelandestatus

Ställ in artikelstatus för meddelanden som ska vara tillgänglig i meddelandebearbetning. Du kan ställa in meddelandestatus på sidan **Artikelstatus för meddelanden** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Meddelandestatus**).

### <a name="additional-fields"></a>Ytterligare fält

Funktionen för elektroniska meddelanden låter dig fylla i poster från en transaktionell tabell. På så sätt kan du förbereda posterna för rapportering och sedan rapportera dem. Ibland finns det inte tillräckligt med information i den transaktionella tabellen för att rapportera en post enligt rapportkraven. Du kan fylla i all information som ska rapporteras för en post genom att ställa in ytterligare fält. Ytterligare fält kan associeras med både meddelanden och meddelandeartiklar. Du kan ställa in ytterligare fält på sidan **Ytterligare fält** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Ytterligare fält**).

I följande tabell beskrivs fälten på sidan **Ytterligare fält**.

| Fält                | beskrivning |
|----------------------|-------------|
| Fältnamn           | Ange namnet på ett ytterligare attribut med meddelandeartiklar som är relaterade till processen. Detta namn visas i användargränssnittet när du arbetar med processen. Den kan också användas i ER-konfigurationer som är relaterade till processen. |
| beskrivning          | Ange en beskrivning på ytterligare attribut med meddelandeartiklar som är relaterade till processen. |
| Fältvärde          | Ange fältvärdet som ska användas i relation till en meddelandeartikel under rapportering. |
| Fältbeskrivning    | Ange en beskrivning av fältvärdet som ska användas i relation till en meddelandeartikel under rapportering. |
| Kontotyp         | Vissa värden i ytterligare fält kan begränsas till särskilda kontotyper. Välj ett av följande värden: **Alla**, **Kunden**, eller **Leverantör**. |
| Kontokod         | Om du har valt **Kund** eller **Leverantör** i fältet **Kontotyp** kan du begränsa användningen av fältvärdena ytterligare till en viss grupp eller tabell. |
| Konto-/gruppnummer | Om du har valt **Kund** eller **Leverantör** i fältet **Kontotyp** och om du anger en grupp eller en tabell i fältet **Kontokod** kan du ange en viss grupp eller utländskt ombud i det här fältet. |
| Giltighet            | Ange datum då värdet bör börja övervägas. |
| Utgång           | Ange datum då värdet bör sluta övervägas. |

### <a name="executable-class-settings"></a>Körbara klassinställningar

En körbar klass är en X++-metod eller klass som bearbetning av elektroniska meddelanden kan anropa i relation till en åtgärd om viss utvärdering krävs för processen.

Du kan manuellt ställa in en körbar klass på sidan **Körbara klassinställningar** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Körbara klassinställningar**). Skapa en rad och ange följande fält.

| Fält                 | beskrivning |
|-----------------------|-------------|
| Körbar klass      | Ange namnet som ska användas vid installationen av en åtgärd för meddelandebearbetning som denna klass anropas i relation till. |
| beskrivning           | Ange en beskrivning av den körbara klassen. |
| Körbart klassnamn | Välj en X++ körbar klass. |
| Körningsnivå       | Det här fältet anges automatiskt, eftersom värdet ska fördefinieras för den markerade körbara klassen. Det här fältet begränsar nivån som den relaterade utvärderingen körs på. |
| Klassbeskrivning     | Det här fältet anges automatiskt, eftersom värdet ska fördefinieras för den markerade körbara klassen. |

### <a name="populate-records-actions"></a>Fyll i poster, åtgärder

Du använder ifyllda poster för att konfigurera åtgärder som lägger till poster i artikelregistret för meddelanden så att de kan lägga till ett elektroniskt meddelande. Till exempel om elektroniska meddelandet måste rapportera kundfakturor, måste du ställa in åtgärden **Fylla i poster** som kopplas på registret **Kundfakturajournal** register (i fältet **Datakälla**). Du kan ange åtgärder för att fylla i poster på sidan **Fyll i poster, åtgärd** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Fyll i poster, åtgärder**). Skapa en ny post för varje åtgärd som ska lägga till poster i tabellen och ange följande fält.

| Fält       | beskrivning                                                               |
|-------------|---------------------------------------------------------------------------|
| Namn        | Ange ett namn för åtgärden som fyller i poster i din process.       |
| beskrivning | Ange en beskrivning för åtgärden som fyller i poster i din process. |

På snabbfliken **Inställningar för datakällor**, lägg till en rad för varje datakälla som används för processen och ange följande fält.

| Fält                  | beskrivning |
|------------------------|-------------|
| Namn                   | Ange namnet på datakällan. |
| Meddelandets artikeltyp      | Välj typ av meddelandeobjekt som ska användas när poster skapas för datakällan. |
| Kontotyp           | Välj typ av konto som ska associeras med poster från datakällan. |
| Namn på huvudregister      | Välj registret i Finance and Operations som ska vara en datakälla. |
| Dokumentnummerfält  | Markera fältet som dokumentnumret ska tas från i det valda registret. |
| Dokumentdatumfält    | Markera fältet som dokumentdatum ska tas från i det valda registret. |
| Dokumentkontofält | Markera fältet som dokumentkonto ska tas från i det valda registret. |
| Användarfråga             | Om den här kryssrutan är markerad kan du skapa en fråga genom att markera **Redigera fråga** ovanför rutnätet. Annars fylls alla poster i från datakällan. |

### <a name="web-service-settings"></a>Inställningar för webbtjänst

Du använder inställningar för webbtjänst för att konfigurera dataöverföring direkt till en webbtjänst. Du kan konfigurera inställningar för webbtjänst på sidan **Inställningar för webbtjänst** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Inställningar för webbtjänst**) .

I följande tabell beskrivs fälten på sidan **Inställningar för webbtjänst**.

| Fält                   | beskrivning |
|-------------------------|-------------|
| Webbtjänst             | Skriv ett namn på webbtjänsten. |
| beskrivning             | Ange en beskrivning för webbtjänsten. |
| Internet-adress        | Ange internetadressen till webbtjänsten. |
| Intyg             | Välj ett Key Vault-certifikat som tidigare har ställts in. |
| Svarstyp – XML | Ange det här alternativet till **Ja** om svarstypen är XML. |
| Metod för begäran          | Ange vilken metod för begäran. HTTP definierar en uppsättning metodförfrågan som anger vilken åtgärd som ska utföras av en viss resurs. Metoden kan vara **HÄMTA**, **BOKFÖR**, eller någon annan HTTP-metod. |
| Rubrik för begäran         | Ange rubrik för begäran. En rubrik för begäran är en HTTP-rubrik som kan användas i en HTTP-begäran och som inte är relaterat till innehållet i meddelandet. |
| Godkänn kodning         | Ange vilken acceptera-kodning. HTTP-huvudet för begäran att acceptera-kodning meddelar innehålllskodning som klienten kan förstå. Den här innehållskodningen är vanligtvis en komprimeringsalgoritm. |
| Innehållstyp            | Ange innehållstyp. Entitetsrubriken Innehållstyp anger medietypen för resursen. |

### <a name="message-processing-actions"></a>Åtgärder för meddelandebearbetning

Du använder åtgärder för meddelandebearbetning om du vill skapa åtgärder för dina processer och ställa in parametrarna. Du kan ställa in åtgärder för meddelandebearbetning på sidan **Åtgärder för meddelandebearbetning** (**Skatt** \> **Inställningar** \> **Elektroniska meddelanden** \> **Åtgärder för meddelandebearbetning**).

I följande tabell beskrivs fälten på sidan **Åtgärder för meddelandebearbetning**.

#### <a name="general-fasttab"></a>Snabbfliken Allmänt

| Fält                   | beskrivning |
|-------------------------|-------------|
| Åtgärdstyp             | Välj typ av åtgärd Mer information om alternativen finns i [Åtgärdstyper för meddelandebearbetning](#message-processing-action-types). |
| Mappning av format          | Välj ER-format som ska anropas för åtgärden. Det här fältet är endast tillgängligt för åtgärder av typerna **Export av elektronisk rapportering**, **Import av elektronisk rapportering** och **Meddelande om export av elektronisk rapportering**. |
| Meddelandets artikeltyp       | Välj typ av poster som åtgärden ska utvärderas för. Det här fältet är endast tillgängligt för åtgärder av typerna **Körningsnivå för meddelandeartikel**, **Export av elektronisk rapportering** och **Import av elektronisk rapportering** och även några andra typer. Om du lämnar fältet tomt beräknas alla meddelandeobjekttyper som har definierats för meddelandebehandling. |
| Körbar klass        | Välj körbara klassinställningar som skapades tidigare. Det här fältet är bara tillgängligt för åtgärder av typerna **Körningsnivå för meddelandeartikel** och **Körningsnivå för meddelandeartikel**. |
| Fyll i poster, åtgärd | Välj en åtgärd för att fylla i poster som redan har ställts in. Det här fältet är endast tillgängligt för åtgärder av typen **fylla i poster**. |

##### <a name="message-processing-action-types"></a>Åtgärdstyper för meddelandebearbetning

Följande alternativ finns tillgängliga **Åtgärdstyp**:

- **Uppdatera poster** – en åtgärd för att **fylla i posterna** måste ställas in tidigare. Associera den med en åtgärd av typen **Fylla i posterna** så att den kan inkluderas i bearbetning. Det antas att den här åtgärdstypen används för den första åtgärden i behandlingen av meddelandet. Därför kan bara resultatstatus ställas in för en åtgärd av den här typen. En inledande status kan inte anges.
- **Skapa meddelande** – Använd denna typen för att låta användarna manuellt skapa meddelanden på sidan **elektroniskt meddelande**. En inledande status kan inte ställas in för en åtgärd av den här typen.
- **Körningsnivå för meddelandeartikel** – Använd den här typen om du vill ställa in en körbar klass som ska utvärderas på meddelandeartikelnivå visas.
- **Körningsnivå för meddelande** – Använd den här typen om du vill ställa in en körbar klass som ska utvärderas på nivån visas.
- **Export av elektronisk rapportering** – Använd den här typen för åtgärder som ska generera en rapport som är baserad på en ER-konfiguration på meddelandeartikelnivå.
- **Meddelande om export av elektronisk rapportering** – Använd den här typen för åtgärder som ska generera en rapport som är baserad på en ER-konfiguration på meddelandeartikelnivå (till exempel när ett meddelande inte har några meddelandeartiklar.)
- **Import av elektronisk rapportering** – Använd den här typen för åtgärder som ska generera en rapport som är baserad på import av ER-konfiguration.
- **Användares bearbetning på meddelandenivå** – Använd den här typen för åtgärder antar vissa manuella åtgärder av användaren. Användaren kan till exempel uppdatera status för meddelanden.
- **Användares bearbetning** – Använd den här typen för åtgärder antar vissa manuella åtgärder av användaren. Användaren kan till exempel uppdatera status för meddelandeartiklar.
- **Webbtjänst** – Använd den här typen för åtgärder som ska överföra en genererad rapport till en webbtjänst. Den här åtgärdstypen används inte för italienska kommunikationsrapporter för inköps och försäljningsfakturor.
- **Begära verifiering** – Använd den här typen till begäran av verifiering från en server.

#### <a name="initial-statuses-fasttab"></a>Snabbfliken Ursprunglig status

> [!NOTE]
> Snabbfliken **inledande status** är inte tillgänglig för åtgärder som har en inledande typ av **Fylla i poster** eller **Skapa ett meddelande**.

| Fält               | beskrivning                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Status för meddelandeartikel | Välj meddelandeartikelstatus som den vald meddelandebearbetningsåtgärden ska utvärderas för. |
| beskrivning         | En beskrivning av den valda meddelandeartikelstatusen.                                                  |

#### <a name="result-statuses-fasttab"></a>Snabbfliken Status för resultat

| Fält               | beskrivning |
|---------------------|-------------|
| Meddelandestatus      | Välj meddelandestatus som den vald meddelandebearbetningsåtgärden ska utvärderas för. Det här fältet är endast tillgängligt för åtgärder för meddelandebearbetning som utvärderas på meddelandenivå. Den är till exempel tillgänglig för åtgärder av typerna **Export av elektronisk rapportering** och **Import av elektronisk rapportering**. Den är inte tillgänglig för åtgärder av typen **Användarbearbetning** och **Körningsnivå för meddelandeartikel**. |
| beskrivning         | En beskrivning av den valda meddelandestatusen. |
| Svarstyp       | Svarstyp för den valda meddelandestatusen. |
| Status för meddelandeartikel | Välj resulterande status som ska vara tillgänglig efter att meddelandebearbetningsåtgärden utvärderas. Det här fältet är endast tillgängligt för åtgärder för meddelandebearbetning som utvärderas på meddelandeartikelnivå. Den är till exempel tillgänglig för åtgärder av typen **Användarbearbetning** och **Körningsnivå för meddelandeartikel**. För meddelandebearbetningsåtgärder som utvärderas på meddelandenivån visar det här fältet statusen för meddelandetypen som ställdes in för den valda meddelandestatusen. |

### <a name="electronic-message-processing"></a>Elektronisk meddelandebearbetning

Elektronisk meddelandebearbetning är ett grundläggande begrepp för funktionen för elektroniska meddelanden. Den sammanställer åtgärder som ska utvärderas för det elektroniska meddelandet. Åtgärderna kan kopplas via en inledande status och resulterande status. Alternativt kan åtgärder av typen **Användarbearbetning** startas oberoende av varandra. På sidan **Elektronisk meddelandebearbetning** (**Moms** \> **Inställningar** \> **Elektroniska meddelanden** \> **Elektronisk meddelandebearbetning**), kan du också välja ytterligare fält som ska användas för bearbetning.

Snabbfliken **Åtgärd** låter dig lägga till fördefinierade åtgärder till bearbetningen. Du kan ange om en åtgärd måste köras separat, eller om den kan startas av bearbetningen. (Användaråtgärder måste köras separat.)

Snabbfliken **Ytterligare fält för meddelandeartikel** låter dig lägga till fördefinierade ytterligare fält som är relaterade till meddelandeobjekt. Du måste lägga till ytterligare fält för varje typ av meddelandeobjekt som hör till fälten.

Snabbfliken **Ytterligare fält för meddelanden** låter dig lägga till fördefinierade ytterligare fält som är relaterade till meddelanden.

Snabbfliken **säkerhetsroller** låter dig konfigurera de säkerhetsroller som fördefinierats i systemet för viss bearbetning. Användare som har en viss roll ser endast bearbetning som definierats för rollen.

Snabbfliken **Batch** låter dig ställa in bearbetning för att arbeta i ett system för batchordning.

## <a name="work-with-electronic-messages-functionality"></a>Arbeta med funktioner för elektroniska meddelanden

Om du arbetar på meddelandenivån är sidan **elektroniska meddelanden** (**moms** \> **förfrågningar och rapporter** \> **elektroniska meddelanden** \> **elektroniska meddelanden**)mer användbar. Om du arbetar på datainsamlingsnivån (meddelandeobjekt) är sidan **elektroniska meddelanden** (**skatt** \> **förfrågningar och rapporter** \> **elektroniska meddelanden** \> **elektroniska meddelanden**) mer användbar.

### <a name="electronic-messages"></a>Elektroniska meddelanden

Sidan **elektroniska meddelanden** visar den behandling som är tillgänglig för dig, baserat på din roll. Säkerhetsroller är kopplade till bearbetning i inställningarna för bearbetning. För varje bearbetning som är tillgänglig för dig visar sidan elektroniska meddelanden och information som är relaterad till dem.

Snabbfliken **Meddelanden** visar elektroniska meddelanden för det valda jobbet. Beroende på status för det valda meddelandet och fördefinierad behandling kan du köra vissa åtgärder genom att välja knapparna ovanför rutnätet:

- **Ny** – den här knappen är kopplad till åtgärder i typen **Skapa meddelanden**.
- **Ta bort** - Den här knappen är tillgänglig om kryssrutan **Tillåt borttagning** är markerad för aktuell status för det markerade meddelandet.
- **Generera rapport** – den här knappen är kopplad till åtgärder av typen **Meddelande om export av elektronisk rapportering**.
- **Skicka rapport** – den här knappen är kopplad till åtgärder av typen **webbtjänst**.
- **Uppdatera status** – den här knappen är kopplad till åtgärder av typen **Användares bearbetning på meddelandenivå**.
- **Meddelandeartiklar** – öppnar sidan **Elektroniska meddelandeartiklar**.

Snabbfliken **Åtgärdslogg** visar information om alla åtgärder som har körts för det markerade meddelandet.

Snabbfliken **Ytterligare fält för meddelande** visar alla ytterligare fält som har definierats för meddelanden i inställningarna för bearbetning. Den visar också värdena för dessa ytterligare fält.

Snabbfliken **Meddelandeobjekt** visar alla meddelandeobjekt som är relaterade till det markerade meddelandet.

Du kan granska alla bilagor för det markerade meddelandet. Dessa bilagor är rapporter som redan har skapats och mottagits. Markera meddelandet för att granska bilagor för och välj sedan knappen **bilaga** i åtgärdsfönstret.

![Knappen Bilaga](media/attachment-icon.png)

Sidan **Bilagor** visar alla bilagor som hör till meddelandet. Om du vill visa en fil markerar du den i listan till vänster och markerar **öppna** i åtgärdsfönstret.

![Knappen Öppna](media/open-button.png)

Om du vill granska en bifogad fil som är kopplad till en viss åtgärd som kördes tidigare för ett meddelande markerar du meddelandet på sidan **elektroniska meddelanden** och klickar sedan på snabbfliken **Åtgärdslogg** och väljer åtgärd. Välj sedan knappen **bilaga** i åtgärdsfönstret.

Du kan också köra antingen hela bearbetningen eller bara någon specifik åtgärd genom att markera **Kör bearbetning** i åtgärdsfönstret.

### <a name="electronic-message-items"></a>Elektroniska meddelandeartiklar

Sidan **Elektroniska meddelandeartiklar** visar alla meddelandeobjekt och en logg över de åtgärder som har körts för varje meddelandeartikel. Det visar också de ytterligare fält som definieras för meddelandeposter och värdena för de ytterligare fälten.

I följande tabell hittar du beskrivningar av fälten på fliken **Meddelandeartiklar**.

<table>
<thead>
<tr>
<th>Fält</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bearbetning</td>
<td>Namnet på den bearbetning som användes för att skapa meddelandeartikeln.</td>
</tr>
<tr>
<td>Meddelandeartikel</td>
<td>ID för meddelandeartikeln. Detta ID tilldelas automatiskt baserat på nummerserien <strong>Meddelandeobjekt</strong> som definieras på sidan <strong>Redovisningsparametrar</strong>.</td>
</tr>
<tr>
<td>Datum för meddelandeartikel</td>
<td>Datumet då meddelandeartikeln skapades.</td>
</tr>
<tr>
<td>Meddelandets artikeltyp</td>
<td>Typen av meddelandeartikel. Flera typer av meddelandeartiklar kan ställas in för samma behandling (t.ex. <strong>inkommande fakturor</strong> och <strong>utgående fakturor</strong>). Fältet kan endast fyllas i automatiskt när en faktura har lagts till artikelregistret för meddelanden.</td>
</tr>
<tr>
<td>Status för meddelandeartikel</td>
<td>Faktisk status för e-postmeddelandet. Tillgängliga status beror på vilken typ av meddelandeobjekt som visas. Nedan följer några exempel:
<ul>
<li><strong>Ifyllt</strong> – en post har lagts till i artikelregistret för meddelanden.</li>
<li><strong>Utvärderad</strong> – ytterligare attribut beräknades för meddelandeartikeln.</li>
<li><strong>Rapporterad</strong> – meddelandeartikeln har lagts till i en rapport.</li>
<li><strong>Undantagen</strong> – den här statusen kan vara användbar om måste du utesluta vissa meddelandeobjekt från en rapport innan den exporteras.</li>
</ul>
</td>
</tr>
<tr>
<td>Överföringsdatum</td>
<td>För bearbetning som automatiskt överför en genererad rapport utanför systemet, datum då meddelandeartikeln överfördes.</td>
</tr>
<tr>
<td>Dokumentnummer</td>
<td>Det här fältet fylls i automatiskt, baserat på inställningen av åtgärd för att fylla i poster. Fältet kan endast fyllas i automatiskt när en faktura har lagts till artikelregistret för meddelanden.</td>
</tr>
<tr>
<td>Kontonummer</td>
<td>Kontonumret för kunden eller leverantören (eller ett annat fältvärde, beroende på vilket fält som definieras i åtgärden <strong>fylla i poster</strong>). Fältet kan endast fyllas i automatiskt när en faktura har lagts till artikelregistret för meddelanden.</td>
</tr>
<tr>
<td>Meddelande</td>
<td>Numret på meddelandet. Detta nummer tilldelas automatiskt baserat på nummerserien <strong>Meddelande</strong> som definieras på sidan <strong>Redovisningsparametrar</strong>.</td>
</tr>
<tr>
<td>Meddelandestatus</td>
<td>Faktisk status för elektroniskt meddelande.</td>
</tr>
<tr>
<td>Nästa åtgärd</td>
<td>Nästa åtgärd som kan inledas för aktuell status för objektet visas.</td>
</tr>
</tbody>
</table>

Fliken **ytterligare fält** visar ytterligare fält för den markerade meddelandeartikeln och deras värden.

#### <a name="run-processing"></a>Kör bearbetning

Välj **Kör bearbetning** i åtgärdsfönstret om du vill köra bearbetning för meddelandeobjekt. Att köra en viss åtgärd i dialogrutan **Kör bearbetning**, ange alternativet **Välj åtgärd** till **Ja** och välj en åtgärd. Om du vill köra hela bearbetningen lämna alternativet **Välj åtgärd** till **Nej**.

#### <a name="generate-report"></a>Generera rapport

Välj **Generera rapport** i åtgärdsfönstret om du vill skapa en rapport. Den här knappen är kopplad till åtgärder av typen **Export av elektronisk rapportering**.

#### <a name="update-status"></a>Uppdatera status

Välj **uppdatera status** i åtgärdsfönstret om du vill uppdatera status för ett eller flera meddelandeobjekt. I dialogrutan **uppdatera status** använd snabbfliken **poster som ska ingå** för att välja meddelandeobjekt för uppdatering. Se till att du korrekt definierar urvalskriterierna, eftersom meddelandeartikelstatus uppdateras enligt dessa kriterier, den ursprungliga statusen för den valda åtgärden och värdet **ny status** du angav. När en statusuppdatering har slutförts kan det vara svårt att avgöra vilka artiklar som precis har uppdaterats. Därför är det svårt att återställa statusuppdateringar.

#### <a name="electronic-messages"></a>Elektroniska meddelanden

Välj **elektroniskt meddelande** i åtgärdsfönstret om du vill granska ett elektroniskt meddelande som är relaterat till det markerade meddelandeobjektet.

Du kan också granska alla filer som motsvarar meddelandeobjektet. Välj fältet **meddelande** i meddelandeartikel eller välj **elektroniskt meddelande** i åtgärdsfönstret. På sidan **elektroniskt meddelande** markera meddelandet att granska en rapport för och välj sedan knappen **bilaga** i åtgärdsfönstret.

![Knappen Bilaga](media/attachment-icon.png)

Sidan **Bilagor** visar alla bilagor som hör till meddelandet. Om du vill visa en fil markerar du den i listan till vänster och markerar **öppna** i åtgärdsfönstret.

![Knappen Öppna](media/open-button.png)

#### <a name="original-document"></a>Ursprungsdokument

Välj **originaldokumentet** i åtgärdsfönstret för att öppna det ursprungliga dokumentet för det markerade meddelande objektet.

## <a name="example"></a>Exempel

När du har skapat ett ER-format, mappat det till datakällor och slutfört det kan du köra det med arbetsytan **elektronisk rapportering**. En rapport skapas som du kan spara lokalt.

Om du vill kontrollera följande aspekter av rapporteringsprocessen måste du konfigurera behandling av elektroniska meddelanden:

- Logga information om som genererade rapporten.
- Logga när rapporten genererats.
- Spara rapporter som har skapats för tidigare perioder.

Det här avsnittet innehåller ett exempel som visar hur du kan konfigurera funktionen för elektroniska meddelanden för att bygga en rapporteringsprocess.

### <a name="set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Ställa in och köra bearbetning för att anropa ett enkelt ER-exportformat om du vill generera en Excel-rapport

Det här avsnittet innehåller ett exempel som visar hur du ställer in elektroniska meddelanden för att generera en rapport som är baserad på ett exporterande ER-format för Excel. Om du vill öppna det här exemplet måste ER Excel-exportformat redan skapats, mappats till datakällor och slutförts. En nummerserie måste redan ha ställts in för elektroniska meddelanden.

När du skapar bearbetning, är det viktigt att du först definierar åtgärder för bearbetning och status som ska ställas in. Följande bild visar hur bearbetningen ser ut i det här exemplet.

![Schemat för bearbetning](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Skapa meddelandestatus

1. Gå till **moms \> inställningar \> elektroniska meddelanden \> meddelandestatus**.
2. Skapa följande meddelandestatusar:

    - Ny
    - Förberedd
    - Skapad

    ![Meddelandestatus](media/message-statuses.png)

3. På raden för status **Ny**, markera kryssrutan **Tillåt borttagning** för att låta användarna ta bort meddelanden som har denna status.

#### <a name="create-additional-fields"></a>Skapa ytterligare fält

1. Gå till **moms \> inställningar \> elektroniska meddelanden \> ytterligare fält**.
2. Lägg till ytterligare fält och dess värden. Här är ett exempel:

    ![Ytterligare fält](media/additional-fields.png)

3. Ange alternativet **Användarredigering** till **Ja** för att låta användarna redigera fältet.

#### <a name="create-message-processing-actions"></a>Skapa åtgärder för meddelandebearbetning

I det här exemplet skapas följande åtgärder:

- **Skapa ett meddelande**
- **Uppdatera till förberedd**
- **Generera rapport**
- **Uppdatera till ursprunglig status** (valfritt)

1. Gå till **moms \> inställningar \> elektroniska meddelanden \> åtgärder för meddelandebearbetning**.
2. Skapa en åtgärd med namnet **Skapa meddelande**. På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **skapa ett meddelande**.
3. Skapa en åtgärd med namnet **uppdatera till förberedd** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Användares bearbetning på meddelandenivå**.
    - På snabbfliken **Ursprunglig status** i fältet **meddelandestatus** väljer du **ny**.
    - På snabbfliken **Resultatstatus** i fältet **meddelandestatus** väljer du **Förberedd**. I fältet **svarstyp** anger du **har körts**.

4. Skapa en åtgärd med namnet **Generera rapport** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Export av elektronisk rapportering**. I fältet **Formatmappning**, markera exporterande ER-formatet. Alternativen är **Excel**, **XML**, **JSON**, **Text** och **Andra**.
    - På snabbfliken **Ursprunglig status** i fältet **meddelandestatus** väljer du **Förberedd**.
    - På snabbfliken **Resultatstatus** i fältet **meddelandestatus** väljer du **Genererad**. I fältet **svarstyp** anger du **har körts**.

    ![Åtgärden Generera rapport](media/generate-report-action.png)

5. Valfritt: För att låta användarna generera en rapport om flera gånger, kan du skapa åtgärden **ursprunglig statusuppdatering** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Användares bearbetning på meddelandenivå**.
    - På snabbfliken **ursprungliga statusar** i fältet **meddelandestatus** väljer du **Genererad**.
    - På snabbfliken **Status för resultat** i fältet **meddelandestatus** väljer du **Förberedd** eller (och) **Ny**. I fältet **svarstyp** anger du **har körts**.

#### <a name="electronic-message-processing"></a>Elektronisk meddelandebearbetning

I det här exemplet ska alla åtgärder konfigureras så att de körs separat. Förutsättningen är att varje åtgärd ska initieras av användaren.

1. Gå till **moms \> inställningar \> elektroniska meddelanden \> Elektronisk meddelandebearbetning**.
2. Lägg till en post för din bearbetning och lägg till alla tidigare definierade åtgärder och ett ytterligare fält.
3. Valfritt: På snabbfliken **säkerhetsroller**, definiera säkerhetsroller för din bearbetning för att begränsa åtkomsten till särskild rapportering.
4. Gå till **skatt \> frågor och rapporter \> elektroniska meddelanden \> elektroniska meddelanden**.
5. Välj **Ny** för att skapa ett meddelande. Nu kan du lägga till datum och en beskrivning. Du kan också uppdatera värdet för ytterligare fält som du behöver.

    ![Skapa ett elektroniskt meddelande](media/create-electronic-message.png)

Rutnätet på snabbfliken **Åtgärdslogg** fylls i automatiskt med en logg över alla åtgärder som utförs på meddelandet.

Du kan nu ta bort eller uppdatera meddelandestatus. Välj om du vill uppdatera meddelandestatus **uppdateringsstatus** och sedan i fältet **ny status** väljer du **förberedd**. Välj sedan **OK**.

![Uppdatera meddelandets status](media/update-status.png)

Meddelandestatus har uppdaterats till **förberedd** och du kan nu skapa rapporten genom att markera **generera rapporten**. Rapporten genereras och meddelandestatus och åtgärdsloggen uppdateras. Om du vill visa den genererade rapporten, välj knappen **bilaga** i åtgärdsfönstret.

