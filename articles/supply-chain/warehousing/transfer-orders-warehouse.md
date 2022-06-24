---
title: Ställ in lagerställen för överföringsorder
description: Denna artikel beskriver hur du konfigurerar lagerställen för överföringsorder.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 984f90343805d35833b7ddd1a175af5833c23dd5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905527"
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
> <P>Om du vill tilldela ett lagerställe för påfyllning, måste du först konfigurera lagerstället som en lagerdimension i formuläret <STRONG>Lagringsdimensionsgrupper</STRONG>. På den här sidan väljer du fältet <STRONG>Aktiv</STRONG> och fältet <STRONG>Disponera per dimension</STRONG> för lagerstället.</P>

## <a name="set-up-transport-lead-time"></a>Ställa in ledtid för transport

Du måste också ange ledtiden för transport mellan lagerställen på sidan **Transportdagar**. 
1. Gå till **Lagerhantering > Inställningar > Distribution > Transport dagar**.
2. I fältet **Mottagningsplats**, välj **Lagerställe**.
3. Välj **speditionslager**, **mottagande lager** och **transportdagar**. 
4. (Valfritt) Du kan också ange transporttiden beroende på leveranssätt, under fliken **Transportdagar per leveranssätt**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]