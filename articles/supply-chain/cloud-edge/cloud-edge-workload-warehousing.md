---
title: Arbetsbelastningar för distributionslagerhantering för moln- och molnskalningsenheter
description: Det här avsnittet innehåller information om funktionen som gör att enheterna kan köra valda processer från din arbetsbelastningar för distributionslagerhantering.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 91e614889c719ae700b13e54150e5025d64e2b97
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104950"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Alla affärsfunktioner för lagerstyrning stöds inte fullt ut för lagerställen som kör en arbetsbelastning på en skalningsenhet. Se till att bara använda de processer som det här ämnet explicit beskriver som det stöds.

## <a name="warehouse-execution-on-scale-units"></a>Lagerkörning på skalningsenheter

Den här funktionen gör det möjligt för skalningsenheter att köra valda processer från kapacitet för lagerstyrning. Molnskalningsenheter kör sina arbetsbelastningar i molnet genom att använda dedikerad bearbetningskapacitet i det valda Microsoft Azure-området. För molnskalningsenheter kan du köra vissa arbetsbelastningar oberoende av varandra, även om skalningsenheterna tillfälligt kopplas bort från molnet.

I det här avsnittet kallas lagerstyrningskörningar i ett lagerställe som definieras som en enhet för *lagerkörningssystem* (*WES*).

## <a name="prerequisites"></a>Förutsättningar

Du måste ha ett Dynamics 365 Supply Chain Management nav och en skalningsenhet som har distribuerats med arbetsbelastningen för lagerstyrning. Mer information om arkitektur och distributionsprocess finns i [moln och kantskalningsenhet med arbetsbelastning för tillverkning och distributionslagerhantering](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Så här arbetar WES-arbetsbelastning på skalningsenheter

För processerna i arbetsbelastningen för lagerstyrning synkroniseras data mellan navet och skalningsenheter.

En skalningsenhet kan endast bevara de data som den äger. Konceptet för dataägarskap för skalningsenheter bidrar till att förhindra konflikter i flera original. Därför är det viktigt att du förstår vilka processer som ägs av navet och som ägs av skalningsenheterna.

Skalningsenheterna äger följande data:

- **Påfyllnadsbearbetningsdata** – valda metoder för påfyllnadsprocess hanteras som en del av skalningsenhetens påfyllnadsbearbetning.
- **Data om arbetsbearbetning** – följande typer av bearbetning av arbetsorder stöds:

  - **Lagerrörelser** (manuell förflyttning och förflyttning per mallarbete)
  - **Inköpsorder** (artikelinförselarbetet via en lagerställeorder när inköpsorder inte är kopplade till läses in)
  - **Försäljningsorder** (enkelt plocknings- och lastningsarbete)
  - **Överföringsorder** (bara utgående med enkel plockning och inläsning av arbete)

- **Mottagningsdata för lagerorder** – dessa data används bara för inköpsorder som manuellt frigörs till ett lagerställe.
- **ID-nummerdata** – ID-nummer kan skapas på navet och skalningsenheten. En dedikerad konflikthantering har tillhandahållits. Observera att dessa data inte är lagerställespecifika.

## <a name="outbound-process-flow"></a>Utgående processflöde

Navet äger följande data:

- Alla källdokument, t.ex. försäljningsorder och överföringsorder
- Orderallokering och utgående lastbearbetning
- Processerna frisläpp till lager, skapande av försändelse, skapande av påfyllnad och slutförande av påfyllnad

Skalningsenheterna som äger den faktiska påfyllnadsbearbetningen (t.ex. arbetsfördelning, lagerpåfyllnadsarbete och skapande av efterfrågan) efter att påfyllnad har frisläppts. Därför kan lagerarbetare bearbeta utgående arbete genom att använda en distributionslagerappen som är kopplad till skalningsenheten.

![Påfyllnadsbearbetningsflöde](./media/wes-wave-processing-ga.png "Påfyllnadsbearbetningsflöde")

## <a name="inbound-process-flow"></a>Ingående processflöde

Navet äger följande data:

- Alla källdokument, t.ex. inköpsorder och försäljningsreturorder
- Inkommande lastbearbetning
- Alla kostnader och finansiella uppdateringar

> [!NOTE]
> Det inkommande inköpsorderflödet skiljer sig begreppen från det utgående flödet. Du kan använda samma lagerställe på antingen skalningsenhet eller hubb beroende på om inköpsordern har frisläppts till lagerstället eller inte. När du har frisläppt en order till lagerstället kan du bara arbeta med den ordern när du är inloggad på skalningsenhet.

Om du använder processen *frisläppning till lagerställe*, [*lagerställeorder*](cloud-edge-warehouse-order.md) skapas lagerställeorder och ägarskapet för det relaterade mottagningsflödet tilldelas till skalningsenheten. Navet kommer inte att kunna registrera inkommande inleveranser.

Arbetaren kan köra mottagningsprocessen med hjälp av en distributionslagerapp som är ansluten till skalningsenhet. Data registreras sedan av skalningsenheten och rapporteras mot inkommande lagerorder. Skapandet och bearbetningen av efterföljande borttagning kommer också att hanteras av skalningsenheten.

Om du inte använder processen *frisläppning till lager* och därför inte använder *lagerställeorder*, kan navet bearbeta inleverans och bearbetning av lager oberoende från skalningsenheter.

![Ingående processflöde](./media/wes-inbound-ga.png "Ingående processflöde")

## <a name="supported-processes-and-roles"></a>Processer och roller som stöds

Inte alla hanteringsprocesser för lagerställen stöds i en WES arbetsbelastning på en skalningsenhet. Därför rekommenderar vi att du tilldelar roller som matchar funktionerna som är tillgängliga för varje användare.

För att underlätta den här processen ingår en exempelroll med namnet *Lagerchef på arbetsbelastning* ingår i demodata på **Systemadministration \> Säkerhet \> Säkerhetskonfiguration**. Syftet med den här rollen är att göra det möjligt för lagerchefer att få åtkomst till WES på skalningsenheten. Rollen beviljar åtkomst till de sidor som är relevanta i kontexten för en arbetsbelastning som finns på en skalningsenhet.

Användarroller i en skalningsenhet tilldelas som en del av den ursprungliga datasynkroniseringen från navet till skalningsenhet.

Om du vill ändra rollerna som tilldelas en användare, gå till **systemadministration \> säkerhet \> tilldela användare till roller**. Användare som endast fungerar som lagerchefer på skalningsenheter bör endast tilldelas *Lagerchef på arbetsbelastning*. På så sätt ser du till att användarna bara har tillgång till de funktioner som stöds. Ta bort alla andra roller som har tilldelats dessa användare.

Användare som fungerar som lagerchefer på både nav- och skalningsenheterna bör tilldelas den befintliga rollen *Lagerarbetare*. Tänk på att den här rollen beviljar åtkomst till lagerarbetare till funktioner (t.ex. bearbetning av inleverans av överföringsorder) som visas i användargränssnittet (UI) men som för närvarande inte stöds i skalningsenheter.

## <a name="supported-wes-processes"></a>WES-processer som stöds

Följande processer för lagerkörning kan aktiveras för en WES arbetsbelastning på en skalningsenhet:

- Valda påfyllningsmetoder för försäljnings- och överföringsorder (allokering, efterfrågepåfyllnad, skapande av behållare, skapande av arbete och utskrift av påfyllnadsetikett)
- Bearbeta lagerställearbete för försäljnings- och överföringsorder med hjälp av lagerställeprogrammet (inklusive påfyllnadsarbete)
- Fråga om lagerbehållning med hjälp av distributionslagerappen
- Skapa och köra lagerrörelser med hjälp av distributionslagerappen
- Registrera inköpsorder och utföra inlagringsarbete med hjälp av distributionslagerappen

Följande arbetsordertyper stöds för närvarande för WES-arbetsbelastningar vid distributioner av skalningsenhet:

- Försäljningsorder
- Överför leverans
- Lagerpåfyllnad
- Lagerrörelse
- Inköpsorder (som är kopplade till lagerorder)

Inga andra typer av källdokumenthantering eller lagerarbete stöds för närvarande på skalningsenheter. För WES-arbetsbelastning på en skalningsenhet kan du till exempel inte utföra en mottagningsprocess för överföringsorder (överföringsinleverans) eller bearbeta arbetsuppgift för rullande inventering.

> [!NOTE]
> Menyalternativ och knappar för mobila enheter för funktioner som inte stöds visas inte i _distributionslagerapp_ när den är ansluten till en distribution av skalningsenhet.

> [!WARNING]
> När du kör en arbetsbelastning på en skalningsenhet kan du inte köra processer som inte stöds för det specifika lagerstället i navet. De tabeller som finns längre fram i det här avsnittet innehåller de funktioner som stöds.
>
> Valda arbetstyper för lagerställen kan skapas både i hubben och i skalningsenheter, men kan endast underhållas av den ägda hubben eller skalningsenheten (distributionen som skapade data).
>
> Även om en viss process stöds av en skalningsenhet bör du vara medveten om att alla data inte behöver synkroniseras från hubb till skalningsenhet, eller från skalningsenhet till hubb, vilket innebär en risk för att den oväntade systembearbetningen ska bearbetas. Exempel:
> 
> - Om du använder en platsdirektivfråga som sammanfogar en datatabellpost som endast finns i hubb distribution.
> - Om du använder platsstatus och/eller platsvolymfunktioner. Dessa data kommer inte att synkroniseras mellan distributionerna och fungerar därför bara när platsens lagerbehållning uppdateras i en av distributionerna.

Följande funktioner för lagerstyrning stöds för närvarande inte i arbetslaster för skalningsenheter:

- Inkommande bearbetning av inköpsorderrader som tilldelats en belastning
- Inkommande bearbetning av inköpsorder för ett projekt
- Ingående och utgående bearbetning för artiklar som har aktiva spårningsdimensioner **Ägare** och/eller **Serienummer**
- Bearbetning av lagret med värdet statusspärr
- Ändra lagerstatus under en arbetsrörelseprocess
- Orderallokerade flexibla lagerbokningar på lagernivå
- Användning av funktionen *Distributionslagrets platsstatus* (data synkroniseras inte mellan distributionerna)
- Användning av funktionen *Placering för plats-ID-nummer*
- Användning av *produktfilter* och *produktfiltergrupper*, inklusive inställningen **Antal dagar för att blanda batchar**
- Integrering med kvalitetshantering
- Bearbetning artiklar med faktisk/nominell vikt
- Bearbetning av artiklar som endast aktiverats för Transporthantering (NIS)
- Bearbetning av negativ lagerbehållning
- Bearbetning av lagerställe med anpassade arbetstyper
- Bearbetning av lagerställe med leveransnoteringar
- Bearbetning av lagerställe med tröskelvärde för rullande inventering som utlöser
- Bearbetning av distributionslagerarbete med materialhantering/Warehouse Automation
- Användning av bilden av huvuddata för produkt (t.ex. på distributionslagerappen)

> [!WARNING]
> Vissa lagerställefunktioner är inte tillgängliga för lagerställen som kör lagerstyrningsarbetsbelastningar på en skalningsenhet, och den har inte heller stöd för hantering av lagerställen eller på arbetsbelastningen vid lagerstyrning.
> 
> Andra funktioner kan bearbetas på båda, men du måste använda den noggrant i vissa situationer, till exempel när lagerbehållningen uppdateras för samma lagerställe på både avdelnings- och skalningsenhet på grund av den asynkrona datauppdateringsprocessen.
> 
> Särskilda funktioner (t.ex. *blockera arbete*) som stöds på både hubb och skalningsenheterna stöds endast för dataägaren.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Utgående (stöds endast för försäljning och överföringsorder)

I följande tabell visas vilka utgående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                                      | Hubb | WES arbetsbelastning på en skalningsenhet |
|--------------------------------------------------------------|-----|------------------------------|
| Bearbetning av källdokument                                   | Ja | Nr |
| Last- och transporthanteringsprocesser                | Ja | Nr |
| Frisläpp till distributionslager                                         | Ja | Nr |
| Planerad direktleverans                                        | Nr  | Nr |
| Konsolidering av leverans                                       | Ja | Nr |
| Påfyllnadsbearbetning för leverans                                     | Ja, men endast initiering och slutförandet av påfyllnadsstatus hanteras i hubb. Detta innebär att utgående överföring och bearbetning av försäljningsorder bara kan hanteras av skalningsenhet.|<p>Nej, initialisering och slutförande hanteras av navet och **Lastuppbyggnad och sortering** stöds inte<p><b>Obs!</b> Åtkomst till navet måste uppfylla påfyllnadsstatus som en del av påfyllnadsbearbetningen.</p> |
| Underhålla försändelser för cykel                                  | Ja | Nr |
| Arbetsprocess för lager (inkl. tryck på ID-nummer)        | Nr  | <p>Ja, men endast för de ovan nämnda funktionerna. |
| Klusterplockning                                              | Nr  | Ja|
| Manuell förpackningsbearbetning, inklusive bearbetning av "Plockning för packad behållare"                                           | Nr <P>Viss bearbetning kan utföras efter en ursprunglig plockningsprocess som hanteras av en vågenhet, men du rekommenderas inte på grund av följande spärrade operationer.</p>  | Nr  |
| Ta bort behållare från grupp                        | Nr  | Nr                           |
| Utgående sorteringsbearbetning                                  | Nr  | Nr |
| Utskrift av läsrelaterade dokument                           | Ja | Nr |
| Fraktsedel och ASN-generering                            | Ja | Nr |
| Försändelsebekräftelse                    | Ja  | Nr |
| Försändelsebekräftelse med "Bekräfta och överför"                    | Nr  | Nr |
| Följesedel- och faktureringsbearbetning                | Ja | Nr |
| Kort plockning (försäljnings- och överföringsorder)                    | Nr  | Nr |
| Överplockning (försäljnings- och överföringsorder)                     | Nr  | Nr |
| Ändring av arbetsplatser (försäljnings- och överföringsorder)         | Nr  | Ja|
| Slutföra arbete (försäljnings- och överföringsorder)                    | Nr  | Ja|
| Skriv ut arbetsrapport                                            | Ja | Nr |
| Påfyllnadsetikett                                                   | Nr  | Ja|
| Arbetsdelning                                                   | Nr  | Ja|
| Bearbetning av arbete - Styrt av "Transportlastning"            | Nr  | Nr |
| Minska plockad kvantitet                                       | Nr  | Nr |
| Återför arbete                                                 | Nr  | Nr |
| Återför leveransbekräftelse                                | Ja | Nr |

### <a name="inbound"></a>Inkommande

I följande tabell visas vilka ingående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                                          | Hubb | WES arbetsbelastning på en skalningsenhet<BR>*(Artiklar som markerats "Ja" gäller endast för lagerställeorder)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Käll&nbsp;dokument&nbsp;bearbetning                                       | Ja | Nr |
| Last- och transporthanteringsprocesser                    | Ja | Nr |
| Inkommande försändelsebekräftelse                                            | Ja | Nr |
| Frisläppning av inköpsorder till lagerställe (bearbetning av lagerorder) | Ja | Nr |
| Annullering av orderrader för lagerställe<p>Observera att detta endast stöds om ingen registrering har skett mot raden</p>          | Ja | Nr |
| Inleverans och inlagring av inköpsorderartikel                       | <p>Ja,&nbsp;när&nbsp;det&nbsp;inte finns lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja, när en inköpsorder inte ingår i en <i>last</i></p> |
| Inköpsorderrad har inlevererats och inlagrats                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja, när en inköpsorder inte ingår i en <i>last</i></p></p> |
| Returorder mottagning och inleverans                               | Ja | Nr |
| Plats och mottagning för blandat ID-nummer                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Mottagande av lastartikel                                             | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Plats och mottagning av registreringsskylt                              | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Inleverans och inlagring av överföringsorderartikel                        | Ja | Nr |
| Överför orderrad inleverans och inlagring                        | Ja | Nr |
| Avbryt arbete (inkommande)                                              | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja men endast när alternativet <b>Avregistreringskvitto vid annullering av arbete</b> (på sidan <b>parametrar för lagerstyrning</b>) är avmarkerat.</p> |
| Inköpsorder, bearbetning av produktinleverans                          | Ja | Nr |
| Inköpsorder som tas emot med underleverans                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nej, eftersom du bara kan annullera fullständiga radkvantiteter för lagerställeordern. |
| Inköpsorder som tas emot med överleverans                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Ja  |
| Ta emot med skapande av *Direktleveransarbete*                   | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Kvalitetsorder*                  | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Sampling av kvalitetsartikel*          | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av *Kvalitet på kvalitetskontroll*       | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Ta emot med skapande av kvalitetsorder                            | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Bearbetning av arbete - Dirigerad av *kluster för artikelinförsel*                             | Ja | Nr |
| Bearbetning av arbete med *kort plockning*                                           | Ja | Nr |
| Läs in registreringsskylt                                           | Ja | Nr |

### <a name="warehouse-operations-and-exception-handing"></a>Lageroperationer och hantering av undantag

I följande tabell visas vilka funktioner för lagerställeåtgärder och hantering av undantag som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                            | Hubb | WES arbetsbelastning på en skalningsenhet |
|----------------------------------------------------|-----|------------------------------|
| Registreringsskyltsförfrågan                              | Ja | Ja                          |
| Artikelförfrågan                                       | Ja | Ja                          |
| Platsförfrågan                                   | Ja | Ja                          |
| Byt lagerställe                                   | Ja | Ja                          |
| Rörelse                                           | Ja | Ja                          |
| Förflyttning efter registreringsskylt                               | Ja | Ja                          |
| Överföring lagerställe                                 | Ja | Nr                           |
| Skapa överföringsorder från distributionslagerappen           | Ja | Nr                           |
| Justering (in/ut)                                | Ja | Nr                           |
| Ändring av lagerstatus                            | Ja | Nr                           |
| Rullande inventering och inventering av avvikelsebearbetning | Ja | Nr                           |
| Skriv ut etikett igen (utskrift av ID-nummer)             | Ja | Ja                          |
| Skapa registreringsskylt                                | Ja | Nr                           |
| Avbrott för registreringsskylt                                | Ja | Nr                           |
| Packa till kapslade ID-nummer                                | Ja | Nr                           |
| Förarens incheckning                                    | Ja | Nr                           |
| Förarens utcheckning                                   | Ja | Nr                           |
| Ändra batchdispositionskod                      | Ja | Ja                          |
| Visa lista över öppet arbete                             | Ja | Ja                          |
| Konsolidera ID-nummer                         | Ja | Nr                           |
| Bearbetning av minimi-/max- och zontröskeln| Ja <p>Rekommendationen ska inte inkludera samma platser som en del av frågorna</p>| Ja                          |
| Bearbetning av artikelplacering för lagerpåfyllnad                  | Ja  | Ja<p>Observera att inställningen måste göras på skalningsenhet.</p>                           |
| Blockera och låsa upp arbete                             | Ja | Ja                          |
| Ändra användare                                        | Ja | Ja                          |
| Ändra arbetspool för arbete                           | Ja | Ja                          |
| Avbryt arbete                                        | Ja | Ja                          |


### <a name="production"></a>Produktion

Produktionsscenarier för lagerstyrning stöds för närvarande inte på arbetslaster i skalningsenheter, vilket anges i följande tabell.

| Process | Hubb | WES arbetsbelastning på en skalningsenhet |
|---------|-----|------------------------------|
| <p>Alla lagerstyrningsprocesser som är relaterade till produktion. Nedan följer några exempel:</p><li>Frisläpp till distributionslager</li><li>Bearbetning av produktionspåfyllnader</li><li>Råmaterialhämtning</li><li>RAF och lagring av färdig vara</li><li>Plats för samprodukt och biprodukt</li><li>Kanban-plats</li><li>Kanban-plockning</li><li>Starta produktionsorder</li><li>Produktionskassation</li><li>Sista produktionspall</li><li>Registrera materialförbrukning</li><li>Töm kanban</li></ul> | Ja | Nr |

## <a name="maintaining-scale-units-for-wes"></a>Underhålla skalningsenheter för WES

Flera batchjobb körs på både nav och skalningsenheterna.

På navdistributionen kan du manuellt underhålla batch-jobben. Du kan hantera följande batchjobb i **lagerstyrning \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning**:

- Uppdateringshändelse för status för processarbete
- Meddelandeprocessor för skalningsenhet till hubb
- Registrera inleveranser av källorder
- Slutför lagerställeorder
- Bearbeta kvantitetsuppdateringssvar för lagerställeorderrader

På arbetsbelastningen i skalningsenheter kan du hantera följande batchjobb på **lagerstyrning \> periodiska uppgifter \> hantering av arbetsbelastning**:

- Bearbeta registerposter för påfyllnad
- Lagerställehubb till meddelandeprocessorn för skalningsenhet
- Bearbeta kvantitetsuppdateringsbegäranden för lagerställeorderrader


[!INCLUDE[footer-include](../../includes/footer-banner.md)]