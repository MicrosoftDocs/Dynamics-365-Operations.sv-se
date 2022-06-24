---
title: Ställ in källskattemyndigheter för TDS-skattetypen
description: I den här artikeln beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).
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
ms.openlocfilehash: 43562381bab93d2f143788b8dc61f2b13d05db3b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864225"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a>Ställ in källskattemyndigheter för TDS-skattetypen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).

1. Gå till **Skatt \> Indirekt skatt \> Källskattemyndigheter**.

    [![Sidan Källskattemyndigheter-](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)

2. I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattemyndigheter för skattetypen TDS.
3. I åtgärdsfönstret, välj **Ny** för att skapa en rad.
4. I fältet **Källskattemyndigheter** anger du ett namn på TDS-myndigheten.
5. Ange en beskrivning i fältet **beskrivning**.
6. Under snabbfliken **Allmänt**, i fältet **Leverantörskonto**, väljer du leverantörskontot för TDS-myndigheten.

    > [!NOTE]
    > Du måste ange namnet på den bank där skulder till TDS-myndighetens leverantör ska sättas in. Bankens namn definieras på sidan **Bankkonton** (**Leverantörsreskontra \> Alla leverantörer \> Leverantör \> Konfigurera \> Bankkonton**).

7. Stäng sidan.
