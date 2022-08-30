---
title: GS1-streckkoder
description: I denna artikel beskrivs hur du konfigurerar GS1-streckkoder och QR-koder så att etiketter kan skannas på ett lagerställe.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: e1c1c274054ed1c14c9b3fc0595baa029bf3124d
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336378"
---
# <a name="gs1-bar-codes"></a>GS1-streckkoder

[!include [banner](../includes/banner.md)]

Lagerarbetare måste ofta slutföra flera uppgifter när de använder en mobil enhetsskanner i syfte att registrera rörelser för en artikel, palett eller behållare. Dessa uppgifter kan innefatta både skanning av streckkoder och att manuellt ange information på den mobila enheten. Streckkoderna använder ett företagsspecifikt format som du definierar och hanterar med hjälp av Microsoft Dynamics 365 Supply Chain Management.

GS1-streckkoder för frakthandlingar utvecklades för att tillhandahålla en global standard för datautbyte mellan företag. Dessa är tillgängliga i både linjära (1D) symboler (streckkodsformat), till exempel GS1-128, och 2D-symboler, till exempel GS1 DataMatrix- och GS1-QR-koder. GS1-streckkoder kodar inte bara data – du kan även använda en fördefinierad lista med *programidentifierare* i syfte att definiera datans betydelse. GS1-standarden definierar dataformatet och de olika typer av data som den kan koda. Till skillnad från äldre streckkodsstandarder kan GS1-streckkoder ha flera dataelement. Därför kan en enskild streckkodsgenomsökning samla in flera typer av produktinformation, till exempel batch och utgångsdatum.

GS1-stöd i Supply Chain Management förenklar avsevärt skanningsprocessen på lagerställen där lastpallar och behållare märks med hjälp av streckkoder i GS1-format. Lagerarbetare kan ta fram all nödvändig information med en enda skanning av en GS1-streckkod. Genom att eliminera behovet av att utföra skanna flera skanningar och/eller registrera information manuellt minskar GS1-streckkoderna den tid som är kopplad till vissa uppgifter. Samtidigt bidrar de också till att göra dem mer korrekta.

Logistikchefer måste konfigurera den lista över programidentifierare som krävs och associera var och en av dem med lämpliga menyalternativ för mobila enheter. Programidentifierarna kan sedan användas över flera lagerställen som en global inställning i flytt- och förpackningssyfte. Därför kommer alla frakthandlingar att ha ett enhetligt utseende.

Om inget annat anges använder denna artikel termen *streckkod* för att hänvisa till såväl linjära (1D) som 2D-streckkoder.

## <a name="the-gs1-bar-code-format"></a>Formatet för GS1-streckkod

I de allmänna specifikationerna för GS1 anges vilka symboler som kan användas för GS1-streckkoder och hur data i streckkoden ska kodas. Detta avsnitt innehåller en kort introduktion till artikeln. Fullständiga detaljer finns i de [allmänna specifikationerna för GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf) som publiceras av GS1. Specifikationsdokumentet för GS1 uppdateras regelbundet och informationen som det innehåller är uppdaterad i och med GS1 General Specifications version 22.0.

I GS1-streckkoder används följande symboler:

- **Linjära eller 1D-streckkoder** – GS1-128 och GS1 DataBar
- **2D-streckkoder** – GS1 DataMatris, GS1-QR-kod och GS1-punktkod

Observera att GS1 omnämns specifikt i GS1-128, vilket är ett specialvall av den vanliga linjöra Code-128-streckkod, GS1 DataMatris- och GS1 QR-kod. Skillnaden mellan GS1-versionen och den version som inte är GS1 är att det finns ett specialtecken (FNC1) som det första tecknet i streckkodsdatan. Närvaro av ett FNC1-tecken indikerar att datan i streckkoden ska tolkas enligt GS1-specifikationen.

Datan i streckkoden består av flera dataelement som vart och ett identifieras av en programidentifierare i början av fältet. Vanligtvis presenteras också data under streckkoden i ett mänskligt läsbart format där programidentifieraren visas inom parentes. Här är ett exempel: `(01) 09521101530001 (17) 210119 (10) AB-123`. Denna streckkod innehåller tre element:

- **Programidentifierare 01** – Artikelns GS1-artikelnummer för global handel (GTIN).
- **Programidentifierare 17** – Utgångsdatum.
- **Programidentifierare 10** – Batchnumret.

För varje element kan data ha antingen en fördefinierad längd eller en variabel längd. Det finns en fast lista över programidentifierare med fördefinierade längder. Alla andra programidentifierare har variabel längd, och listan för GS1-programidentifierare anger maximala längder och format för data. Programidentifierare 01 har till exempel en fördefinierad längd på 16 tecken (två för själva programidentifieraren och därefter 14 för GTIN), och programidentifierare 17 har en fördefinierad längd på åtta tecken (två för själva programidentifieraren och därefter sex för datumet). Programidentifierare 10 har emellertid två värden för själva programidentifieraren och därefter upp till 20 alfanumeriska tecken.

När element sätts ihop måste en avgränsare användas om ett element följer på ett variabelt längdelement. Denna avgränsare kan antingen vara det speciella FNC1-tecknet eller gruppavgränsartecknet (ett icke-utskrivbart tecken med ASCII-kod 29 och hexadecimal kod 1D). Avgränsaren ska inte användas efter det sista elementet. Även om avgränsaren inte heller ska användas efter element som har en fördefinierad längd utgär dess närvaro inget kritiskt fel.

I streckkodsdatan från det föregående exemplet på en streckkod som innehåller programidentifierarna 01, 17 och 10 kodas data i kod-128-, QR-kod- eller Datamatris-symboler som `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (programidentifierare visas i fetstil). Det rekommenderas att placera alla element som har variabel längd i slutet, detta för att ta bort behovet av ytterligare en gruppavgränsare. Streckkoden kan emellertid också ha olika typer av element, där avgränsaren är obligatorisk. Här följer ett exempel: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Datum och decimaltal

Datum representeras alltid i formatet *ÅÅMMDD*, där årtalets århundrade bestäms av GS1-specifikationer. Endast datum från 49 år bakåt till 50 år framåt (relativt till aktuellt år) kan visas.

Vissa dataelement innehåller decimaltal. Programidentifierarna 3100, 3101, ... 3105 motsvarar exempelvis en nettovikt i kilo. Eftersom dessa programidentifierare har en fördefinierad längd på 10 är sex nummer tillgängliga för kvantiteten. Decimaltecknets placering anges med det sista numret för programidentifieraren. Därför kan denna familj programidentifierare också anges som *310n*. Eftersom GS1-standarden anger att det alltid måste finnas minst en siffra till vänster om decimaltecknet tillåts maximalt fem decimaler.

Nedan följer några exempel som visar hur värdet *123456* tolkas av olika programidentifierare (anges i fetstil):

- **`3100`**`123456` &rarr; 123456 (heltal)
- **`3101`**`123456` &rarr; 12345,6 (en decimal)
- **`3102`**`123456` &rarr; 1234,56 (två decimaler)
- **`3103`**`123456` &rarr; 123,456 (tre decimaler)
- **`3104`**`123456` &rarr; 12,3456 (fyra decimaler)
- **`3105`**`123456` &rarr; 1,23456 (fem decimaler)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Skanning av GS1-streckkoder i Supply Chain Management

Vid skanning av GS1-streckkoder använder lagerarbetare en skanner som är inbyggd i eller anslutna till en mobil enhet. Skannern överför sedan den skannade streckkoden till mobilappen Warehouse Management som en serie tangentbordshändelser. Detta driftsätt kallas också för *tangentbordsbaserad* eller *"wedge"*. Mobilappen skickar sedan den mottagna texten i befintligt skick till Supply Chain Management. När systemet erhåller inkommande data bestämmer det först om datan börjar med ett av de konfigurerade prefixen som anger att datan verkligen är en GS1-streckkod (se avsnitt [Konfigurera globala GS1-alternativ](#set-gs1-options)). Om den skannade datan börjar med ett av dessa prefix använder systemet en GS1-parser för att parsa data och hämta enskilda dataelement enligt deras programidentifierare. När datan har parsats fylls antingen det aktuella inmatningsfältet eller flera fält i med den skannade datan.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Konfiguration av maskinvara och programvara för streckkodsskanner

Om Supply Chain Management ska kunna identifiera och avkoda GS1-streckkoder måste maskinvaruskannern eller stödprogramvaran vara konfigurerad för att utföra följande åtgärder:

- Lägg till ett prefix till de skannade streckkoderna, detta så att systemet kan känna igen en GS1-streckkod.
- Konvertera det icke utskrivbara ASCII-gruppavgränsartecknet (ASCII-kod 29 eller hexadecimalkod 1D) till ett utskrivbart tecken, till exempel en tilde (~).

Även om du kan lägga till ett prefix till den skannade streckkoden, är ett alternativ att lägga till en ISO/IEC 15424-symbolidentifierare, även kallad en *AIM-identifierare*. Denna treteckensidentifierare börjar med `]` och följs sedan av ett tecken som identifierar den symboluppsättning som används samt ett värde som används som ytterligare en modifierare. AIM-identifieraren `]C1` anger exempelvis en Code 128-streckkod (på grund av tecknet `C`), och modifieraren `1` anger att det finns ett FNC1-tecken på datans första position. Å andra sidan är `]C0` en kod 128-streckkod som har något annat tecken som det första tecknet i datan.

Följande fem symbolidentifierare motsvarar GS1-streckkoder som har programidentifierarelement:

- `]C1` – Kod 128 (`C`) med FNC1-tecken på första position (`1`), även kallat GS1-128.
- `]e0` – GS1 DataBar.
- `]d2`– DataMatris (`d`) med ECC 200 och FNC1 på första position (`2`), även kallat GS1- DataMatris.
- `]Q3` – QR-kod (`Q`) modell 2-symbol med FNC1 på första position (`3`), även kallat GS1-QR-kod.
- `]J1` – GS1-punktkod.

Om du använder dessa identifierare kräver kompatibiliteten med icke-GS1-streckkoder att skannrarna eller skanningsprogrammet är konfigurerade att ta bort eventuella identifierare som inte motsvarar GS1-identifierarna. Om du till exempel skannar en "normal" kod 39-streckkod, läggs prefixet `]A0` till. Eftersom systemet inte förstår prefixet som ett GS1-prefix, tolkar systemet det som data och genererar oväntade resultat.

> [!NOTE]
> Av bekvämlighetsskäl kommer version 2.0.17.0 och senare mobilappen Warehouse Management att ta bort eventuella AIM-prefix som inte finns med i föregående lista. Detta beteende stöder fall där du kan konfigurera skannern att lägga till AIM-prefixet men inte ta bort icke-önskade prefix.

### <a name="single-and-multiple-field-scanning"></a>Skanna fält med ett eller flera fält

När datan har parsats från streckkoden matas den in i flödeskontrollerna för den mobila enheten. Det finns två metoder som ska bearbetas i tur och ordning:

- **Skanning av enskilda fält** – Denna metod fyller bara i det fält som streckkoden skannades in i. Om du t.ex. skannar streckkoden `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` medan markören finns i fältet **Artikel**, anges GTIN `09521101530001` från streckkoden i det fältet. Om du skannar samma streckkod medan markören finns i fältet **Batch-ID**, kommer batchnumret `AB-123` från streckkoden att anges. Detta läget fungerar för alla fält i alla flöden och kräver bara att den allmänna GS1-inställningen konfigureras. Om en streckkod innehåller flera element måste den fortfarande skannas flera gånger, detta eftersom bara en del av streckkoden åt gången kommer att anges i flödet för den mobila enheten. Detta beteende styrs av de allmänna inställningarna i GS1, enligt beskrivet i avsnittet [Upprätta allmänna GS1-inställningar](#generic-gs1-setup).
- **Genomsökning av flera fält** – Den här metoden fyller i flera fält när en streckkod skannas, detta genom att föra in ytterligare data i flödet för den mobila enheten. Policyn konfigureras till exempel för att flytta programidentifierare 01 `ItemId` till kontroll- och program-ID 10 i fältet `InventBatchId`. Om du skannar streckkoden `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` kommer i detta fall data för båda variabler att distribueras samtidigt. Därför efterfrågar systemet inte artikel- och/eller batchnummer i flödet. Detta beteende styrs av GS1-principer som är länkade till menyalternativ enligt beskrivningen i avsnittet [Konfigurera GS1-principer till menyalternativ för mobil enhet](#policies-for-menus).

> [!WARNING]
> Standardprinciperna för GS1 har testats så att de fungerar utan oväntade beteenden. Anpassning av GS1-principer som är länkade till menyalternativ kan emellertid leda till oväntade beteenden, detta eftersom vissa data kanske inte förväntas vara tillgängliga vid en viss tidpunkt.

## <a name="turn-on-the-gs1-feature"></a>Aktivera GS1-funktion

Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Skanna GS1-streckkoder*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Aktivera funktionen Förbättrad parser för GS1-streckkoder

Om du använder GS1-streckkoder rekommenderar vi att du även aktiverar funktionen *Förbättrad parser för funktionen för GS1-streckkoder*. Med den här funktionen får du en förbättrad implementering av GS1-streckkodsparsern. Denna lägger till följande förbättringar:

- Den följer algoritmen för allmän GS1 specifikation för symboldataparsing, samt validerar att datan i symbolen gäller enligt specifikationen.
- Detta kräver inte att du konfigurerar ett värde för **Maximal längd på identifierare** och använder matchning av längsta prefix från konfigurerade programidentifierare.
- Detta gör det enklare att konfigurera decimaler för programidentifiewrare med hjälp av bokstaven *n* i syfte att matcha alla nummer. Du kan till exempel konfigurera endast en (1) programidentifierare (*310n*) istället för separata programidentifierare (*3101*, *3102*, *3103* och så vidare).
- Detta korrigerar ett problem där felaktigt kodade data tolkas som fältdata.
- Den levereras som en separat klass som kan återanvändas i andra sammanhang och gör det möjligt att använda en punkt för utbyggbarhet med syfte att manipulera skannade data innan flödesfälten fylls i.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Konfigurera globala GS1-alternativ

På sidan **Parametrar för lagerstyrning** finns några inställningar som skapar globala GS1-alternativ.

Följ dessa steg för att konfigurera globala GS1-alternativ:

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. På snabbfliken **Streckkoder** ställer du in följande fält:

    - **FNC1-tecken**, **Tecken för datamatris** och **QR-kodtecken** – Ange tecken som ska tolkas som prefix för respektive typ av GS1-streckkod.
    - **Gruppavgränsare** – Ange det tecken som ersätter ASCII-gruppavgränsartecknet.
    - **Maximal längd på identifieraren** – Ange det maximala antal tecken som är tillåtet för programidentifieraren. Detta fält behövs inte om funktionen för *Förbättrad GS1-parser* är aktiverad i ditt system.

> [!NOTE]
> Prefix talar om för systemet att en streckkod är kodad enligt GS1-standarden. Upp till tre prefix (**FNC1-tecken**, **prefixtecken för datamatris** och **QR-kod**) kan användas samtidigt och för olika ändamål.

## <a name="gs1-application-identifiers"></a>GS1-programidentifierare

I GS1-formaten kodas inte bara data – du kan även använda en fördefinierad lista med programidentifierare för att definiera datans betydelse. Logistikchefer måste konfigurera den lista över programidentifierare som krävs och associera var och en av dem med lämpliga menyalternativ för mobila enheter. Identifierarna kan sedan användas i flera olika lagerställen som en global inställning i flytt- och förpackningssyfte. Därför kommer alla frakthandlingar att ha ett enhetligt utseende.

Systemet använder data – i synnerhet fördefinierade programidentifierare – för att upprätta de regler som ska tillämpas på relevant information som skannas.

Varje programidentifierare signalerar till systemet att efterföljande tecken i den skannade streckkoden ska betraktas som ett block med krypterad information. Inställningen av programidentifierare definierar hur systemet ska tolka en streckkod och spara den som ett värde i systemet.

Logistikansvariga kan använda standardidentifierare för internationella programidentifierare och/eller skapa egna.

### <a name="load-the-standard-application-identifiers"></a>Läs in standardprogramidentifierare

Du kommer igång snabbt genom att läsa in en lista med vanliga internationella programidentifierare. Du kan sedan utöka eller redigera listan senare vid behov.

Följ dessa steg genom att lösa in ID:n för standardprogram.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-programidentifierare**.
1. Klicka på **Skapa standardinställning** i åtgärdsfönstret.

> [!WARNING]
> Kommandot **Skapa standardinställningar** raderar alla för tillfället definierade programidentifierare och ersätter dem med standardlistan. När du har läst in standardinställningarna kan du emellertid anpassa listan efter behov.

### <a name="set-up-custom-application-identifiers"></a>Ställa in anpassade programidentifierare

Om vissa eller alla programidentifierare som ditt företag använder skiljer sig från standarduppsättningen kan du skapa egna koder från grunden eller anpassa standarduppsättningen efter behov.

Följ de här stegen om du vill konfigurera och anpassa dina egna programidentifierare för GS1.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-programidentifierare**.
1. Gör något av följande:

    - Om du vill skapa ett nytt ID väljer du **Ny** i åtgärdsfönstret.
    - Om du vill redigera en befintlig identifierare: Välj identifieraren och välj sedan **Redigera** i åtgärdsfönstret.

1. Ställ in följande fält för den nya eller valda identifieraren:

    - **Programidentifierare** – Ange identifieringskod för programidentifieraren. Denna kod är vanligtvis ett heltal med två siffror, men kan även vara längre. För decimalvärden anger den sista siffran antalet decimaler. Mer information finns i beskrivningen av kryssrutan **Decimal** senare i denna lista. Om funktionen *Förbättrad parser för GS1-streckkoder* är aktiverad kan du skapa en enskild programidentifierare för alla decimalvarianter genom att använda bokstaven *n* som sista tecken i programidentifieraren. Du kan till exempel konfigurera endast en (1) programidentifierare (*310n*) istället för en separat programidentifierare för respektive antal decimaler (*3101*, *3102*, *3103* och så vidare).
    - **Beskrivning** – ange en kort beskrivning av identifieraren.
    - **Fast längd** – Markera den här kryssrutan om värden som skannas med hjälp av dena programidentifierare har ett fast antal tecken. Avmarkera denna kryssruta om värdenas längd är variabel. I det här fallet måste du ange slutet på värdet med hjälp av gruppavgränsartecknet som du angav på sidan **Lagerstyrningsparametrar**.
    - **Längd** – Ange det maximala antal tecken som kan visas i de värden som skannas med hjälp av programidentifieraren. Om kryssrutan **Fast längd** är markerad förväntas exakt detta antal tecken.
    - **Typ** – Välj den typ av värde som skannas med hjälp av denna programidentifierare (*numeriskt*, *alfanumeriskt* eller *datum*). Mer information om hur datum och nummer visas i streckkodsdata finns i avsnittet [Datum och decimaler](#dates-and-decimal-numbers).
    - **Decimaler** – Markera den här kryssrutan om värdet inkluderar en underförstådd decimalpunkt. Om den här rutan markeras använder systemet den sista siffran i programidentifieraren för att bestämma antalet decimalplatser. Mer information om hur datum och nummer visas i streckkodsdata finns i avsnittet [Datum och decimaler](#dates-and-decimal-numbers).

> [!WARNING]
> Även om systemet låter dig konfigurera kryssrutan **Fast längd** för valfri programidentifierare bör den endast användas för den iunderuppsättning programidentifierare som har en fördefinierad längd i enlighet med allmänna GS1-specifikationer. Den förbättrade GS1-parsern innehåller redan en lista över alla programidentifierare som har fördefinierade längder.

> [!NOTE]
> Värdet **Gruppavgränsare** som anges på sidan **Lagerstyrningsparametrar** är valfritt om ett värde som följs av en programidentifierare har en fast längd.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Upprätta allmän GS1-konfiguration

Den allmänna GS1-konfigurationen innehåller en samling vanliga mappningar. Dessa mappningar matchar alla relevanta inmatningsfält i mobilappen mot den programidentifierare som styr hur värden från skannade streckkoder ska tolkas och lagras i det fältet. Som standard gäller dessa inställningar för alla skanningar efter alla menyalternativ på den mobila enheten. De kan dock skrivas över för ett eller flera specifika fält av en GS1-policy som har tilldelats till ett visst menyalternativ.

Den allmänna GS1-konfigurationen tillåter bara att ett (1) värde skannas åt gången. Om du vill läsa in flera fältvärden från en enda skanning måste du därför konfigurera en GS1-policy för de relevanta menyalternativen.

Mer information om GS1-policyer finns i nästa avsnitt.

### <a name="load-the-standard-generic-gs1-setup"></a>Läs in den allmänna GS1-standardkonfigurationen

På sidan **Allmän GS1-konfiguration** kan du läsa in en standarduppsättning mappningar mellan fält för mobila enheter och standardprogramidentifierare som skapas av standardkonfigurationen.

Om du vill skapa den allmänna GS1-inställningen går du till **Lagerstyrning \> Inställningar \> GS1 \> Allmänna GS1-inställningar**. Välj sedan **Skapa standardkonfiguration** om du automatiskt vill tilldela en passande programidentifierare till varje fält som normalt används av menyalternativen på mobila enheter.

> [!WARNING]
> Om någon allmän GS1-konfiguration redan finns raderar kommandot **Skapa standardkonfiguration** detta fullständigt innan det läser in standardinställningarna.

### <a name="customize-the-standard-generic-gs1-setup"></a>Anpassa den allmänna GS1-standardkonfigurationen

Anpassa den allmänna GS1-konfigurationen genom att följa dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> Allmän -konfiguration**.
1. Gör något av följande:

    - I åtgärdsfönstret väljer du **Ny** för att skapa en ny mappning.
    - Om du vill redigera en befintlig mappning: Välj mappningen och sedan **Redigera** i åtgärdsfönstret.

1. Ställ in följande fält för den nya eller valda mappningen:

    - **Fält** – Välj eller ange det inmatningsfält för mobilappen som inkommande värde ska tilldelas till. Värdet är inte det visningsnamn som visas för arbetarna. Istället är det nyckelnamnet som tilldelas fältet i den underliggande koden. Standardinställningen omfattar en samling fält som kan vara användbara och innehåller namn som är viktiga för varje fält och matchande programmererade funktioner. Du kanske emellertid måste tala med dina utvecklingspartners om du vill finna rätt val för just din implementering.
    - **Programidentifierare** – Välj tillämplig programidentifierare enligt definitionen på sidan **GS1-programidentifierare**. Identifieraren anger hur streckkoden ska tolkas och lagras som ett värde för det namngivna fältet. När du har valt en programidentifierare visar fältet **Beskrivning** dess beskrivning.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Konfigurera GS1-policyer som menyalternativ för mobila enheter

Syftet med GS1-standarden är att göra det möjligt för medarbetare att läsa in flera värden när de skannar en enskild streckkod en (1) gång. För att uppnå detta syfte måste logistikchefer konfigurera GS1-policyer som talar om för systemet hur det ska tolka streckkoder med flera värden. Du kan senare tilldela policyer till menyalternativ för mobila enheter i syfte att styra hur en streckkod tolkas när medarbetare skannar den medan de använder ett specifikt menyalternativ.

Om ingen GS1-policy har tilldelats till ett menyalternativ kan systemet bara samla in ett enda värde. Detta värde tillämpas på den mobila appindata som väljs när arbetaren utför skanningen, enligt angivet av den allmänna GS1-inställningen. Om en GS1-policy tilldelas menyalternativet använder systemet fortfarande den allmänna GS1-inställningen för att mappa det första streckkodsvärdet till det valda fältet. Den kan sedan fånga in ytterligare fältvärden enligt vad som angetts i den tillämpliga policyn.

### <a name="load-the-standard-specific-gs1-policies"></a>Läs in de standardspecifika GS1-policyerna

Om du vill komma igång snabbt kan du läsa in en uppsättning GS1-policyer. Du kan sedan utöka eller redigera policyerna senare efter behov.

Följ dessa steg genom att lösa in ID:n för standardprogram.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-policy**.
1. Klicka på **Skapa standardinställning** i åtgärdsfönstret.

> [!WARNING]
> Kommandot **Skapa standardinställningar** raderar alla för tillfället definierade policyer och ersätter dem med standarduppsättningen policyer. När du har läst in standardinställningarna kan du emellertid anpassa policyerna efter behov.

### <a name="set-up-custom-specific-gs1-policies"></a>Konfigurera anpassade GS1-policyer

> [!WARNING]
> Vissa GS1-policyer kanske inte fungerar med alla mobilflöden som du använder. När du konfigurerar anpassade GS1-principer måste du testa det mobila enhetsflödet genom att använda olika delar av informationen som skannas vid olika tidpunkter i flödet. På detta sätt kan du avgöra om flödet fungerar som förväntat.

Ställ in och anpassa GS1-policyer genom att följa dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-policy**.
1. Gör något av följande:

    - I åtgärdsfönstret väljer du **Ny** för att skapa en ny policy.
    - Om du vill redigera en befintlig policy: Markera policyn i listfönstret.

1. Ange följande fältvärden i den nya eller valda policyns rubrik:

    - **Policynamn** – Ange ett namn för policyn.
    - **Beskrivning** – Ange en kort beskrivning av policyn.

1. På snabbfliken under rubriken mappar du fältnamn till programidentifierare efter behov för den aktuella policyn. Använd knapparna i verktygsfältet om du vill lägga till eller ta bort rader efter behov. För varje rad anger du följande fält:

    - **Fält** – Välj eller ange det inmatningsfält för mobilappen som inkommande värde ska tilldelas till. Värdet är inte det visningsnamn som visas för arbetarna. Istället är det nyckelnamnet som tilldelas fältet i den underliggande koden. Standardinställningen omfattar en samling fält som kan vara användbara och innehåller namn som är viktiga för varje fält och matchande programmererade funktioner. Du kanske emellertid måste tala med dina utvecklingspartners om du vill finna rätt val för just din implementering.
    - **Programidentifierare** – Välj tillämplig programidentifierare enligt definitionen på sidan **GS1-programidentifierare**. Identifieraren anger hur streckkoden ska tolkas och lagras som ett värde för det namngivna fältet. När du har valt en programidentifierare visar fältet **Beskrivning** dess beskrivning.
    - **Sortering** – Varje streckkod med flera värden innehåller en serie programidentifierare, som vardera följs av ett värde. Den tillämpliga GS1-policyn identifierar vilken programidentifierare som mappas till respektive databasfält. Om en streckkod använder samma programidentifierare mer än en gång använder systemet emellertid den ordning i vilken programidentifierare visas i koden för att mappa dem till fält. För rader som delar en programidentifierare med en eller flera andra rader använder du detta fält för att fastställa i vilken ordning de matchande raderna bearbetas i. Raden som har det lägsta sorteringsvärdet behandlas först.

> [!NOTE]
> För streckkoder som innehåller mer än en identisk programidentifierare *måste* du använda fältet **Sortering** för att skapa fältens ordning.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Tilldela GS1-policyer till menyalternativ för mobil enhet

Som standard innehåller alla menyalternativ för mobila enheter indatafält där arbetare kan skanna ett enda värde enligt den allmänna GS1-inställningen. Om du vill att medarbetarna ska kunna skanna mer än ett fältvärde i en enda skanning för alla menyalternativ för mobila enheter måste du tilldela en GS1-policy genom att följa dessa steg.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Skapa eller öppna ett menyalternativ.
1. På snabbfliken **Allmänt** anger du fältet **GS1-policy** som den policy som gäller för menyartikeln.

## <a name="gs1-setup-example"></a>Exempel på GS1-konfiguration

Detta exempel gäller för ett system där GS1-alternativen konfigureras på följande sätt:

- På sidan **Parametrar för Lagerstyrning** fastställs följande globala inställningar:

    - **FNC1-tecken:** *\]C1*
    - **Gruppavgränsare:** *\~*

- På sidan **GS1-programidentifierare** är följande programidentifierare relevanta för detta exempel:

    | Programidentifierare | beskrivning | Fast längd | Längd | Typ | Decimal |
    |---|---|---|---|---|---|
    | 01 | GTIN | Markerad | 14 | Numerisk | Reglerat |
    | 10 | Batchnummer | Reglerat | 20 | Alfanumeriska | Reglerat |
    | 17 | Utgångsdatum | Markerad | 6 | Datum | Reglerat |
    | 30 | Kvantitet för inleverans | Reglerat | 8 | Numerisk | Reglerat |

- På sidan **Allmänna inställningar för GS1** är följande inställningar för den allmänna GS1-policyn relevanta för det här exemplet.

    | Fält | Programidentifierare | beskrivning |
    |---|---|---|
    | ItemId | 01 | GTIN |

- På sidan **GS1-policy** finns en policy där fältet **Policynamn** är inställt på *Inleverans av inköp*. Denna policy omfattar följande rader:

    | Fält | Programidentifierare | beskrivning | Sortering |
    |---|---|---|---|
    | ExpDate | 17 | Utgångsdatum | 0 |
    | InventBatchId | 10 | Batchnummer | 0 |
    | Antal | 30 | Kvantitet för inleverans | 0 |

- På sidan **Menyalternativ för mobila enheter** finns en menyartikel med namnet *Inleverans av inköp*. Dess **GS1-policyfält** är inställt på *Inleverans av inköp*.

När varor för en inköpsorder anländer till lagerstället följer arbetaren dessa steg.

1. Välj menyalternativet **Inleverans av inköp** på den mobila enheten.
1. Ange inköpsordernummer.
1. Välj fältet **Artikel** och skanna följande streckkod: `]C10100000012345678~3030~10b1~17220215`.

På grund av inställningarna som angetts för detta exempel tolkar systemet den skannade streckkoden på följande sätt:

| Fältnyckel | Sökande-ID | Värde | Sedel |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Eftersom arbetaren skannas till fältet **Artikel** mappas det första värdet i streckkoden till det fältet. Mappningen har tagits från de allmänna inställningarna för GS1. |
| Antal | 30 | 30 | Eftersom flera fältvärden registreras i en enda skanning tas den här mappningen och alla återstående mappningar från den GS1-policy som tilldelats till menyalternativet **Inleverans av inköp**. Detta värde är den kvantitet som togs emot. |
| InventBatchId | 10 | b1 | Detta värde är batchens ID. |
| ExpDate | 17 | 220215 | Datumformatet är ÅÅMMDD. Därför är utgångsdatum den 15 februari 2022. |

Kvittot registreras sedan, och relevanta databasvärden anges efter den enskilda genomsökningen.
