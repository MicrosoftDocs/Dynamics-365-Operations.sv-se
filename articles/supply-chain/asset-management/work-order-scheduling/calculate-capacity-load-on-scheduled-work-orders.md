---
title: Beräkna kapacitetsbeläggning på schemalagda arbetsorder
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning på planerade arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0c0dd1e306c54d3f99b86ad6f1816d5acabe6c18
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887169"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Beräkna kapacitetsbeläggning på schemalagda arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Du kan beräkna kapacitetsbeläggning på schemalagda arbetsorder för att få en översikt över arbetsbeläggningen för resurser under en viss period. Beräkningar kan göras för följande resurser: underhållsarbetare, arbetargrupper, verktyg och tillgångar.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tidsplan** > **Kapacitetsbeläggning**.

2. I dialogrutan **Beräkna kapacitetsbeläggning** > fältet **Visa** väljer du vilken beläggningstyp du vill beräkna: "Kapacitet", "Reserverad" eller "Rest".

3. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll.

4. Välj de resurstyper som du vill beräkna kapacitetsbeläggning för genom att välja "Ja" på de relevanta växlingsknappar: **Arbetare**, **Underhållsarbetargrupp**, **Verktyg** och **Tillgång**.

5. Välj startdatum för beräkningen i fältet **Från datum**.

6. I fältet **Intervalltyp** väljer du intervallet för beräkningen: "dag", "vecka", "månad" eller "kvartal".

7. I fältet **Periodfrekvens** anger du antalet intervaller du vill beräkna. Om du till exempel har valt "dag" som intervalltyp och infogar siffran "5" i det här fältet, kommer en beräkning på fem dagar från startdatumet att göras.

8. Klicka på **OK** för att starta beräkningen.

I bilden nedan visas resultatet av en beräkning som täcker tre veckor för beläggningstypen "reserverad".

![Figur 1](media/08-work-order-scheduling.png)

>[!NOTE]
>Om du väljer beläggningstyperna "kapacitet" eller "rest" för beräkningen kommer samma resultat att visas om inga reservationer gjorts för resurserna under den valda perioden.

I [Beräkna kapacitetsbeläggning](../capacity-planning/calculate-capacity-load.md) finns information om hur du beräknar kapacitetsbeläggning på rader för underhållsplanrader och ej schemalagda arbetsorder.
