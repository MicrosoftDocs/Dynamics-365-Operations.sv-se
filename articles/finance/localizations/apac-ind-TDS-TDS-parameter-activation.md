---
title: Ställ in TDS-parametrar
description: I det här avsnittet beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner. Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e0c0c830391b790f3bc066e319a855b44f7e243f4e086144bbafaa6bb2fa1df3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781717"
---
# <a name="set-the-tds-parameters"></a>Ställ in TDS-parametrar

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner. Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).

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
