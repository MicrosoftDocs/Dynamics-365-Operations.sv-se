---
title: "Definiera och underhålla kanal klienter, register och stationer för maskinvara"
description: "Denna wiki innehåller information om hur du ansluter kringutrustning till Retail POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dee5745670ad86000795f2913f99f49c0f123a00
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-channel-clients-registers-and-hardware-stations"></a>Definiera och underhålla kanal klienter, register och stationer för maskinvara

Denna wiki innehåller information om hur du ansluter kringutrustning till Retail POS.

**Obs!** Särskilda installationsanvisningar hittar du i [Konfiguration och installation av Retail Hardware Station](retail-hardware-station-configuration-installation.md) och [Självservice hämtning/installation av Retail Modern POS och enhetsaktivering av Modern POS och Cloud POS](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Nyckelkomponenter
Flera komponenter används för att definiera relationerna mellan en butik, kassaregistren eller kanalerna i butiken och kringutrustningen de registrerar eller kanalerna som används för att bearbeta transaktioner. Det här avsnittet innehåller en beskrivning av varje komponent och hur den ska användas i butiken.

### <a name="pos-registers"></a>Kassaregister

Navigering: Klicka **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**. POS-register är en enhet som används för att definiera egenskaperna hos en viss instans av KASSAN. Dessa egenskaper omfattar maskinvaruprofil eller inställningar för retail-kringutrustning som ska användas vid kassan och butiken som kassan har mappats till den visuella upplevelsen för användare som loggar in som registreras.

### <a name="devices"></a>Enheter

Navigering: Klicka **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**enheter**. En enhet är en entitet som representerar en fysisk instans av en enhet som är mappad till ett kassaregister. När en enhet skapas är den mappad till ett kassaregister. Enhetsentiteten spårar information om när ett kassaregister aktiveras, vilken typ av klient som används och programpaketet som har distribuerats till en viss enhet. Det finns två typer av enheter: **Retail Modern POS** (modernt butikskassaregister (MPOS)) och **Retail Cloud POS** (molnbaserat butikskassaregister).

#### <a name="mpos"></a>MPOS

MPOS är ett kassaklientprogram som är installerat på Windows 8.1 eller ett senare PC-baserat operativsystem. Om programtypen **Retail modern POS** har mappats till en enhet kan hämtningspaketet anges för en viss enhet. Paketet kan anpassas för att inkludera olika versioner av installationspaketet. Möjligheten att distribuera olika paket ger flexibilitet i de fall där olika kassaregister kan behöva olika integrationer. MPOS distribueras tillsammans med en inbyggd maskinvarustation.

#### <a name="cloud-pos"></a>Cloud POS

Molnet POS är ett webbläsarbaserat POS. Eftersom det körs i webbläsaren kräver molnbaserad kassa inte Windows 8.1 eller en senare operativsystemsversion datorbaserade. Om programtypen **Retail Cloud POS** är mappad till en viss enhet i back office, kan enheten användas via webbläsaren utan att paketet behöver hämtas eller installeras. Cloud POS kräver en maskinvarustation för att kunna använda maskinvara utöver tangentbordbaserad skanning av streckkoder.

### <a name="hardware-profile"></a>Maskinvaruprofil

Navigering: Klicka **Commerce**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**. En maskinvaruprofil identifierar den maskinvara som är ansluten till ett kassaregister eller en maskinvarustation. Maskinvaruprofilen används också för att ange betalningsprocessorparametrar som ska användas vid kommunikation med SDK (Software Development Kit) för betalning. (SDK för betalning distribueras som en del av maskinvarustationen.)

### <a name="hardware-station"></a>Maskinvarustation

Navigering: Klicka **butik och handel**&gt;**kanaler**&gt;**detaljhandel**&gt;**alla detaljhandel**. Markera en butik och klicka på snabbfliken **Maskinvarustationer**. En station för maskinvara är en instans av affärslogiken som ligger till grund för kringutrustningen för kassan. En maskinvarustation installeras automatiskt tillsammans med MPOS. Alternativt kan maskinvarustationen installeras som en fristående komponent och sedan kommas åt via MPOS eller Cloud POS via en webbtjänst. Maskinvarustationen måste definieras på kanalnivå.

### <a name="hardware-station-profile"></a>Maskinvarustationens profil

Navigering: Klicka **Commerce**&gt;**kanal**&gt;**POS-inställning**&gt;**profiler för kassa**&gt;**station maskinvaruprofiler**. Medan maskinvarustationen som anges på kanalnivå innehåller instansspecifik information såsom URL för maskinvarustationen innehåller maskinvarustationens profil information som kan vara statisk eller delad över flera maskinvarustationer. Statisk information innehåller den port som ska användas, maskinvarustationspaketet och maskinvaruprofilen. Statisk information innehåller också en beskrivning av vilken typ av maskinvarustation som distribueras såsom **Checka ut**eller **Returer** beroende på vilken maskinvara som krävs för varje specifik maskinvarustation.

## <a name="scenarios"></a>Scenarier
### <a name="mpos-with-connected-peripheral-devices"></a>MPOS med ansluten kringutrustning

[![Traditionell fast försäljningsstället](./media/traditional-300x279.png)](./media/traditional.png) för att anslutas POS kringutrustning i ett traditionellt, fast POS scenario MOPS först navigera till själva registret och tilldela en maskinvaruprofil. Du hittar kassor i **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**. När du har tilldelat maskinvaruprofilen ska du synkronisera ändringar i kanaldatabasen med hjälp av distributionsschemat "Kassor". Du scheman fördelning på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**. Ställ därefter in en "lokal" maskinvarustation på kanalen. Klicka på **butik och handel**&gt;**kanaler**&gt;**detaljhandel**&gt;**alla detaljhandel**, och välj en butik. Välj sedan snabbfliken **Maskinvarustationer** och klicka på **Lägg till** för att lägga till en maskinvarustation. Ange en beskrivning, ange **localhost** som värdnamn och synkronisera sedan ändringarna till kanalen med hjälp av distributionsschemat "Kanalkonfiguration". Du scheman fördelning på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**. Gå sedan till MPOS och använd åtgärden **Välj maskinvarustation** och markera maskinvarustationen **localhost**. Ställ in maskinvarustation till **Aktiv**. Den maskinvaruprofil som används i det här fallet bör komma från själva kassaregistret. En maskinvarustationsprofil är inte obligatorisk för det här scenariot. **Obs!** Vissa ändringar av maskinvaruprofilen såsom ändringar av kassalådor kräver att ett nytt skift öppnas efter att ändringarna har synkroniserats till kanalen. **Obs!** Cloud POS måste använda den fristående maskinvarustationen för kommunikation med kringutrustningen i butiken.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS eller Cloud POS med en fristående maskinvarustation

\[Rubrik-id = "bilaga\_340041" justera = "alignleft" width = "300"\][![delad kringutrustning](./media/shared-300x254.png)](./media/shared.png) delad kringutrustning\[/beskrivning\] stationerna fristående maskinvara i det här scenariot delas bland MOPS och molnbaserad kassa klienter. Det här scenariot kräver att du skapar en maskinvarustationsprofil för att du ska kunna specificera vilket hämtningsbart paket, vilken port och vilken maskinvaruprofil maskinvarustationen använder. Du hittar station maskinvaruprofil på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**station maskinvaruprofiler**. När du har skapat station maskinvaruprofil navigera till specifika butikskanal (**butik och handel**&gt;**kanaler**&gt;**detaljhandel**&gt;**alla detaljhandel**), och Lägg till en ny maskinvara station. Mappa den nya maskinvarustationen till maskinvarustationsprofilen som skapades tidigare. Tillhandahåll sedan en beskrivning som hjälper kassören att identifiera maskinvarustationen. I den **värdnamn** ange maskin Värdadressen i följande format: **https://&lt;MachineName:Port&gt;/HardwareStation**. (Ersätter **&lt;MachineName:Port&gt;** med det faktiska datornamnet på stationen maskinvara och den port som anges i maskinvaruprofilen station.) För en fristående maskinvara radiostation måste du också ange överföra elektronisk betalningsöverföring (EFT) terminal-ID. Det här värdet identifierar den EFT-terminal som är ansluten till maskinvarustationen när betalningskopplingen kommunicerar med betalningsförmedlaren. Navigera sedan från den faktiska maskinvarustationen till kanalen och välj maskinvarustation. Klicka på **Hämta** och installera maskinvarustationen. Använd därefter MPOS eller Clod POS för att utföra åtgärden **Välj maskinvarustation** för att välja den maskinvarustation som tidigare installerades. Välj **Koppla** för att upprätta en säker förbindelse mellan kassan och maskinvarustationen. Det här steget måste slutföras en gång för varje kombination av en kassa och en maskinvarustation. När maskinvarustationen är kopplad används samma operation för att aktivera maskinvarustationen medan den används. I det här scenariot ska maskinvaruprofilen tilldelas maskinvaruprofilen station i stället för själva journalen. Om stationerna maskinvara inte har en maskinvaruprofil som direkt tilldelats av någon anledning, används maskinvaruprofil som tilldelats journalen

## <a name="client-maintenance"></a>Underhåll av klient
### <a name="registers"></a>Kassor

Kassor hanteras i första hand via själva kassan och via de profiler som är kopplade till kassan. Attribut som är specifika för en enskild kassa hanteras på kassanivå. Dessa attribut omfattar butiken där kassan används, kassanumret, beskrivningen och det EFT-terminal-ID som är specifikt för själva kassan.

### <a name="pos-profiles"></a>Kassaprofiler

Du hittar POS-profiler i **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**. Det är praktiskt att hantera många aspekter av en kassa via profiler, eftersom profilerna kan delas av många kassor. Profiler kan mappas antingen till en enskild kassa eller, om en profil används på butiksnivå, till en butik. I följande avsnitt beskrivs kassaprofiler och hur de används.

#### <a name="offline-profile"></a>Offlineprofil

Offline-profilen ställs in på butiksnivån. Den används för att ange inställningarna för överföring av transaktioner som utförs på en kassa när kassan inte är ansluten till kanalens databas.

#### <a name="functionality-profile"></a>Funktionsprofil

Funktionsprofilen ställs in på butiksnivån. Den används för att ange inställningar för hela butiken om funktioner som kan utföras i KASSAN. Följande funktioner hanteras via funktionsprofilen. Dessa funktioner är ordnade efter snabbfliken.

-   Snabbfliken **Allmänt**:
    -   Internationella standardiseringsorganisationen (ISO).
    -   Skapa en kund i offlineläge.
    -   Profil för att ta emot e-post.
    -   Central autentisering av personalinloggning.
-   Snabbfliken **Funktioner**:
    -   Hantering av inloggning och utökad inloggning.
    -   Ekonomiska aspekter och valutarelaterade aspekter för kassan såsom inmatning av priser och om decimaler som krävs för mindre valuta.
    -   Aktivera tidsregistrering via kassan.
    -   Hur produkter och betalningar visas i kassan och på kvitton.
    -   Dagsavstämning.
    -   Kvarhållningsparametrar för kanalens databastransaktion.
    -   Hur kunder letas upp och skapas från kassan.
    -   Hur rabatter beräknas.
-   Snabbfliken **Belopp**:
    -   Tillåtna högsta och lägsta priser.
    -   Rabattprogram och beräkning.
-   Snabbfliken **Infokoder**:
    -   Alla aspekter av hur Infokoder hanteras i KASSAN. Mer information finns i [Infokoder](info-codes-retail.md).
-   Snabbfliken **Kvittonumrering**:
    -   Ange kvittonumreringsmaskar (som kan innefatta segment för butiksnummer, terminalnummer och konstanter) och om försäljning, returer, försäljningsorder och offerter ska skrivas ut i olika sekvenser eller om alla ska följa samma sekvens.

#### <a name="receipt-profiles"></a>Kvittoprofiler

Kvittoprofiler tilldelas till skrivare via maskinvaruprofilen. De används för att ange vilken typ av kvitto som skrivs ut på en viss skrivare. Profilerna innehåller inställningar för kvittoformat och inställningar som fastställer om kvittot alltid ska skrivas ut eller om kassören ska uppmanas att besluta om kvittot ska skrivas ut. Olika skrivare kan också använda olika kvittoprofiler. Exempel: Skrivare 1 är en termisk standardkvittoskrivare och har därför ett mindre kvittoformat. Skrivare 2 är dock en skrivare som skriver ut fullskaliga kvitton som enbart används för att skriva ut kundorderkvitton, vilket kräver mer utrymme.

#### <a name="hardware-profiles"></a>Maskinvaruprofiler

Maskinvaruprofiler beskrevs som en komponent för klientinstallation tidigare i denna artikel. Maskinvaruprofiler tilldelas direkt till kassaregister eller till maskinvarustationsprofiler. De används för att ange vilka typer av enheter ett visst kassaregister eller maskinvarustation använder. Maskinvaruprofiler kan även användas för att ange EFT-inställningar som används för att kommunicera med betalnings-SDK:n.

#### <a name="visual-profiles"></a>Visuella profiler

Visuella profiler tilldelas på registernivå. De används för att ange temat för en viss kassa. Profilerna innehåller inställningarna för typen av program som ska användas (MPOS eller Cloud POS), accentfärg och tema, teckensnittsschema, inloggningsbakgrund och kassabakgrund.

### <a name="custom-fields"></a>Anpassade fält

Du kan skapa anpassade fält om du vill lägga till fält som inte är direkt vid leverans till KASSAN. Mer information om hur du använder anpassade fält finns på [arbetar med anpassade fält blogginlägg](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Språktext

Du kan åsidosätta standardsträngar i kassan med hjälp av språktextposter. Lägga till en ny språktextrad om du vill åsidosätta en sträng i kassan. Ange ett ID, standardsträngen som ska åsidosättas och den text som ska visas i kassan i stället för standardsträngen.

### <a name="hardware-station-profiles"></a>Maskinvarustationens profiler

Maskinvarustationens profiler beskrevs tidigare i denna artikel. De används för att tilldela ej instansspecifik information till maskinvarustationer.

### <a name="channel-reports-configuration"></a>Konfiguration av kanalrapporter

Du ställer in de rapporter som är tillgängliga i butikskanalen på sidan **Rapportkonfiguration för butikskanal**. Du kan skapa nya rapporter genom att ange XML-definitionen för rapporten och tilldela rapporten till en viss behörighetsgrupp i kassan.

### <a name="devices"></a>Enheter

Enheter beskrevs tidigare i denna artikel. De används för att hantera aktivering av ett visst kassaregister. Enheter används också för att ange vilket program som används för en viss kassa och det installationspaket som ska användas för att installera MPOS-klienten. Här är enhetens aktiveringstillstånd:

-   **Väntande** – Enheten är redo att aktiveras.
-   **Aktiverad** – Enheten har aktiverats.
-   **Avaktiverad** – Enheten har avaktiverats i back office eller via kassan.
-   **Inaktiverad** – Enheten har inaktiverats.

Ytterligare aktiveringsrelaterad information omfattar arbetstagare som har ändrat aktiveringsstatus för enheten, en tidsstämpel för aktivering och om enhetskonfigurationen har verifierats.

### <a name="client-data-synchronization"></a>Klientdatasynkronisering

Alla ändringar av en kassaklient, förutom ändringar av enhetens aktiveringsstatus, måste synkroniseras till kanaldatabasen för att börja gälla. Om du vill synkronisera ändringar i databasen kanal, gå till **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**, och köra nödvändiga distributionsschema. För klientändringar bör du köra distributionsschemat "Kassor" och även distributionsschemat "Kanalkonfiguration".


