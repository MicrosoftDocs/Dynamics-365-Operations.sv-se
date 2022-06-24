---
title: Lastmallar
description: I denna artikel beskrivs hur du konfigurerar lastmallar och hur du kopplar en lastmall till en ny last.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 47b4925c528b64b835ce3e88659ee6ab0572eb2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844193"
---
# <a name="load-templates"></a>Lastmallar

[!include [banner](../../includes/banner.md)]

När du skapar en ny last kan du tilldela en lastmall. Lastmallen innehåller information om utrustning och om mått som höjd, bredd, djup och volym för lasten.

I denna artikel beskrivs hur du konfigurerar lastmallar och hur du kopplar en lastmall till en ny last.

## <a name="set-up-a-load-template"></a>Ställa in en lastmall

1. Gå till **Transporthantering \> Installation \> Lastuppbyggnad \> Lastmall**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en ny mall eller **Redigera** för att redigera en befintlig mall.
1. Ange följande fält i raden för den nya eller befintliga mallen:

    - **Lastmall-ID** – Ange en unik identifierare (ID) för lastmallen.
    - **Utrustning** – Välj den utrustning som ska användas för att leverera lasten.
    - **Lastens höjd**, **Lastens bredd** och **Lastens djup** – Ange måtten för lasten.
    - **Max. tillåten lastvolym** och **Max. tillåten lastvikt** – Ange högsta tillåtna volym och vikt för lasten.
    - **Högsta tillåtna bruttovikt** – Ange lastens maximala tillåtna bruttovikt. Lastens bruttovikt inkluderar både dess taravikt och dess lastvikt.
    - **Maximalt tillåtet antal fraktenheter** – Ange det maximala antalet gods som lasten kan innehålla.
    - **Stapla last på golv** – Markera den här kryssrutan om du vill använda golvpåfyllning. I ett scenario för golvpåfyllning staplas lådor från golv till taket och vägg till vägg inuti behållaren för att maximera kapaciteten.

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="associate-a-load-template-with-a-new-load"></a>Associera en lastmall med en ny last

1. Gå till **Transporthantering \> Planering \> Workbench för lastplanering**.
1. Välj en av följande flikar i den övre delen av sidan, beroende på vilken typ av källdokument som du har skapat en beläggning för: **leveranser**, **försäljningsrader**, **överföringsrader** eller **inköpsorderrader**. 
1. Välj det specifika dokument som du vill planera lasten för.
1. I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**.
1. I dialogrutan **Lastmall** ange fältet **Lastmall-ID** välj mall att tillämpa.
1. Välj **OK** för att använda mallen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]