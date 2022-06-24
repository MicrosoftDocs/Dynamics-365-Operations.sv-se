---
title: Ställ in källskatterapporteringskoder för TDS-skattetypen
description: Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS). I den här artikeln beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.
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
ms.openlocfilehash: bdd2e89d29807dc31d8f2d4684ee413470b1dbde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907810"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Ställ in källskatterapporteringskoder för TDS-skattetypen

[!include [banner](../includes/banner.md)]

Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS). I den här artikeln beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.

1. Gå till **Skatt \> Konfiguration \> Källskatt \> Källskatterapporteringskoder**.

    [![Sidan Källskatterapporteringskoder.](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. I fältet **Skattetyp** väljer du **TDS** för att definiera källskatterapporteringskoder för skattetypen TDS.
3. I fältet **Källskattekomponent** väljer du TDS-komponent som du definierar källskatterapporteringskoden för. I fältet **Källskattekomponentgrupp** visas TDS-komponentgruppen som definierades för TDS-komponenten som du definierar.

    I fältet **Avsnittskod** under snabbfliken **Allmänt** visas avsnittskoden som är kopplad till TDS-komponentgruppen.

4. Under snabbfliken **Allmänt**, i fältet **Raporteringskod**, väljer du TDS-rapporteringskod:

    - TDS
    - TCS
    - Tillägg
    - PE\_Cess
    - SHE\_Cess

5. Stäng sidan.
