---
title: Policyer för leveranskonsolidering
description: Det här ämnet ger en översikt över de funktioner som ger en flexibel konfiguration av policyer för leveranskonsolidering.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 4afa037ce9e446402128e4908a61ed32a30ebd59
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986960"
---
# <a name="shipment-consolidation-policies"></a>Policyer för leveranskonsolidering

Konsolideringsprocessen för leveranser som använder konsolideringspolicyer för leveranser möjliggör automatisk leveranskonsolidering vid automatisk och manuell frisläppning till lagerstället. Den automatiska konsolideringen som var tillgänglig innan den här funktionen introducerades hade hårdkodade fält och baserades på fältet **Konsolidera leverans vid frisläpp till lagerställe** som var inställd för ett lagerställe.

Policyer för leveranskonsolidering används för följande funktioner:

- Batch-jobbet för automatiserad frisläppning till lagerställe
- Kommandot **Frisläpp till lagerställe** på en försäljnings- eller överföringsorder
- Den dedikerade **Frisläpp till lagerställe**
- Kommandot **Frisläpp till lagerställe** på sidan **Workbench för lastplanering**
- Den manuella konsolideringen av leveranser på sidorna **Konsolidera leveranser** och **Workbench för leveranskonsolidering**

Innan policyer för leveranskonsolidering introducerades fanns konsolideringsfunktionen som en inställning på lagerställesnivå. Alla order för alla kunder från ett enda lagerställe behandlades som om de hade samma konsolideringskrav. Policyer för leveranskonsolidering tillför stöd för scenarier där olika organisationer har olika krav för leveranskonsolidering.

Frågor används för att identifiera gällande policyer för leveranskonsolidering, varefter en redigerbar uppsättning fält avgör hur beläggningsraderna grupperas på leveransnivå. (Detta mönster påminner om vågmallarnas mönster.) Dessutom har alternativet **Konsolidera med befintliga leveranser** lagts till i varje enskild policy. När detta alternativ är aktiverat hittar proceduren *Frisläpp till lagerställe* utleveranser för konsolidering genom att söka bland befintliga leveranser som har skapats baserat på samma konsolideringspolicy. I det här fallet väljer systemet en befintlig leverans eller beläggning istället för att skapa en ny. Systemet kommer dock endast att konsolideras med befintliga leveranser som har statusen *Öppen*. Leveranser som tillhör en påfyllnadsversion med statusen *Frisläppt* eller högre betraktas inte som mål för konsolideringen.

När en konsolideringspolicy för leverans görs tillgänglig döljs inställningen **Konsolidera leverans vid släpp till lagerställe** som tidigare var tillgänglig på inställningssidan **Lagerställen**. För att underlätta övergången till den nya funktionen för leveranskonsolidering kommer en funktion på sidan **Konsolideringspolicyer för leverans** att skapa en standardpolicy som automatiskt omfattar den gamla inställningen för befintliga lagerställen. När standardpolicyn har skapats kommer inställningen **Konsolidera leverans vid släpp till lagerställe** på konfigurationssidan för **Lagerställen** inte längre att beaktas.

Du kan använda sidan **Släpp till lagerställe** om du vill åsidosätta den tillämpliga konsolideringspolicyn manuellt på samma sätt som du kan åsidosätta efterlevnadspolicyer.

Du kan använda kommandot **Släpp \> Släpp till lagerställe** på sidan **Workbench för lastplanering** om du vill skapa utgående överföringar som baseras på försäljnings- och överföringsorderrader innan du släpper till lagerstället. Dessa beläggningar använder samma konsolideringslogik som introducerades tillsammans med konsolideringen av leveranspolicyerna.

Du kan använda sidan **Workbench för leveranskonsolidering** för att konsolidera befintliga leveranser som ännu inte har bekräftats men som redan har frisläppts till lagerstället. Den här funktionen stöder scenarier där den automatiserade frisläppningsprocessen, som har sin egen leveranskonsolidering, körs flera gånger per dag, men eventuella ytterligare konsolideringar identifieras manuellt innan leveransen till transportföretag slutförs under bekräftelseprocessen. Med den här funktionen kan du konsolidera utgående leveranser som skapas från försäljnings- eller överföringsorder rader när dessa har frisläppts till lagret men innan de bekräftas.

Sidan **Workbench för leveransonsolidering** fungerar som en workbench för beläggningsbyggande, där du kan bedöma flera leveranser samtidigt och tilldela en icke-konsoliderad order till en viss leverans. Du kan använda mallar för leveranskonsolidering för att bedöma föreslagna konsolideringar flera gånger och bekräfta dem. Vissa regler är implementerade för att förhindra obehörig konsolidering och för att varna dig för eventuella fel.

## <a name="overview-of-new-functionality"></a>Översikt över nya funktioner

I det här avsnittet beskrivs de sidor, kommandon och funktioner som ändras eller läggs till när du aktiverar och använder funktionen *Policyer för leveranskonsolidering*.

### <a name="shipment-consolidation-policies-page"></a>Sidan Policyer för leveranskonsolidering

Policyer differentieras efter typen av arbetsorder. Typen **Försäljningsorder** representerar leveranser av _försäljningsorder_, och typen **Överföringsorder** representerar leveranser med _Överföringsproblem_.

Varje konsolideringspolicy för leverans har en fråga som definierar när den används och ett ordningsnummer som bestämmer körningsordningen. Konsolidering används för varje unik kombination av de valda fälten. Ytterligare en parameter som tillhandahålls används för konsolidering med befintliga (öppna) leveranser. Policyerna utvärderas och tillämpas varje gång en ny leverans (före påfyllnadsbearbetning).

Om en policy saknar obligatoriska fält, eller om den innehåller alla förbjudna fält, markeras policyn som ogiltig i avsnittet **Valda**. Listorna över obligatoriska och förbjudna fält är hårdkodade och kan utökas.

Följande lista anger obligatoriska fält. Eftersom leveranser alltid delas baserat på dessa fält kan du inte gruppera flera leveranser som har olika värden för dessa fält.

- För försäljningsorder:

    - **Kontonummer:** _WHSShipmentTable.AccountNum_
    - **Leveransmottagare:** _WHSShipmentTable.DeliveryName_
    - **Postadress (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Lagerställe:** _WHSShipmentTable.InventLocationId_

- För överföringsorder:

    - **Från lagerställe:** _InventTransferTable.InventLocationIdFrom_
    - **Till lagerställe:** _InventTransferTable.InventLocationIdTo_

Följande fält är inte tillgängliga för alla dokumenttyper. Dessa fält visas inte i användargränssnittet (UI) och kan inte användas för konsolidering.

- **Leverans-ID:** _WHSShipmentTable.ShipmentId_
- **Status:** _WHSShipmentTable.ShipmentStatus_
- **Policy för leveranskonsolidering:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Typ av arbetstransaktion:** _WHSShipmentTable.WorkTransType_
- **Wave-ID:** _WHSShipmentTable.WaveId_
- **Beläggnings-ID:** _WHSShipmentTable.LoadId_
- **Leverans-ID:** _WHSLoadLine.ShipmentId_
- **Beläggnings-ID:** _WHSLoadLine.LoadId_

Som standard används uppsättningen med obligatoriska fält som konsolideringsfält när du skapar en policy. Du kan dock ändra listan genom att använda vänsterpil och högerpil. (Processen påminner om processen för att välja metoder i påfyllnadsmallar.)

De värden som användarna väljer för dessa fält kommer att användas för alla nyskapade leveranser, eller också läggs de till i befintliga utleveranser under konsolideringen med dessa leveranser. När två leveranser har samma värde för ett fält som valts för konsolidering av dessa leveranser konsolideras utleveranserna. Samma princip gäller för alla efterföljande konsolideringsfält som väljs. Om värdena är olika ignoreras den andra leveransen och markeras för en ny leverans. Den automatiserade konsolideringsprocessen består i att skapa alla unika kombinationer av värden för fälten för leveranskonsolidering och sedan tilldela en leverans till relevant kombination.

Omarkerade fält ignoreras under konsolideringsprocessen. Om två leveranser har olika värden för ett omarkerat fält, avmarkeras fältet (dvs. det ställs in på "tomt"). Om båda utleveranser har samma värde för ett omarkerat fält fylls fältet i.

Listan över konsolidering fält (det vill säga fält som rensas om de har olika värden) är hårdkodade. Listan innehåller alla fält som initieras från en försäljnings- eller överföringsorderrad när en ny leverans skapas. Detta innebär att om ett fält inte initieras från en försäljnings- eller överföringsorderrad, så ignoreras det när nya data läggs till i en befintlig leverans.

### <a name="release-to-warehouse-page"></a>Släpp på sida för lagerställe

- Ett nytt fält i det nedre rutnätet visar konsolideringspolicyn som tillämpats.
- Med en ny knapp kan du välja och/eller åsidosätta konsoliderings policyn manuellt.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>Kommandot Frisläpp till lagerställe på sidan Workbench för lastplanering

- Logiken justerades så att den använder tillämpade konsolideringspolicyer.
- Leveranser har nu konsoliderats inom en enda beläggning.

### <a name="consolidate-shipments-page"></a>Sidan Konsolidera leveranser

- Sökningen efter liknande leveranser (dvs. kandidater för konsolidering) har ändrats så att den använder fält som har valts i konsolideringspolicyn för leveransen.
- Fält som har olika värden i olika leveranser har nu värdet "tom". (Tidigare användes värdena från den valda "bas"-leveransen.)

### <a name="shipment-consolidation-workbench-page"></a>Sidan Workbench för leveranskonsolidering

- Nya funktioner replikerar processen för manuell konsolidering i större skala.
- Du kan nu öppna denna sida via menyn **Släpp till lagerställe** i modulen **Lagerstyrning**.
- Algoritmen analyserar befintliga leveranser som ännu inte har skickats. Den föreslår sedan konsolidering baserat på fält som väljs i konsolideringspolicyerna.

## <a name="comparison-of-functionality"></a>Funktionsjämförelse

I följande tabell sammanfattas hur leveranskonsolideringen fungerar när du inte använder policyer för leveranskonsolidering samt när du använder dem.

| Utan policyer för leveranskonsolidering | Med policyer för leveranskonsolidering |
|---|----|
| Inte tillämpligt | Försäljnings- eller överföringsleveranser som har valts för konsolidering måste ha samma konsolideringspolicy som den leverans som skapas, eller också måste de tilldelas till en öppen leverans när alternativet (**Konsolidera med befintliga leveranser**är aktiverat). |
| Proceduren *Släpp till lagerställe* söker inte bland befintliga leveranser för att hitta en leverans för konsolidering. Endast leveranser som skapas av en aktuell instans tillhörande proceduren *Släpp till lagerställe* används för att hitta en leverans för konsolidering. | Om alternativet **Konsolidera med befintliga leveranser** är aktiverat för en konsoliderings policy som för närvarande används kommer proceduren *Släpp till lagerställe* att söka bland befintliga leveranser som skapats baserat på samma konsolideringspolicy i syfte att hitta en leverans att konsolidera. Om du har två policyer kommer därför en leverans som skapas baserat på Policy 2 aldrig att konsolideras med en leverans som skapats baserat på Policy 1. |
| Inte tillämpligt | Om en lista över fält för konsolideringspolicy är tom, eller om en policy inte kan hittas, skapas en ny leverans för varje enskild försäljningsorder eller överföringsorderrad. |
| I följande konsolideringsfält definieras den unika kombinationen av värden som används för att konsolidera leveranser för en *överföringsrad*. (Alla andra fält ignoreras.)<ul><li>Ordernummer (OrderNum)</li></ul> | Följande konsolideringsfält definierar den unika kombinationen av värden som används för att konsolidera leveranser för en *överföringsrad*. (Alla andra fält ignoreras.)<ul><li>Ordernummer (OrderNum)</li><li>Leveransmottagare (DeliveryName)</li><li>Postadress (DeliveryPostalAddress)</li><li>ISO-landskod (CountryRegionISOCode)</li><li>Adress (Address)</li><li>Plats (InventSiteId)</li><li>Lagerställe (InventLocation)</li><li>Transportföretag (CarrierCode)</li><li>Transportföretagstjänst (CarrierServiceCode)</li><li>Leveranssätt (ModeCode)</li><li>Transportföretagsgrupp (CarrierGroupCode)</li><li>Leveransvillkor (DlvTermId)</li></ul>Dessa fält är de enda fält som är tillgängliga och initierade när en ny leverans skapas. |
| Följande konsolideringsfält definierar den unika kombinationen av värden som används för att konsolidera leveranser för en *försäljningsrad*. (Alla andra fält ignoreras.)<ul><li>Ordernummer (OrderNum)</li><li>Kundreferens (CustomerRef)</li><li>Kundrekvisition (CustomerReq)</li><li>Leveransvillkor (DlvTermId)</li></ul> | Följande konsolideringsfält definierar den unika kombinationen av värden som används för att konsolidera leveranser för en *försäljningsrad*. (Alla andra fält ignoreras.)<ul><li>Ordernummer (OrderNum)</li><li>Kontonummer (AccountNum)</li><li>Leveransmottagare (DeliveryName)</li><li>Postadress (DeliveryPostalAddress)</li><li>ISO-landskod (CountryRegionISOCode)</li><li>Adress (Address)</li><li>Plats (InventSiteId)</li><li>Lagerställe (InventLocation)</li><li>Transportföretag (CarrierCode)</li><li>Transportföretagstjänst (CarrierServiceCode)</li><li>Leveranssätt (ModeCode)</li><li>Transportföretagsgrupp (CarrierGroupCode)</li><li>Mäklar-ID (BrokerCode)</li><li>Riktning (LoadDirection)</li><li>Leveransvillkor (DlvTermId)</li><li>Kundreferens (CustomerRef)</li><li>Kundrekvisition (CustomerReq)</li></ul>Dessa fält är de enda fält som är tillgängliga och initierade när en ny leverans skapas. |
| Inte tillämpligt | Följande konsolideringsfält är obligatoriska för en *försäljningsrad* och kan inte tas bort:<ul><li>Kontonummer (AccountNum)</li><li>Leveransmottagare (DeliveryName)</li><li>Postadress (DeliveryPostalAddress)</li><li>Lagerställe (InventLocation)</li></ul>Som standard kommer dessa fält att tilldelas när en ny policy skapas. De kan inte tas bort. |
| Proceduren *Släpp av beläggning till lagerställe* på sidan **Beläggningsplanering** använder en egen, separat kod för att skapa leveranser och påfyllnader. | Policyer för leveranskonsolidering tillämpas för att bestämma vilka fält som ska utvärderas för konsolidering. Leveranser konsolideras nu endast inom en enda beläggning. |
| Du väljer manuellt **Konsolidera leveranser** på sidan **Alla leveranser** innan du väljer en "målbas"-leverans. Filtret föreslår alla befintliga leveranser som har matchande värden för flera nyckelfält. | Du väljer manuellt **Konsolidera leveranser** på sidan **Alla leveranser** innan du väljer en "målbas"-leverans. Systemet kommer att föreslå andra befintliga leveranser genom att matcha värdena från flera nyckelfält som är konfigurerade för relevanta policyer för leveranskonsolidering. |
| Du kan använda kommandot **Konsolidera leveranser** på sidan **Alla leveranser** för endast en enskild leverans. | På sidan **Workbench för leveranskonsolidering** kan du hitta en uppsättning leveranser som ännu inte har skickats. Dessa leveranser analyseras baserat på flera nyckelfält som har konfigurerats i dina policyer för leveranskonsolidering. Alla leveranser där värdena för dessa fält matchar föreslås för konsolidering.<p>Du kan underhålla konsolideringen manuellt genom att ta bort leveranser från föreslagna konsolideringar och/eller lägga till leveranser i dem. Flera typer av fel kan uppstå, men du kan åsidosätta vissa av dem.</p> |
| **Designkommentar:** Proceduren *Automatisk frisläppning av försäljningsorder till lagerställe* delar upp försäljningsrader i grupper. Varje grupp har sitt eget unika **ReleaseToWarehouseId**-värde och bearbetas separat av proceduren *Frisläpp till lagerställe*. Med den här proceduren skapas nytt arbete oavsett inställningar för arbetsavbrott. | **Designkommentar:** Proceduren *Automatisk frisläppning av försäljningsorder till lagerställe* tilldelar samma **ReleaseToWarehouseId**-värde till alla försäljningsrader som bearbetas. Alla försäljningsrader bearbetas samtidigt av proceduren *Frisläpp till lagerställe*. För att säkerställa det tidigare beteendet måste du konfigurera arbetsavbrott per leverans-ID. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)