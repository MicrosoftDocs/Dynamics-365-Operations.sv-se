---
title: Ställ in TDS-parametrar
description: I den här artikeln beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner. Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3390cad6979858fbff73769d0d25132ba18a2157
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865625"
---
# <a name="set-the-tds-parameters"></a>Ställ in TDS-parametrar

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner. Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).

1. Gå till **Redovisning \> Redovisningsinställning \> Allmänna redovisningsparametrar**.
2. Under fliken **Direkta skatter**, i avsnittet **Skatteavdrag vid källa**, ställer du in alternativet **Aktivera TDS** på **Ja** för att aktivera TDS-funktionaliteten och sidorna och fälten som används för den.
3. Ställ in alternativet **Faktura** på **Ja** för att aktivera fälten som används för att beräkna och dra av TDS på fakturanivå.
4. Ställ in alternativet **Betalning** på **Ja** för att aktivera fälten som används för att beräkna och dra av TDS på betalningsnivå.

    [![Fliken Direkt skatt.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Under fliken **Nummersekvenser** letar du upp raden där fältet **Referens** är inställt på **Betalning av källskatt**. I fältet **Nummersekvenskod** för raden väljer du nummersekvenskoden. Nummersekvenskoden används för att generera verifikationsnummer för den periodiska TDS-kvittningsprocessen.

    > [!NOTE]
    > Om du vill köra den periodiska TDS-kvittningsprocessen går du till **Skatt \> Deklarationer \> Källskatt \> Betalning av källskatt**.

    [![Fliken Nummerserie.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Stäng sidan.
