---
title: Ansluta kringutrustning till POS
description: Denna artikel innehåller information om hur du ansluter kringutrustning till Retail POS.
author: BrianShook
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ffee75e1713c7c9d31b1d023cd055c2f1a3fc43d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897118"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Ansluta kringutrustning till POS

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om hur du ansluter kringutrustning till Retail POS.

> [!NOTE]
> Specifika installationsinstruktioner finns i [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) och [Konfigurera, installera och aktivera Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Nyckelkomponenter

Flera komponenter används för att definiera relationerna mellan en butik, kassaregistren eller kanalerna i butiken och kringutrustningen de registrerar eller kanalerna som används för att bearbeta transaktioner. Det här avsnittet innehåller en beskrivning av varje komponent och hur den ska användas i butiken.

### <a name="pos-registers"></a>Kassaregister

Navigering: klicka på **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassor**.

Kassaregistret är en enhet som används för att definiera egenskaperna hos en viss instans av POS. Dessa egenskaper omfattar maskinvaruprofil eller inställningar för kringutrustning som ska användas i POS, butiken som POS har mappats till och den visuella upplevelsen när användare loggar in på den POS.

### <a name="devices"></a>Enheter

Navigering: klicka på **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Enheter**.

En enhet är en entitet som representerar en fysisk instans av en enhet som är mappad till en kassaapparat. När en enhet skapas är den mappad till en kassaapparat. Enhetsentiteten spårar information om när en kassaapparat aktiveras, vilken typ av klient som används och programpaketet som har distribuerats till en viss enhet. Det finns två typer av enheter: **Retail modern POS** (modern butikskassaapparat (MPOS)) och **Retail Cloud POS** (molnbaserat butikskassaapparater).

#### <a name="mpos"></a>MPOS

MPOS är ett kassaklientprogram som är installerat på Windows 8.1 eller ett senare PC-baserat operativsystem. Om programtypen **Retail modern POS** har mappats till en enhet kan hämtningspaketet anges för en viss enhet. Paketet kan anpassas för att inkludera olika versioner av installationspaketet. Möjligheten att distribuera olika paket ger flexibilitet i de fall där olika kassaapparater kan behöva olika integreringer. MPOS distribueras tillsammans med en inbyggd maskinvarustation.

#### <a name="cloud-pos"></a>Cloud POS

Molnkassa är en webbläsarbaserad kassa. Eftersom det körs i webbläsaren kräver molnkassan inte Windows 8.1 eller ett senare datorbaserat operativsystem. Om programtypen **Retail Cloud POS** är mappad till en viss enhet i administration, kan enheten användas via webbläsaren utan att paketet behöver hämtas eller installeras. Cloud POS kräver en maskinvarustation för att kunna använda maskinvara utöver tangentbordbaserad skanning av streckkoder.

### <a name="hardware-profile"></a>Maskinvaruprofil

Navigering: Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**.

En maskinvaruprofil identifierar den maskinvara som är ansluten till en kassaapparat via en inbyggd eller delad maskinvarustation. Maskinvaruprofilen används också för att ange betalningsprocessorparametrar som ska användas vid kommunikation med SDK (Software Development Kit) för betalning. SDK för betalning distribueras som en del av maskinvarustationen.

### <a name="hardware-station"></a>Maskinvarustation

Navigering: Gå till **Butik och handel \> Kanaler \> Butiker \> Alla butiker**, välj en butik och välj sedan snabbfliken **Maskinvarystationer**.

En station för maskinvara är en instans av affärslogiken som ligger till grund för kringutrustningen för POS. En maskinvarustation installeras automatiskt tillsammans med MPOS. Alternativt kan maskinvarustationen installeras som en fristående komponent och sedan kommas åt via MPOS eller Cloud POS via en webbtjänst. Maskinvarustationen måste definieras på kanalnivå.

## <a name="scenarios"></a>Scenarier

### <a name="mpos-with-connected-peripheral-devices"></a>MPOS med ansluten kringutrustning

[![Traditionell, fast kassa.](./media/traditional-300x279.png)](./media/traditional.png)

Anslut MPOS till kassans kringutrustning i ett traditionellt, fast kassascenario genom att först navigera till själva POS och tilldela en maskinvaruprofil. Du hittar kassaapparater om du går till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassor**. 

När du har tilldelat maskinvaruprofilen ska du synkronisera ändringar i kanaldatabasen med hjälp av distributionsschemat **Kassor**. Du hittar distributionsscheman om du går till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema**. 

Konfigurera därefter en särskild maskinvarustation på kanalen. Gå till **Butik och handel \> Kanaler \> Butiker \> Alla butiker** och välj en butik. 

På snabbfliken **Maskinvarustationer** väljer du sedan **Lägg till** för att lägga till en maskinvarustation. Välj **Dedikerad** som maskinvarustationstyp och ange sedan en beskrivning. Fältet **Maskinvaruprofil** kan lämnas tomt, detta eftersom maskinvaruprofilen som används i det här scenariot kommer från själva kassaapparaten. Synkronisera sedan ändringarna med kanalen via distributionsschemat **Kanalkonfiguration**. Du hittar distributionsscheman på **Butik och handel \> IT för butik och handel \> Distributionsschema**. 

Slutligen kan du i MPOS använda åtgärden **Välj maskinvarustation** för att välja den maskinvarustation som matchar värdet du tidigare angett för beskrivningen samt konfigurera maskinvarustationen på **Aktiv**. 

> [!NOTE]
> - Vissa ändringar av maskinvaruprofilen såsom ändringar av kassalådor kräver att ett nytt skift öppnas efter att ändringarna har synkroniserats till kanalen.
> - Cloud POS måste använda den fristående maskinvarustationen för kommunikation med kringutrustningen.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS eller Cloud POS med en fristående maskinvarustation

[![Delad kringutrustning.](./media/shared-300x254.png)](./media/shared.png)

I det här scenariot delas en fristående maskinvarustation mellan MPOS- och Cloud POS-klienter. Detta scenario kräver att du skapar en delad maskinvarustation och anger vilket hämtningsbart paket, vilken port och vilken maskinvaruprofil som maskinvarustationen använder. Du definierar en ny maskinvarustation genom att välja snabbfliken **Maskinvarustationer** i den specifika kanalen (**Butik och handel \> Kanaler \> Butiker \> Alla butiker**) och lägger till en ny maskinvarustation av typen **Delad**. 

Tillhandahåll sedan en beskrivning som hjälper kassören att identifiera maskinvarustationen. I fältet **Värdnamn** anger du värdmaskinens URL i följande format: `https://<MachineName:Port>/HardwareStation`. (Ersätt **&lt;MachineName:Port&gt;** med det faktiska maskinnamnet på maskinvarustationen.) För en fristående maskinvarustation måste du också ange terminal-ID för elektronisk betalning (EFT). Det här värdet identifierar den EFT-terminal som är ansluten till maskinvarustationen när betalningskopplingen kommunicerar med betalningsförmedlaren. 

Navigera sedan från den maskin som ska agera värd för maskinvarustationen, gå till kanalen i administrationen och välj maskinvarustationen. Välj sedan **Hämta** för att hämta installationsprogrammet för maskinvarustationen och installera maskinvarustationen. Mer information om hur du installerar maskinvarustationen finns i [Konfigurera och installera maskinvarustation för butik](retail-hardware-station-configuration-installation.md). 

Använd därefter MPOS eller Clod POS för att utföra åtgärden **Välj maskinvarustation** för att välja den maskinvarustation som tidigare installerades. Välj **Koppla** för att upprätta en säker förbindelse mellan POS och maskinvarustationen. Det här steget måste slutföras en gång för varje kombination av en kassa och en maskinvarustation. 

När maskinvarustationen är kopplad används samma åtgärd för att aktivera maskinvarustationen medan den används. I det här scenariot ska maskinvaruprofilen tilldelas till den delade maskinvarustationen istället för själva kassaapparaten. Om en maskinvaruprofil av någon anledning inte har tilldelats någon maskinvarustation direkt, kommer den maskinvaruprofil som tilldelats kassaapparaten att användas.

## <a name="client-maintenance"></a>Underhåll av klient

### <a name="registers"></a>Kassor

Kassor hanteras i första hand via själva POS och via de profiler som är kopplade till POS. Attribut som är specifika för en enskild kassa hanteras på kassanivå. Dessa attribut omfattar butiken där POS används, kassanumret, beskrivningen och det EFT-terminal-ID som är specifikt för själva POS.

### <a name="pos-profiles"></a>Kassaprofiler

Du hittar kassaprofiler om du går till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler**. Det är praktiskt att hantera många aspekter av en kassa via profiler, eftersom profilerna kan delas av många kassor. Profiler kan mappas antingen till en enskild kassa eller, om en profil används på butiksnivå, till en butik. I följande avsnitt beskrivs kassaprofiler och hur de används.

#### <a name="offline-profile"></a>Offlineprofil

Offline-profilen ställs in på butiksnivån. Den används för att ange inställningarna för överföring av transaktioner som utförs på en kassa när POS inte är ansluten till kanalens databas.

#### <a name="functionality-profile"></a>Funktionsprofil

Funktionsprofilen ställs in på butiksnivån. Denna används för att ange inställningar för hela butiken som berör de funktioner som kan utföras i POS. Följande funktioner hanteras via funktionsprofilen. Dessa funktioner är ordnade efter snabbfliken.

- Snabbfliken **Allmänt**:

    - Internationella standardiseringsorganisationen (ISO).
    - Skapa en kund i offlineläge.
    - Profil för att ta emot e-post.
    - Central autentisering av personalinloggning.

- Snabbfliken **Funktioner**:

    - Hantering av inloggning och utökad inloggning.
    - Ekonomiska aspekter och valutarelaterade aspekter för POS såsom inmatning av priser och om decimaler som krävs för mindre valuta.
    - Aktivera tidsregistrering via POS.
    - Hur produkter och betalningar visas i POS och på kvitton.
    - Dagsavstämning.
    - Kvarhållningsparametrar för kanalens databastransaktion.
    - Hur kunder letas upp och skapas från POS.
    - Hur rabatter beräknas.

- Snabbfliken **Belopp**:

    - Tillåtna högsta och lägsta priser.
    - Rabattprogram och beräkning.

- Snabbfliken **Infokoder**:

    - Alla aspekter av hur infokoder hanteras i POS. För mer information, se [Infokoder och infokodgrupper](info-codes-retail.md).

- Snabbfliken **Kvittonumrering**:

    - Ange inleveransnumreringsmaskar (som kan innefatta segment för butiksnummer, terminalnummer och konstanter) samt huruvida försäljning, returer, försäljningsorder och offerter ska skrivas ut i olika sekvenser eller om alla ska följa samma sekvens.

#### <a name="receipt-profiles"></a>Kvittoprofiler

Inleveransprofiler tilldelas till skrivare via maskinvaruprofilen. De används för att ange vilken typ av kvitto som skrivs ut på en viss skrivare. Profilerna innehåller inställningar för kvittoformat och inställningar som fastställer om kvittot alltid ska skrivas ut eller om kassören ska uppmanas att besluta om kvittot ska skrivas ut. Olika skrivare kan också använda olika kvittoprofiler. Exempel: Skrivare 1 är en termisk standardkvittoskrivare och har därför ett mindre kvittoformat. Skrivare 2 är dock en skrivare som skriver ut fullskaliga kvitton som enbart används för att skriva ut kundorderkvitton, vilket kräver mer utrymme. Mer information finns i [konfigurera en inleveransprofil](configure-emailed-receipt-formats.md#configure-a-receipt-profile).

#### <a name="hardware-profiles"></a>Maskinvaruprofiler

Maskinvaruprofiler beskrevs som en komponent för klientinstallation tidigare i denna artikel. Maskinvaruprofiler tilldelas direkt till kassaapparaten eller till en delad maskinvarustation och används för att ange de typer av enheter som en specifik kassaapparat eller maskinvara använder. Maskinvaruprofiler kan även användas för att ange EFT-inställningar som används för att kommunicera med betalnings-SDK:n.

#### <a name="visual-profiles"></a>Visuella profiler

Visuella profiler används för att ange tema för en specifik kassaapparat och tilldelas på kassaapparatnivå. Profilerna innehåller inställningarna för typen av program som används (MPOS eller Cloud POS), accentfärg och tema, teckensnittsschema, inloggningssidans bakgrund och kassabakgrund. Mer information finns i [Skapa visuella profiler för kassa (POS)](tasks/create-pos-visual-profile-2016-02.md). 

### <a name="custom-fields"></a>Anpassade fält

Du kan skapa anpassade fält om du vill lägga till fält som inte tillhandahålles direkt vid leverans till POS. Mer information om hur du använder anpassade fält finns i [Blogginlägget Arbeta med anpassade fält](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Språktext

Du kan åsidosätta standardsträngar i POS med hjälp av språktextposter. Lägga till en ny språktextrad om du vill åsidosätta en sträng i POS. Ange ett ID, standardsträngen som ska åsidosättas och den text som ska visas i POS i stället för standardsträngen.

### <a name="channel-reports-configuration"></a>Konfiguration av kanalrapporter

Du konfigurerar de rapporter som är tillgängliga i kanalen på sidan **Rapportkonfiguration för kanal**. Du kan skapa nya rapporter genom att ange XML-definitionen för rapporten och tilldela rapporten till en viss behörighetsgrupp i POS.

### <a name="devices"></a>Enheter

Enheter beskrevs tidigare i denna artikel. De används för att hantera aktivering av en viss kassaapparat. Enheter används också för att ange vilket program som används för en viss kassa och det installationspaket som ska användas för att installera MPOS-klienten. Här är enhetens aktiveringstillstånd:

- **Väntande** – Enheten är redo att aktiveras.
- **Aktiverad** – Enheten har aktiverats.
- **Avaktiverad** – Enheten har avaktiverats i administration eller via POS.
- **Inaktiverad** – Enheten har inaktiverats.

Ytterligare aktiveringsrelaterad information omfattar arbetstagare som har ändrat aktiveringsstatus för enheten, en tidsstämpel för aktivering och om enhetskonfigurationen har verifierats.

### <a name="client-data-synchronization"></a>Klientdatasynkronisering

Alla ändringar av en kassaklient, förutom ändringar av enhetens aktiveringsstatus, måste synkroniseras till kanaldatabasen för att börja gälla. Om du vill synkronisera ändringar i kanaldatabasen, gå till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema** och kör det obligatoriska distributionsschemat. För klientändringar bör du köra distributionsschemat **Kassor** och även distributionsschemat **Kanalkonfiguration**.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
