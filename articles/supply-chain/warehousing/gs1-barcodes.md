---
title: GS1-streckkoder och QR-koder
description: I detta ämne beskrivs hur du ställer in GS1-streckkoder och QR-koder så att etiketter kan skannas på ett lagerställe.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8f438e18356a6c16cc75bb59153ae7353d984a5a
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500340"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>GS1-streckkoder och QR-koder

[!include [banner](../includes/banner.md)]

Lagerarbetare måste ofta slutföra flera uppgifter när de använder en mobil enhetsskanner i syfte att registrera rörelser för en artikel, palett eller behållare. Dessa uppgifter kan innefatta både skanning av streckkoder och att manuellt ange information på den mobila enheten. Streckkoderna använder ett företagsspecifikt format som du definierar och hanterar med hjälp av Microsoft Dynamics 365 Supply Chain Management.

GS1-streckkods- och QR-kodformat för leveransetiketter utvecklades för att tillhandahålla en global standard för datautbyte mellan företag. I GS1-formaten kodas inte bara data – du kan även använda en fördefinierad lista med för att *programidentifierare* definiera datans betydelse. GS1-standarden definierar dataformatet och de olika typer av data som den kan koda. Till skillnad från äldre streckkoder kan GS1-streckkoder ha flera dataelement. Därför kan en enskild streckkodsgenomsökning samla in flera typer av produktinformation, till exempel batch och utgångsdatum.

GS1-stöd i Supply Chain Management förenklar avsevärt skanningsprocessen på lagerställen där lastpallar och behållare märks med hjälp av koder i GS1-format. Lagerarbetare kan ta fram all nödvändig information med en enda skanning av en GS1-streckkod. Genom att eliminera behovet av att utföra skanna flera skanningar och/eller registrera information manuellt minskar GS1-streckkoderna den tid som är kopplad till vissa uppgifter. Samtidigt bidrar de också till att göra dem mer korrekta.

Logistikchefer måste konfigurera den lista över programidentifierare som krävs och associera var och en av dem med lämpliga menyalternativ för mobila enheter. Programidentifierarna kan sedan användas över flera lagerställen som en global inställning i flytt- och förpackningssyfte. Därför kommer alla frakthandlingar att ha ett enhetligt utseende.

Om inget annat anges använder detta ämne termen *streckkod* för att hänvisa till såväl streckkoder som QR-koder.

## <a name="turn-on-the-gs1-feature"></a>Aktivera GS1-funktion

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Skanna GS1-streckkoder*

## <a name="set-up-global-gs1-options"></a>Konfigurera globala GS1-alternativ

På sidan **Parametrar för lagerstyrning** finns några inställningar som skapar globala GS1-alternativ.

Följ dessa steg för att konfigurera globala GS1-alternativ:

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. På snabbfliken **Streckkoder** ställer du in följande fält:

    - **FNC1-tecken** – Ange tecken som ska tolkas som prefix när en streckkod tolkas.
    - **Datamatris-tecken** – Ange tecken som ska tolkas som prefix när en datamatris tolkas.
    - **QR-kodtecken** – Ange tecken som ska tolkas som prefix när en QR-kod tolkas.
    - **Gruppavgränsare** – Anger tecknet som identifierar separata delar av en streckkod eller QR-kod.
    - **Maximal längd på identifieraren** – Ange det maximala antal tecken som är tillåtet för programidentifieraren.

> [!NOTE]
> Prefix talar om för systemet att en streckkod är krypterad enligt GS1-standarden. Upp till tre prefix (**FNC1-tecken**, **prefixtecken för datamatris** och **QR-kod**) kan användas samtidigt och för olika ändamål.

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

Följ de här stegen om du vill ställa in och anpassa dina egna programidentifierare för GS1.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-programidentifierare**.
1. Gör något av följande:

    - Om du vill skapa ett nytt ID väljer du **Ny** i åtgärdsfönstret.
    - Om du vill redigera en befintlig identifierare: Välj identifieraren och välj sedan **Redigera** i åtgärdsfönstret.

1. Ställ in följande fält för den nya eller valda identifieraren:

    - **Programidentifierare** – Ange identifieringskod för programidentifieraren. Denna kod är vanligtvis ett heltal med två siffror, men kan även vara längre. För decimalvärden anger den sista siffran antalet decimaler. Mer information finns i beskrivningen av kryssrutan **Decimal** senare i denna lista.
    - **Beskrivning** – ange en kort beskrivning av identifieraren.
    - **Fast längd** – Markera den här kryssrutan om värden som skannas med hjälp av dena programidentifierare har ett fast antal tecken. Avmarkera denna kryssruta om värdenas längd är variabel. I det här fallet måste du ange slutet på värdet med hjälp av gruppavgränsartecknet som du angav på sidan **Lagerstyrningsparametrar**.
    - **Längd** – Ange det maximala antal tecken som kan visas i de värden som skannas med hjälp av programidentifieraren. Om kryssrutan **Fast längd** är markerad förväntas exakt detta antal tecken.
    - **Typ** – Välj den typ av värde som skannas med hjälp av denna programidentifierare (*numeriskt*, *alfanumeriskt* eller *datum*). För datum är det förväntade formatet ÅÅMMDD (utan blanksteg eller bindestreck).
    - **Decimaler** – Markera den här kryssrutan om värdet inkluderar en underförstådd decimalpunkt. Om den här rutan markeras använder systemet den sista siffran i programidentifieraren för att bestämma antalet decimalplatser. Om till exempel programidentifieraren är *3205* kommer värdets fem yttersta siffror att tolkas som kommandes efter decimaltecknet.

> [!NOTE]
> Gruppavgränsaren som anges på sidan **Parametrar för lagerstyrning** är valfri om ett värde som följs av ett program-ID har en fast längd, eller om längden är maximerad (om längden är lika med värdet för **längd** som har angetts för programidentifieraren).

## <a name="establish-the-generic-gs1-setup"></a>Upprätta allmän GS1-konfiguration

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

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Konfigurera GS1-policyer som du kan tilldela till menyalternativ för mobila enheter

Syftet med GS1-standarden är att göra det möjligt för medarbetare att läsa in flera värden när de skannar en enskild streckkod en (1) gång. För att uppnå detta syfte måste logistikchefer ställa in GS1-policyer som talar om för systemet hur det ska tolka streckkoder med flera värden. Du kan senare tilldela policyer till menyalternativ för mobila enheter i syfte att styra hur en streckkod tolkas när medarbetare skannar den medan de använder ett specifikt menyalternativ.

Om ingen GS1-policy har tilldelats till ett menyalternativ kan systemet bara samla in ett enda värde. Detta värde tillämpas på den mobila appindata som väljs när arbetaren utför skanningen, enligt angivet av den allmänna GS1-inställningen. Om en GS1-policy tilldelas menyalternativet använder systemet fortfarande den allmänna GS1-inställningen för att mappa det första streckkodsvärdet till det valda fältet. Den kan sedan fånga in ytterligare fältvärden enligt vad som angetts i den tillämpliga policyn.

### <a name="load-the-standard-specific-gs1-policies"></a>Läs in de standardspecifika GS1-policyerna

Om du vill komma igång snabbt kan du läsa in en uppsättning GS1-policyer. Du kan sedan utöka eller redigera policyerna senare efter behov.

Följ dessa steg genom att lösa in ID:n för standardprogram.

1. Gå till **Lagerstyrning \> Inställningar \> GS1 \> GS1-policy**.
1. Klicka på **Skapa standardinställning** i åtgärdsfönstret.

> [!WARNING]
> Kommandot **Skapa standardinställningar** raderar alla för tillfället definierade policyer och ersätter dem med standarduppsättningen policyer. När du har läst in standardinställningarna kan du emellertid anpassa policyerna efter behov.

### <a name="set-up-custom-specific-gs1-policies"></a>Konfigurera anpassade GS1-policyer

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
1. Välj fältet **Artikel** och skanna följande streckkod: *\]C10100000012345678\~3030\~10b1\~17220215*.

På grund av inställningarna som angetts för detta exempel tolkar systemet den skannade streckkoden på följande sätt:

| Fältnyckel | Sökande-ID | Värde | Sedel |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Eftersom arbetaren skannas till fältet **Artikel** mappas det första värdet i streckkoden till det fältet. Mappningen har tagits från de allmänna inställningarna för GS1. |
| Antal | 30 | 30 | Eftersom flera fältvärden registreras i en enda skanning tas den här mappningen och alla återstående mappningar från den GS1-policy som tilldelats till menyalternativet **Inleverans av inköp**. Detta värde är den kvantitet som togs emot. |
| InventBatchId | 10 | b1 | Detta värde är batchens ID. |
| ExpDate | 17 | 220215 | Datumformatet är ÅÅMMDD. Därför är utgångsdatum den 15 februari 2022. |

Kvittot registreras sedan, och relevanta databasvärden anges efter den enskilda genomsökningen.
