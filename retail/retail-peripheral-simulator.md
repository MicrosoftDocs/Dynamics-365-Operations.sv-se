---
title: Retail-kringutrustning simulator
description: "Det här avsnittet beskrivs verktyget simulator kringutrustning som medföljer Microsoft Dynamics 365 för verksamhet – Retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Retail-kringutrustning simulator

Det här avsnittet beskrivs verktyget simulator kringutrustning som medföljer Microsoft Dynamics 365 för verksamhet – Retail.

<a name="overview"></a>Översikt
--------

Microsoft Dynamics 365 för verksamhet – Retail kringutrustning simulator är ett verktyg som hjälper dig att skapa, testa och felsöka kringutrustning som används i retail-miljöer. Du kan använda kringutrustning simulatorn testning av retail kringutrustning och hitta problem som orsakas av felaktig inställning eller felaktiga drivrutiner. Desktop programmet som innehåller virtuella versioner av enheter som Dynamics 365 för operationer som ingår i yttre simulatorn - stöd för Retail. Ett avsnitt för varje virtuell enhet visar interaktionen mellan enheten och den butik inköpstillfället (PO). Du kan också använda det för att ge feedback som gäller för olika scenarier för kassa. Yttre simulatorn stöder KASSAN tillsammans med följande virtuella enheter:

-   **Skrivaren** – kringutrustning simulatorn kan visa inleveranser som har konfigurerats för en POS-skrivare.
-   **Visa rad** – du kan konfigurera ett virtuellt radskärmen så att aktiviteten på en fysisk radskärmen.
-   **Kortläsare (MSR)** – du kan skicka simulerade Magnetremsan händelser till KASSAN från yttre simulatorn.
-   **Låda** – du kan simulera en fysisk kassalådan.
-   **Låda 2** – du kan simulera kanske du behöver en enda kassaregister med två aktiva SKIFT genom att skapa en andra kassalådan i yttre simulatorn.
-   **Skannern** – de virtuella streckkodsskanner som stöder kringutrustning simulatorn kan utfärda streckkod skannerhändelser.
-   **Anpassa** – en virtuell skala kan du simulera interaktionen vägd artiklar med KASSAN.
-   **Personlig kod (PIN) numeriska** – du kan simulera operationer PIN-knappsatsen. **Anmärkning:** måste du implementera stöd för ett fysiskt PIN-knappsats genom betalningskopplingen.
-   **Signatur** – kringutrustning simulatorn inkluderar en enhet för digital signatur virtuella som du kan ställa in att signaturer som krävs för vissa anbud, till exempel konto för kundbetalningar.

Du kan också använda kringutrustning simulatorn simulera wedge tangentbordshändelser som härstammar från en streckkodsskanner och MSR. Virtuella kringutrustning simulatorn stöd särskilt för objektlänkning och inbäddning för Retail POS (OPOS) enheter.

## <a name="key-scenarios"></a>Vanliga scenarier
### <a name="troubleshooting"></a>Felsökning

Du kan använda kringutrustning simulatorn du felsöker Enhetsinställningar. Om du inte har simulatorn kringutrustning eller andra enheter av samma slag, kan det vara svårt att avgöra om problem kommer från. Men när måste du simulatorn kringutrustning kan du ställa in virtuella enheter och köra samma kodsökvägar och affärslogik som används för fysiska enheter. Från yttre simulatorn synpunkt är den huvudsakliga skillnaden mellan virtuella enheter och fysiska enheter serviceobjekt eller drivrutin. Serviceobjektet tillhandahålls av enhetens tillverkare för fysiska enheter. Yttre simulatorn finns däremot serviceobjekt som en del av simulatorn kringutrustning. När du simulatorn kringutrustning fungerar korrekt, om en enhet inte fungerar korrekt när enhetsnamnet i maskinvaruprofilen ändras till namnet på den faktiska enheten antar du att det finns ett problem med serviceobjektet från tillverkaren.

### <a name="training"></a>Kurs

Du kan använda kringutrustning simulatorn att lägga till ett lager och realistiska kassören utbildning när en fysisk maskinvara inställning inte är tillgänglig. När yttre simulatorn ingår i utbildningen scenarier kan interagera kassören effektivare med POS genom att ange indata till exempel product code sökningar och presentkort kort swipes och genom att iaktta vilka inleveranser som ska skrivas ut för en viss transaktion.

### <a name="testing"></a>Testa

Du kan använda kringutrustning simulatorn testa produkten streckkoder, kvittoformat och så vidare, utan att använda en fysisk maskinvara i en virtuell miljö. Fysisk maskinvara behövs inte efter uppgraderingen och du behöver inte distribuera en POS-klient på en station maskinvara eller en fysisk dator, kan du testa ändringar som görs i back office snabbare.

## <a name="set-up-the-peripheral-simulator"></a>Konfigurera kringutrustning simulatorn
### <a name="set-up-a-hardware-profile"></a>Ställ in en maskinvaruprofil

1.  Konfigurera kringutrustning simulatorn genom att gå till **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**.
2.  Om du vill skapa en ny profil klickar du på **New**.
3.  Ange värden i de **Profilnummer** och **beskrivning** fält.
4.  Använd följande tabell när du vill ställa in virtuella enheter som ska testas. Här följer en förklaring av kolumner i tabellen:
    -   **Enheten** -den här kolumnen visas namnet på snabbfliken utvidgas konfigurera enheten.
    -   **Typ av** -den här kolumnen innehåller värdet som du väljer i fältet som är märkt med namnet på enheten.
    -   **Enhetsnamn** -den här kolumnen visas det exakta värdet som du anger för enhetsnamn. **Viktigt:** enhetsnamn som anges här krävs eftersom stationen maskinvara använder dessa specifika namn för enheterna. Enheten kommer inte att användas om du inte använder dessa specifika namn.

    | Enhet            | Enhetstyp | Enhetsnamn              |
    |-------------------|-------------|--------------------------|
    | Skrivare           | OPOS        | MockOPOSPrinter          |
    | Radvisning      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | Utställare            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Skanner           | OPOS        | MockOPOSScanner          |
    | Skala             | OPOS        | MockOPOSScale            |
    | PIN-knappsats           | OPOS        | MockOPOSPinPad           |
    | Digital signatur | OPOS        | MockOPOSSignatureCapture |

**Anmärkning:** inga särskilda inställningar i maskinvaruprofilen som krävs för att simulera wedge tangentbordshändelser från streckkodsskanner och MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Tilldela en kassa maskinvaruprofilen

1.  När du har skapat maskinvaruprofilen gå till **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**.
2.  I den **kassor** klickar du på länken i den **registreringsnummer** för registret som ska använda kringutrustning simulatorn.
3.  Klicka på **Redigera**.
4.  I den **profiler** avsnitt i den **maskinvaruprofil**, markera den maskinvaruprofil som du skapat för virtuella kringutrustning.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar till databasen kanal

1.  Gå till **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
2.  Välj den **1090** distributionsschema.
3.  Klicka på **kör nu** att synkronisera ändringar i KASSAN.

När data synkroniseras finns den nya maskinvaruprofilen och ändringar i registret i databasen kanal.

## <a name="install-the-peripheral-simulator"></a>Installerar du simulatorn kringutrustning
1.  Gå till **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**.
2.  Klicka på **hämtar**, och klicka sedan på **PeripheralSimulator**. **Anmärkning:** måste du inaktivera popup-blockerare innan du kan hämta kringutrustning simulatorn.
3.  När hämtningen är klar öppnar du den **hämtar** mapp och dubbelklickar på **VirtualPeripherals.msi** starta installationsprogrammet.
4.  Installera simulatorn kringutrustning med standardinställningarna.

Förutom kringutrustning simulatorn, måste du installera common control-objekt från Monroe konsulttjänster. I annat fall fungerar kringutrustning simulatorn inte korrekt. Hämta common control-objekt genom att gå till <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Med hjälp av simulatorn kringutrustning
Yttre simulatorn, klicka på **starta** på din dator, skriver du **yttre Retail simulator**, och välj sedan programmet när det visas i sökresultaten. Klicka på ett enhetsnamn för att visa enheterna som stöds när du har startat kringutrustning simulatorn. Enheterna visas som flikar till vänster i fönstret. Klicka på fliken för enheten om du vill visa en viss enhet.

### <a name="line-display-capabilities"></a>Raden visningsmöjligheter

Radskärmen är den första enheten som anges i yttre simulatorn. Konfigurerades virtuella radskärmen visar poster som söks igenom i POS-transaktionen. Förutom radposter visas den summa som förfaller när ett anbud har valts i KASSAN. Visas saldot som förfaller om ett anbud har angetts men balans fortfarande förfallodatumet för transaktionen. När KASSAN inte används, visas ett meddelande om du vill ange att fältet till är stängd. Måste du konfigurera meddelandet på den **rad visas** på snabbfliken i maskinvaruprofilen.

### <a name="cash-drawer-capabilities"></a>Kontant kassalådan funktioner

Kassalådan är den andra enheten som anges i yttre simulatorn. När maskinvaruprofilen har konfigurerats för att använda virtuella kassalådor POS öppnar kassalådan för aktiva skillnaden som svar på operationer låda som kassaavstämning, och så att kassören kan ändra eller sätta in kontant standard cash-and-carry transaktioner. Virtuella kassalådor har etiketterna **huvud kassalådan** och **sekundära kassalådan**. Dessa etiketter representerar kassalådan kassalådan 2 i maskinvaruprofilen, respektive. När en låda stängs visas en bild av en stängd kassalådan och heter knappen i kassalådan stängda **Öppna kassalådan**. Om du klickar på den här knappen ersätts bilden med en bild av en Öppna kassalådan för att indikera att kassalådan är öppen. Öppna kassalådan på knappen heter **Stäng kassalådan**. Flera operationer i KASSAN kan orsaka att öppna kassalådan. De flesta åtgärder kan inte fortsätta medan kassalådan är öppen. Undantagen är vissa procedurer i slutet av dagen. Om POS-användare får ett felmeddelande som säger att en operation inte kan utföras när kassalådan är öppen, måste användaren stänga virtuella eller fysiska kassalådan när du vill fortsätta. Om en kassalådan markeras som **delade** systemet inte i maskinvaruprofilen, kontrollera att lådan är stängda innan en åtgärd. Operationen fortsätter som vanligt även om kassalådan är öppen. Detta stöd för scenarier där kassalådor delas affärskontakter och en associera använder en kassalådan när associera en annan utför relaterade uppgifter på sitt eget POS-enhet. Ändringar som görs i kassalådan inte tydligt förrän det aktuella arbetspasset stängs och öppnas ett nytt SKIFT.

### <a name="msr-capabilities"></a>MSR-funktioner

Yttre simulatorn stöder robust virtuell MSR operationer genom att arbeta i antingen OPOS eller tangentbordet wedge läge. OPOS-läget kräver att MSR konfigureras att fungera som en OPOS-enhet i maskinvaruprofilen. Bara skickar wedge tangentbordsläge tangentbordshändelser wedge data till Microsoft Windows. Förutom skillnaderna i inställningarna för OPOS- och tangentbordet wedge lägen skiljer sig på följande sätt:

-   POS-klienten kan OPOS MSR enheter för specifika scenarier, t ex scenarier som tillåter Magnetremsan data för förmånskort eller post presentkort.
-   I tangentbordsläge wedge, kringutrustning simulatorn tangentbord wedge informationen skickas till det fält som är aktiv när data skickas. Detta påminner om vad som händer om du anger data genom att använda ett tangentbord. Om du vill använda MSR som ett tangentbord wedge måste användaren byta till Retail Modern POS (MOPS) och kontrollera att data tas emot i rätt fält. Därför kan du konfigurera en stund så att användaren får tid att säkerställa att data skickas till rätt fält.

#### <a name="testing-gift-and-payment-card-swipes"></a>Testa swipes presentkort och betalning kort

Virtuella MSR som yttre simulatorn ger också kan du konfigurera specifika MSR data om du vill testa scenarier för swipes presentkort och betalning kortet. Klicka på plustecknet för att skapa ett kort (**+**) och välj vilken typ av kort. Ange kortnumret sedan eller spåra data som ska skickas till KASSAN tillsammans med den sista månaden och året för det kort som du definierar. Värdet som du väljer i den **korttyp** är bara en etikett som kan mappas till ett kort. Etiketten gör det enklare att identifiera korten när de är draget via kringutrustning simulatorn. Du kan välja kort som har konfigurerats i simulatorn kringutrustning med vänsterpilen (**&lt;**) och högerpilen (**&gt;**) ovanför bilden av kortet. Du kan redigera och ta bort kort med den **redigera** och **bort** knappar bredvid plustecknet (**+**) knappen.

### <a name="pin-pad"></a>PIN-knappsats

Du kan konfigurera tangentbordet simulatorn PIN-kod för att simulera en OPOS PIN-knappsatsen. När en elektronisk överföringstransaktion utförs i KASSAN och kräver att PIN-koden, anropar stationen maskinvara PIN enheten frågar om PIN-post. Genom kräver PIN-knappsats i yttre simulatorn stöd för EFT betalning connector.

### <a name="printer"></a>Skrivare

Virtuell kringutrustning skrivare visar inleveranser när de skrivs ut från KASSAN. Om en publikation åtgärd leder till flera inleveranser, rullar du inleveranser.

#### <a name="configure-receipt-printing"></a>Konfigurera Kvittoutskrift

1.  Gå till **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**.
2.  Välj den maskinvaruprofil som du skapat för virtuella kringutrustning.
3.  I den **skrivare** på snabbfliken klickar du på **redigera**.
4.  I den **Kvittoprofil-ID** väljer du en kvittoprofil.
5.  Click **Save**.

### <a name="scale"></a>Skala

När en vägningsprodukt läggs till POS-transaktionen och en skala är konfigurerad, hämtar POS vikten på skalan. För både virtuella och fysiska omfattning, bör produkt eller vikt anges innan produkten har lagts till i transaktionen. Innan du lägger till produkten skala transaktionen gå till skala i simulatorn kringutrustning och använda plustecknet (**+**) eller minustecken (**–**) för att justera vikt bör rapportera omfattningen. Du kan även ange önskade vikten direkt i den **aktuella värdet** fält. Du kan justera vikt för skalning enheter med plustecknet (**+**), **redigera**, och **bort** knappar. På så sätt kan anges enheter utifrån de produkter som vägs eller språk där skalan används.

#### <a name="configure-a-scale-product"></a>Konfigurera en vägningsprodukt

1.  Gå till **(butik) och****commerce**&gt;**produkter och kategorier**&gt;**frisläppta produkter efter kategori**.
2.  Öppna den produkt.
3.  Välj produkt att väga.
4.  I den **Retail** på snabbfliken ställa den **vägningsprodukt** alternativet från **nr** till **Ja**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar till databasen kanal

1.  Gå till **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
2.  Välj den **1040** distributionsschema.
3.  Klicka på **kör nu** att synkronisera ändringar i KASSAN.

När data synkroniseras när en vägningsprodukt läggs till POS-transaktionen, kontrollerar POS vikten skala.

### <a name="signature-capture"></a>Digital signatur

Enheten för virtuella digital signatur uppmanar användaren att ange en signatur i virtuella signatur signaturer vanligt när anbud som kräver en signatur. Användaren kan acceptera signatur om du vill visa den i KASSAN. Kassören kan sedan acceptera signaturen. Signaturen sparas tillsammans med anbud och synkroniseras till back office tillsammans med andra transaktionsdata.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Ställ in ett anbud signatur krävs

1.  Gå till **butik och handel**&gt;**kanaler**&gt;**detaljhandel**&gt;**alla detaljhandel**.
2.  Välj butiken.
3.  Klicka på **Redigera**.
4.  Klicka på **ställer in**, och sedan, i den **ställa in** klickar du på **betalningsmetoder**.
5.  Klicka på **Redigera**.
6.  Välj den betalningsmetod som kräver en signatur.
7.  I den **allmänna** under avsnittet **signatur fånga**, ange den **Använd enhet för digital signatur** att **Ja**.
8.  I den **minimibelopp för digital signatur** ange minimibeloppet som ska utlösa en signatur.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar till databasen kanal

1.  Gå till **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
2.  Välj den **1070** distributionsschema.
3.  Klicka på **kör nu** att synkronisera ändringar i KASSAN.

När data synkroniseras när anbud används som kräver en signatur och beloppet överstiger tröskeln signatur, uppmanas för en signatur på enheten för virtuella digital signatur.

## <a name="additional-configuration"></a>Ytterligare konfiguration
Du kan redigera konfigurationsfilen kringutrustning simulatorn passande löser scenarier som du testar. Du kan hitta konfigurationsfilen på C:\\programfiler (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Konfigurationsfilen definierar de enheter som finns tillgängliga för test på skalan Korttyper för testning och Streckkodstyper. Genom att ändra textvärden i konfigurationsfilen kan du exempelvis lägga till en ny korttyp eller enhet som kan väljas vid körning. De nya värdena visas när programmet startas.

## <a name="troubleshooting"></a>Felsökning
Aktiviteter för kringutrustning simulatorn loggas i yttre simulatorn. Du hittar loggen på C:\\programfiler (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Kringutrustning simulatorn informerar också fel till händelseloggen i Windows som du kan nå när **program- och tjänstloggar**&gt;**Microsoft**&gt;**DynamicsAX**. Kontrollera om ändringar som du gjort i maskinvaruprofilen eller andra områden inte är klart när du använder MOPS eller kringutrustning simulatorn, schemaläggare de fördelning som du vill synkronisera data till databasen kanal. Om ändringarna har synkroniserats, men fortfarande inte är uppenbart i KASSAN, avsluta POS-klienten. Ändringar i konfigurerade kassalådor inte gälla tills skapas ett nytt SKIFT. Om du ändrar kassalådor Se därför alltid stänga befintligt Skift om du vill testa de nya inställningarna i kontanter kassalådan. Ibland kan kan en tillverkare installeras efter common control-objekt från Monroe konsulttjänster, drivrutinen orsaka common control-objekt slutade fungera korrekt. I så fall bör du installera common control-objekt.

<a name="see-also"></a>Se även
--------

[Retail peripherals overview](retail-peripherals-overview.md)


