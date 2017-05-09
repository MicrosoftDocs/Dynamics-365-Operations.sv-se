---
title: "Kringutrustningssimulator för butik"
description: "Det här avsnittet beskrivs verktyget kringutrustningssimulator som medföljer Microsoft Dynamics 365 for Operations – Retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
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

# <a name="retail-peripheral-simulator"></a>Kringutrustningssimulator för butik

[!include[banner](includes/banner.md)]


Det här avsnittet beskrivs verktyget kringutrustningssimulator som medföljer Microsoft Dynamics 365 for Operations – Retail.

<a name="overview"></a>Översikt
--------

Microsoft Dynamics 365 for Operations – kringutrustningssimulator för butik är ett verktyg som hjälper dig att skapa, testa och felsöka kringutrustning som används i butiksmiljöer. Du kan använda kringutrustningssimulatorn för att effektivisera testning av butikskringutrustning och hitta problem som orsakas av felaktig inställning eller felaktiga drivrutiner. Kringutrustningssimulatorn innehåller ett skrivbordsprogram med virtuella versioner av enheter som stöds av Dynamics 365 for Operations - Retail. Ett avsnitt för varje virtuell enhet visar interaktionen mellan enheten och butikens kassa (POS). Du kan också använda den för att ge feedback som gäller för olika kassascenarier. Kringutrustningssimulatorn stöder interaktion mellan kassan och följande virtuella enheter:

-   **Skrivaren** – kringutrustningssimulatorn kan visa kvitton som har konfigurerats för en kassaskrivare.
-   **Radvisning** – du kan konfigurera en virtuell radbildskärm för att visa aktiviteten på en fysisk radbildskärm.
-   **Kortläsare (MSR)** – du kan skicka simulerade kortläsarhändelser till kassan från kringutrustningssimulatorn.
-   **Kassalåda** – du kan simulera en fysisk kassalåda.
-   **Kassalåda 2** – du kan simulera en enda kassaapparat med två aktiva skift genom att skapa en andra kassalådan i kringutrustningssimulatorn.
-   **Skanner** – den virtuella streckkodsskanner som kringutrustningssimulatorn stöder kan utfärda skannerhändelser för streckkod.
-   **Våg** – med en virtuell våg kan du simulera interaktionen mellan vägda artiklar och kassan.
-   **Personlig PIN-knappsats** – du kan simulera åtgärder med PIN-knappsatsen. **Anmärkning:** måste du implementera stöd för en fysisk PIN-knappsats via betalningskopplingen.
-   **Digital signatur** – kringutrustningssimulatorn inkluderar en virtuell enhet för digital signatur som du kan ställa in för att begära signaturer som krävs för vissa betalningsmedel, till exempel kundkontobetalningar.

Du kan också använda kringutrustningssimulatorn för att simulera händelser för tangentbords-wedge som härstammar från en streckkodsskanner och MSR. Den virtuella kringutrustningssimulatorn stöder särskilt objektlänkning och inbäddning för Retail POS-enheter (OPOS).

## <a name="key-scenarios"></a>Viktiga scenarier
### <a name="troubleshooting"></a>Felsökning

Du kan använda kringutrustningssimulatorn när du felsöker enhetsinställningar. Om du inte har kringutrustningssimulatorn eller en andra enhet av samma slag, kan det vara svårt att avgöra var problem kommer från. Men när du har kringutrustningssimulatorn kan du ställa in virtuella enheter och köra samma kodsökvägar och affärslogik som används för fysiska enheter. Från kringutrustningssimulatorns synvinkel är serviceobjektet eller enhetsdrivrutinen den huvudsakliga skillnaden mellan virtuella enheter och fysiska enheter. För fysiska enheter tillhandahålls serviceobjektet av enhetens tillverkare. För kringutrustningssimulatorn finns däremot serviceobjekten som en del av kringutrustningssimulatorn. När du kringutrustningssimulatorn fungerar korrekt, om en enhet inte fungerar korrekt när enhetsnamnet i maskinvaruprofilen ändras till namnet på den faktiska enheten, kan du anta att det finns ett problem med serviceobjektet från tillverkaren.

### <a name="training"></a>Kurs

Du kan använda kringutrustningssimulatorn för att lägga till ett realistiskt lager vid kassörsutbildningen när ingen fysisk maskinvaruinställning är tillgänglig. När kringutrustningssimulatorn ingår i utbildningsscenarier kan kassören interagera effektivare med kassan genom att ange indata som till exempel att streckkodsskanna produkter och dra presentkort, och genom att iaktta vilka kvitton som skrivs ut för en viss transaktion.

### <a name="testing"></a>Testa

Du kan använda kringutrustningssimulatorn för att testa produktstreckkoder, kvittoformat och så vidare, utan att använda en fysisk maskinvara i en virtuell miljö. Eftersom fysisk maskinvara behövs inte och du inte behöver distribuera en kassaklient på en maskinvarustation eller en fysisk dator, kan du snabbare testa ändringar som görs i back office.

## <a name="set-up-the-peripheral-simulator"></a>Ställa in kringutrustningssimulatorn
### <a name="set-up-a-hardware-profile"></a>Ställa in en maskinvaruprofil

1.  För att ställa in kringutrustningssimulatorn, gå till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.
2.  Klicka på **Ny** för att skapa en ny profil.
3.  Ange värden i fälten **Profilnummer** och **Beskrivning**.
4.  Använd följande tabell när du vill ställa in virtuella enheter som ska testas. Här följer en förklaring av kolumnerna i tabellen:
    -   **Enhet** – i den här kolumnen visas namnet på snabbfliken som du utvidgar för att ställa in enheten.
    -   **Enhetstyp** – den här kolumnen innehåller värdet som du väljer i fältet som är märkt med namnet på enheten.
    -   **Enhetsnamn** – i den här kolumnen visas det exakta värdet som du anger för enhetsnamn. **Viktigt!** Enhetsnamn som anges här är obligatoriska eftersom maskinvarustationen använder dessa specifika namn för att adressera enheterna. Enheten kan inte att användas om du inte använder dessa specifika namn.

    | Enhet            | Enhetstyp | Enhetsnamn              |
    |-------------------|-------------|--------------------------|
    | Skrivare           | OPOS        | MockOPOSPrinter          |
    | Radvisning      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | Utställare            | OPOS        | MockOPOSDrawer1          |
    | Kassalåda2           | OPOS        | MockOPOSDrawers          |
    | Skanner           | OPOS        | MockOPOSScanner          |
    | Skala             | OPOS        | MockOPOSScale            |
    | PIN-knappsats           | OPOS        | MockOPOSPinPad           |
    | Digital signatur | OPOS        | MockOPOSSignatureCapture |

**Anmärkning:** inga särskilda inställningar i maskinvaruprofilen krävs för att simulera händelser för tangentbords-wedge från streckkodsskanner och MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Tilldela maskinvaruprofilen till ett register

1.  När du har skapat maskinvaruprofilen, gå till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassor**.
2.  I listan **Kassor** klickar du på länken i fältet **Kassanummer** för den kassan som ska använda kringutrustningssimulatorn.
3.  Klicka på **Redigera**.
4.  I sektionen **Profiler** i fältet **Maskinvaruprofil**, välj den maskinvaruprofil som du har skapat för virtuell kringutrustning.
5.  Klicka på **Spara**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar i kanaldatabasen

1.  Gå till **Butik och handel** &gt; **Butikens IT** &gt; **Distributionsschema**.
2.  Välj distributionsschemat **1090**.
3.  Klicka på **Kör nu** för att synkronisera ändringar i kassan.

När data har synkroniserats finns den nya maskinvaruprofilen och ändringar i kassan i kanaldatabasen.

## <a name="install-the-peripheral-simulator"></a>Installera kringutrustningssimulatorn
1.  Gå till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.
2.  Klicka på **Hämta**, och klicka sedan på **PeripheralSimulator**. **Anmärkning:** Du måste inaktivera popup-blockerare innan du kan hämta kringutrustningssimulatorn.
3.  När hämtningen är klar öppnar du mappen **Hämtningar** och dubbelklickar på **VirtualPeripherals.msi** för att starta installationsprogrammet.
4.  Installera kringutrustningssimulatorn med standardinställningarna.

Förutom kringutrustningssimulatorn måste du installera Common Control-objekt från Monroe Consulting Services. I annat fall fungerar kringutrustningssimulatorn inte korrekt. Hämta Common Control-objekten genom att gå till <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Använda kringutrustningssimulatorn
För att starta kringutrustningssimulatorn, klicka på **Starta** på din dator, skriv **Kringutrustningssimulator för butik**, och välj sedan appen när den visas i sökresultaten. Klicka på ett enhetsnamn för att visa enheterna som stöds när du har startat kringutrustningssimulatorn. Enheterna visas som flikar till vänster i fönstret. Klicka på fliken för enheten om du vill visa en viss enhet.

### <a name="line-display-capabilities"></a>Funktioner för radvisning

Radvisningen är den första enheten som anges i kringutrustningssimulatorn. När den virtuella radvisningen har konfigurerats visar den radartiklar när de skannas i kassatransaktionen. Förutom radartiklar visas den summa som ska betalas när ett betalningsmedel väljs i kassan. Den visar även saldot som ska betalas om ett betalningsmedel har angetts men saldot fortfarande ska betalas för transaktionen. När kassan inte används kan ett meddelande visas som ange att kassalådan är stängd. Du måste konfigurera meddelandet på snabbfliken **Radvisning** i maskinvaruprofilen.

### <a name="cash-drawer-capabilities"></a>Funktioner för kassalådan

Kassalådan är den andra enheten som anges i kringutrustningssimulatorn. När maskinvaruprofilen har konfigurerats för att använda virtuella kassalådor öppnar kassan kassalådan för det aktiva skiftet som svar på kasslådsåtgärder som kassaavstämning, och så att kassören kan ge växel eller sätta in kontanter vid hämtköpstransaktioner (cash-and-carry) av standardtyp. De v kassalådorna har etiketterna **Huvudkassa** och **Sekundär kassa**. Dessa etiketter representerar Kassalåda och Kassalåda 2 i maskinvaruprofilen. När en låda stängs visas en bild av en stängd kassalåda och knappen på den stängda kassalådan har etiketten **Öppna kassalåda**. Om du klickar på den här knappen ersätts bilden med en bild av en öppen kassalåda för att ange att kassalådan är öppen nu. Knappen på den öppna kassalådan på har etiketten **Stäng kassalådan**. Flera åtgärder i kassan kan orsaka att öppna kassalådan. De flesta åtgärder kan inte fortsätta medan kassalådan är öppen. Undantagen är vissa procedurer vid dagsavslut. Om kassaanvändare får ett felmeddelande som säger att en åtgärd inte kan utföras när kassalådan är öppen, måste användaren stänga den virtuella eller fysiska kassalådan för att fortsätta. Om en kassalåda markeras som **Delad** i maskinvaruprofilen verifierar systemet inte att lådan är stängd innan en åtgärd. Åtgärden fortsätter som vanligt även om kassalådan är öppen. Detta beteende stöder scenarier där kassalådor delas av säljassistenter och en assistent använder en kassalåda när en annan assistent utför relaterade uppgifter på sin egen kassaenhet. Ändringar som görs i kassalådan blir inte uppenbara förrän det aktuella arbetsskiftet stängs och ett nytt skift öppnas.

### <a name="msr-capabilities"></a>MSR-funktioner

Kringutrustningssimulatorn ger robust stöd för virtuella MSR-åtgärder genom att arbeta i antingen OPOS- eller tangentbords-wedge-läge. OPOS-läget kräver att MSR konfigureras för att fungera som en OPOS-enhet i maskinvaruprofilen. Tangentbords-wedge-läget skickar bara tangentbords-wedge-datahändelser till Microsoft Windows. Förutom skillnaderna i inställningarna skiljer sig OPOS- och tangentbords-wedge-lägena åt på följande sätt:

-   Kassaklienten aktiverar OPOS MSR-enheter för specifika scenarier, t ex scenarier som tillåter magnetremsadata för att ange förmånskort eller presentkort.
-   I tangentbords-wedge-läge skickar kringutrustningssimulatorn tangentbords-wedge-data till det fält som är aktivt när dessa data skickas. Det påminner om vad som händer om du anger data genom att använda ett tangentbord. För att använda MSR som en tangentbord-wedge måste användaren byta till Retail Modern POS (MOPS) för att se till att data tas emot i rätt fält. Därför kan du konfigurera en fördröjning så att användaren får tid att säkerställa att data skickas till rätt fält.

#### <a name="testing-gift-and-payment-card-swipes"></a>Testa dragning av presentkort och betalkort

Den virtuella MSR som kringutrustningssimulatorn tillhandhåller låter dig också konfigurera specifika MSR-data för att testa scenarier för att dra presentkort och betalkort. Klicka på plustecknet (**+**) för att skapa ett kort och välj typen av kort. Ange sedan kortnumret eller spåra data som ska skickas till kassan, tillsammans med utgångsmånaden och utgångsåret för det kort som du definierar. Värdet som du väljer i fältet **Typ av kort** är bara en etikett som kan mappas till ett kort. Etiketten gör det enklare att identifiera korten när de dras genom kringutrustningssimulatorn. Du kan välja kort som har konfigurerats i kringutrustningssimulatorn med vänsterpilen (**&lt;**) och högerpilen (**&gt;**) ovanför bilden av kortet. Du kan redigera och ta bort kort med knapparna **Redigera** och **Ta bort** bredvid plustecknet knappen med (**+**).

### <a name="pin-pad"></a>PIN-knappsats

Du kan konfigurera PIN-knappsatssimulatorn för att simulera en OPOS PIN-knappsats. När en elektronisk betalning (EFT) utförs i kassan och kräver PIN-koden, anropar maskinvarustationen PIN-enheten för att fråga om PIN-koden. För att fungera kräver PIN-knappsatsen i kringutrustningssimulatorn stöd för EFT-betalningskoppling.

### <a name="printer"></a>Skrivare

Den virtuella skrivaren skrivare visar kvitton när de skrivs ut från kassan. Om en utskriftsåtgärd leder till flera kvitton kan du bläddra genom kvittona.

#### <a name="configure-receipt-printing"></a>Konfigurera kvittoutskrift

1.  Gå till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.
2.  Välj den maskinvaruprofil som du skapat för virtuell kringutrustning.
3.  På snabbfliken **Skrivare** klickar du på **Redigera**.
4.  I fältet **Kvittoprofil-ID** väljer du en kvittoprofil.
5.  Klicka på **Spara**.

### <a name="scale"></a>Skala

När en vägningsprodukt läggs till i kassatransaktionen och en våg är konfigurerad, hämtar kassan vikten från vågen. För både den virtuella och den fysiska vågen bör produkten eller vikten anges innan produkten läggs till i transaktionen. Innan du lägger till vågprodukten till transaktionen, gå till vägen i kringutrustningssimulatorn och använd plustecknet (**+**) eller minustecknet (**–**) för att justera vikten som vågen ska rapportera. Du kan även ange den önskade vikten direkt i fältet **Aktuellt värde**. Du kan justera viktenheterna för vågen med plustecknet (**+**), **Redigera** och **Ta bort**. På så sätt kan enheter anges utifrån de produkter som vägs eller det språk där vågen används.

#### <a name="configure-a-scale-product"></a>Konfigurera en vägningsprodukt

1.  Gå till **Butik och** **handel** &gt; **Produkter och kategorier** &gt; **Frisläppta produkter efter kategori**.
2.  Öppna produktposten.
3.  Välj produkten som ska vägas.
4.  På snabbfliken **Butik**, ange alternativet **Vägningsprodukt** från **Nej** till **Ja**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar i kanaldatabasen

1.  Gå till **Butik och handel** &gt; **Butikens IT** &gt; **Distributionsschema**.
2.  Välj distributionsschemat **1040**.
3.  Klicka på **Kör nu** för att synkronisera ändringar i kassan.

När data har synkroniserats, när en vägningsprodukt läggs till i kassatransaktionen, kontrollerar kassan vikten från vågen.

### <a name="signature-capture"></a>Digital signatur

Den virtuella enheten för digital signatur uppmanar användaren att ange en signatur på den virtuella knappsatsen för signatur när det betalningsmedel som används kräver en signatur. Användaren kan godkänna signaturen för att visa den i kassan. Kassören kan sedan godkänna signaturen. Signaturen sparas tillsammans med betalningsmedlet och synkroniseras till back office tillsammans med andra transaktionsdata.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Ställa in ett betalningsmedel så att signatur krävs

1.  Gå till **Butik och handel** &gt; **Kanaler** &gt; **Butiker** &gt; **Alla butiker**.
2.  Välj butik.
3.  Klicka på **Redigera**.
4.  Klicka på **Ställ in**, och sedan, i sektionen **Ställ in** klickar du på **Betalningsmetoder**.
5.  Klicka på **Redigera**.
6.  Välj den betalningsmetod som kräver en signatur.
7.  I avsnittet **Allmänt** under **Digital signatur**, anger du alternativet **Använd enhet för digital signatur** till **Ja**.
8.  I fältet **Minimibelopp för digital signatur**, ange minimibeloppet som ska utlösa en signatur.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar i kanaldatabasen

1.  Gå till **Butik och handel** &gt; **Butikens IT** &gt; **Distributionsschema**.
2.  Välj distributionsschemat **1070**.
3.  Klicka på **Kör nu** för att synkronisera ändringar i kassan.

När data har synkroniserats och ett betalningsmedel används som kräver en signatur, och beloppet uppnår signaturtröskeln, kräver kassan en signatur på den virtuella enheten för digital signatur.

## <a name="additional-configuration"></a>Ytterligare konfiguration
Du kan redigera konfigurationsfilen för kringutrustningssimulatorn för att på ett bättre sätt passa de scenarier som du testar. Konfigurationsfilen finns på C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Konfigurationsfilen definierar de enheter som finns tillgängliga för test på vågen, de korttyper som är tillgängliga för testning samt streckkodstyper. Genom att ändra textvärdena i konfigurationsfilen kan du exempelvis lägga till en ny korttyp eller måttenhet som kan väljas vid körning. De nya värdena visas när programmet startas om.

## <a name="troubleshooting"></a>Felsökning
Aktiviteter för kringutrustningssimulatorn loggas i kringutrustningssimulatorn. Loggen finns på C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Kringutrustningssimulatorn rapporterar också fel till händelseloggen i Windows som du kan nå på **Program- och tjänstloggar** &gt; **Microsoft** &gt; **DynamicsAX**. Om ändringar som du gjort i maskinvaruprofilen eller andra områden inte är uppenbara när du använder MPOS eller kringutrustningssimulatorn, kontrollera de distributionsschemaläggarjobb som du använde för att synkronisera data till kanaldatabasen. Om ändringarna har synkroniserats, men fortfarande inte är uppenbara i kassan, startar du om kassaklienten. Ändringar i konfigurerade kassalådor gäller inte förrän ett nytt skift skapas. Om du ändrar i kassalådor, se därför alltid till att stänga befintligt skift om du vill testa de nya inställningarna för kassalådan. Ibland, om en tillverkares drivrutin installeras efter Common Control-objekt från Monroe Consulting Services, kan drivrutinen göra att Common Control-objekt slutar fungera korrekt. I så fall bör du installera om Common Control-objekten.

<a name="see-also"></a>Se även
--------

[Översikt över kringutrustning i butik](retail-peripherals-overview.md)




