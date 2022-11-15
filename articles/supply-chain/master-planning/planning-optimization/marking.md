---
title: Lagermarkering
description: I denna artikel finns information om alternativen som är tillgängliga för markering av lager i bekräftade order.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c86db6a670d7d0f7bfe74b7466b9bce766e4a08d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740614"
---
# <a name="inventory-marking"></a>Lagermarkering

[!include [banner](../../includes/banner.md)]

I denna artikel finns information om alternativen som är tillgängliga för markering av lager i bekräftade order.

*Märkning* används för att koppla tillgång och efterfrågan. Den påminner om *pegging*, som visar hur efter frågan förväntas täcka huvudplaneringen. Ur en planeringssynpunkt är den huvudsakliga skillnaden att markeringen är mer permanent än pegging.

Markering har införts för att stödja särskilda kostnadsscenarier för först in, först ut (FIFO) och sist in, först ut (LIFO). Den används dock också för vissa icke-kostnadsscenarier. Att markera mellan tillgång och efterfrågan är valfritt och nästan permanent. Markering kan tas bort manuellt av en användare, eller så kan du ta bort den genom att köra en nedbrytning av en försäljningsorderrad där alternativet **ta bort markering** har valts.

Pegging styrs av huvudplanering vid disponering för att länka efterfrågan med den leverans som krävs. Pegging kan uppdateras för varje planeringskörning för att optimera leveransen som krävs för att täcka efterfrågan. När huvudplaneringen uppdaterar pegging-information respekteras eventuell befintlig markering.

Pegging startar genom att inkludera relevanta markeringar, lagerbehållningar och reservationer på order i följande ordning:

1. Markera mellan efterfrågan och leverans
1. Lagerbehållningar
1. Reservationer på order

När du bekräftar en planerad order innehåller dialogrutan **Bekräftelse** ett fält för **Uppdatera markering** som du använder för att konfigurera markeringsalternativ för de beställningar som skapas under bekräftelse. Välj ett av följande värden:

- *Nej* – ingen lagermarkering används.
- *Standard* – Lagermarkeringen uppdateras baserat på pegging. Posterna i en order (efterfrågan) markeras i jämförelse med en uppfyllelseorder (tillgång). Om en kvantitet finns kvar i uppfyllelseorder markeras den inte och referensinformationen lämnas tom. Om till exempel en försäljningsorder för 100 ea peggas mot en inköpsorder för 150 ea, tilldelas referensinformation endast till försäljningsordern.
- *Utökad* – Både behovsordern (efterfrågan) och uppfyllelseordern (tillgång) markeras, oberoende av om någon kvantitet återstår i uppfyllelseordern. Om till exempel en försäljningsorder för 100 ea peggas mot en inköpsorder för 150 ea, tilldelas referensinformation till både försäljningsordern och inköpsordern.
- *Standard på en nivå* – Markering på en nivå används. Markeringar på en nivå markerar endast huvudartikeln, inte dess strukturlistekomponenter. Därför kan du vara flexibel i komponenttilldelningen för tillverkningsorder när du har bekräftat. Med en nivåmarkering kan systemet optimera för ändringar av efterfrågan i sista minuten. I *standard* markering på en nivå markeras behovsorder mot uppfyllelseorder, men uppfyllelseorder markeras inte om de har resterande kvantitet.
- *Utökad på en nivå* – Markering på en nivå används. I *utökad* markering på en nivå markeras behovsorder mot uppfyllelseorder, men uppfyllelseorder markeras alltid oavsett om hur många som finns kvar.

Om du vill ställa in standardmarkeringsalternativ för ditt system går du till parametrarna **Huvudplanering \> Inställningar \> Parametrar för huvudplanering**. Sedan på fliken **Standarduppdatering** anger du **Uppdateringsmarkering** i önskat alternativ.

> [!NOTE]
> Alternativen *En nivå, standard* och *En nivå, utökad* är bara tillgängliga om funktionen *Tillverka mot order-automation* har aktiverats i systemet. Mer information om den här funktionen och hur du aktiverar den finns i [Tillverka mot order-automation](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
