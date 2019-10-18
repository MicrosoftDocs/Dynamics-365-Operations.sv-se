---
title: Butikskringutrustning
description: Det här avsnittet förklarar koncepten som är relaterade till kringutrustning i butik.
author: rubencdelgado
manager: AnnBe
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice, RetailHardwareProfile
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cf4eb74acbd305eb67861ab3f09648bf8af8f86c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025063"
---
# <a name="retail-peripherals"></a>Butikskringutrustning

[!include [banner](includes/banner.md)]

Det här avsnittet förklarar koncepten som är relaterade till kringutrustning i butik. Här beskrivs olika sätt att ansluta kringutrustning till kassan och komponenterna som är ansvariga för anslutning till kassan.

## <a name="concepts"></a>Begrepp

### <a name="pos-registers"></a>Kassaregister

Navigering: Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparat**. Kassaregistret är en enhet som används för att definiera egenskaperna hos en viss instans av kassan. Dessa egenskaper omfattar maskinvaruprofil eller inställningar för kringutrustning i butik som ska användas i kassan, butiken som kassan har mappats till och den visuella upplevelsen när användare loggar in på den kassan.

### <a name="devices"></a>Enheter

Navigering: Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Enheter**. En enhet är en entitet som representerar en fysisk instans av en enhet som är mappad till ett kassaregister. När en enhet skapas är den mappad till ett kassaregister. Enhetsentiteten spårar information om när ett kassaregister aktiveras, vilken typ av klient som används och programpaketet som har distribuerats till en viss enhet. Enheter som kan mappas till följande programtyper: Retail Modern POS, Retail Cloud POS, Retail Modern POS – Windows Phone Retail Modern POS - Android och Retail Modern POS – iOS.

### <a name="retail-modern-pos"></a>Retail Modern POS

Modern POS är kassaprogrammet för Microsoft Windows. Det kan användas på Windows 10 operativsystem (OSs).

### <a name="cloud-pos"></a>Cloud POS

Cloud POS är en webbläsarbaserad versionen av Modern POS-programmet som kan användas i en webbläsare.

### <a name="modern-pos-for-ios"></a>Modern POS för iOS

Modern POS för iOS är en iOS-baserad version av Modern POS-programmet som kan användas på iOS-enheter

### <a name="modern-pos-for-android"></a>Modern POS för Android

Modern POS för Android är en Android-baserad version av Modern POS-programmet som kan användas på Android-enheter

### <a name="pos-peripherals"></a>Kringutrustning för kassa

Kringutrustning för kassa är enheter som uttryckligen har stöd för kassafunktioner. Denna kringutrustning är vanligtvis uppdelade i klasser. Mer information om dessa klasser finns i avsnittet "Enhetsklasser" i det här avsnittet.

### <a name="hardware-station"></a>Hardware Station

Navigering: Klicka på **Butik** &gt; **Kanaler** &gt; **Butiker** &gt; **Alla butiker**. Markera en butik och klicka på snabbfliken **Maskinvarustationer**. Inställningen **Maskinvarustation** är en inställning på kanalnivå som används för att definiera instanser där logiken för kringutrustning i butik ska distribueras. Inställningen på kanalnivå används för att bestämma egenskaperna hos maskinvarustationen. Den används också för att lista maskinvarustationer som är tillgängliga för en Modern POS-instans i en viss butik. Maskinvarustationen ingår i Modern POS-programmet för Windows. Maskinvarustationen kan också distribueras separat som ett fristående Microsoft Internet Information Services-program (IIS). I detta fall får du åtkomst till det via ett nätverk.

### <a name="hardware-profile"></a>Maskinvaruprofil

Navigering: Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**. Maskinvaruprofilen är en lista över enheter som är konfigurerade för ett kassaregister eller en maskinvarustation. Maskinvaruprofilen kan mappas direkt till ett kassaregister eller till en maskinvarustation.

## <a name="devices-classes"></a>Enhetsklasser
Kringutrustning för kassa är vanligtvis uppdelade i klasser. Det här avsnittet beskriver och ger en översikt över enheterna som stödjer Modern POS.

### <a name="printer"></a>Skrivare

Skrivare som är traditionella kassakvittoskrivare och helsideskrivare. Skrivare stöds via objektlänkning och inbäddning för Retail POS (OPOS) och Microsoft Windows-drivrutinsgränssnitt. Upp till två skrivare kan användas samtidigt. Den här funktionen har stöd för scenarier där kundinleveranser för cash and carry skrivs ut på kvittoskrivare, medan kundorder som har mer information skrivs ut på helsidesskrivare. Kvittoskrivare kan vara direkt anslutna till en dator via USB, anslutna till ett nätverk via Ethernet eller anslutna via Bluetooth.

### <a name="scanner"></a>Skanner

Upp till två streckkodsläsare kan användas samtidigt. Den här funktionen stöder scenarier där en skanner som är mer mobil krävs för att söka igenom stora eller tunga artiklar, medan en fast inbäddad skanner används för de flesta objekt med standardstorlek för att snabba på utcheckningstider. Skannrar kan stödjas genom OPOS Universal Windows Platform (UWP) eller tangentbordbaserat gränssnitt. USB och Bluetooth kan användas för att ansluta en skanner till en dator.

### <a name="msr"></a>MSR

En USB-kortläsare (MSR) kan konfigureras genom att använda OPOS-drivrutiner. Om du vill använda en fristående MSR för betalningstransaktioner med elektronisk betalningsöverföring (EFT) måste MSR hanteras av en betalningsanslutning. Fristående MSR:er kan användas för kundbonusinmatning, medarbetarinloggning och presentkortsinmatning, oberoende av betalningsanslutningen.

### <a name="cash-drawer"></a>Kassalåda

Två kassalådor kan användas per maskinvaruprofil. Med den här funktionen kan du ha två aktiva skift per kassa som kan användas samtidigt. När det gäller ett delat skift eller en kassalåda som används av flera mobila kassaenheter samtidigt tillåts endast en kassalådan per maskinvaruprofil. Kassalådor kan vara direkt anslutna till en dator via USB, anslutna till ett nätverk eller anslutna till en kvittoskrivare via ett RJ12-gränssnitt. I vissa fall kan kassalådor anslutas via Bluetooth.

### <a name="line-display"></a>Radvisning

Radbildskärmar används för att visa produkter, transaktionssaldon och övrig värdefull information till kunden under en transaktion. En radbildskärm kan anslutas till datorn via USB genom att använda OPOS-drivrutiner.

### <a name="signature-capture"></a>Digital signatur

Enheter för digital signatur kan anslutas direkt till en dator via USB genom att använda OPOS-drivrutiner. När digital signatur är konfigurerad uppmanas kunden till att logga in på enheten. När signaturen har angivits visas den för kassören för godkännande.

### <a name="scale"></a>Skala

Skalor kan anslutas till datorn via USP genom att använda OPOS-drivrutiner. När en produkt som är markerad som en "Vägd" produkt läggs till i en transaktion, läser kassan vikten från skalan, lägger till produkten i transaktionen och använder den kvantitet som skalan har angett.

### <a name="pin-pad"></a>PIN-knappsats

Knappsatser för personligt identifieringsnummer (PIN) stöds via OPOS, men de måste hanteras via en betalningsanslutning.

### <a name="secondary-display"></a>Sekundär bildskärm

När en sekundär bildskärm konfigureras används den andra Windows-displayen för att visa grundläggande information. Syftet med den sekundära bildskärmen är att stödja tillägget för oberoende programleverantör (ISV) eftersom out of the box kan inte den sekundära bildskärmen konfigureras och visar begränsat innehåll.

### <a name="payment-device"></a>Betalningsenhet

Stöd för betalningsenheten implementeras via betalningskopplingen. Betalningsenheter kan utföra en eller flera funktioner som andra enhetsklasser ger. Exempelvis kan en betalningsenhet fungera som en MSR/kortläsare, radbildskärm, enhet för digital signatur eller PIN-knappsats. Stöd för betalningsenheter implementeras oberoende av det fristående enhetsstöd som ges för andra enheter som ingår i maskinvaruprofilen.

## <a name="supported-interfaces"></a>Gränssnitt som stöds

### <a name="opos"></a>OPOS

För att garantera att den största mängden enheter kan användas med Retail är OLE för kassabranschstandard den primära enhetsplattformen för kringutrustning i butik som stöds. OLE för kassastandarden anses vara framställt av National Retail Federation (NRF), som fastställer branschstandardiserade kommunikationsprotokoll för kringutrustning i butik. OPOS är en ATSC implementering av OLE för POS-standarden. Den utvecklades i mitten av 1990-talet och har uppdaterats flera gånger sedan dess. OPOS ger en enhetsdrivrutinarkitektur som ger enkel integrering av maskinvaruprofil för kassa med Windows-baserade kassasystem. OPOS-kontrollerna styr kommunikationen mellan kompatibel maskinvara och kassaprogram. En OPOS-kontroll består av två delar:

- **Kontrollobjekt** – Kontrollobjektet för en enhetsklass (t.ex. radvisningar) tillhandahåller ett gränssnitt för programmet. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) tillhandahåller en standardiserad uppsättning OPOS-kontrollobjekt som kallas Common Control-objekt (CCO). CCO som används för att testa POS-komponent i Retail. Därför kan testningen garantera att många enhetstyper stöds under förutsättning att tillverkaren tillhandahåller ett serviceobjekt som skapats för OPOS, om Retail stöder en enhetsklass via OPOS. Du behöver inte uttryckligen testa varje enhetstyp.
- **Serviceobjekt** – Serviceobjektet ger kommunikation mellan kontrollobjektet (CCO) och enheten. Vanligtvis tillhandahålls serviceobjektet för en enhet av enhetens tillverkare. Men i vissa fall kan du behöva hämta serviceobjektet från tillverkarens webbplats. Till exempel kan ett nyare serviceobjekt vara tillgängligt. Se maskinvarudokumentationen för att hitta adressen till tillverkarens webbplats.

[![Kontrollobjekt och serviceobjekt](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png)

Stöd för OPOS-implementeringen av OLE för POS hjälper till att garantera att om tillverkare och utgivare POS följer korrekt, POS-system och enheter som stöds kan samarbeta, även om de inte tidigare testats tillsammans.

> [!NOTE]
> OPOS-stöd garanterar inte stöd för alla enheter som har OPOS-drivrutiner. Retail måste först stöd för denna enhetstyp eller via OPOS-klass. Dessutom kanske serviceobjekt inte alltid är uppdaterade med den senaste versionen av dessa CCO. Du bör också vara medveten om att i allmänhet varierar kvaliteten på serviceobjekten.

### <a name="windows"></a>Windows

Kvittoutskrift i kassan optimeras för OPOS. OPOS brukar vara betydligt snabbare än utskrift genom Windows. Därför är det en bra idé att använda OPOS, särskilt i butiksmiljöer där 40-kolumnkvitton skrivs ut och transaktionstiderna måste vara snabba. För de flesta enheter används OPOS-kontroller. Vissa OPOS kvittoskrivare stöder emellertid Windows-drivrutiner. Genom att använda en Windows-drivrutin kan du komma åt de senaste teckensnitten och en nätverksskrivare för flera kassor. Det finns emellertid nackdelar med Windows-drivrutiner. Här följer några exempel på dessa nackdelar:

- När Windows-drivrutiner används återges bilder innan utskrift sker. Därför brukar utskrifter vara långsammare än på skrivare med OPOS-kontroller.
- Enheter som är anslutna till skrivaren ("daisy-fastkedjad") fungerar inte när Windows-drivrutiner används. Exempelvis går det inte att öppna kassalådan eller kvittoskrivaren kanske inte skriver som förväntat.
- OPOS stöder även en mer omfattande uppsättning variabler som avser butikskvittoskrivare, som t.ex. pappersskärning eller kvittoutskrift.

Om det finns OPOS-kontroller för Windows-skrivaren som du använder fungerar skrivaren ändå korrekt med Retail.

### <a name="universal-windows-platform"></a>Universal Windows-plattform

UWP, när det gäller butikskringutrustning är relaterat till Windows stöd för Plug and Play-enheter. När en Plug and Play-enhet ansluts till en version av Windows operativsystem som stöder denna typ av enhet, krävs ingen drivrutin för enheten som ska användas som avsett. Till exempel om Windows identifierar en Bluetoothhögtalare vet operativsystemet att enheten har klasstypen **Högtalare**. Därför behandlar den enheten som en högtalare. Ingen ytterligare inställning krävs. När det gäller kassaenheter kan många USB-enheter anslutas, och Windows känner igen dem som Human Interface Devices (HID). Den kan dock inte avgöra kapaciteten som ingår i enheten eftersom enheten inte anger klass eller typ av enhet. I Windows 10 har enhetsklasser för streckkodsläsare och MSR lagts till. Om därför en enhet förklarar sig till Windows 10 som en enhet av någon av dessa klasser, kommer Windows att lyssna efter händelser från enheten vid lämpliga tidpunkter. Modern POS stöder UWP MSR:er och skannrar. Därför kan enheten användas när den är klar för indata från en av dessa enheter och en enhet som tillhör någon av dessa klasser är ansluten. Till exempel om en UWP-streckkodsskanner ansluts till en dator med Windows 10 och streckkodsinloggning har konfigurerats för Modern POS, ska streckkodsskannern aktiveras på inloggningsskärmen. Ingen ytterligare inställning krävs. Ytterligare klasser av UWP-enheter för kassa läggs till Windows. Dessa klasser innehåller klasser för kassalådor och kvittoskrivare. Stöd för dessa nya klasser i Modern POS väntar.

### <a name="keyboard-wedge"></a>Tangentbords-wedge

Tangentbords-wedgeenheter skickar data till datorn som om informationen har skrivits på ett tangentbord. Därför kommer som standard fältet som är aktiverat i kassan att ta emot data som skannas eller dras. I vissa fall kan detta orsaka att fel typ av data skannas till fel fält. Exempelvis kan en streckkod läsas in i ett fält som är avsett för inmatning av data för kreditkort. I de flesta fall finns en logik i kassan som avgör om data som skannas eller dras är en streckkod eller ett gortdragning. Därför hanteras data på rätt sätt. Men när enheterna ställs in som OPOS i stället för tangentbord-wedge-enheter finns det mer kontroll över hur data från dessa enheter kan förbrukas, eftersom man "känner till" mer om enheten som informationen kommer från. Exempelvis data från en streckkodsskanner identifieras automatiskt som en streckkod och den associerade posten i databasen hittas enklare och snabbare än om en generisk söksträng användes, vilket gäller för tangentbord-wedge-enheter.

### <a name="native-printer"></a>Inbyggd skrivare

Inbyggda (eller "Enhet" som typen heter i maskinvaruprofilen) skrivare kan konfigureras för att uppmana användaren att välja en skrivare som har konfigurerats för datorn. När en skrivare av typen **Enhet** konfigureras om Modern POS upptäcker ett utskriftskommando uppmanas användaren att välja en skrivare i en lista. Detta skiljer sig från funktionen för Windows-drivrutiner genom att **Windows** skrivartyp i maskinvaruprofilen inte visar en lista över skrivare. I stället förutsätts att en namngiven skrivare anges i fältet **Enhetsnamn**.

### <a name="windows"></a>Windows

Enhetstypen **Windows** används endast för skrivare. När en Windows-skrivare konfigureras i maskinvaruprofilen måste skrivarnamn anges. När Modern POS hittar skrivarhändelser, om Windows-skrivaren har konfigurerats, skickas händelsen till den angivna Windows-skrivaren. Användaren ombeds inte att välja en skrivare.

### <a name="network"></a>Nätverk

Nätverkets adresserbara kassalådor, kvittoskrivare och betalningsterminaler kan användas i ett nätverk direkt antingen via maskinvarustationen Interprocess Communications (IPC) som ingår i Modern POS för Windows- och Modern POS för Android-program eller maskinvarustationen IIS för andra Modern POS-klienter.

## <a name="hardware-station-deployment-options"></a>Distributionsalternativ för maskinvarustation

### <a name="ipc-built-in"></a>IPC (inbyggd)

Maskinvarustationen Interprocess Communications (IPC) är inbyggd i Modern POS för Windows- and Modern POS för Android-programmet. Om du vill använda maskinvarustationen IPC tilldelar du en maskinvaruprofil till en kassa som kommer att använda Modern POS för Windows-program. Skapa en maskinvarustation av typen **Dedikerad** för butiken som kassan ska användas i. När du startar Modern POS kommer maskinvarustationen IPC att vara aktiv och den kringutrustning för kassa som har konfigurerats är klar att användas. Om du tillfälligt inte kräver lokal maskinvara av någon anledning använder du åtgärden **hantera maskinvarustationer** för att inaktivera maskinvarustationkapaciteterna. Modern POS kan också använda IPC maskinvarustation till att kommunicera direkt med kringutrustning i nätverket.

### <a name="iis"></a>IIS

Du kan använda IIS eller fristående version av maskinvarustation på två sätt. Beskrivningen "IIS" innebär att POS-programmet ansluter till maskinvarustationen via Microsoft Internet Information Services. POS-programmet ansluter till IIS maskinvarustation via webbtjänster som körs på en dator där enheterna är anslutna. När IIS används kan butikskringutrustningen som är ansluten till en maskinvarustation användas av alla kassaregister som finns i samma nätverk som IIS maskinvarustation. Eftersom endast Modern POS för Windows har inbyggt stöd för butikskringutrustning, måste andra Modern POS-program använda IIS maskinvarustation för att kommunicera med kassakringutrustning som har konfigurerats i maskinvaruprofilen. Varje förekomst av IIS-maskinvarustation kräver därför en dator som kör webbtjänsten och program som kommunicerar med enheter. IIS maskinvarustation krävs för alla icke - Windows Modern POS-program.

#### <a name="dedicated"></a>Dedikerad

Modern POS använder maskinvarustationer som ingår i typen **dedikerad** för att identifiera att kringutrustning ansluts direkt till den dator där programmet används. Men typen **dedikerad** kan också användas för IIS maskinvarustationen. I ett traditionellt, fast kassascenario som använder Cloud POS som POS-program används maskinvarustationstypen **dedikerad** för IIS maskinvarustation som distribueras på samma dator som kör Cloud POS. Från ett butikskringutrustningsperspektiv har den dedikerade IIS maskinvarustationen bättre butikskringutrustningsstöd för traditionella, fasta POS-scenarier. Dedikerade maskinvarustationer stöder all kringutrustning som stöds i maskinvaruprofilen.

#### <a name="shared"></a>Delade

Delade maskinvarustationer som är avsedda att användas av flera POS-enheter under dagen. Delade maskinvarustationer optimeras för att endast stödja kassalådor, kvittoskrivare och betalningsterminaler. Du kan inte direkt ansluta fristående streckkodsläsare, MSR:er, radvisningar, skalor andra enheter. I annat fall inträffar konflikter när flera POS-enheter försöker göra anspråk på denna kringutrustning samtidigt. Här visas hur konflikter hanteras för enheter som stöds:

- **Kassalådan** – kassalådan öppnas via en händelse som skickas till enheten. Endast problem som kan uppstå när en kassalådan kallas uppstår om kassalådan är redan öppen. När det gäller delade maskinvaustationer ska kassalådan vara inställd på **delade** i maskinvaruprofilen. Den här inställningen förhindrar att POS kontrollerar om kassalådan redan är öppen när du skickar öppna-kommandon.
- **Kvittoskrivaren** – om två kvittoutskriftskommandon skickas till maskinvarustationen på samma gång kan ett kommando försvinna, beroende på vilken enhet. Vissa enheter har internminne eller poolning som kan förhindra att det här problemet. Om utskriftskommando misslyckas kommer kassören att få ett felmeddelande och kan försöka utföra utskriftkommandot från kassan.
- **Betalningsterminal** – om en kassör försöker utföra en transaktion som redan används på en betalningsterminal får kassören ett meddelande att terminalen används och uppmanas att försöka igen senare. Vanligtvis kan kassörer se att en terminal används redan och ska vänta tills den andra transaktionen har slutförts innan de kan försöka igen.

Validering planeras för kommande versioner för att identifiera om enheter som inte stöds har ställts in för en maskinvaruprofil som är mappad till en delad maskinvarustation. Om några enheter som inte stöds upptäcks får användaren ett meddelande om att enheterna inte stöder delad maskinvarustationer. När det gäller delade maskinvarustationer i **Välj vid anbudet** är inställt på **Ja** på registernivån. Kassaanvändaren uppmanas att välja maskinvarustation när ett anbud har valts för en transaktion i kassan. När maskinvarustationen markeras endast vid tid för anbud läggs maskinvarustationen till direkt till kassaarbetsflödet för mobila scenarier. Som en extra förmån används inte radvisning för betalningsterminal för gemensamma scenarion. Om betalningsterminal används som en radvisning hindras andra användare från att använda terminalen förrän transaktionen har slutförts. Mobila scenarier kan rader läggas till en transaktion under en längre period. Därför krävs alternativet **Välj vid anbudet** krävs för att garantera optimala enhetstillgänglighet.

### <a name="network-peripherals"></a>Nätverkskringutrustning

Nätverketsbeteckningen för enheter i maskinvaruprofilen kan kassalådor, kvittoskrivare och betalningsterminaler anslutas via en nätverksanslutning.

#### <a name="modern-pos-for-windows"></a>Modern POS för Windows

Du kan ange IP-adresser för nätverkets kringutrustning på två ställen. Om Modern POS Windows-klienten använder en uppsättning kringutrustning i nätverket, bör du ange IP-adresserna för dessa enheter med hjälp av alternativet **IP-konfigurationen för** i åtgärdsfönstret för själva journalen. När det gäller enheter som ska delas mellan kassor, kan en maskinvaruprofil som har tilldelats nätverksenheter mappas direkt till en delad maskinvarustation. Markera den maskinvarustation om du vill tilldela IP-adresser på sidan **Butiker** och använd sedan alternativet **IP-konfiguration** i avsnittet **maskinvarustationer** för att ange alla nätverksenheter som är tilldelade till maskinvarustationen. För maskinvarustationer som endast har nätverksenheter har du inte distribuera själva maskinvarustationen. Då kräver maskinvarustationen endast för att konceptuellt gruppera nätverket adresserbara enheter enligt deras placering i butiken.

#### <a name="modern-pos-for-android"></a>Modern POS för Android

Fr.o.m. Retail version 8.1.3 innehåller Modern POS för Android-program innehåller en inbyggd IPC-maskinvarustation. Maskinvarustationen stöder kommunikation med nätverksskrivare och betalningsanslutningar. För mer information, besök [Artikeln appen Hybrid för Android dokument](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/hybridapp#dedicated-hardware-station-support-for-the-hybrid-android-app). 

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>Cloud POS och Modern POS för iOS

Logiken som driver fysiskt anslutna och nätverkets adresserbara kringutrustning finns på maskinvarustationen. För alla POS-klienter utom Modern POS för Windows, måste en station för IIS maskinvarustationer måste därför distribueras och aktivera kassan för att kommunicera med kringutrustning, oavsett om denna kringutrustning är fysiskt ansluten till en maskinvarustation eller beskrivas i nätverket.

## <a name="setup-and-configuration"></a>Installation och konfiguration

### <a name="hardware-station-installation"></a>Installation av maskinvarustation

För mer information se [Konfiguration och installation av Retail hardware station](retail-hardware-station-configuration-installation.md)

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Modern POS för Windows-installation och konfiguration

Mer information om [Retail Modern POS inställning och konfiguration finns i](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>OPOS inställning och konfiguration av enheter

Mer information om OPOS-komponenter finns i avsnittet "Gränssnitt som stöds" i det här dokumentet. Vanligtvis tillhandahålls OPOS-drivrutiner av enhetens tillverkare. När en OPOS-drivrutin installeras läggs en nyckel till i Windows-registret på någon av följande platser:

- **32-bitarssystem:** HKEY\_LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS
- **64-bitarssystem:** HKEY\_LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Konfigurerade enheter är organiserade enligt enhetsklassen OPOS inom registerplatsen ServiceOPOS. Flera drivrutiner sparas.

## <a name="supported-scenarios-by-hardware-station-type"></a>Scenarier som stöds efter maskinvarustationstyp

### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Klientstöd – IPC maskinvarustation jämfört med IIS maskinvarustation

I följande tabell visas topologier och distributionsscenarier som stöds.

| Kund      | IPC maskinvarustation | IIS maskinvarustation |
|-------------|----------------------|----------------------|
| Windows-app | Ja                  | Ja                  |
| Cloud POS   | Nej                   | Ja                  |
| Android     | Ja                  | Ja                  |
| iOS         | Nej                   | Ja                  |

### <a name="network-peripherals"></a>Nätverkskringutrustning

Nätverkskringutrustning kan användas direkt via maskinvarustationen som ingår i Modern POS för Windows-program. Du måste distribuera en IIS maskinvarustation för andra klienter.

| Kund      | IPC maskinvarustation | IIS maskinvarustation |
|-------------|----------------------|----------------------|
| Windows-app | Ja                  | Ja                  |
| Cloud POS   | Nej                   | Ja                  |
| Android     | Ja                  | Ja                  |
| iOS         | Nej                   | Ja                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Enhetstyper som stöds efter maskinvarustationstyp

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS för Windows med en IPC maskinvarustation (inbyggt)

<table>
<thead>
<tr>
<th>Enhetsklass som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr>
<td>Skrivare</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Enhet</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Skrivare 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Enhet</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Radvisning</td>
<td>OPOS</td>
</tr>
<tr>
<td>Dubbla bildskärmar</td>
<td>Windows-drivrutin</td>
</tr>
<tr>
<td>MSR</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (Ingen inställning krävs.)</li>
<li>Tangentbord-wedge (Ingen inställning krävs.)</li>
</ul>
</td>
</tr>
<tr>
<td>Utställare</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk
<p><strong>Obs!</strong> Bara en enda kassalåda kan ställas in om <strong>Använda delade skift</strong> konfigureras i kassalådan.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Kassalåda 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk
<p><strong>Obs!</strong> Bara en enda kassalåda kan ställas in om <strong>Använda delade skift</strong> konfigureras i kassalådan.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Skanner</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (Ingen inställning krävs.)</li>
<li>Tangentbord-wedge (Ingen inställning krävs.)</li>
</ul>
</td>
</tr>
<tr>
<td>Skanner 2</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (Ingen inställning krävs.)</li>
<li>Tangentbord-wedge (Ingen inställning krävs.)</li>
</ul>
</td>
</tr>
<tr>
<td>Skala</td>
<td>OPOS</td>
</tr>
<tr>
<td>PIN-knappsats</td>
<td>OPOS (Support tillhandahålls via anpassning av betalningskopplingen).</td>
</tr>
<tr>
<td>Digital signatur</td>
<td>OPOS</td>
</tr>
<tr>
<td>Betalterminal </td>
<td>
<ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (För mer information, se dokumentationen för betalningsanslutning)</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Alla Modern POS-klienter som har en dedikerad IIS maskinvarustation

> [!NOTE]
> När IIS maskinvarustation är "dedikerad", finns ett samarbete mellan POS-klienten och maskinvarustationen.

<table>
<thead>
<tr>
<th>Enhetsklass som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr>
<td>Skrivare</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin
<p><strong>Obs!</strong> För Windows-skrivare i ett nätverk, måste användaren av maskinvarustationen ha behörighet att komma åt skrivaren.</p>
</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Skrivare 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Radvisning</td>
<td>OPOS</td>
</tr>
<tr>
<td>MSR</td>
<td>OPOS</td>
</tr>
<tr>
<td>Utställare</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk
<p><strong>Obs!</strong> Bara en enda kassalåda per hårdvaruprofil kan ställas in om <strong>Använda delade skift</strong> konfigureras i kassalådan.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Kassalåda 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Skanner</td>
<td>OPOS</td>
</tr>
<tr>
<td>Skanner 2</td>
<td>OPOS</td>
</tr>
<tr>
<td>Skala</td>
<td>OPOS</td>
</tr>
<tr>
<td>PIN-knappsats</td>
<td>OPOS (Support tillhandahålls via anpassning av betalningskopplingen).</td>
</tr>
<tr>
<td>Sig. fånga</td>
<td>OPOS</td>
</tr>
<tr>
<td>Betalterminal </td>
<td>
<ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (För mer information, se dokumentationen för betalningsanslutning)</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Alla Modern POS-klienter som har en delad IIS maskinvarustation

> [!NOTE]
> När IIS maskinvarustation "delas" kan flera enheter använda maskinvarustationen samtidigt. I det här scenariot bör du använda de enheter som visas i följande tabell. Om du försöker dela enheter som inte visas här, t.ex. streckkodsläsare och MSR:er, inträffar fel när flera enheter försöker göra anspråk på samma enhet. I framtiden kommer en sådan konfiguration uttryckligen att förhindras.

<table>
<thead>
<tr>
<th>Enhetsklass som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr>
<td>Skrivare</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin
<p><strong>Obs!</strong> För Windows-skrivare i ett nätverk, måste användaren av maskinvarustationen ha behörighet att komma åt skrivaren.</p>
</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Skrivare 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Utställare</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk
<p><strong>Obs!</strong> Bara en enda kassalåda per hårdvaruprofil kan ställas in om <strong>Använda delade skift</strong> konfigureras i kassalådan.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Kassalåda 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Nätverk</li>
</ul>
</td>
</tr>
<tr>
<td>Betalterminal </td>
<td>
<ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (För mer information, se dokumentationen för betalningsanslutning)</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguration för scenarier som stöds

Mer information om hur du skapar maskinvaruprofiler finns i [definiera och underhålla kanalklienter såsom register och maskinvarustationer](define-maintain-channel-clients-registers-hw-stations.md).

> [!NOTE]
> För Retail version 1611, maskinvarustationprofilen används inte längre. Attribut som du tidigare skapat i maskinvaruprofilstation ingår nu i själva maskinvarustationen.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS för Windows med en IPC maskinvarustation (inbyggt)

Den här konfigurationen är de vanligaste konfigurationen för traditionella, fasta kassor. I det här scenariot mappas maskinvaruprofilinformation till själva kassan direkt. EFT-terminalnummer bör också anges i själva kassan. För att konfigurera denna konfiguration, följ dessa steg.

1. Skapa en maskinvaruprofil där all kringutrustning har konfigurerats.
2. Mappa maskinvaruprofilen till en kassa.
3. Skapa en maskinvarustation av typen **Dedikerad** för butiken som kassan ska användas i. En beskrivning är valfri.

    > [!NOTE]
    > Du behöver inte ange andra egenskaper för maskinvarustationen. Alla övriga uppgifter som krävs till exempel maskinvaruprofilen kommer från själva kassan.

4. Klicka på **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
5. Välj distributionsschema **1090** för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
6. Välj distributionsschema **1070** för att synkronisera den nya maskinvarustationen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
7. Installera och aktivera Modern POS för Windows.
8. Starta Modern POS för Windows och börja använda ansluten kringutrustning.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Alla Modern POS-klienter som har en dedikerad IIS maskinvarustation

Den här konfigurationen kan användas för alla Modern POS-klienter som har en maskinvarustation som används exklusivt av en kassa. För att konfigurera denna konfiguration, följ dessa steg.

1. Skapa en maskinvaruprofil där all kringutrustning har konfigurerats.
2. Skapa en maskinvarustation av typen **Dedikerad** för butiken som kassan ska användas i.
3. Ange följande egenskaper på dedikerade maskinvarustationen:

    - **Värdnamn** – namnet på värddatorn där maskinvarustationen körs.

        > [!NOTE]
        > Cloud POS kan lösa **localhost** för att avgöra den lokala datorn där Cloud POS körs. Certifikat som behövs för att länka en Cloud POS till maskinvarustationen måste dock även ha "Localhost" som datornamn. För att undvika problem bör du ange en instans av varje dedikerad maskinvarustation maskinvara för butiken som krävs. För varje maskinvarustation bör värdnamnet vara det specifika datornamn där maskinvarustationen ska distribueras.

    - **Port** – porten som ska användas för maskinvarustationen för att kommunicera med Modern POS-klienten.
    - **Maskinvaruprofil** – om maskinvaruprofilen inte ges på själva maskinvarustationen kommer maskinvaruprofilen som har tilldelats kassan att användas.
    - **EFT-POS-nummer** – det EFT terminal-ID som används när EFT-tillstånd skickas. Detta ID tillhandahålls av kreditkortsföretaget.
    - **Paketnamnet** – maskinvarustationspaketet att använda när maskinvarustationen distribueras.

4. Klicka på **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
5. Välj distributionsschema **1090** för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
6. Välj distributionsschema **1040** för att synkronisera den nya maskinvarustationen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
7. Installation av maskinvarustation. Mer information om hur du installerar maskinvarustationen finns [Konfiguration och installation av Retail hardware station](retail-hardware-station-configuration-installation.md).
8. Installera och aktivera Modern POS. Mer information om hur du installerar Modern POS finns si [Retail Modern POS konfiguration och installation](retail-modern-pos-device-activation.md).
9. Logga in i Modern POS och markera **Utföra en åtgärd som inte är en lådåtgärd**.
10. Starta åtgärden **hantera maskinvarustationer**.
11. Klicka på **Hantera**.
12. På sidan för maskinvarustationshantering ställer du in alternativet för att slå på maskinvarustationen.
13. Välj maskinvarustationen som ska användas och klicka sedan på **Para ihop**.
14. När maskinvarustationen har parts ihop klickar du på **Stäng**.
15. På maskinvarustationen urvalssida klickar du på den nyligen valda maskinvarustationen för att aktivera den.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Alla Modern POS-klienter som har en delad IIS maskinvarustation

Den här konfigurationen kan användas för alla Modern POS-klienter som delar maskinvarustation med andra enheter. För att konfigurera denna konfiguration, följ dessa steg.

1. Skapa en maskinvaruprofil där all kringutrustning har konfigurerats.
2. Skapa en maskinvarustation av typen **Delad** för butiken som kassan ska användas i.
3. Ange följande egenskaper på delade maskinvarustationen:

    - **Värdnamn** – namnet på värddatorn där maskinvarustationen körs.
    - **Beskrivning** – Text som hjälper identifiera vilken maskinvarustation, t ex **returnerar** eller **framför butiken**.
    - **Port** – porten som ska användas för maskinvarustationen för att kommunicera med Modern POS-klienten.
    - **Maskinvaruprofil** – för maskinvarustationer bör varje maskinvarustatio ha en maskinvaruprofil. Maskinvaruprofiler kan delas av maskinvarustationer, men de måste kopplas till varje maskinvarustation. Dessutom rekommenderar vi att du använder delade skift när flera enheter använder samma delade maskinvarustation. För att ställa in delat skift: Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**. För varje delad maskinvaruprofil, välj kassalådan och ange **Kassalåda för delat skift** till **Ja**.
    - **EFT-POS-nummer** – det EFT terminal-ID som används när EFT-tillstånd skickas. Detta ID tillhandahålls av kreditkortsföretaget.
    - **Paketnamnet** – maskinvarustationspaketet att använda när maskinvarustationen distribueras.

4. Upprepa steg 2 och 3 för varje ytterligare maskinvarustation som krävs i butiken.
5. Klicka på **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
6. Välj distributionsschema **1090** för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
7. Välj distributionsschema **1040** för att synkronisera den nya maskinvarustationen till butiken. Klicka på **Kör nu** för att synkronisera ändringar i kassan.
8. Installera maskinvarustationen på varje värddator som du angav i steg 2 och 3. Mer information om hur du installerar maskinvarustationen finns [Konfiguration och installation av Retail hardware station](retail-hardware-station-configuration-installation.md).
9. Installera och aktivera Modern POS. Mer information om hur du installerar Modern POS finns si [Retail Modern POS konfiguration och installation](retail-modern-pos-device-activation.md).
10. Logga in i Modern POS och markera **Utföra en åtgärd som inte är en lådåtgärd**.
11. Starta åtgärden **hantera maskinvarustationer**.
12. Klicka på **Hantera**.
13. På sidan för maskinvarustationshantering ställer du in alternativet för att slå på maskinvarustationen.
14. Välj maskinvarustationen som ska användas och klicka sedan på **Para ihop**.
15. Upprepa steg 14 för varje maskinvarustation som används i Modern POS.
16. När krävda maskinvarustationer är hopparade klickar du på **Stäng**.
17. På maskinvarustationen urvalssida klickar du på den nyligen valda maskinvarustationen för att aktivera den.

    > [!NOTE]
    > Om enheter ofta använder olika maskinvarustationer rekommenderar vi att du konfigurerar Modern POS för att uppmana kassörer att välja en maskinvarustation när de börjar anbudsprocessen. Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparat**. Markera kassan och ange alternativet **Välj vid anbud** till **Ja**. Använd distributionsschema **1090** för att synkronisera ändringar i databasen för kanalen.

## <a name="extensibility"></a>Utbyggbarhet

Information om tilläggsscenarier för maskinvarustationen finns i [maskinvarustationstillägg](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Säkerhet

Enligt gällande säkerhetsstandarder ska följande inställningar användas i en produktionsmiljö:

> [!NOTE]
> Installationsprogrammet för Hardware Station kommer automatiskt att göra dessa registerredigeringar som en del av installationen genom självbetjäning.

- Secure Sockets Layer (SSL) ska inaktiveras.
- Endast Transport Layer Security (TLS) version 1.2 (eller den aktuella versionen av högsta) ska aktiveras och användas.

    > [!NOTE]
    > SSL och alla versioner av TLS utom TLS 1.2 är inaktiverade som standard.

    Gör så här om du vill redigera eller aktivera dessa värden:

    1. Tryck på Windows-tangenten + R för att öppna ett **kör**-fönster.
    2. I **öppna** ange **Regedit**, och klicka sedan på **OK**.
    3. Om meddelanderutan **Kontroll av användarkonto** visas klickar du på **Ja**.
    4. I den **Registereditorn** fönstret, gå till **HKEY\_lokala\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Följande tangenter infogas automatiskt så att du bara kan ange TLS 1.2:

        - TLS 1.2Server:Enabled=1
        - TLS 1.2Server:DisabledByDefault=0
        - TLS 1.2Client:Enabled=1
        - TLS 1.2Client:DisabledByDefault=0
        - TLS 1.1Server:Enabled=0
        - TLS 1.1Client:Enabled=0
        - TLS 1.0Server:Enabled=0
        - TLS 1.0Client:Enabled=0
        - SSL 3.0Server:Enabled=0
        - SSL 3.0Client:Enabled=0
        - SSL 2.0Server:Enabled=0
        - SSL 2.0Client:Enabled=0

- Inga ytterligare portar öppnas, om de inte krävs av kända skäl.
- Resursdelning mellan ursprung måste inaktiveras och måste ange tillåtna underlag som accepteras.
- Endast betrodda certifikatutfärdare ska användas för att erhålla certifikat som ska användas på datorer som kör maskinvarustationen.

> [!NOTE]
> Det är viktigt att du läser igenom riktlinjerna för IIS och Payment Card Industry (PCI)-kraven.

## <a name="peripheral-simulator"></a>Kringutrustningssimulator

Mer information finns i [Kringutrustningssimulator för butik](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Microsoft-testad kringutrustning

### <a name="ipc-built-in-hardware-station"></a>IPC (inbyggd) maskinvarustation

Följande kringutrustning som har testats med IPC maskinvarustation som ingår i Modern POS för Windows.

#### <a name="printer"></a>Skrivare

| Tillverkare | Modell      | Gränssnitt | Kommentarer                |
|--------------|------------|-----------|-------------------------|
| Epson        | Tm-T88IV   | OPOS      |                         |
| Epson        | TM-T88V    | OPOS      |                         |
| Epson        | ePOS – Skriv ut | Anpassat    | Ansluten via nätverket   |
| Stjärna         | TSP650II   | OPOS      |                         |
| Stjärna         | TSP650II   | Anpassat    | Ansluten via nätverket   |
| Stjärna         | mPOP       | OPOS      | Ansluten via Bluetooth |
| HP           | F7M67AA    | OPOS      | Strömförsörjd USB             |

#### <a name="bar-code-scanner"></a>Streckkodsläsare

| Tillverkare  | Modell         | Gränssnitt | Kommentarer |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbol        | LS2208        | OPOS      |          |
| HP-integrerad | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>PIN-knappsats

| Tillverkare | Modell  | Gränssnitt | Kommentarer                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Anpassning av betalningskopplingen krävs |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkare | Modell        | Gränssnitt | Kommentarer                                                                       |
|--------------|--------------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300        | Anpassa    | Anpassning av betalningskopplingen krävs                                |
| VeriFone     | MX925        | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915        | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | Se kommentarer | Adyen     | Adyen-anslutaren stöder alla enheter som anges [här](https://www.adyen.com/pos-payments/terminals) |

#### <a name="cash-drawer"></a>Kassalåda

| Tillverkare | Modell     | Gränssnitt | Kommentarer                |
|--------------|-----------|-----------|-------------------------|
| Stjärna         | mPOP      | OPOS      | Ansluten via Bluetooth |
| APG          | Atwood    | Anpassa    | Ansluten via nätverket   |
| Stjärna         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Radvisning

| Tillverkare  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| HP-integrerad | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Digital signatur

| Tillverkare | Modell  | Gränssnitt | Kommentarer |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skala

| Tillverkare | Modell         | Gränssnitt | Kommentarer |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Tillverkare | Modell       | Gränssnitt | Kommentarer |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Dedikerad IIS maskinvarustation

Följande kringutrustning har testats med hjälp av en särskild (Ej delad) IIS maskinvarustation tillsammans med Modern POS for Windows och Cloud POS.

#### <a name="printer"></a>Skrivare

| Tillverkare | Modell    | Gränssnitt | Kommentarer                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Stjärna         | TSP650II | OPOS      |                           |
| Stjärna         | TSP650II | Anpassa    | Ansluten via nätverket     |
| HP           | F7M67AA  | OPOS      | Strömförsörjd USB               |

#### <a name="bar-code-scanner"></a>Streckkodsläsare

| Tillverkare  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Symbol        | LS2208  | OPOS      |          |
| HP-integrerad | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>PIN-knappsats

| Tillverkare | Modell  | Gränssnitt | Kommentarer                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Anpassning av betalningskopplingen krävs |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkare | Modell | Gränssnitt | Kommentarer                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Anpassa    | Anpassning av betalningskopplingen krävs                                |
| VeriFone     | MX925 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |

#### <a name="cash-drawer"></a>Kassalåda

| Tillverkare | Modell     | Gränssnitt | Kommentarer              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Anpassa    | Ansluten via nätverket |
| Stjärna         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Radvisning

| Tillverkare  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| HP-integrerad | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Digital signatur

| Tillverkare | Modell  | Gränssnitt | Kommentarer |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skala

| Tillverkare | Modell         | Gränssnitt | Kommentarer |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Tillverkare | Modell       | Gränssnitt | Kommentarer |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Delad IIS maskinvarustation

Följande kringutrustning har testats med hjälp av en delad IIS maskinvarustation tillsammans med Modern POS for Windows och Cloud POS.

> [!NOTE]
> Endast en skrivare, betalningsterminal och kassalåda stöds.

#### <a name="printer"></a>Skrivare

| Tillverkare | Modell    | Gränssnitt | Kommentarer                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Stjärna         | TSP650II | OPOS      |                           |
| Stjärna         | TSP650II | Anpassa    | Ansluten via nätverket     |
| HP           | F7M67AA  | OPOS      | Strömförsörjd USB               |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkare | Modell | Gränssnitt | Kommentarer                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |

#### <a name="cash-drawer"></a>Kassalåda

| Tillverkare | Modell     | Gränssnitt | Kommentarer              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Anpassa    | Ansluten via nätverket |
| Stjärna         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Felsökning

### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS kan identifiera maskinvarustation i listan för val men kan inte utföra parning

**Lösning:** kontrollera listan över potentiella felpunkter:

- Datorn som körs Modern POS litar på certifikatet som används på datorn som kör hårdvarustationen.

    - Kontrollera inställningarna i en webbläsare genom att gå till följande URL: `https://<Computer Name>:<Port Number>/HardwareStation/ping`.
    - URL:en använder ping för att verifiera att datorn kan nås och webbläsaren anger om certifikatet är betrott. (Till exempel i Internet Explorer visas en låsikon i adressfältet. När du klickar på ikonen kontrollerar Internet Explorer om certifikatet är betrott för närvarande. Du kan installera certifikatet på den lokala datorn genom att visa information om certifikatet visas.)

- Den port som används av maskinvarustationen öppnas i brandväggen på datorn som kör maskinvarustationen.
- Maskinvarustationen har installerats korrekt handelskontoinformation via verktyget Installera handelsinformation som ska köras i slutet av installationsprogrammet för Maskinvarustationen.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS kan inte identifiera Hardware Station i listan för val

**Lösning:** något av följande faktorer kan orsaka problemet:

- Hardware Station har inte ställts in korrekt i administrationen. Använd instruktionerna tidigare i det här avsnittet för att kontrollera att maskinvarustationprofilen och maskinvarustationen har angetts korrekt.
- Jobb har inte körts om du vill uppdatera kanalkonfigurationen. I det här fallet kör du jobbet 1070 för kanalkonfiguration.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS innehåller inte de nya inställningarna för kassalådan

**Solution:** Stäng den aktuella batchen. Ändringar i kassalådan uppdateras inte till Modern POS tills den aktuella batchen stängs.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Modern POS rapporterar ett problem med en officiell kringutrustning

**Lösning:** här följer några vanliga orsaker till problemet:

- Kontrollera att andra konfigurationsverktyg för enhetens drivrutin är stängda. Om verktygen körs hindrar de att Modern POS eller maskinvarustationen begär enheten.
- Om butikskringutrustningen delas med flera kassaenheter, kontrollerar du att den tillhör en av följande kategorier:

    - Kassalåda
    - Kvittoskrivare
    - Betalterminal 

    Om kringutrustningen inte tillhör någon av dessa kategorier, är inte maskinvarustationen utformad för kringutrustning som ska delas mellan flera kassaenheter.

- Drivrutiner kan ibland orsaka att common control objekt (CCOs) inte fungerar korrekt. Om en enhet nyligen har installerats men inte fungerar korrekt eller om du upplever andra problem, kan du ofta las problemet genom att installera om CCO. Du kan hämta CCO på <http://monroecs.com/oposccos_current.htm>.
- Om du ofta ändrar kringutrustning vid testning eller felsökning, kan du behöva återställa IIS i stället att uppdatera själva cacheminnet. Återställ IIS genom att följa dessa steg:

    1. Från menyn **starta** skriver du **CMD**.
    2. Högerklicka i sökresultatet **kommandotolk**, och klicka sedan på **kör som administratör**.
    3. I fönstret **kommandotolk** skriver du **iisreset/restart** och trycker på RETUR.
    4. Starta om Modern POS när IIS har startats om.

- När du ofta gör ändringar i kringutrustning, om du ofta också startar och stänger kassaklienten kan dllhost-processen från en tidigare kassasession påverka den aktuella sessionen. En enhet kan då inte användas förrän du stänger värden dynamisk-länkbiblioteket (DLL) som hanterar den senaste sessionen. Gör följande om du vill stänga dll-värden:

    1. Från menyn **starta** skriver du **Uppgiftshanterare**.
    2. I sökresultaten klickar du på **Uppgiftshanterare**.
    3. I ppgiftshanteraren på fliken **uppgifter** klickar du på kolumnrubriken som heter **namn** för att sorteras tabellen i alfabetisk ordning efter namn.
    4. Bläddra nedåt tills du hittar dllhost.exe.
    5. Markera varje DLL-värd och klicka på **Avsluta uppgift**.
    6. Starta om Modern POS när dll-värdar har avslutats.

## <a name="additional-resources"></a>Ytterligare resurser

[Kringutrustningssimulator för Retail](dev-itpro/retail-peripheral-simulator.md)
