---
title: Ställ in kvittningsperioder för källskatt för TDS-skattetyp
description: I det här avsnittet beskrivs hur du ställer in kvittningsperioder för kvittningsperioder för funktionen Skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 12ba639ccf670997d4f16325172aa351732a5722
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348919"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Ställ in kvittningsperioder för källskatt för TDS-skattetyp

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in kvittningsperioder för kvittningsperioder för funktionen Skatteavdrag vid källa (TDS).

1. Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekvittningsperioder**.

    [![Sidan Källskattekvittningsperioder.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattekvittningsperioder för skattetypen TDS.
3. Klicka på **Nytt** för att skapa en ny rad.
4. I fältet **Kvittningsperiod** anger du ett namn på TDS-kvittningsperioden.
5. Ange en beskrivning i fältet **beskrivning**.
6. I fältet **Källskattemyndighet** väljer du TDS-myndighet som du definierar TDS-kvittningsperioden för.
7. Under snabbfliken **Allmänt**, i fältet **Periodintervall**, väljer du typen av periodintervall för TDS-kvittningsperioden.
8. I fältet **Antal enheter** anger du antalet enheter för periodintervalltypen.
9. Under snabbfliken **Perioder**, i fältet **Från-datum**, väljer du startdatum för TDS-kvittningsperioden. I fältet **Till-datum** anger du slutdatum.
10. Om du vill skapa en efterföljande TDS-kvittningsperiod för en befintlig period, baserat på periodintervallet och periodenheterna, väljer du **Ny period**.
11. Om du vill visa information om den periodiska TDS-kvittning som körs för en viss kvittningsperiod väljer du **Källskattebetalningar** för att öppna sidan **Källskattebetalning**.

    > [!NOTE]
    > Om du vill köra den periodiska TDS-kvittningsprocessen går du till **Redovisning \> Periodisk \> Källskatt \> Betalning av källskatt**.

    [![Sidan Betalning av källskatt.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Stäng sidan.
