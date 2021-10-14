---
title: Leveranstidsplan
description: Det här avsnittet innehåller information om sidan Leveranstidsplan och dess funktioner.
author: ChristianRytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0d2f0f38d86ae307ef80bd02901e19a08d5e30ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578378"
---
# <a name="supply-schedule"></a>Leveranstidsplan

[!include [banner](../includes/banner.md)]

På sidan **Leveransplan** visas en omfattande översikt över tillgång och efterfrågan för en produkt- eller produktfamilj. Informationen filtreras efter plats, huvudplan och perioder. Du kan också använda sidan om du vill skapa nya order, ändra befintliga planerade order och köra huvudplanering.

## <a name="open-the-supply-schedule-page"></a>Öppna sidan Leveransplan

Du kan öppna sidan **Leveransplan** på något av följande sätt:

- Gå till **Huvudplanering \> Huvudplanering \> Leveransplan**. I dialogrutan **Modifiera filter** ange den plan och produkt som du letar efter genom att ange filtervärden i de angivna fälten.  (I resten av det här ämnet kallas samlingen av filtervärden som du anger som "filtret" eller "det aktuella filtret.") När du är klar väljer du **OK**.
- Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**. Välj eller öppna en produkt. I åtgärdsrutan på fliken **Plan** i gruppen **Visa** väljer du **Leveransplan**.
- Gå till **Huvudplanering \> Inställningar \> Efterfrågeprognosticering \> Artikelallokeringsnycklar**. Välj en artikelallokeringsnyckel som används som produktfamilj. I åtgärdsfönstret väljer du **Leveransplan**.
- Gå till **Huvudplanering \> Huvudplanering \> Planerade order**. Välj eller öppna en planerad order. I åtgärdsrutan på fliken **Visa** i gruppen **Visa** väljer du **Leveransplan**.

> [!NOTE]
> När du öppnar sidan **Leveransplan** från en produkt, produktfamilj eller planerad order behöver du inte ange filtervärden. I systemet används standardperiodmallen.

## <a name="use-the-supply-schedule-page"></a>Använd sidan Leveransplan

Sidan **Leveransplan** består av ett övre avsnitt, snabbfliken **Periodslutlager** om visas, baserat på raden som valts i det övre avsnittet och faktaboxrutan. (Om du vill öppna faktaboxrutan och visa en faktaruta väljer du **Relaterad information** på sidans högra kant.)

### <a name="upper-section"></a>Övre delen

Den övre delen av sidan **Leveransplan** innehåller ett rutnät som visar följande data för en produkt- eller produktfamilj. Informationen delas upp efter perioder som definieras av värdet för **Periodmall** från filtret.

- **Periodstartlager** – Denna rad visar det förväntade lagersaldot vid periodens början om alla order i systemet sker.
- **Periodslutlager** – Denna rad visar det förväntade lagersaldot vid periodens slut om alla order i systemet sker.
- **Peggade lager för periodslut** – Denna rad visar lagermängden i slutet av perioden som är peggad till framtida efterfrågan.
- **Periodens nettobehov** – Den här raden visar skillnaden mellan tillgång och efterfrågan under perioden.
- **Minimilager** – Den här noden visar säkerhetslager för en produkt- eller produktfamilj. Du expanderar eller komprimerar den här noden genom att markera den och sedan välja **Visa** eller **Dölj** i verktygsfältet. Den här noden visas bara när det finns säkerhetslager för produkt- eller produktfamiljen.
- **Efterfrågan** – Den här noden visar efterfrågan på en produkt- eller produktfamilj. Efterfrågan grupperas efter transaktionstyp. Du expanderar eller komprimerar den här noden genom att markera den och sedan välja **Visa** eller **Dölj** i verktygsfältet. Efterfrågetransaktionstyper omfattar försäljning, överföringar och lagerjournaler. Den här noden visas bara när det finns efterfrågan för produkt- eller produktfamiljen.
- **Försörjning** – Den här noden visar försörjning på en produkt- eller produktfamilj. Försörjning grupperas efter transaktionstyp. Du expanderar eller komprimerar den här noden genom att markera den och sedan välja **Visa** eller **Dölj** i verktygsfältet. Försörjningstransaktionstyper omfattar produktion, inköp och överföringar. Den här noden visas bara när det finns försörjning för produkt- eller produktfamiljen.

Många av de tillgängliga verktygsfältsknapparna, faktaboxskärmarna och snabbflikarna beror på vad du väljer i den övre delen. Vanligtvis väljer du en transaktionstyp genom att markera en av raderna under noden **försörjning** eller **efterfrågan**. Du väljer sedan en period genom att välja en viss kolumn för den valda raden.

Verktygsfältet ovanför rutnätet i den övre delen av sidan **Leveransschema** innehåller följande knappar:

- **Visa/dölj** – Visa eller dölj en vald nod, som noden **Efterfrågan**, noden **tillgång** och deras undernoder. (Noder visar ett **\[+\]** eller **\[-\]** prefix för att ange om de för närvarande är komprimerade eller utökade.)
- **Nytt** – Öppna en meny där varje kommando i sin tur öppnar en dialogruta eller sida som låter dig lägga till en specifik typ av objekt för markeringen. Tillgängliga kommandon inkluderar **Prognostillförsel**, **Planerad order**, **Tidsplanerad kanban**, **Ny tillverkningsorder**, **Inköpsorder** och **Överföringsorder**.
- **Huvudplanering** – Kör huvudplanering. En dialogruta visas där du kan ange vilken plan som ska köras. Som standard är fältet **Huvudplan** inställt för att matcha aktuellt filter.
- **Max. antal rapporterat som färdigt** – Öppna sidan **Max. antal rapporterat som färdigt** för produkten som är definierad i det aktuella filtret.
- **Uppdatera planerade order** – Öppna sidan **Planerade order** som visar planerade order för den produkt eller produktfamilj som har definierats i det aktuella filtret.
- **Nivå** – Sprid planerade order enligt inställningarna från dialogrutan som visas.
- **Materialplanpolicy efter plats** – Öppna sidan **Artikeldisponering** för produkten som definieras i det aktuella filtret.
- **Kanban-regel** – Öppna sidan **Kanban-regel** för produkten som definieras i det aktuella filtret.

### <a name="fasttabs"></a>Snabbflik

Sidan **Leveransplan** kan innehålla följande snabbflikar:

- **Periodslutlager** – På den här snabbfliken visas periodslutlagerdata i ett grafiskt format.
- **Leveransprofil** – På den här snabbfliken visas leveransdata i ett grafiskt format. Den blir synlig när du väljer en nod för **tillgång** eller en rad nedanför den i den övre delen.
- **Sammanfattning** – På den här snabbfliken visas sammanfattningsinformation som hör till den transaktionstyp du valde i det övre avsnittet. Om du till exempel väljer **Försäljning** under noden **Efterfrågan** visar den här snabbfliken fält som är relaterade till försäljningsorder, till exempel **Begärda försäljningsorderrader** eller **Totalbelopp**. Om du väljer **Tillverkningsorder** under undernoden **Produktion** för noden **Tillgång**, denna snabbflik visar fält som är relaterade till produktionsorder, t.ex. **Planerade produktionsorder** eller **Totalt schemalagt**. Fältvärdena beror på perioden som du valde i den övre delen. 
- **\[Transaktionstyp\] - \[Period\]** – På den här snabbfliken visas order för transaktionstypen och perioden som du valde i det övre avsnittet. Namnet på snabbflikarna speglar dessa val. Det kan till exempel kallas **Försäljningsorder - eftersläpning** eller **Tillverkningsorder - vecka 37**.

### <a name="action-pane"></a>Åtgärdsfönster

Följande knappar är tillgängliga i åtgärdsrutan:

- **Ändra filter** – Öppna dialogrutan **Ändra filter** där du kan uppdatera filtervärden och sedan öppna igen sidan **Leveransplan** uppdaterade, filterinställningarna visas.
- **Visa fördröjningar** – Markera relevanta rader i den övre delen om en försenad order av den transaktionstypen finns.

### <a name="factbox-pane"></a>Faktaboxfönster

Om du vill öppna faktaboxrutan och visa en faktaruta väljer du **Relaterad information** på sidans högra kant. Följande faktaboxar är tillgängliga på **Leveransplan**:

- **Artikelinformation** – Denna faktabox visar grundläggande information om produkten som definieras i det aktuella filtret. Det är tomt om du har definierat en produktfamilj i filtret.
- **Åtgärder** – Denna faktaboxen visar åtgärder för de order av transaktionstypen som du valde i det övre avsnittet.
- **Fördröjningar** – Denna faktaboxen visar fördröjningar för de order av transaktionstypen som du valde i det övre avsnittet.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
