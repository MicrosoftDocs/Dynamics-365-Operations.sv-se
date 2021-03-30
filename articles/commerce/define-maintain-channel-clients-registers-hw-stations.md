---
title: Ansluta kringutrustning till POS
description: Detta avsnitt innehåller information om hur du ansluter kringutrustning till Retail POS.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 03a77306f17fbf76a4bcd1ecd682a4e2f199d330
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213732"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Ansluta kringutrustning till POS

[!include [banner](includes/banner.md)]

Detta avsnitt innehåller information om hur du ansluter kringutrustning till Retail POS.

> [!NOTE]
> Specifika installationsinstruktioner finns i [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) och [Konfigurera, installera och aktivera Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Nyckelkomponenter

Flera komponenter används för att definiera relationerna mellan en butik, kassaregistren eller kanalerna i butiken och kringutrustningen de registrerar eller kanalerna som används för att bearbeta transaktioner. Det här avsnittet innehåller en beskrivning av varje komponent och hur den ska användas i butiken.

### <a name="pos-registers"></a>Kassaregister

Navigering: klicka på **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassor**.

Kassaregistret är en enhet som används för att definiera egenskaperna hos en viss instans av POS. Dessa egenskaper omfattar maskinvaruprofil eller inställningar för kringutrustning som ska användas i POS, butiken som POS har mappats till och den visuella upplevelsen när användare loggar in på den POS.

### <a name="devices"></a>Enheter

Navigering: klicka på **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Enheter**.

En enhet är en entitet som representerar en fysisk instans av en enhet som är mappad till ett kassaregister. När en enhet skapas är den mappad till ett kassaregister. Enhetsentiteten spårar information om när ett kassaregister aktiveras, vilken typ av klient som används och programpaketet som har distribuerats till en viss enhet. Det finns två typer av enheter: **Retail modern POS** (modernt butikskassaregister (MPOS)) och **Retail Cloud POS** (molnbaserat butikskassaregister).

#### <a name="mpos"></a>MPOS

MPOS är ett kassaklientprogram som är installerat på Windows 8.1 eller ett senare PC-baserat operativsystem. Om programtypen **Retail modern POS** har mappats till en enhet kan hämtningspaketet anges för en viss enhet. Paketet kan anpassas för att inkludera olika versioner av installationspaketet. Möjligheten att distribuera olika paket ger flexibilitet i de fall där olika kassaregister kan behöva olika integrationer. MPOS distribueras tillsammans med en inbyggd maskinvarustation.

#### <a name="cloud-pos"></a>Cloud POS

Molnkassa är en webbläsarbaserad kassa. Eftersom det körs i webbläsaren kräver molnkassan inte Windows 8.1 eller ett senare datorbaserat operativsystem. Om programtypen **Retail Cloud POS** är mappad till en viss enhet i administration, kan enheten användas via webbläsaren utan att paketet behöver hämtas eller installeras. Cloud POS kräver en maskinvarustation för att kunna använda maskinvara utöver tangentbordbaserad skanning av streckkoder.

### <a name="hardware-profile"></a>Maskinvaruprofil

Navigering: Klicka på **Commerce** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.

En maskinvaruprofil identifierar den maskinvara som är ansluten till ett kassaregister eller en maskinvarustation. Maskinvaruprofilen används också för att ange betalningsprocessorparametrar som ska användas vid kommunikation med SDK (Software Development Kit) för betalning. (SDK för betalning distribueras som en del av maskinvarustationen.)

### <a name="hardware-station"></a>Hardware Station

Navigering: Klicka på **Retail och Commerce** &gt; **Kanaler** &gt; **Butiker** &gt; **Alla butiker**. Markera en butik och klicka på snabbfliken **Maskinvarustationer**.

En station för maskinvara är en instans av affärslogiken som ligger till grund för kringutrustningen för POS. En maskinvarustation installeras automatiskt tillsammans med MPOS. Alternativt kan maskinvarustationen installeras som en fristående komponent och sedan kommas åt via MPOS eller Cloud POS via en webbtjänst. Maskinvarustationen måste definieras på kanalnivå.

### <a name="hardware-station-profile"></a>Maskinvarustationens profil

Navigering: Klicka på **Commerce** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Profiler för maskinvarustation**.

Medan maskinvarustationen som anges på kanalnivå innehåller instansspecifik information såsom URL för maskinvarustationen innehåller maskinvarustationens profil information som kan vara statisk eller delad över flera maskinvarustationer. Statisk information innehåller den port som ska användas, maskinvarustationspaketet och maskinvaruprofilen. Statisk information innehåller också en beskrivning av vilken typ av maskinvarustation som distribueras såsom **Checka ut** eller **Returer** beroende på vilken maskinvara som krävs för varje specifik maskinvarustation.

## <a name="scenarios"></a>Scenarier

### <a name="mpos-with-connected-peripheral-devices"></a>MPOS med ansluten kringutrustning

[![Traditionell, fast kassa](./media/traditional-300x279.png)](./media/traditional.png)

Anslut MPOS till kassans kringutrustning i ett traditionellt, fast kassascenario genom att först navigera till själva POS och tilldela en maskinvaruprofil. Du hittar kassaregister om du går till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassor**. 

När du har tilldelat maskinvaruprofilen ska du synkronisera ändringar i kanaldatabasen med hjälp av distributionsschemat **Kassor**. Du hittar distributionsscheman om du går till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema**. 

Ställ därefter in en "lokal" maskinvarustation på kanalen. Klicka på **Retail och Commerce** &gt; **Kanaler** &gt; **Butiker** &gt; **Alla butiker** och välj en butik. 

Välj sedan snabbfliken **Maskinvarustationer** och klicka på **Lägg till** för att lägga till en maskinvarustation. Ange en beskrivning, ange **localhost** som värdnamn och synkronisera sedan ändringarna till kanalen med hjälp av distributionsschemat **Kanalkonfiguration**. Du hittar distributionsscheman om du går till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema**. 

Gå sedan till MPOS och använd åtgärden **Välj maskinvarustation** och markera maskinvarustationen **localhost**. Ställ in maskinvarustation till **Aktiv**. Den maskinvaruprofil som används i det här fallet bör komma från själva kassaregistret. En maskinvarustationsprofil är inte obligatorisk för det här scenariot.

> [!NOTE]
> Vissa ändringar av maskinvaruprofilen såsom ändringar av kassalådor kräver att ett nytt skift öppnas efter att ändringarna har synkroniserats till kanalen.
>
> Cloud POS måste använda den fristående maskinvarustationen för kommunikation med kringutrustningen.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS eller Cloud POS med en fristående maskinvarustation

[![Delad kringutrustning](./media/shared-300x254.png)](./media/shared.png)

I det här scenariot delas en fristående maskinvarustation mellan MPOS- och Cloud POS-klienter. Det här scenariot kräver att du skapar en maskinvarustationsprofil för att du ska kunna specificera vilket hämtningsbart paket, vilken port och vilken maskinvaruprofil maskinvarustationen använder. Du hittar maskinvarustationsprofilen genom att gå till **Butik och handel** &gt; **Kanalinställning** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Maskinvarustationens profiler**. 

När du har skapat maskinvarustationsprofilen, navigera till den specifika kanalen (**Retail och Commerce** &gt; **Kanaler** &gt; **Butiker** &gt; **Alla butiker**) och lägg till en ny maskinvarustation. Mappa den nya maskinvarustationen till maskinvarustationsprofilen som skapades tidigare. 

Tillhandahåll sedan en beskrivning som hjälper kassören att identifiera maskinvarustationen. I fältet **Värdnamn** anger du värdmaskinens URL i följande format: `https://<MachineName:Port>/HardwareStation`. (Ersätt **&lt;MachineName:Port&gt;** med det faktiska datornamnet på maskinvarustationen och den port som anges i maskinvarustationens profil.) För en fristående maskinvarustation måste du också ange terminal-ID för elektronisk betalning (EFT). Det här värdet identifierar den EFT-terminal som är ansluten till maskinvarustationen när betalningskopplingen kommunicerar med betalningsförmedlaren. 

Navigera sedan från den faktiska maskinvarustationen till kanalen och välj maskinvarustation. Klicka på **Hämta** och installera maskinvarustationen. 

Använd därefter MPOS eller Clod POS för att utföra åtgärden **Välj maskinvarustation** för att välja den maskinvarustation som tidigare installerades. Välj **Koppla** för att upprätta en säker förbindelse mellan POS och maskinvarustationen. Det här steget måste slutföras en gång för varje kombination av en kassa och en maskinvarustation. 

När maskinvarustationen är kopplad används samma operation för att aktivera maskinvarustationen medan den används. I det här scenariot ska maskinvaruprofilen tilldelas maskinvarustationens profil snarare än själva kassaapparaten. Om en maskinvarustation av någon anledning inte har tilldelats någon maskinvaruprofil direkt, kommer den maskinvaruprofil som tilldelats kassaapparaten att användas.

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

    - Ange kvittonumreringsmaskar (som kan innefatta segment för butiksnummer, terminalnummer och konstanter) och om försäljning, returer, försäljningsorder och offerter ska skrivas ut i olika sekvenser eller om alla ska följa samma sekvens.

#### <a name="receipt-profiles"></a>Kvittoprofiler

Kvittoprofiler tilldelas till skrivare via maskinvaruprofilen. De används för att ange vilken typ av kvitto som skrivs ut på en viss skrivare. Profilerna innehåller inställningar för kvittoformat och inställningar som fastställer om kvittot alltid ska skrivas ut eller om kassören ska uppmanas att besluta om kvittot ska skrivas ut. Olika skrivare kan också använda olika kvittoprofiler. Exempel: Skrivare 1 är en termisk standardkvittoskrivare och har därför ett mindre kvittoformat. Skrivare 2 är dock en skrivare som skriver ut fullskaliga kvitton som enbart används för att skriva ut kundorderkvitton, vilket kräver mer utrymme.

#### <a name="hardware-profiles"></a>Maskinvaruprofiler

Maskinvaruprofiler beskrevs som en komponent för klientinstallation tidigare i denna artikel. Maskinvaruprofiler tilldelas direkt till kassaregister eller till maskinvarustationsprofiler. De används för att ange vilka typer av enheter ett visst kassaregister eller maskinvarustation använder. Maskinvaruprofiler kan även användas för att ange EFT-inställningar som används för att kommunicera med betalnings-SDK:n.

#### <a name="visual-profiles"></a>Visuella profiler

Visuella profiler tilldelas på registernivå. De används för att ange temat för en viss kassa. Profilerna innehåller inställningarna för typen av program som ska användas (MPOS eller Cloud POS), accentfärg och tema, teckensnittsschema, inloggningsbakgrund och kassabakgrund.

### <a name="custom-fields"></a>​Anpassade fält

Du kan skapa anpassade fält om du vill lägga till fält som inte tillhandahålles direkt vid leverans till POS. Mer information om hur du använder anpassade fält finns i [Blogginlägget Arbeta med anpassade fält](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Språktext

Du kan åsidosätta standardsträngar i POS med hjälp av språktextposter. Lägga till en ny språktextrad om du vill åsidosätta en sträng i POS. Ange ett ID, standardsträngen som ska åsidosättas och den text som ska visas i POS i stället för standardsträngen.

### <a name="hardware-station-profiles"></a>Maskinvarustationens profiler

Maskinvarustationens profiler beskrevs tidigare i denna artikel. De används för att tilldela ej instansspecifik information till maskinvarustationer.

### <a name="channel-reports-configuration"></a>Konfiguration av kanalrapporter

Du ställer in de rapporter som är tillgängliga i kanalen på sidan **Rapportkonfiguration för kanal**. Du kan skapa nya rapporter genom att ange XML-definitionen för rapporten och tilldela rapporten till en viss behörighetsgrupp i POS.

### <a name="devices"></a>Enheter

Enheter beskrevs tidigare i denna artikel. De används för att hantera aktivering av ett visst kassaregister. Enheter används också för att ange vilket program som används för en viss kassa och det installationspaket som ska användas för att installera MPOS-klienten. Här är enhetens aktiveringstillstånd:

- **Väntande** – Enheten är redo att aktiveras.
- **Aktiverad** – Enheten har aktiverats.
- **Avaktiverad** – Enheten har avaktiverats i administration eller via POS.
- **Inaktiverad** – Enheten har inaktiverats.

Ytterligare aktiveringsrelaterad information omfattar arbetstagare som har ändrat aktiveringsstatus för enheten, en tidsstämpel för aktivering och om enhetskonfigurationen har verifierats.

### <a name="client-data-synchronization"></a>Klientdatasynkronisering

Alla ändringar av en kassaklient, förutom ändringar av enhetens aktiveringsstatus, måste synkroniseras till kanaldatabasen för att börja gälla. Om du vill synkronisera ändringar i kanaldatabasen, gå till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema** och kör det obligatoriska distributionsschemat. För klientändringar bör du köra distributionsschemat **Kassor** och även distributionsschemat **Kanalkonfiguration**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]