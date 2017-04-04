---
title: "Översikt över Retail-kringutrustning"
description: "Det här avsnittet förklaras koncept som är relaterade till retail kringutrustning. Här beskrivs olika sätt att ansluta kringutrustning till försäljningsstället (PO) och komponenterna som är ansvarig för anslutning till KASSAN."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Översikt över Retail-kringutrustning

Det här avsnittet förklaras koncept som är relaterade till retail kringutrustning. Här beskrivs olika sätt att ansluta kringutrustning till försäljningsstället (PO) och komponenterna som är ansvarig för anslutning till KASSAN.

<a name="concepts"></a>Begrepp
--------

### <a name="pos-registers"></a>Kassaregister

Navigering: Klicka **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**. Mittpunkt registrera försäljning (PO) är en enhet som används för att definiera egenskaperna hos en viss instans av KASSAN. Dessa egenskaper omfattar maskinvaruprofil eller inställningar för retail-kringutrustning som ska användas vid kassan och butiken som kassan har mappats till den visuella upplevelsen när användare loggar in på registret.

### <a name="devices"></a>Enheter

Navigering: Klicka **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**enheter**. En enhet är en entitet som representerar en fysisk instans av en enhet som är mappad till ett kassaregister. När en enhet skapas kopplas den till POS register. Enhetsentiteten spårar information om när ett kassaregister aktiveras, vilken typ av klient som används och programpaketet som har distribuerats till en viss enhet. Enheter som kan mappas till följande programtyper: Modern Retail POS, moln Retail POS, Modern Kundinformationen – Windows Phone, Modern Retail POS – Android och Modern Kundinformationen – iOS.

### <a name="retail-modern-pos"></a>Retail Modern POS

Modern POS är POS-program för Microsoft Windows. Använda du kan IPSec på 10 för Windows-operativsystem (OSs).

### <a name="cloud-pos"></a>Cloud POS

Molnet POS är en webbläsarbaserade versionen av Modern POS-program som kan användas i en webbläsare.

### <a name="modern-pos-for-ios"></a>Modern POS för iOS

Modern POS för iOS är en iOS-baserad version av programmet som kan distribueras i/o-enheter Modern POS.

### <a name="modern-pos-for-android"></a>Modern POS för Android

Modern POS för Android är en Android-baserad version av programmet som kan distribueras på en Android-enheter Modern POS.

### <a name="pos-peripherals"></a>POS-kringutrustning

POS-kringutrustning är enheter som uttryckligen har stöd för POS-funktioner. Här kringutrustningen är vanligtvis uppdelade i klasser. Mer information om dessa klasser finns i avsnittet "Klasser" i det här avsnittet.

### <a name="hardware-station"></a>Maskinvarustation

Navigering: Klicka **butik och handel**&gt;**kanaler**&gt;**detaljhandel**&gt;**alla detaljhandel**. Markera en butik och klicka på snabbfliken **Maskinvarustationer**. Den **maskinvara station** är en kanal inställningen som används för att definiera instanser där logiken retail kringutrustning ska distribueras. Inställningen på nivån kanalen används för att bestämma egenskaperna hos maskinvara stationen. Den används också lista maskinvara stationer som är tillgängliga för en Modern POS-förekomst i ett visst Arkiv. Stationen maskinvara ingår i Modern POS-program för Windows. Stationen maskinvara kan också distribueras separat som ett fristående program i Microsoft Internet Information Services (IIS). I detta fall hittar du det via ett nätverk.

### <a name="hardware-profile"></a>Maskinvaruprofil

Navigering: Klicka **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**. Maskinvaruprofilen är en lista över enheter som konfigurerats för ett kassaregister eller stationerna maskinvara. Maskinvaruprofilen kan mappas till ett kassaregister eller stationerna maskinvara.

## <a name="devices-classes"></a>Klasser av enheter
POS-kringutrustning är vanligtvis uppdelade i klasser. Det här avsnittet beskriver och ger en översikt över enheterna som stödjer Modern POS.

### <a name="printer"></a>Skrivare

Skrivare som är traditionella POS inleverans och hela sidan skrivare. Skrivare stöds via objektlänkning och inbäddning för gränssnitt för Retail POS (OPOS) och Microsoft Windows-drivrutin. Upp till två skrivare kan användas samtidigt. Den här funktionen har stöd för scenarier där cash-and-carry kundinleveranser trycks på kvittoskrivare, medan kundorder som medför mer information skrivs ut på skrivare över hela sidan. Kvittoskrivare kan vara direkt ansluten till en dator via USB, ansluten till ett nätverk via Ethernet och ansluten via Bluetooth.

### <a name="scanner"></a>Skanner

Upp till två streckkod kan skannrar användas samtidigt. Den här funktionen stöder scenarier där en skanner som är mer mobila krävs för att söka igenom stora eller tunga artiklar, medan en fast inbäddade skanner används för de flesta standardstorlek objekt utcheckning gånger snabbare. Skannrar kan stödjas genom OPOS Universal Windows plattform (UWP) eller tangentbordet wedge gränssnitt. USB och Bluetooth kan användas för att ansluta en skanner till en dator.

### <a name="msr"></a>MSR

En USB-kortläsare (MSR) kan konfigureras genom att använda OPOS-drivrutiner. Om du vill använda en fristående MSR för elektronisk överföring betalningstransaktioner måste MSR hanteras av en betalningsanslutning. Fristående MSRs kan användas för kundtransaktionen lojalitet medarbetare-inloggning och presentkort post, oberoende av betalningskopplingen.

### <a name="cash-drawer"></a>Kassalådan

Två kassalådor kan användas per maskinvaruprofilen. Den här funktionen kan två aktiva SKIFT per kassa kan användas samtidigt. När det gäller en delad SKIFT eller en kassalådan som används av flera mobila enheter för kassa samtidigt tillåts endast en kassalådan per maskinvaruprofil. Kassalådor kan anslutas direkt till en dator via USB, ansluten till ett nätverk eller ansluten till en kvittoskrivaren via ett RJ12 gränssnitt. I vissa fall kan kassalådor anslutas via Bluetooth.

### <a name="line-display"></a>Radvisning

Visar används för att visa produkter, transaktionen saldon och andra värdefull information under en transaktion till kunden. En radskärmen kan anslutas till datorn via USB genom att använda OPOS-drivrutiner.

### <a name="signature-capture"></a>Digital signatur

Signatur signaturer enheter kan anslutas direkt till en dator via USB genom att använda OPOS-drivrutiner. När signatur är konfigurerat uppmanas kunden att logga på enheten. När signaturen angivits visas för kassören för godkännande.

### <a name="scale"></a>Skala

Kan byggas ut kan anslutas till datorn via USP genom att använda OPOS-drivrutiner. När en produkt som är markerad som en "Weighed" produkt läggs till i en transaktion, POS läser vikten skalan lägger till produkten i transaktionen och den kvantitet skalan som används.

### <a name="pin-pad"></a>PIN-knappsats

Personlig kod nummer (PIN) pads stöds via OPOS, men de måste hanteras via en betalningsanslutning.

### <a name="secondary-display"></a>Sekundär bildskärm

När en sekundär skärm konfigureras används Windows nummervisning 2 till att visa grundläggande information. Syftet med den sekundära bildskärmen är att stödja oberoende programleverantörer tillägget eftersom och sekundära bildskärmen inte kan konfigureras och visar begränsat innehåll.

### <a name="payment-device"></a>Betalningsenhet

Stöd för betalningen implementeras via betalningskopplingen. Betalning enheter kan utföra en eller flera funktioner med andra klasser. Exempelvis kan en enhet betalning fungera som en MSR/kortläsare radskärmen, enhet för digital signatur eller PIN-knappsatsen. Stöd för enheter för betalningen implementeras oberoende av fristående enhet stöd för andra enheter som ingår i maskinvaruprofilen.

## <a name="supported-interfaces"></a>Gränssnitt som stöds
### <a name="opos"></a>OPOS

För att garantera att den största mängden enheter kan användas med Microsoft Dynamics 365 verksamhet – återförsäljning, OLE för POS branschstandard är primära retail kringutrustningen plattformar som stöds av Microsoft Dynamics 365 för verksamhet – Retail. OLE för POS-standarden anses vara framställt av den nationella Retail Federation (NRF), som fastställer kommunikationsprotokoll branschstandard för retail-kringutrustning. OPOS är en ATSC implementering av OLE för POS-standarden. Det utvecklades i mitten-av 1990-talet och uppdaterats sedan flera gånger. OPOS ger en enhet drivrutinarkitektur som ger enkel integrering av maskinvaruprofil för kassa med Windows-baserade POS-system. Hantera OPOS styr kommunikationen mellan kompatibel maskin- och programvaran POS. En OPOS-kontroll består av två delar:

-   **Kontrollobjekt** – control-objekt för en enhetsklass (t ex visar) tillhandahåller ett gränssnitt för programmet. Monroe konsulttjänster ([www.monroecs.com](http://www.monroecs.com/)) tillhandahåller en standardiserad uppsättning OPOS control-objekt som kallas common control-objekt (CCOs). I CCOs används för att testa komponenten Microsoft Dynamics 365 för verksamhet – Retail POS. Därför kan testningen garantera att, om Microsoft Dynamics 365 för verksamhet – Retail stöder en enhetsklass via OPOS många enhetstyper kan stödjas, under förutsättning att tillverkaren tillhandahåller ett serviceobjekt som skapats för OPOS. Du har inte uttryckligen Testa varje enhetstyp.
-   **Serviceobjekt** – ger kommunikation mellan control-objekt (CCO) och en enhet för serviceobjektet. Vanligtvis tillhandahålls serviceobjekt för en enhet av enhetens tillverkare. Men i vissa fall kan behöva du hämta serviceobjektet från tillverkarens webbplats. Ett nyare serviceobjekt kan vara tillgängliga. Se maskinvarudokumentationen för att hitta adressen till tillverkarens webbplats.

[![Kontrollera objekt och serviceobjekt](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) stöd för OPOS-implementeringen av OLE för POS hjälper till att garantera att om tillverkare och utgivare POS följer korrekt, POS-system och enheter som stöds kan samarbeta, även om de inte tidigare testats tillsammans. **Anmärkning:** stöd för OPOS garanterar dock inte stöd för alla enheter som har OPOS-drivrutiner. Microsoft Dynamics 365 för verksamhet – Retail måste först stöd för denna enhetstyp eller via OPOS-klass. Dessutom kanske serviceobjekt inte alltid är uppdaterade med den senaste versionen av de här CCOs. Du bör också vara medveten om att, i allmänhet kvaliteten på serviceobjektens varierar.

### <a name="windows"></a>Windows

Kvittoutskrift i KASSAN optimeras för OPOS. OPOS brukar vara betydligt snabbare än utskrift genom Windows. Därför är det en bra idé att använda OPOS, särskilt i retail miljöer där 40 tecken kvitton skrivs ut och gånger transaktionen måste vara snabb. För de flesta enheter används OPOS-kontroller. Vissa OPOS kvittoskrivare stöder emellertid drivrutiner i Windows. Genom att använda en Windows-drivrutin kan öppna du senaste teckensnitt och en nätverksskrivare för flera kassor. Det finns emellertid nackdelar med Windows-drivrutiner. Nedan följer några exempel på dessa nackdelar:

-   När Windows-drivrutiner används återges bilder innan utskrift sker. Därför brukar skrivs ut vara längre än på skrivare med OPOS-kontroller.
-   Enheter som är anslutna till skrivaren ("daisy-samman") fungerar inte när Windows-drivrutiner används. Exempelvis går det inte att öppna kassalådan eller följesedeln skrivaren word kanske inte som förväntat.
-   OPOS stöder även en mer omfattande uppsättning variabler som avser retail kvittoskrivare t ex skäras eller skriva ut följesedeln.

Om det finns kontroller för OPOS för Windows-skrivaren du använder fungera skrivaren ändå korrekt med Microsoft Dynamics 365 för verksamhet – Retail.

### <a name="universal-windows-platform"></a>Universal Windows-plattform

UWP, när det gäller retail kringutrustning hör till Windows stöd för Plug and Play-enheter. När en Plug and Play-enhet ansluts till en version av Windows-operativsystem som stöder denna typ av enhet, krävs ingen drivrutin för enheten som ska användas som tänkt. Till exempel om en bluetoothenhet högtalare identifieras, Operativsystemet vet att enheten har den **högtalare** klasstyp. Därför och det hanterar enheten som en högtalare. Inga ytterligare inställningar krävs. Många USB-enheter kan du ansluta för POS-enheter och Windows känner igen dem som Human Interface Devices (HIDs). Det kan dock inte avgöra kapaciteten som ingår i enheten eftersom enheten inte anger klassen eller typ av enhet. Klasser för streckkodsläsare och MSRs har lagts till i Windows-10. Därför om en enhet förklarar sig Windows 10 som en enhet av någon av dessa klasser, Windows kommer att lyssna efter händelser från enheten vid lämpliga tidpunkter. Modern POS stöder UWP MSRs och skannrar. Därför, när den är klar för indata från en av dessa enheter och ansluts enheten som tillhör någon av dessa klasser, enheten kan användas. Till exempel om en UWP streckkodsskanner ansluts till en dator med Windows 10 och inloggning streckkoden har konfigurerats för Modern POS, ska streckkod skannern aktiveras på skärmen-modulen. Inga ytterligare inställningar krävs. Ytterligare slag av mittpunkt service UWP enheter läggs till Windows. Dessa klasser innehåller klasser för kassalådor och kvittoskrivare. Stöd för dessa nya klasser i Modern POS väntar.

### <a name="keyboard-wedge"></a>Tangentbord wedge

Tangentbord wedge enheter skickar data till datorn som om informationen har skrivits på ett tangentbord. Därför normalt visas fältet aktiveras i KASSAN data som skannas eller draget. I vissa fall kan detta orsaka fel typ av data som ska läsas in i fel fält. Exempelvis kan en streckkod läsas in i ett fält som är avsett för inmatning av data för kreditkort. I de flesta fall finns logiken i KASSAN som avgör om data som skannas eller draget är en streckkod eller kort. Därför hanteras data på rätt sätt. Men när enheterna ställs in som OPOS i stället för tangentbordet wedge enheter finns mer kontroll över hur data från dessa enheter kan förbrukas, eftersom flera "kallas" om enheten som informationen kommer från. Exempelvis data från en streckkodsskanner identifieras automatiskt som en streckkod och den associerade posten i databasen hittas enklare och snabbare än om en sträng allmän sökning användes som gäller för tangentbordet wedge enheter.

### <a name="native-printer"></a>Inbyggd skrivare

Inbyggda (eller "Enhet" som heter i maskinvaruprofilen) skrivare kan konfigureras för att uppmana användaren att välja en skrivare som har konfigurerats för datorn. När en skrivare av den **enhet** typ konfigureras om Modern POS upptäcker en utskrift, uppmanas användaren att välja en skrivare i en lista. Detta skiljer sig från funktionen för drivrutiner i Windows genom att den **Windows** skrivartyp maskinvaruprofilen inte visas en lista över skrivare. I stället förutsätts att en namngiven skrivare anges i den **enhetsnamnet** fält.

### <a name="windows"></a>Windows

Den **Windows** enhetstyp används för endast skrivare. När en Windows-skrivare konfigureras i maskinvaruprofilen måste skrivarnamn anges. Vid Modern POS ut händelser om Windows-skrivare konfigureras, skickas händelsen till den angivna skrivaren i Windows. Användaren ombeds inte att välja en skrivare.

### <a name="network"></a>Nätverk

Nätverket adresserbara kassalådor kvittoskrivare och betalningsterminaler kan användas i ett nätverk direkt via ///"Interprocess kommunikation (IPC) maskinvara stationen som ingår i Modern POS för Windows-program eller maskinvara stationen IIS för andra klienter Modern POS.

## <a name="hardware-station-deployment-options"></a>Maskinvara station distributionsalternativ
### <a name="ipc-built-in"></a>IPC (inbyggt)

Stationen maskinvara ///"Interprocess kommunikation (IPC) ingår i Modern POS för Windows-program. Om du vill använda maskinvara stationen IPC Tilldela maskinvaruprofil en journal som används i moderna POS för Windows-program. Skapa en fönsterstation maskinvara från den **dedikerad** för butiken som kassan ska användas. När du startar Modern POS stationen IPC maskinvara kommer att vara aktiv och POS kringutrustningen som har konfigurerats är klart att användas. Om du tillfälligt inte kräver lokal maskinvara av någon anledning använder den **hantera maskinvara stationer** åtgärd för att inaktivera station maskinvarukapaciteterna. Modern POS kan också använda maskinvara IPC stationen kan kommunicera direkt med kringutrustning i nätverket.

### <a name="iis"></a>IIS

Du kan använda IIS eller fristående version av stationen maskinvara på två sätt. Beskrivningen "IIS" innebär att programmet POS ansluter till stationen maskinvara via Microsoft Internet Information Services. POS-programmet ansluter till IIS maskinvara stationen via webbtjänster som körs på en dator där enheterna är anslutna. När IIS används retail kringutrustningen som är anslutna till en station maskinvara kan användas av alla kassaregister finns i samma nätverk som IIS maskinvara stationen. Eftersom endast Modern POS för Windows har inbyggt stöd för retail-kringutrustning, måste andra Modern POS-program använda maskinvara stationen IIS för att kommunicera med POS kringutrustning som har konfigurerats i maskinvaruprofilen. Varje förekomst av maskinvara stationen IIS kräver därför en dator som kör webbtjänsten och program som kommunicerar med enheter. Stationen IIS maskinvara krävs för alla icke - Windows Modern POS-program.

#### <a name="dedicated"></a>Dedikerad

Använder moderna POS-stationer maskinvara som ingår i den **dedikerad** typ för att identifiera kringutrustning ansluts direkt till den dator där programmet används. Men den **dedikerad** typ kan också användas för IIS maskinvara stationer. I ett traditionellt, fast POS-scenario som använder programmet POS molnbaserad kassa i **dedikerad** maskinvara stationstyp används för IIS maskinvara stationer som distribueras på samma dator som kör molnbaserad kassa. Ur serverklusterperspektiv retail kringutrustning retail bättre dedikerad maskinvara stationen IIS har stöd för kringutrustning för traditionella, fast POS scenarier. Stationer dedikerad maskinvara stöder all kringutrustning som stöds i maskinvaruprofilen.

#### <a name="shared"></a>Delade

Dela maskinvara stationer som är avsedda att användas av flera POS-enheter under dagen. Dela maskinvara stationer optimeras för att stöd endast kassalådor kvittoskrivare och betalningsterminaler. Du kan inte direkt ansluta streckkodsläsare fristående MSRs, visar, ändrar eller andra enheter. I annat fall inträffar konflikter när flera POS-enheter försöker göra anspråk på dessa kringutrustning samtidigt. Här visas hur konflikter hanteras för enheter som stöds:

-   **Kassalådan** – kassalådan öppnas via en händelse som skickas till enheten. Endast problem som kan uppstå när en kassalådan kallas uppstår om kassalådan är redan öppen. När det gäller delade maskinvara stationer kassalådan ska vara inställd på **delade** i maskinvaruprofilen. Den här inställningen förhindrar POS kontrollerar om kassalådan redan är öppen när du skickar den öppna-kommandon.
-   **Kvittoskrivaren** – om två inleverans utskriftskommandon skickas till stationen maskinvara på samma gång ett kommando kan försvinna, beroende på vilken enhet. Vissa enheter har internminne eller på serversidan som kan förhindra att det här problemet. Om inte innehåller någon bekräftelse utskriftskommando för en, kassören får du ett felmeddelande och kan försöka utföra kommandot print från KASSAN.
-   **Betalning terminal** – om en kassör försöker lämna anbud på en transaktion som redan används på en terminal betalning meddelandet meddelar kassören att terminalen används och frågar uppmanas att försöka igen senare. Vanligtvis kan kassörer se att en terminal används redan och ska vänta tills den andra transaktionen har slutförts innan de kan lämna anbud igen.

Validering planeras för kommande versioner att identifiera om enheter som inte stöds har ställts in för en maskinvaruprofil som är mappat till en station delade maskinvara. Om några enheter stöds inte upptäcks får användaren ett meddelande om att enheterna inte stöder delad maskinvara stationer. När det gäller delade maskinvara stationer i **markerar vid inbjudan att lämna anbud** är inställt på **Ja** på nivån i registret. POS användaren uppmanas sedan att välja stationerna maskinvara när ett anbud har valts för en transaktion i KASSAN. När maskinvara stationen markeras endast när betalningsmedel läggs maskinvara station markeringen direkt till POS arbetsflödet för mobila scenarier. Som en extra förmån används inte radskärmen för betalningen terminal för gemensamma scenarion. Om betalningen terminal som en radskärmen, hindras andra användare från att använda terminalen förrän transaktionen har slutförts. Mobila scenarier kan rader läggas till en transaktion under en längre period. Därför den **Välj vid inbjudan att lämna anbud** alternativet krävs för att garantera optimala enhet tillgänglighet.

### <a name="network-peripherals"></a>Nätverk-kringutrustning

Nätverket beteckningen för enheter i maskinvaruprofilen kan kassalådor kvittoskrivare och betalningsterminaler anslutas via en nätverksanslutning.

#### <a name="modern-pos-for-windows"></a>Modern POS för Windows

Du kan ange IP-adresser för nätverket kringutrustning på två ställen. Om Modern POS Windows-klienten använder en uppsättning kringutrustning i nätverket, bör du ange IP-adresserna för dessa enheter med hjälp av den **IP-konfigurationen för** alternativet i åtgärdsfönstret för själva journalen. När det gäller enheter som ska delas mellan kassor, kan en maskinvaruprofil som har tilldelats nätverksenheter mappas direkt till en station delade maskinvara. Markera den stationen maskinvara om du vill tilldela IP-adresser på den **detaljhandel** sidan och sedan använda den **IP-konfiguration** alternativet i den **maskinvara stationer** att ange alla nätverksenheter som är tilldelade till stationen maskinvara. För maskinvara stationer som endast nätverksenheter har du inte distribuera själva stationen maskinvara. Då krävs stationen maskinvara endast för att konceptuellt gruppera nätverket adresserbara enheter enligt deras placering i retail store.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>POS-molnet och Modern POS för iOS Modern POS för Android

Logiken som fysiskt anslutna och nätverket adresserbara kringutrustning enheter finns på stationen maskinvara. För alla klienter POS utom Modern POS for Windows, måste en station för IIS-maskinvara därför distribuerade och aktiv för att aktivera KASSAN ska kommunicera med kringutrustning, oavsett om dessa kringutrustning är fysiskt ansluten till en dator maskin eller beskrivs i nätverket.

## <a name="setup-and-configuration"></a>Installation och konfiguration
### <a name="hardware-station-installation"></a>Maskinvaruinstallation station

Mer information finns i [för Retail-maskinvarukonfiguration och installation](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Modern POS för Windows-installation och konfiguration

Mer information finns i [Modern Retail POS konfiguration och installation](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>OPOS enhet installation och konfiguration

Mer information om OPOS-komponenter finns i avsnittet "Gränssnitt som stöds" i det här dokumentet. Vanligtvis tillhandahålls OPOS förarna av enhetens tillverkare. När en OPOS-drivrutin installeras läggs en nyckel i Windows-registret på någon av följande platser:

-   **32-bitarssystem:** HKEY\_lokala\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **64-bitars system:** HKEY\_lokala\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Konfigurerade enheter är organiserade enligt enhetsklassen OPOS inom registerplats ServiceOPOS. Flera drivrutiner sparas.

## <a name="supported-scenarios-by-hardware-station-type"></a>Stöds efter maskinvarutyp station scenarier
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Klientstöd – IPC maskinvara station jämfört med IIS maskinvara station

I följande tabell visas topologier och distributionsscenarier som stöds.

| Kund      | IPC maskinvara station | IIS maskinvara station |
|-------------|----------------------|----------------------|
| Windows-program | Ja                  | Ja                  |
| Cloud POS   | Ingen                   | Ja                  |
| Android     | Ingen                   | Ja                  |
| / o         | Ingen                   | Ja                  |

### <a name="network-peripherals"></a>Nätverk-kringutrustning

Nätverket kringutrustning kan användas direkt via maskinvara stationen som ingår i Modern POS för Windows-program. Du måste distribuera en station för IIS maskinvara för andra klienter.

| Kund      | IPC maskinvara station | IIS maskinvara station |
|-------------|----------------------|----------------------|
| Windows-program | Ja                  | Ja                  |
| Cloud POS   | Ingen                   | Ja                  |
| Android     | Ingen                   | Ja                  |
| / o         | Ingen                   | Ja                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Vilka enhetstyper av efter maskinvarutyp station stöds
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS för Windows med en maskinvara station IPC (inbyggt)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klass för enheten som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skrivare</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Enhet</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="even">
<td>Skrivare 2</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Enhet</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="odd">
<td>Radvisning</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Dubbla bildskärmar</td>
<td>Windows-drivrutin</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>OPOS</li>
<li>UWP (inga inställningar krävs.)</li>
<li>Tangentbord wedge (inga inställningar krävs.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Utställare</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk <strong>Obs!:</strong> bara en enda låda kan ställas in om <strong>använda delade SKIFT</strong> konfigureras i kassalådan.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kassalåda 2</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk <strong>Obs!:</strong> bara en enda låda kan ställas in om <strong>använda delade SKIFT</strong> konfigureras i kassalådan.</li>
</ul></td>
</tr>
<tr class="even">
<td>Skanner</td>
<td><ul>
<li>OPOS</li>
<li>UWP (inga inställningar krävs.)</li>
<li>Tangentbord wedge (inga inställningar krävs.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skanner 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (inga inställningar krävs.)</li>
<li>Tangentbord wedge (inga inställningar krävs.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Skala</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>PIN-knappsats</td>
<td>OPOS (Support tillhandahålls via anpassning av betalningskopplingen).</td>
</tr>
<tr class="even">
<td>Digital signatur</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Betalterminal </td>
<td><ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (Mer information finns i dokumentationen för betalningen koppling.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Alla moderna POS-klienter stationerna dedikerade IIS maskinvara

**Anmärkning:** när IIS maskinvara station "dedicerat", finns ett samarbete mellan POS-klienten och stationen maskinvara.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klass för enheten som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skrivare</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin för <strong>Obs!:</strong> för Windows-skrivare i ett nätverk, maskinvara stationens användaren måste ha behörighet att komma åt skrivaren.</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="even">
<td>Skrivare 2</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="odd">
<td>Radvisning</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Utställare</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk <strong>Obs!:</strong> bara en enda låda per maskinvaruprofil kan ställas in om <strong>använda delade SKIFT</strong> konfigureras i kassalådan.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kassalåda 2</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skanner</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Skanner 2</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Skala</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>PIN-knappsats</td>
<td>OPOS (Support tillhandahålls via anpassning av betalningskopplingen).</td>
</tr>
<tr class="odd">
<td>Sig. fånga</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Betalterminal </td>
<td><ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (Mer information finns i dokumentationen för betalningen koppling.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Alla moderna POS klienter som har en delad IIS maskinvara station

**Anmärkning:** när IIS maskinvara station "delas" maskinvara stationen samtidigt använder flera enheter. I det här scenariot bör du använda de enheter som visas i följande tabell. Om du försöker dela enheter som inte visas här, t ex streckkodsläsare och MSRs, inträffar fel när flera enheter försöker göra anspråk på samma enhet. I kommer en sådan konfiguration att uttryckligen förhindras.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klass för enheten som stöds</th>
<th>Gränssnitt som stöds</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skrivare</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin för <strong>Obs!:</strong> för Windows-skrivare i ett nätverk, maskinvara stationens användaren måste ha behörighet att komma åt skrivaren.</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="even">
<td>Skrivare 2</td>
<td><ul>
<li>OPOS</li>
<li>Windows-drivrutin</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="odd">
<td>Utställare</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk <strong>Obs!:</strong> bara en enda låda per maskinvaruprofil kan ställas in om <strong>använda delade SKIFT</strong> konfigureras i kassalådan.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kassalåda 2</td>
<td><ul>
<li>OPOS</li>
<li>Nätverk</li>
</ul></td>
</tr>
<tr class="odd">
<td>Betalterminal </td>
<td><ul>
<li>Stöd för anpassade enheter</li>
<li>Nätverk (Mer information finns i dokumentationen för betalningen koppling.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguration för scenarier som stöds
Mer information om hur du skapar maskinvaruprofiler finns [definiera och underhålla kanal-klienter såsom register och maskinvara stationer](define-maintain-channel-clients-registers-hw-stations.md). **Anmärkning:** för Microsoft Dynamics 365 för operationer version 1611 station maskinvaruprofilen används inte längre. Attribut som du tidigare skapat i maskinvaruprofilen station ingår nu i själva stationen maskinvara.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS för Windows med en maskinvara station IPC (inbyggt)

Den här konfigurationen är de vanligaste konfigurationen för traditionella, fast kassor. I det här scenariot mappas profilinformation maskinvara till själva registret direkt. EFT-terminalnummer bör också anges i själva journalen. Följ dessa steg om du vill ställa in den här konfigurationen.

1.  Skapa en maskinvaruprofil där all kringutrustning har konfigurerats.
2.  Motsvarar kassaregister maskinvaruprofilen.
3.  Skapa en fönsterstation maskinvara från den **dedikerad** för butik där kassaregister ska användas. En beskrivning är valfritt. **Anmärkning:** du inte behöver ange andra egenskaper för stationen maskinvara. Alla övriga uppgifter som krävs till exempel maskinvaruprofilen kommer från själva registret.
4.  Klicka på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
5.  Välj den **1090** distributionsschema för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
6.  Välj den **1040** distributionsschema för att synkronisera den nya kanalen maskinvara till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
7.  Installera och aktivera Modern POS för Windows.
8.  Starta Modern POS för Windows och börjar använda ansluten kringutrustning.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Alla moderna POS-klienter stationerna dedikerade IIS maskinvara

Den här konfigurationen kan användas för alla moderna POS-klienter stationerna maskinvara används exklusivt av en POS registrera. Följ dessa steg om du vill ställa in den här konfigurationen.

1.  Skapa en maskinvaruprofil där all kringutrustning har konfigurerats.
2.  Skapa en fönsterstation maskinvara från den **dedikerad** för butik där kassaregister ska användas.
3.  Ange följande egenskaper på stationen dedikerad maskinvara:
    -   **Värdnamn** – namnet på värddatorn där stationen maskinvara körs. **Anmärkning:** molnbaserad POS kan lösa **localhost** att avgöra den lokala datorn där körs molnbaserad kassa. Certifikat som behövs för att länka en molnbaserad kassa till stationen maskinvara måste dock även ha "Localhost" som datornamn. För att undvika problem bör du ange en instans av varje station dedikerad maskinvara för butiken som krävs. För varje maskinvara station finnas värdnamn specifika datornamn där maskinvara stationen ska distribueras.
    -   **Port** – porten som ska användas vid ankomststationen maskinvara för att kommunicera med POS Modern klienten.
    -   **Maskinvaruprofil** – om maskinvaruprofilen inte om på maskinvara stationen själva den maskinvaruprofil som har tilldelats journalen används.
    -   **EFT-POS-nummer** – den EFT terminal-ID som används när EFT tillstånd skickas. Detta ID tillhandahålls av kreditkortsföretaget.
    -   **Paketnamnet** – maskinvara station paketet ska användas vid stationen maskinvara distribueras.

4.  Klicka på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
5.  Välj den **1090** distributionsschema för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
6.  Välj den **1040** distributionsschema för att synkronisera den nya kanalen maskinvara till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
7.  Installera maskinvara stationen. Mer information om hur du installerar maskinvara stationen finns [Retail maskinvarukonfiguration och installation](retail-hardware-station-configuration-installation.md).
8.  Installera och aktivera Modern POS. Mer information om hur du installerar Modern POS finns [Modern Retail POS konfiguration och installation](retail-modern-pos-device-activation.md).
9.  Logga in i en Modern POS och markera **-låda operationer**.
10. Starta den **hantera maskinvara stationer** åtgärd.
11. Klicka på **hantera**.
12. Ange alternativet Aktivera stationen maskinvara på hanteringssidan station för maskinvara.
13. Välj maskinvara stationen ska användas och klicka sedan på **par**.
14. När stationen maskinvara tillsammans, klickar du på **nära**.
15. Om du vill aktivera det senast markerade maskinvara stationen på sidan maskinvara station val.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Alla moderna POS klienter som har en delad IIS maskinvara station

Den här konfigurationen kan användas för alla moderna POS-klienter som delar maskinvara stationer med andra enheter. Följ dessa steg om du vill ställa in den här konfigurationen.

1.  Skapa en maskinvaruprofil där nödvändiga kringutrustning har konfigurerats.
2.  Skapa en fönsterstation maskinvara från den **delade** för butik där kassaregister ska användas.
3.  Ange följande egenskaper på stationen delade maskinvara:
    -   **Värdnamn** – namnet på värddatorn där stationen maskinvara körs.
    -   **Beskrivning** – Text som hjälper identifierar vilken dator maskin, t ex **returnerar** eller **framför butiken**.
    -   **Port** – porten som ska användas vid ankomststationen maskinvara för att kommunicera med POS Modern klienten.
    -   **Maskinvaruprofil** – varje station maskinvara bör ha en maskinvaruprofil för delade maskinvara stationer. Maskinvaruprofiler kan delas av maskinvara stationer, men de måste kopplas till varje station maskinvara. Dessutom rekommenderar vi att du använder delade SKIFT när flera enheter använder samma delade maskinvara stationen. Klicka på Konfigurera en delad SKIFT **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**. För varje delad maskinvaruprofil Välj kassalådan och den **Shared SKIFT kassalådan** att **Ja**.
    -   **EFT-POS-nummer** – den EFT terminal-ID som används när EFT tillstånd skickas. Detta ID tillhandahålls av kreditkortsföretaget.
    -   **Paketnamnet** – maskinvara station paketet ska användas vid stationen maskinvara distribueras.

4.  Upprepa steg 2 och 3 för varje ytterligare maskinvara station som krävs i butiken.
5.  Klicka på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
6.  Välj den **1090** distributionsschema för att synkronisera den nya maskinvaruprofilen till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
7.  Välj den **1040** distributionsschema för att synkronisera den nya kanalen maskinvara till butiken. Klicka på **kör nu** att synkronisera ändringar i KASSAN.
8.  Installera maskinvara stationen på varje värddator som du angav i steg 2 och 3. Mer information om hur du installerar maskinvara stationen finns [Retail maskinvarukonfiguration och installation](retail-hardware-station-configuration-installation.md).
9.  Installera och aktivera Modern POS. Mer information om hur du installerar Modern POS finns [Modern Retail POS konfiguration och installation](retail-modern-pos-device-activation.md).
10. Logga in i en Modern POS och markera **-låda operationer**.
11. Starta den **hantera maskinvara stationer** åtgärd.

12. Klicka på **hantera**.
13. Ange alternativet Aktivera stationen maskinvara på hanteringssidan station för maskinvara.
14. Välj maskinvara stationen ska användas och klicka sedan på **par**.
15. Upprepa steg 14 för varje station maskinvara som används i moderna POS.
16. När nödvändig maskinvara stationer utrustade klickar du på **nära**.
17. Om du vill aktivera det senast markerade maskinvara stationen på sidan maskinvara station val. **Anmärkning:** om ofta med enheterna stationer för olika typer av maskinvara, rekommenderar vi att du konfigurerar Modern POS som uppmanar kassören att välja när de påbörja betalningsmedel stationerna maskinvara. Klicka på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**. Markera registret och ange den **Välj vid anbud** att **Ja**. Använd den **1090** distributionsschema för att synkronisera ändringar i databasen för kanalen.

## <a name="extensibility"></a>Utbyggbarhet
Information om tillägg scenarier vid ankomststationen maskinvara finns i [maskinvara Station tillägg](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Säkerhet
Enligt aktuella säkerhetskrav följande inställningar ska användas i en produktionsmiljö: **Obs!:** maskinvara station installationsprogrammet ska göra ändringarna i registret som en del av installationen via Self Service.

-   Secure Sockets Layer (SSL) ska inaktiveras.
-   Endast Transport Layer Security (TLS) version 1.2 (eller den aktuella versionen av högsta) ska aktiveras och användas. **Anmärkning:** SSL och alla version TLS utom 1,2 TLS är inaktiverat som standard. Om du vill redigera eller aktivera värdena så här:
    1.  Tryck på Windows-tangenten + R för att öppna en **kör** fönster.
    2.  I den **öppna** ange **Regedit**, och klicka sedan på **OK**.
    3.  Om en **User Account Control** meddelanderuta visas klickar du på **Ja**.
    4.  I den **Registereditorn** fönstret, gå till **HKEY\_lokala\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Följande tangenter infogas automatiskt så att du bara kan TLS 1.2:
        -   TLS-1.2Server: aktiveras = 1
        -   TLS-1.2Server:DisabledByDefault = 0
        -   TLS-1.2Client: aktiveras = 1
        -   TLS-1.2Client:DisabledByDefault = 0
        -   TLS-1.1Server: aktiveras = 0
        -   TLS-1.1Client: aktiveras = 0
        -   TLS-1.0Server: aktiveras = 0
        -   TLS-1.0Client: aktiveras = 0
        -   SSL-3.0Server: aktiveras = 0
        -   SSL-3.0Client: aktiveras = 0
        -   SSL-2.0Server: aktiveras = 0
        -   SSL-2.0Client: aktiveras = 0
-   Inga ytterligare portar öppnas, om de inte är tvingande kända, angivna skäl.
-   Resursdelning mellan ursprung måste inaktiveras och måste ange tillåtna underlag som accepteras.
-   Endast betrodda certifikatutfärdare ska användas för att erhålla certifikat som ska användas på datorer som kör stationen maskinvara.

**Anmärkning:** är det viktigt att du läser igenom riktlinjerna för IIS och betalning kortet bransch PCI-kraven.

## <a name="peripheral-simulator"></a>Kringutrustningssimulator
Mer information finns i [yttre Retail simulator](retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Kringutrustning för Microsofttested
### <a name="ipc-built-in-hardware-station"></a>IPC (inbyggt) maskinvara station

Följande kringutrustning som har testats med IPC maskinvara stationen som ingår i Modern POS för Windows.

#### <a name="printer"></a>Skrivare

| Tillverkaren | Modell    | Gränssnitt | Kommentarer                |
|--------------|----------|-----------|-------------------------|
| Epson        | TM T88IV | OPOS      |                         |
| Epson        | TM T88V  | OPOS      |                         |
| Stjärna         | TSP650II | OPOS      |                         |
| Stjärna         | TSP650II | Anpassa    | Ansluten via nätverket   |
| Stjärna         | mPOP     | OPOS      | Ansluten via Bluetooth |
| HP           | F7M67AA  | OPOS      | Strömförsörjd USB             |

#### <a name="bar-code-scanner"></a>Streckkodsskanner

| Tillverkaren  | Modell         | Gränssnitt | Kommentarer |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbol        | LS2208        | OPOS      |          |
| HP integrerade | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>PIN-knappsats

| Tillverkaren | Modell  | Gränssnitt | Kommentarer                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Anpassning av betalningskopplingen krävs |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkaren | Modell | Gränssnitt | Kommentarer                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | MED UR L5300 | Anpassa    | Anpassning av betalningskopplingen krävs                                |
| VeriFone     | MX925 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |

#### <a name="cash-drawer"></a>Kassalådan

| Tillverkaren | Modell     | Gränssnitt | Kommentarer                |
|--------------|-----------|-----------|-------------------------|
| Stjärna         | mPOP      | OPOS      | Ansluten via Bluetooth |
| APG          | Atwood    | Anpassa    | Ansluten via nätverket   |
| Stjärna         | SMD2 1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Radvisning

| Tillverkaren  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| HP integrerade | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Digital signatur

| Tillverkaren | Modell  | Gränssnitt | Kommentarer |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skala

| Tillverkaren | Modell         | Gränssnitt | Kommentarer |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Tillverkaren | Modell       | Gränssnitt | Kommentarer |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Dedikerad maskinvara station för IIS

Följande kringutrustning som har testats med hjälp av en särskild (Ej delad) IIS maskinvara station tillsammans med molnbaserad kassa och Modern POS för Windows.

#### <a name="printer"></a>Skrivare

| Tillverkaren | Modell    | Gränssnitt | Kommentarer                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM T88IV | OPOS      |                           |
| Epson        | TM T88V  | OPOS      |                           |
| Stjärna         | TSP650II | OPOS      |                           |
| Stjärna         | TSP650II | Anpassa    | Ansluten via nätverket     |
| Stjärna         | TSP100   | OPOS      | Kräver drivrutiner för TSP650II |
| HP           | F7M67AA  | OPOS      | Strömförsörjd USB               |

#### <a name="bar-code-scanner"></a>Streckkodsskanner

| Tillverkaren  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Symbol        | LS2208  | OPOS      |          |
| HP integrerade | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>PIN-knappsats

| Tillverkaren | Modell  | Gränssnitt | Kommentarer                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Anpassning av betalningskopplingen krävs |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkaren | Modell | Gränssnitt | Kommentarer                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | MED UR L5300 | Anpassa    | Anpassning av betalningskopplingen krävs                                |
| VeriFone     | MX925 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |

#### <a name="cash-drawer"></a>Kassalådan

| Tillverkaren | Modell     | Gränssnitt | Kommentarer              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Anpassa    | Ansluten via nätverket |
| Stjärna         | SMD2 1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Radvisning

| Tillverkaren  | Modell   | Gränssnitt | Kommentarer |
|---------------|---------|-----------|----------|
| HP integrerade | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Digital signatur

| Tillverkaren | Modell  | Gränssnitt | Kommentarer |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Skala

| Tillverkaren | Modell         | Gränssnitt | Kommentarer |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Tillverkaren | Modell       | Gränssnitt | Kommentarer |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Delad IIS maskinvara station

Följande kringutrustning som har testats med hjälp av en delad IIS maskinvara station tillsammans med Modern POS för Windows och molnbaserad kassa. **Anmärkning:** stöds endast en skrivare betalning terminal och kassalådan.

#### <a name="printer"></a>Skrivare

| Tillverkaren | Modell    | Gränssnitt | Kommentarer                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM T88IV | OPOS      |                           |
| Epson        | TM T88V  | OPOS      |                           |
| Stjärna         | TSP650II | OPOS      |                           |
| Stjärna         | TSP650II | Anpassa    | Ansluten via nätverket     |
| Stjärna         | TSP100   | OPOS      | Kräver drivrutiner för TSP650II |
| HP           | F7M67AA  | OPOS      | Strömförsörjd USB               |

#### <a name="payment-terminal"></a>Betalterminal 

| Tillverkaren | Modell | Gränssnitt | Kommentarer                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |
| VeriFone     | MX915 | Anpassa    | Kräver anpassning av betalningsanslutning; ansluten via nätverket och USB |

#### <a name="cash-drawer"></a>Kassalådan

| Tillverkaren | Modell     | Gränssnitt | Kommentarer              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Anpassa    | Ansluten via nätverket |
| Stjärna         | SMD2 1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Felsökning
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS kan identifiera maskinvara station i listan för val av, men inte kan utföras i par

**Lösning:** kontrollera listan över potentiella felpunkter följande:

-   Certifikatet som används på datorn som kör stationen maskinvara har förtroende för den dator där Modern POS.
    -   Kontrollera inställningarna i en webbläsare går du till följande URL: https://&lt;datornamn&gt;:&lt;portnummer&gt;/HardwareStation/ping.
    -   URL: en använder ping för att verifiera att datorn kan nås och webbläsaren anger om certifikatet är betrott. (Till exempel i Internet Explorer en låsikon visas i adressfältet. När du klickar på ikonen kontrollerar Internet Explorer om certifikatet är betrott för närvarande. Du kan installera certifikatet på den lokala datorn genom att visa information om certifikatet visas.)
-   Den port som används av maskinvara stationen öppnas i brandväggen på datorn som kör stationen maskinvara.
-   Stationen maskinvara har installerats korrekt information handelskonto via Install handlare information verktyg som ska köras i slutet av installationsprogrammet station maskinvara.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS kan inte identifiera maskinvara station i listan för val

**Lösning:** något av följande faktorer kan orsaka problemet:

-   Stationen maskinvara har inte ställts in korrekt i headquarters. Använda instruktionerna tidigare i det här avsnittet för att kontrollera att stationen maskinvaruprofilen och stationen maskinvara har angetts korrekt.
-   Jobb har inte körts om du vill uppdatera konfigurationen kanal. I det här fallet köra jobbet för Kanalkonfiguration 1070.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS innehåller inte de nya inställningarna för kassalådan

**Lösning:** den aktuella batchen stängs. Ändringar i kassalådan uppdateras inte till Modern POS tills den aktuella batchen stängs.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Modern POS rapporterar ett problem med en officiell kringutrustning

**Lösning:** här följer några vanliga orsaker till problemet:

-   Kontrollera att andra konfigurationsverktyg för enhetens drivrutin är stängda. Om verktygen körs de hindra att Modern POS eller maskinvara stationen äger enheten.
-   Om kringutrustningen retail lämnas ut till flera enheter POS, kontrollerar du att den tillhör en av följande kategorier:
    -   Kassalådan
    -   Kvittoskrivare
    -   Betalterminal 

    Om kringutrustningen inte tillhör någon av dessa kategorier, är inte stationen maskinvara utformat för kringutrustning som ska delas mellan flera POS-enheter.
-   Drivrutiner kan ibland orsaka common control-objekt (CCOs) inte fungerar korrekt. Om en enhet nyligen har installerats men inte fungerar korrekt eller om du upplever andra problem, kan du ofta Lös problemet genom att installera om CCOs. Du kan hämta CCOs <http://monroecs.com/oposccos_current.htm>.
-   Om du ändrar ofta kringutrustning vid testning eller felsökning, kan du behöva återställa IIS i stället att uppdatera själva cacheminnet. Så här återställer du IIS:
    1.  Från den **starta** -menyn, Skriv **CMD**.
    2.  Högerklicka i sökresultatet **kommandotolk**, och klicka sedan på **kör som administratör**.
    3.  I den **kommandotolk** fönster, skriver **iisreset/restart** och tryck på RETUR.
    4.  Starta om Modern POS när IIS har startats om.
-   När du gör ofta ändringar till kringutrustning, om du ofta också startar och stänger klienten POS, kan från en tidigare session KASSAN dllhost processen påverka den aktuella sessionen. En enhet kan då inte användas förrän du stänger värden dynamisk-länkbiblioteket (DLL) som hanterar den senaste sessionen. Gör följande om du vill stänga dll-värden:
    1.  Från den **starta** -menyn, Skriv **Aktivitetshanteraren**.
    2.  I sökresultaten klickar du på **Aktivitetshanteraren**.
    3.  I Aktivitetshanteraren: på den **uppgifter** klickar du på kolumnrubriken som heter **namn** ska sorteras tabellen i alfabetisk ordning efter namn.
    4.  Bläddra nedåt tills du hittar dllhost.exe.
    5.  Markera varje värd DLL och klicka **slutuppgift**.
    6.  Starta om Modern POS när dll-värdar har avslutats.


<a name="see-also"></a>Se även
--------

[Retail-kringutrustning simulator](retail-peripheral-simulator.md)


