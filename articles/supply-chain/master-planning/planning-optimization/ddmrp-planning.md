---
title: Efterfrågedriven planering
description: I artikeln beskrivs hur du genererar planerade order för artiklar som har ställts in som avdelningspunkter.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 4dadd8e258af6e6ffbe8c28fc8f9be511fcdb5bc
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186724"
---
# <a name="demand-driven-planning"></a>Efterfrågedriven planering

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

I artikeln beskrivs hur du genererar planerade order för artiklar som har ställts in som avdelningspunkter.

## <a name="net-flow-and-qualified-demand"></a>Nettoflöde och kvalificerad efterfrågan

Under huvudplaneringen använder systemet begreppet *nettoflöde* för att upprätta den faktiska lagerbehållningskvantiteten baserad på den faktiska lagerbehållningen plus det lager som är behållning (befintliga leveransorder som ännu inte inkommit), minus det som refereras till som *kvalificerat behov* (kvalificerad kommande försäljning) som visas i följande illustration. När systemet fastställer vilken buffertzon en artikel tillhör och vilken den beställda kvantiteten bör vara, utvärderas nettoflödet och inte den faktiska lagerbehållningen.

![Exempel på ett beräkningsdiagram för nettoflöde.](media/ddmrp-net-flow-example.png "Exempel på ett beräkningsdiagram för nettoflöde")

När en planerad order utlöses under en planeringskörning blir den beställda kvantiteten maximinivån minus nettoflödet. Om du vill tilldela en orderprioritet använder systemet [prioriterad planering](priority-based-planning.md) istället för behovsdatum. Efterfrågebaserad materialbehovsplanering (DDMRP) tilldelar prioriteten för en planerad order baserat på den beställda kvantiteten som en procentandel av maximilagret. I illustrationen ovan är den beställda kvantiteten 53 procent av den maximala kvantiteten. Orderprioriteten för lagerpåfyllnaden blir därför 53. (I sammanhanget är 0 den högsta prioriteten och 100 lägst prioritet.)

*Kvalificerad efterfrågan* är den förfallna efterfrågan plus dagens efterfrågan, plus kvalificerade orderbehov i framtiden. Följande bild visar ett exempel på efterfrågenivåer för idag (12 juni) och följande tre dagar. Med DDMRP kan du ange en tröskel för ordertopp i syfte att identifiera efterfrågan som överträffar de normala förväntningarna. Om tröskelvärdet sätts till 25 stycken, kvalificerar två av de framtida datum som visas i illustrationen som ordertoppar. Du måste tilldela en tröskel för ordertopp enskilt för respektive produkt genom att använda dess **Artikeldisponering**-sida enligt beskrivet i [Konfigurera buffertar för en artikel med avdelningspunkt](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Exempel på ett beräkningsdiagram för kvalificerad efterfrågan.](media/ddmrp-net-qualified-demand-example.png "Exempel på ett beräkningsdiagram för kvalificerad efterfrågan")

Förutsatt att det inte finns någon förfallen efterfrågan kan du nu lägga dagens efterfrågan (18) till kvantiteterna för de två ordertopparna (29 och 26) i syfte att få en kvalificerad efterfrågan på 73. Även om det finns efterfrågan den 23 juni bör du observera att denna inte är inkluderad i nettoflödesberäkningen, detta eftersom DDMRP utlöser planerade order på ett annat sätt än de traditionella disponeringsgrupperna.

## <a name="generating-planned-orders-with-ddmrp"></a>Generera planerade order med DDMRP

Under en planeringskörning skapar systemet en ny planerad order om nettoflödet för en artikel sjunker under beställningspunkten. När du använder DDMRP kommer du vanligtvis att köra en planering om dagen. Därför kontrollerar du i grund och botten lagernivåerna en gång om dagen i syfte att ta reda på vilka artiklar som måste fyllas på.

I följande bild visas ett exempel på en situation där du har en order på 18 stycken den 20 juni, 29 stycken den 21 juni, 26 stycken den 22 juni och 20 stycken den 23 juni. Eftersom tröskeln för topp satts till 25 enheter markeras två av dessa order som toppar. Det finns 220 stycken av denna artikel i behållning.

![Planeringsexempel 1.](media/ddmrp-planning-example-1.png "Planeringsexempel 1")

Om du kör huvudplanering nu genererar detta en planerad order om nettoflödet befinns vara under beställningspunkten (219 enheter i detta exempel).

![Planeringsexempel 2.](media/ddmrp-planning-example-2.png "Planeringsexempel 2")

Det här exemplet genererar en planerad inköpsorder för kvantiteten 130, som är lika med maximinivån minus nettoflödet. Den planerade ordern tilldelas prioriteten 53,07, baserat på procentandelen av maximikvantiteten. Eftersom dessa värden hittades den 20 juni skapar systemet en planerad order som är daterad den 20 juni plus den avdelade ledtiden för artikeln (fem arbetsdagar i det här exemplet). Eftersom "fem arbetsdagar" är lika med en vecka från idag dateras de planerade ordern den 27 juni.

> [!NOTE]
> Vid planeringsoptimering beräknas enbart avdelade artiklar med hjälp av DDMRP. Alla andra artiklar beräknas med hjälp av behovsplanering för standardmaterial (MRP).
