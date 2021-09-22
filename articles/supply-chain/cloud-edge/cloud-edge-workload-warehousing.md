---
title: Arbetsbelastningar för distributionslagerhantering för moln- och molnskalningsenheter
description: Det här avsnittet innehåller information om funktionen som gör att enheterna kan köra valda processer från din arbetsbelastningar för distributionslagerhantering.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f3de160cb4e62f9b30c01c56fa6fe5a4dfad5229
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471726"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Alla affärsfunktioner för lagerstyrning stöds inte fullt ut för lagerställen som kör en arbetsbelastning på en skalningsenhet. Se till att bara använda de processer som det här ämnet explicit beskriver som det stöds.

## <a name="warehouse-execution-on-scale-units"></a>Lagerkörning på skalningsenheter

Med hjälp av arbetsbelastningar för lagerstyrning kan moln- och kantskalningsenheter köra valda processer från lagerstyrningsfunktionerna.

## <a name="prerequisites"></a>Förutsättningar

Du måste ha ett Dynamics 365 Supply Chain Management nav och en skalningsenhet som har distribuerats med arbetsbelastningen för lagerstyrning. Mer information om arkitektur och distributionsprocess finns i [Skalningsenheter i en distribuerad hybridtopologi](cloud-edge-landing-page.md).

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Så här fungerar arbetsbelastningar för lagerkörning på skalningsenheter

För processerna i arbetsbelastningen för lagerstyrning synkroniseras data mellan navet och skalningsenheter.

En skalningsenhet kan endast bevara de data som den äger. Konceptet för dataägarskap för skalningsenheter bidrar till att förhindra konflikter i flera original. Därför är det viktigt att du förstår vilka processdata som ägs av hubben och vilka som ägs av skalningsenheterna.

Beroende på vilka affärsprocesser som används kan samma datapost byta ägarskap mellan hubben och skalningsenheterna. I följande avsnitt ges ett exempel på det här scenariot.

> [!IMPORTANT]
> Vissa data kan skapas i både hubben och skalningsenheten. Exempel är **ID-nummer** och **Batchnummer**. Dedikerad konflikthantering tillhandahålls i händelse av ett scenario där samma unika post skapas både i hubben och i en skalningsenhet under samma synkroniseringscykel. När detta inträffar misslyckas nästa synkronisering och du måste gå till **Systemadministration > Förfrågningar > Arbetsbelastningsförfrågningar > Dubblettposter**, där du kan visa och slå samman data.

## <a name="outbound-process-flow"></a>Utgående processflöde

Den utgående processen för dataägande beror på om du använder lastplaneringsprocessen. I alla fal äger hubben *källdokumenten*, till exempel försäljningsorder och överföringsorder, samt orderallokeringen och relaterade data för ordertransaktioner. Men när du använder lastplaneringsprocessen skapas lasterna i hubben och ägs därför initialt av hubben. Som en del av processen *Frisläpp till lagerställe* överförs ägarskapet för lastdata till den dedikerade skalningsenhetsdistributionen, som blir ägare till den efterföljande *påfyllnadsbearbetningen för leverans* (t.ex. allokering, lagerpåfyllnad och skapande av efterfrågearbete). Därför kan lagerarbetare bara bearbeta utgående försäljnings- och överföringsorderarbete med hjälp av en Warehouse Management-mobilapp som är ansluten till distributionen som kör den specifika arbetsbelastningen för skalningsenheten.

Så snart som den slutliga arbetsprocessen för in lagret på en slutgiltig leveransplats (Baydoor) signalerar skalningsenhetens till hubben att uppdatera källdokumentets lagertransaktioner till *Plockade*. Till dess att den här processen körs och synkroniseras igen reserveras lagerbehållningen för skalningsenhetens arbetsbelastning fysiskt på lagerställenivå. Därmed kan du omedelbart bearbeta den utgående leveransbekräftelsen utan att invänta att synkroniseringen slutförs. Den efterföljande följesedeln för försäljningen och faktureringen eller överföringsorderleveransen för lasten hanteras i hubben.

I bilden nedan visas det utgående flödet och var de enskilda affärsprocesserna äger rum. (Välj diagrammet för att förstora det.)

[![Utgående processflöde.](media/wes_outbound_warehouse_processes-small.png "Utgående processflöde")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Utgående bearbetning med lastplanering

När du använder lastplaneringsprocessen skapas laster och leveranser i hubben och ägarskapet för data överförs till skalningsenheterna som en del av processen *Frisläpp till lagerställe*, vilket visas i bilden nedan.

![Utgående bearbetning med lastplanering.](./media/wes_outbound_processing_with_load_planning.png "Utgående bearbetning med lastplanering")

### <a name="outbound-processing-without-load-planning"></a>Utgående bearbetning utan lastplanering

När du inte använder lastplaneringsprocessen skapas försändelser i skalningsenheterna. Laster skapas också i skalningsenheterna som en del av en påfyllningsprocess.

![Utgående bearbetning utan lastplanering.](./media/wes_outbound_processing_without_load_planning.png "Utgående bearbetning utan lastplanering")

## <a name="inbound-process-flow"></a>Ingående processflöde

Navet äger följande data:

- Alla källdokument, t.ex. inköpsorder och produktionsorder
- Inkommande lastbearbetning
- Alla kostnader och finansiella uppdateringar

> [!NOTE]
> Det inkommande inköpsorderflödet skiljer sig begreppen från det utgående flödet. Du kan använda samma lagerställe på antingen skalningsenhet eller hubb beroende på om inköpsordern har frisläppts till lagerstället eller inte. Efter att du har frisläppt en order till lagerstället kan du bara arbeta med den ordern när du är inloggad på skalningsenheten.
>
> Om du använder processen *frisläppning till lagerställe*, [*lagerställeorder*](cloud-edge-warehouse-order.md) skapas lagerställeorder och ägarskapet för det relaterade mottagningsflödet tilldelas till skalningsenheten. Navet kommer inte att kunna registrera inkommande inleveranser.

Du måste logga in på navet för att använda processen *Släpp till distributionslager*. För bearbetning av inköpsorder går du till någon av följande sidor för att köra eller schemalägga den:

- **Anskaffning och källa > Inköpsorder > All inköpsorder > Distributionslager > Åtgärder > Släpp till distributionslager**
- **Lagerstyrning > Släpp till lagerställe > Automatiskt släpp av försäljningsorder**

När du använder **Automatiskt släpp av försäljningsorder**, du kan välja specifika inköpsorderrader baserat på en frågeställning. Ett vanligt scenario är att ställa in ett återkommande batchjobb som frisläpper alla bekräftade inköpsorderrader som förväntas komma in nästa dag.

Arbetaren kan köra mottagningsprocessen med hjälp av en mobilappen för distributionslagerhantering som är ansluten till skalningsenhet. Data registreras sedan av skalningsenheten och rapporteras mot inkommande lagerorder. Skapandet och bearbetningen av efterföljande borttagning kommer också att hanteras av skalningsenheten.

Om du inte använder processen *frisläppning till lager* och därför inte använder *lagerställeorder*, kan navet bearbeta inleverans och bearbetning av lager oberoende från skalningsenheter.

![Ingående bearbetningsflöde.](./media/wes-inbound-ga.png "Ingående processflöde")

När en arbetare gör inkommande registreringar med hjälp av en Warehouse Management-mobilapp inleveransprocess mot skalningsenheten, registreras ett kvitto för den relaterade lagerställeordern, som lagras i skalningsenheten. Arbetsbelastningen för skalningsenheten signalerar då till hubben att den ska uppdatera den relaterade inköpsorderns radtransaktioner till *Registrerade*. Så snart denna är färdig kommer du att kunna köra en produktinleverans för inköpsorder på navet.

I bilden nedan visas det ingående flödet och var de enskilda affärsprocesserna äger rum. (Välj diagrammet för att förstora det.)

[![Inkommande processflöde](media/wes_inbound_warehouse_processes-small.png "Inkommande processflöde")](media/wes_inbound_warehouse_processes.png)

## <a name="supported-processes-and-roles"></a>Processer och roller som stöds

Inte alla lagerstyrningsprocesser stöds i en arbetsbelastning för lagerkörning på en skalningsenhet. Därför rekommenderar vi att du tilldelar roller som matchar funktionerna som är tillgängliga för varje användare.

För att underlätta den här processen ingår en exempelroll med namnet *Lagerchef på arbetsbelastning* ingår i demodata på **Systemadministration \> Säkerhet \> Säkerhetskonfiguration**. Syftet med den här rollen är att göra det möjligt för lageransvariga att få åtkomst till arbetsbelastningen för lagerkörning på skalningsenheten. Rollen beviljar åtkomst till de sidor som är relevanta i kontexten för en arbetsbelastning som finns på en skalningsenhet.

Användarroller i en skalningsenhet tilldelas som en del av den ursprungliga datasynkroniseringen från navet till skalningsenhet.

Om du vill ändra rollerna som tilldelas en användare, gå till **systemadministration \> säkerhet \> tilldela användare till roller**. Användare som endast fungerar som lagerchefer på skalningsenheter bör endast tilldelas *Lagerchef på arbetsbelastning*. På så sätt ser du till att användarna bara har tillgång till de funktioner som stöds. Ta bort alla andra roller som har tilldelats dessa användare.

Användare som fungerar som lagerchefer på både nav- och skalningsenheterna bör tilldelas den befintliga rollen *Lagerarbetare*. Tänk på att den här rollen beviljar åtkomst till lagerarbetare till funktioner (t.ex. bearbetning av inleverans av överföringsorder) som visas i användargränssnittet (UI) men som för närvarande inte stöds i skalningsenheter.

### <a name="supported-warehouse-execution-processes"></a>Lagerstyrningsprocesser som stöds

Följande processer för lagerstyrning kan aktiveras för en arbetsbelastning för lagerstyrning på en skalningsenhet:

- Valda påfyllningsmetoder för försäljnings- och överföringsorder (validering, lastskapande, allokering, efterfrågepåfyllnad, skapande av behållare, skapande av arbete och utskrift av påfyllnadsetikett)

- Bearbeta lagerställearbete för försäljnings- och överföringsorder med hjälp av lagerställeprogrammet (inklusive påfyllnadsarbete)
- Fråga om lagerbehållning med hjälp av distributionslagerappen
- Skapa och köra lagerrörelser med hjälp av distributionslagerappen
- Skapa och bearbeta inventeringsarbete med hjälp av lagerställeprogrammet
- Göra lagerjusteringar med hjälp av lagerställeprogrammet
- Registrera inköpsorder och utföra inlagringsarbete med hjälp av distributionslagerappen

Följande typer av arbete kan skapas för en skalningsenhet och kan därför bearbetas som en del av en arbetsbelastningen för lagerstyrning:

- **Lagerrörelser** – manuell förflyttning och förflyttning per mallarbete.
- **Rullande inventering** – Inklusive en godkännande-/avvisandeprocess för avvikelser som en del av inventeringsfunktioner.
- **Inköpsorder** – Artikelinförselarbete via en lagerställeorder när inköpsorder inte är associerade med laster.
- **Försäljningsorder** – Enkel plockning och lastning.
- **Överföringsproblem** – Enkel plockning och lastning.
- **Lagerpåfyllnad** – Innefattar inte råmaterial för produktion.
- **Plats för slutförda varor** – Efter produktionsprocessen rapportera som färdig.
- **Plats för samprodukt och biprodukt** – Efter produktionsprocessen rapportera som färdig.

Inga andra typer av källdokumenthantering eller lagerarbete stöds för närvarande på skalningsenheter. För en arbetsbelastning för lagerkörning på en skalningsenhet kan du till exempel inte utföra en mottagningsprocess för överföringsorder (överföringsinleverans). Den måste i stället bearbetas via hubbinstansen.

> [!NOTE]
> Menyalternativ och knappar för mobila enheter för funktioner som inte stöds visas inte i _mobilappen för distributionslagerhantering_ när den är ansluten till en distribution av skalningsenhet.
> 
> När du kör en arbetsbelastning på en skalningsenhet kan du inte köra processer som inte stöds för det specifika lagerstället i navet. De tabeller som finns längre fram i det här avsnittet innehåller de funktioner som stöds.
>
> Valda arbetstyper för lagerställen kan skapas både i hubben och i skalningsenheter, men kan endast underhållas av den ägda hubben eller skalningsenheten (distributionen som skapade data).
>
> Även om en viss process stöds av en skalningsenhet bör du vara medveten om att alla data inte behöver synkroniseras från hubb till skalningsenhet, eller från skalningsenhet till hubb, vilket innebär en risk för att den oväntade systembearbetningen ska bearbetas. Exempel på detta scenario är:
> 
> - Om du använder en platsdirektivfråga som sammanfogar en datatabellpost som endast finns i hubb distribution.
> - Om du använder platsstatus och/eller platsvolymfunktioner. Dessa data kommer inte att synkroniseras mellan distributionerna och fungerar därför bara när platsens lagerbehållning uppdateras i en av distributionerna.

Följande funktioner för lagerstyrning stöds för närvarande inte i arbetslaster för skalningsenheter:

- Inkommande bearbetning av inköpsorderrader som tilldelats en last.
- Inkommande bearbetning av inköpsorder för ett projekt.
- Ingående och utgående bearbetning för artiklar som har aktiva spårningsdimensioner **Ägare** och/eller **Serienummer**.
- Bearbetning av lagret som har statusvärdet spärr.
- Ändra lagerstatus under en arbetsrörelseprocess.
- Orderallokerade flexibla dimensionsreservationer på lagernivå.
- Användning av funktionen *Lagerställets platsstatus* (data synkroniseras inte mellan distributionerna).
- Användning av funktionen *Placering för plats-ID-nummer*.
- Användning av *Produktfilter* och *Produktfiltergrupper*, inklusive inställningen **Antal dagar för att blanda batcher**.
- Integrering med kvalitetshantering.
- Bearbetning av artiklar med faktisk/nominell vikt.
- Bearbetning av artiklar som endast aktiverats för Transporthantering (NIS).
- Bearbetning av negativ lagerbehållning.
- Bearbetning av lagerställe med leveransnoteringar.
- Bearbetning av lagerställearbete med materialhantering/lagerautomatisering.
- Användning av avbildning av produktmalldata (t.ex. på Warehouse Management-mobilappen).

> [!WARNING]
> Vissa lagerställefunktioner är inte tillgängliga för lagerställen som kör lagerstyrningsarbetsbelastningar på en skalningsenhet, och den har inte heller stöd för hantering av lagerställen eller på arbetsbelastningen vid lagerstyrning.
> 
> Andra funktioner kan bearbetas på båda, men du måste använda den noggrant i vissa situationer, till exempel när lagerbehållningen uppdateras för samma lagerställe på både avdelnings- och skalningsenhet på grund av den asynkrona datauppdateringsprocessen.
> 
> Särskilda funktioner (t.ex. *blockera arbete*) som stöds på både hubb och skalningsenheterna stöds endast för dataägaren.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Utgående (stöds endast för försäljning och överföringsorder)

I följande tabell visas vilka utgående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                                      | Hubb | Arbetsbelastning för lagerkörning på en skalningsenhet |
|--------------------------------------------------------------|-----|------------------------------|
| Bearbetning av källdokument                                   | Ja | Nr |
| Last- och transporthanteringsprocesser                | Ja, men bara lastplaneringsprocesserna. Bearbetning av transporthantering stöds inte  | Nr |
| Frisläpp till distributionslager                                         | Ja | Nr |
| Planerad direktleverans                                        | Nr  | Nr |
| Konsolidering av leverans                                       | Ja, när du använder lastplanering | Ja |
| Påfyllnadsbearbetning för leverans                                     | Nr  |Ja, utom **Lastuppbyggnad och sortering** |
| Underhålla försändelser för cykel                                  | Nr  | Ja|
| Arbetsprocess för lager (inkl. tryck på ID-nummer)        | Nr  | Ja, men endast för de tidigare nämnda funktionerna |
| Klusterplockning                                              | Nr  | Ja|
| Manuell förpackningsbearbetning, inklusive bearbetning av "Plockning för packad behållare" | Nr <P>Viss bearbetning kan utföras efter en ursprunglig plockningsprocess som hanteras av en vågenhet, men du rekommenderas inte på grund av följande spärrade operationer.</p>  | Nr |
| Ta bort behållare från grupp                                  | Nr  | Nr |
| Utgående sorteringsbearbetning                                  | Nr  | Nr |
| Utskrift av läsrelaterade dokument                           | Ja | Ja|
| Fraktsedel och ASN-generering                            | Nr  | Ja|
| Försändelsebekräftelse                                             | Nr  | Ja|
| Försändelsebekräftelse med "Bekräfta och överför"            | Nr  | Nr |
| Följesedel- och faktureringsbearbetning                        | Ja | Nr |
| Kort plockning (försäljnings- och överföringsorder)                    | Nr  | Ja, utan att ta bort reservationer för källdokument|
| Överplockning (försäljnings- och överföringsorder)                     | Nr  | Ja|
| Ändring av arbetsplatser (försäljnings- och överföringsorder)         | Nr  | Ja|
| Slutföra arbete (försäljnings- och överföringsorder)                    | Nr  | Ja|
| Skriv ut arbetsrapport                                            | Ja | Ja|
| Påfyllnadsetikett                                                   | Nr  | Ja|
| Arbetsdelning                                                   | Nr  | Ja|
| Bearbetning av arbete – Styrt av "Transportlastning"            | Nr  | Nr |
| Minska plockad kvantitet                                       | Nr  | Nr |
| Återför arbete                                                 | Nr  | Nr |
| Återför leveransbekräftelse                                | Nr  | Ja|

### <a name="inbound"></a>Inkommande

I följande tabell visas vilka ingående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                                          | Hubb | Arbetsbelastning för lagerkörning på en skalningsenhet<BR>*(Artiklar som markerats "Ja" gäller endast för lagerställeorder)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Käll&nbsp;dokument&nbsp;bearbetning                             | Ja | Nr |
| Last- och transporthanteringsprocesser                    | Ja | Nr |
| Inkommande försändelsebekräftelse                                    | Ja | Nr |
| Frisläppning av inköpsorder till lagerställe (bearbetning av lagerorder) | Ja | Nr |
| Annullering av orderrader för lagerställe<p>Observera att detta endast stöds om ingen registrering har skett mot raden</p> | Ja | Nr |
| Inleverans och inlagring av inköpsorderartikel                       | <p>Ja,&nbsp;när&nbsp;det&nbsp;inte finns lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja, när en inköpsorder inte ingår i en <i>last</i></p> |
| Inköpsorderrad har inlevererats och inlagrats                       | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja, när en inköpsorder inte ingår i en <i>last</i></p></p> |
| Returorder mottagning och inleverans                              | Ja | Nr |
| Plats och mottagning för blandat ID-nummer                       | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Ja |
| Mottagande av lastartikel                                              | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Plats och mottagning av registreringsskylt                             | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Inleverans och inlagring av överföringsorderartikel                       | Ja | Nr |
| Överför orderrad inleverans och inlagring                       | Ja | Nr |
| Avbryt arbete (inkommande)                                            | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja men endast när alternativet <b>Avregistreringskvitto vid annullering av arbete</b> (på sidan <b>parametrar för lagerstyrning</b>) är avmarkerat.</p> |
| Inköpsorder, bearbetning av produktinleverans                        | Ja | Nr |
| Inköpsorder som tas emot med underleverans                      | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Ja, men bara genom att göra en annulleringsbegäran från navet |
| Inköpsorder som tas emot med överleverans                       | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Ja  |
| Ta emot med skapande av *Direktleveransarbete*                 | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Kvalitetsorder*                  | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Sampling av kvalitetsartikel*          | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Kvalitet på kvalitetskontroll*       | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av kvalitetsorder                            | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Bearbetning av arbete – Dirigerad av *kluster för artikelinförsel*                 | Ja | Nr |
| Bearbetning av arbete med *kort plockning*                               | Ja | Nr |
| Läs in registreringsskylt                                           | Ja | Ja |

### <a name="warehouse-operations-and-exception-handing"></a>Lageroperationer och hantering av undantag

I följande tabell visas vilka funktioner för lagerställeåtgärder och hantering av undantag som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                            | Hubb | Arbetsbelastning för lagerkörning på en skalningsenhet |
|----------------------------------------------------|-----|------------------------------|
| Registreringsskyltsförfrågan                              | Ja | Ja                          |
| Artikelförfrågan                                       | Ja | Ja                          |
| Platsförfrågan                                   | Ja | Ja                          |
| Byt lagerställe                                   | Ja | Ja                          |
| Rörelse                                           | Ja | Ja                          |
| Förflyttning efter registreringsskylt                               | Ja | Ja                          |
| Överföring lagerställe                                 | Ja | Nr                           |
| Skapa överföringsorder från distributionslagerappen           | Ja | Nr                           |
| Justering (in/ut)                                | Ja | Ja, men inte för justeringsscenariot där lagerreservation måste tas bort med hjälp av inställningen **Ta bort reservationer** för lagerjusteringstyperna</p>                           |
| Ändring av lagerstatus                            | Ja | Nr                           |
| Rullande inventering och inventering av avvikelsebearbetning | Ja | Ja                           |
| Skriv ut etikett igen (utskrift av ID-nummer)             | Ja | Ja                          |
| Skapa registreringsskylt                                | Ja | Nr                           |
| Avbrott för registreringsskylt                                | Ja | Nr                           |
| Packa till kapslade ID-nummer                                | Ja | Nr                           |
| Förarens incheckning                                    | Ja | Nr                           |
| Förarens utcheckning                                   | Ja | Nr                           |
| Ändra batchdispositionskod                      | Ja | Ja                          |
| Visa lista över öppet arbete                             | Ja | Ja                          |
| Konsolidera ID-nummer                         | Ja | Nr                           |
| Bearbetning av minimi-/max- och zontröskeln| Ja <p>Rekommendationen ska inte inkludera samma platser som en del av frågeställningarna</p>| Ja                          |
| Bearbetning av artikelplacering för lagerpåfyllnad                  | Ja  | Ja<p>Observera att inställningen måste göras på skalningsenhet.</p>                           |
| Blockera och låsa upp arbete                             | Ja | Ja                          |
| Ändra användare                                        | Ja | Ja                          |
| Ändra arbetspool för arbete                           | Ja | Ja                          |
| Avbryt arbete                                        | Ja | Ja                          |

### <a name="production"></a>Produktion

Följande tabell sammanfattar vilka produktionsscenarier för lagerstyrning som för närvarande stöds på arbetsbelastningar i skalningsenheter.

| Process | Hubb | Arbetsbelastning för lagerkörning på en skalningsenhet |
|---------|-----|------------------------------|
| Rapportera som färdigt gods och stuvat gods | Ja | Ja |
| Plats för samprodukt och biprodukt | Ja | Ja |
| <p>Alla andra lagerstyrningsprocesser som är relaterade till produktion, inklusive:</p><li>Frisläpp till distributionslager</li><li>Bearbetning av produktionspåfyllnader</li><li>Råmaterialhämtning</li><li>Kanban-plats</li><li>Kanban-plockning</li><li>Starta produktionsorder</li><li>Produktionskassation</li><li>Sista produktionspall</li><li>Registrera materialförbrukning</li><li>Töm kanban</li></ul> | Ja | Nr |
| Lagerpåfyllnad av råmaterial | Nr | Nr |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Underhålla skalningsenheter för lagerställekörning

Flera batchjobb körs på både nav och skalningsenheterna.

På navdistributionen kan du manuellt underhålla batch-jobben. Du kan hantera följande batchjobb i **lagerstyrning \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning**:

- Meddelandeprocessor för skalningsenhet till hubb
- Registrera inleveranser av källorder
- Slutför lagerställeorder

På arbetsbelastningen i skalningsenheter kan du hantera följande batchjobb på **lagerstyrning \> periodiska uppgifter \> hantering av arbetsbelastning**:

- Bearbeta registerposter för påfyllnad
- Lagerställehubb till meddelandeprocessorn för skalningsenhet
- Bearbeta kvantitetsuppdateringsbegäranden för lagerställeorderrader

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
