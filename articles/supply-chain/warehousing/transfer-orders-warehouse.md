---
title: Ställ in lagerställen för överföringsorder
description: Det här avsnittet beskriver hur du ställer in lagerställen för överföringsorder.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 91db6e8f921bd674211f6d478b6d0f0a832c983c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847025"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Ställ in lagerställen för överföringsorder 

[!include [banner](../includes/banner.md)]

Lagerställenivåer kan användas för att skapa en hierarki som stöder överföringsorder mellan lagerställen. Med dessa inställningar beräknar huvudplaneringen artikelbehoven vid den individuella lagerställenivån och genererar planerade överföringsorder från ett tilldelat källagerställe för att uppfylla dem.

1.  Klicka på **Lagerhantering > Inställningar > Lagerindelning > Lagerställen**.

2.  Välj det lagerställe som ska fyllas på.

3.  På snabbfliken **huvudplanering** markerar du kryssrutan **påfyllning**.

4.  I fältet **Huvudlagerställe** väljer du det lagerställe som du vill ange som påfyllningslagerstället. Huvuplaneringen beräknar ett överföringsbehov för det valda lagerstället och genererar en planerad överföringsorder från angivet **Huvudlagerställe**.
   
    > [!NOTE]
    > <P>Om du avmarkerar kryssrutan <STRONG>Påfyllning</STRONG> tilldelas det markerade lagerstället en lagerställenivå i relation till <STRONG>Huvudlagerställe</STRONG>, men <STRONG>Huvudlagerställe</STRONG> ställs inte in som ett påfyllningslagerställe.</P>

5.  Tillämpa de nya inställningarna genom att stänga sidan.


> [!TIP]
> <P>Om du vill tilldela ett lagerställe för påfyllning, måste du först ställa in lagerstället som en lagerdimension i formuläret <STRONG>Lagringsdimensionsgrupper</STRONG>. På den här sidan väljer du fältet <STRONG>Aktiv</STRONG> och fältet <STRONG>Disponera per dimension</STRONG> för lagerstället.</P>

## <a name="set-up-transport-lead-time"></a>Ställa in ledtid för transport

Du måste också ange ledtiden för transport mellan lagerställen på sidan **Transportdagar**. 
1. Gå till **Lagerhantering > Inställningar > Distribution > Transport dagar**.
2. I fältet **Mottagningsplats**, välj **Lagerställe**.
3. Välj **speditionslager**, **mottagande lager** och **transportdagar**. 
4. (Valfritt) Du kan också ange transporttiden beroende på leveranssätt, under fliken **Transportdagar per leveranssätt**.
