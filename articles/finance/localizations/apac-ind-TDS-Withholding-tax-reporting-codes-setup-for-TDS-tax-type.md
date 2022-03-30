---
title: Ställ in källskatterapporteringskoder för TDS-skattetypen
description: Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS). I det här avsnittet beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.
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
ms.openlocfilehash: 6775d9d6d917e617e0d371914f0b8b4958c69c54
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408000"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Ställ in källskatterapporteringskoder för TDS-skattetypen

[!include [banner](../includes/banner.md)]

Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS). I det här avsnittet beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.

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
