---
title: Visa bokförda TDS-betalningar och transaktioner för en TDS-kvittningsperiod
description: I det här avsnittet beskrivs hur du visar betalningar och transaktioner för skatteavdrag vid källan (TDS) som har bokförts för en kvittningsperiod.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: c67f892e36e536ae2a30b242164eeaa581c7d01b163845a529dd777be6d4f1f9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771618"
---
# <a name="view-posted-tds-payments-and-transactions-for-a-tds-settlement-period"></a>Visa bokförda TDS-betalningar och transaktioner för en TDS-kvittningsperiod

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du visar betalningar och transaktioner för skatteavdrag vid källan (TDS) som har bokförts för en kvittningsperiod.

1. Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekvittningsperioder**.

    [![Sidan Källskattekvittningsperioder.](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)

2. På sidan **Källskattekvittningsperioder** väljer du **Källskattebetalningar** för att öppna sidan **Källskattebetalningar**, där du kan visa TDS-kvittningar som gjordes för en specifik TDS-kvittningsperiod.

    Fliken **Översikt** visar följande information:

    - **Datum** – Datumet för TDS-kvittningen.
    - **Verifiering** – Verifieringsnumret för TDS-kvittningstransaktionen.
    - **Skattetyp** – Skattetypen som kvittningsprocessen körs för.
    - **Skattekontonummer (TAN)** – Skattekontonumret (TAN) för den kvittade TDS-transaktionen.
    - **Kvittningsperiod** – Kvittningsperioden som TDS-kvittningsprocessen körs för.
    - **Från-datum** – Startdatumet för kvittningsperioden.
    - **Till-datum** – Slutdatumet för kvittningsperioden.
    - **Källskattebetalningsversion** – Versionen av källskattebetalning: **Original**, **Senaste korrigeringar** eller **Total lista**.

5. Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen.
6. Välj **Källskattetransaktioner** för att visa informationen om TDS-transaktioner som kvittades för en specifik period under kvittningsperioden. Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen. Välj **Källskattekomponenter** för att visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod.
7. Stäng sidan **Källskattebetalningar** för att återgå till sidan **Källskattekvittningsperioder**.
8. Välj **Källskattetransaktioner** för att visa informationen om TDS-transaktioner som kvittades för kvittningsperioden.
