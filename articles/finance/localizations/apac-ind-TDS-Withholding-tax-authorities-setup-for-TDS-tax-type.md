---
title: Ställ in källskattemyndigheter för TDS-skattetypen
description: I det här avsnittet beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a9b6105c227b530f0cd7a932aac18e8942482d12
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408265"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a>Ställ in källskattemyndigheter för TDS-skattetypen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).

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
