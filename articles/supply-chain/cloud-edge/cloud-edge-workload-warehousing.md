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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516878"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Arbetsbelastningar för distributionslagerhantering för moln- och molnskalningsenheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Inte alla företagsfunktioner stöds fullt ut i den allmänna förhandsgranskningen när enheter för belastningsenheter används. Se till att bara använda de processer som det här ämnet explicit beskriver som det stöds.

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

    - Lagerrörelser (manuell förflyttning och förflyttning per mallarbete)
    - Inköpsorder (artikelinförselarbete via en lagerställeorder)
    - Försäljningsorder (enkelt plocknings- och lastningsarbete)

- **Mottagningsdata för lagerorder** – dessa data används bara för inköpsorder som manuellt frigörs till ett lagerställe.
- **ID-nummerdata** – ID-nummer kan skapas på navet och skalningsenheten. En dedikerad konflikthantering har tillhandahållits. Observera att dessa data inte är lagerställespecifika.

## <a name="outbound-process-flow"></a>Utgående processflöde

Navet äger följande data:

- Alla källdokument, t.ex. försäljningsorder och överföringsorder
- Orderallokering och utgående lastbearbetning
- Processerna frisläpp till lager, skapande av försändelse och skapande av påfyllnad

Skalningsenheterna som äger den faktiska påfyllnadsbearbetningen (t.ex. arbetsfördelning, lagerpåfyllnadsarbete och skapande av efterfrågan) efter att påfyllnad har frisläppts. Därför kan lagerarbetare bearbeta utgående arbete genom att använda en distributionslagerappen som är kopplad till skalningsenheten.

![Påfyllnadsbearbetningsflöde](./media/wes_wave_processing_flow.png "Påfyllnadsbearbetningsflöde")

## <a name="inbound-process-flow"></a>Ingående processflöde

Navet äger följande data:

- Alla källdokument, t.ex. inköpsorder och försäljningsreturorder
- Inkommande lastbearbetning

> [!NOTE]
> Det inkommande inköpsorderflödet skiljer sig konceptuellt från det utgående flödet, där den enhet som bearbetningen sker beror på om ordern har frisläppts till ett lagerställe.

Om du använder processen *frisläppning till lagerställe* skapas lagerställeorder och ägarskapet för det relaterade mottagningsflödet tilldelas till skalningsenheten. Navet kommer inte att kunna registrera inkommande inleveranser.

Arbetaren kan köra mottagningsprocessen med hjälp av en distributionslagerapp som är ansluten till skalningsenhet. Data registreras sedan av skalningsenheten och rapporteras mot inkommande lagerorder. Skapandet och bearbetningen av efterföljande borttagning kommer också att hanteras av skalningsenheten.

Om du inte använder processen *frisläppning till lager* och därför inte använder *lagerställeorder*, kan navet bearbeta inleverans och bearbetning av lager oberoende från skalningsenheter.

![Ingående processflöde](./media/wes_Inbound_flow.png "Ingående processflöde")

## <a name="supported-processes-and-roles"></a>Processer och roller som stöds

Inte alla hanteringsprocesser för lagerställen stöds i en WES arbetsbelastning på en skalningsenhet. Därför rekommenderar vi att du tilldelar roller som matchar funktionerna som är tillgängliga för varje användare.

För att underlätta den här processen ingår en exempelroll med namnet *Lagerchef på arbetsbelastning* ingår i demodata på **Systemadministration \> Säkerhet \> Säkerhetskonfiguration**. Syftet med den här rollen är att göra det möjligt för lagerchefer att få åtkomst till WES på skalningsenheten. Rollen beviljar åtkomst till de sidor som är relevanta i kontexten för en arbetsbelastning som finns på en skalningsenhet.

Användarroller i en skalningsenhet tilldelas som en del av den ursprungliga datasynkroniseringen från navet till skalningsenhet.

Om du vill ändra rollerna som tilldelas en användare, gå till **systemadministration \> säkerhet \> tilldela användare till roller** i skalningsenheten. Användare som endast fungerar som lagerchefer på skalningsenheter bör endast tilldelas *Lagerchef på arbetsbelastning*. På så sätt ser du till att användarna bara har tillgång till de funktioner som stöds. Ta bort alla andra roller som har tilldelats dessa användare.

Användare som fungerar som lagerchefer på både nav- och skalningsenheterna bör tilldelas den befintliga rollen *Lagerarbetare*. Tänk på att den här rollen beviljar åtkomst till lagerarbetare till funktioner (t.ex. bearbetning av överföringsorder) som visas i användargränssnittet (UI) men som för närvarande inte stöds i skalningsenheter.

## <a name="supported-wes-processes"></a>WES-processer som stöds

Följande processer för lagerkörning kan aktiveras för en WES arbetsbelastning på en skalningsenhet:

- Valda påfyllningsmetoder för försäljningsorder och påfyllnad baserad på efterfrågan
- Köra arbetsorder från försäljningsorder och påfyllnad baserad på efterfrågan genom att använda distributionslagerappen
- Fråga om lagerbehållning med hjälp av distributionslagerappen
- Skapa och köra lagerrörelser med hjälp av distributionslagerappen
- Registrera inköpsorder och utföra inlagringsarbete med hjälp av distributionslagerappen

Följande arbetsordertyper stöds för närvarande för WES-arbetsbelastningar vid distributioner av skalningsenhet:

- Försäljningsorder
- Lagerpåfyllnad
- Lagerrörelse
- Inköpsorder som är kopplade till lagerorder

Ingen annan bearbetning av källdokument stöds för närvarande i skalningsenheter. För en WES-arbetsbelastning på en skalningsenhet kan du till exempel inte utföra följande åtgärder:

- Frisläpp en överföringsorder.
- Bearbeta de utgående plocknings- och leveransåtgärderna för lagret.

> [!IMPORTANT]
> Om du använder en arbetsbelastning på en skalningsenhet kan du inte köra processer som inte stöds för det specifika lagerstället i navet.

Följande funktioner för lagerstyrning stöds för närvarande inte i skalningsenheter:

- Ingående och utgående bearbetning för artiklar som har aktiva spårningsdimensioner (t.ex. batch- eller serienummerdimensioner)
- Bearbetning av lagerstatusändringar
- Bearbetning av lagret med värdet statusspärr
- Integrering med kvalitetshantering
- Integration med produktion
- Bearbetning artiklar med faktisk/nominell vikt
- Bearbetning av överleverans och underleverans
- Bearbetning av negativ lagerbehållning

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Utgående (stöds endast för försäljningsorder och påfyllnad baserad på efterfrågan)

I följande tabell visas vilka utgående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

> [!WARNING]
> Eftersom endast bearbetning av försäljningsorder stöds kan bearbetningen av lagerstyrningshanteringen inte användas för överföringsorder.
>
> Vissa lagerfunktioner är inte tillgängliga i lagerställen som kör arbetsbelastningarna för lagerstyrning i en skalningsenhet.

| Process                                                      | Hubb | WES arbetsbelastning på en skalningsenhet |
|--------------------------------------------------------------|-----|------------------------------|
| Bearbetning av källdokument                                   | Ja | Nr |
| Last- och transporthanteringsprocesser                | Ja | Nr |
| Frisläpp till distributionslager                                         | Ja | Nr |
| Konsolidering av leverans                                       | Nr  | Nr |
| Direktleveransarbete (plockningsarbete)                                 | Nr  | Nr |
| Påfyllnadsbearbetning för leverans                                     | Nej, men slutförandet av påfyllnadsstatus hanteras i navet |<p>Ja, men följande funktioner stöds inte:</p><ul><li>Parallellt arbetsskapande</li><li>Lastuppbyggnad och sortering</li><li>Skapande av fraktbehållare</li><li>Utskrift av påfyllnadsetikett</li></li></ul><p><b>Obs!</b> Åtkomst till navet måste uppfylla påfyllnadsstatus som en del av påfyllnadsbearbetningen.</p> |
| Arbetsprocess för lager (inkl. tryck på ID-nummer)     | Nr  | <p>Ja, men endast för följande funktioner:</p><ul><li>Försäljningsplockning (utan användning av aktiva spårningsdimensioner)</li><li>Försäljningslast (utan användning av aktiva spårningsdimensioner)</li></ul> |
| Klusterplockning                                              | Nr  | Nr |
| Förpackningsbearbetning                                           | Nr  | Nr |
| Utgående sorteringsbearbetning                                  | Nr  | Nr |
| Utskrift av läsrelaterade dokument                           | Ja | Nr |
| Fraktsedel och ASN-generering                            | Ja | Nr |
| Leverans av transport och bearbetning av följesedel                | Ja | Nr |
| Kort plockning (försäljningsorder)                                 | Nr  | Nr |
| Annullera arbete                                            | Nr  | Nr |
| Ändring av arbetsplatser (försäljningsorder)                      | Nr  | Nr |
| Slutför arbete (försäljningsorder)                                 | Nr  | Nr |
| Blockera och låsa upp arbete                                       | Nr  | Nr |
| Ändra användare                                                  | Nr  | Nr |
| Skriv ut arbetsrapport                                            | Nr  | Nr |
| Påfyllnadsetikett                                                   | Nr  | Nr |
| Återför arbete                                                 | Nr  | Nr |

### <a name="inbound"></a>Inkommande

I följande tabell visas vilka ingående funktioner som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                                          | Hubb | WES arbetsbelastning på en skalningsenhet |
|------------------------------------------------------------------|-----|------------------------------|
| Käll&nbsp;dokument&nbsp;bearbetning                                       | Ja | Nr |
| Last- och transporthanteringsprocesser                    | Ja | Nr |
| Försändelsebekräftelse                                            | Ja | Nr |
| Frisläppning av inköpsorder till lagerställe (bearbetning av lagerorder) | Ja | Nr |
| Inleverans och inlagring av inköpsorderartikel                        | <p>Ja,&nbsp;när&nbsp;det&nbsp;inte finns lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja, när det finns en lagerorder och när en inköpsorder inte ingår i en <i>beläggning</i>. Två menyartiklar för mobila enheter måste dock användas, en för att ta emot (<i>Inleverans av inköpsorderartikel</i>) och en annan med alternativet <b>Använd befintligt arbete</b> aktiverat, för att bearbeta artikelinförsel.</p><p>Nej, när det inte finns en lagerorder.</p> |
| Inköpsorderrad har inlevererats och inlagrats                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Returorder mottagning och inleverans                               | Ja | Nr |
| Plats och mottagning för blandat ID-nummer                        | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Mottagande av lastartikel                                              | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Plats och mottagning av registreringsskylt                              | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |
| Inleverans och inlagring av överföringsorderartikel                        | Ja | Nr |
| Överför orderrad inleverans och inlagring                        | Ja | Nr |
| Annullera arbete                                                | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | <p>Ja men alternativet <b>Avregistreringskvitto vid annullering av arbete</b> (på sidan <b>parametrar för lagerstyrning</b>) stöds inte.</p> |
| Inköpsorder, bearbetning av produktinleverans                        | Ja | Nr |
| Direktutleverans skapa som del av mottagning                 | <p>Ja, när det inte finns en lagerorder</p><p>Nej, när det finns en lagerorder</p> | Nr |

### <a name="warehouse-operations-and-exception-handing"></a>Lageroperationer och hantering av undantag

I följande tabell visas vilka funktioner för lagerställeåtgärder och hantering av undantag som stöds och var de stöds, när lagerstyrningshanteringen används i enheter för moln- och molnskalningsenheter.

| Process                                            | Hubb | WES arbetsbelastning på en skalningsenhet |
|----------------------------------------------------|-----|------------------------------|
| Registreringsskyltsförfrågan                              | Ja | Ja                          |
| Artikelförfrågan                                       | Ja | Ja                          |
| Platsförfrågan                                   | Ja | Ja                          |
| Byt lagerställe                                   | Ja | Ja                          |
| Rörelse                                           | Nr  | Ja                          |
| Förflyttning efter registreringsskylt                               | Nr  | Ja                          |
| Justering (in/ut)                                | Ja | Nr                           |
| Rullande inventering och inventering av avvikelsebearbetning | Ja | Nr                           |
| Skriv ut etikett igen (utskrift av ID-nummer)             | Ja | Nr                           |
| Skapa registreringsskylt                                | Ja | Nr                           |
| Avbrott för registreringsskylt                                | Ja | Nr                           |
| Förarens incheckning                                    | Ja | Nr                           |
| Förarens utcheckning                                   | Ja | Nr                           |
| Ändra batchdispositionskod                      | Ja | Nr                           |
| Visa lista över öppet arbete                             | Ja | Nr                           |
| Konsolidera ID-nummer                         | Nr  | Nr                           |
| Ta bort behållare från grupp                        | Nr  | Nr                           |
| Avbryt arbete                                        | Nr  | Nr                           |
| Bearbetning av min-max för lagerpåfyllnad                   | Nr  | Nr                           |
| Bearbetning av artikelplacering för lagerpåfyllnad                  | Nr  | Nr                           |

### <a name="production"></a>Produktion

Integration av lagerstyrning för produktionsscenarier stöds inte för närvarande, enligt följande tabell.

| Process | Hubb | WES arbetsbelastning på en skalningsenhet |
|---------|-----|------------------------------|
| <p>Alla lagerstyrningsprocesser som är relaterade till produktion. Nedan följer några exempel:</p><li>Frisläpp till distributionslager</li><li>Bearbetning av produktionspåfyllnader</li><li>Råmaterialhämtning</li><li>Plats för slutförda varor</li><li>Plats för samprodukt och biprodukt</li><li>Kanban-plats</li><li>Kanban-plockning</li><li>Starta produktionsorder</li><li>Produktionskassation</li><li>Sista produktionspall</li><li>Registrera materialförbrukning</li><li>Töm kanban</li></ul> | Nr | Nr |

## <a name="maintaining-scale-units-for-wes"></a>Underhålla skalningsenheter för WES

Flera batchjobb körs på både nav och skalningsenheterna.

På navdistributionen kan du manuellt underhålla batch-jobben. Du kan hantera följande tre jobb i **lagerstyrning \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning**:

- Uppdateringshändelse för status för processarbete
- Bearbeta överföringshändelser för kontroll av påfyllnadskörning
- Registrera inleveranser av källorder

På arbetsbelastningen i skalningsenheter kan du hantera följande två batchjobb på **lagerstyrning \> periodiska uppgifter \> hantering av arbetsbelastning**:

- Bearbeta registerposter för påfyllnad
- Bearbeta överföringshändelser för kontroll av påfyllnadskörning
