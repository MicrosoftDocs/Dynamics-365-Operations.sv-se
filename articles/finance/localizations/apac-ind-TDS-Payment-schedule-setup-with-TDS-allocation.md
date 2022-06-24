---
title: Ställ in betalningsplaner med TDS-allokering
description: I den här artikeln beskrivs hur du ställer in betalningsplaner med TDS-allokering (skatteavdrag vid källan).
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
ms.openlocfilehash: 48891c32f39b743ce26e265c5682dab28ecb4b27
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868324"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Ställ in betalningsplaner med TDS-allokering

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in betalningsplaner med TDS-allokering (skatteavdrag vid källan).

1. Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsplaner**.

    [![Sidan Betalningsplaner.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. I åtgärdsfönstret väljer du **Ny** för att skapa en betalningsplan och anger den information som krävs.
3. I fältet **Allokering** väljer du den metod som ska användas för att allokera betalningen för betalningsplanen:

    - Totalt
    - Fast belopp
    - Fast kvantitet
    - Angivet

    I fältet **Källskatteallokering** visas TDS-allokeringsmetoden för betalningsplanen. Om du väljer **Totalt** i fältet **Allokering** ställs fältet **Källskatteallokering** automatiskt in på **Totalt**. Om du väljer **Fast belopp**, **Fast kvantitet** eller **Specificerat** i fältet **Allokering**, ställs fältet **Källskatteallokering** automatiskt in på **Proportionellt**.

    > [!NOTE]
    > Om fältet **Källskatteallokering** är inställt på **Totalt**, beräknas avbetalningarna baserat på bruttobeloppet, som inbegriper TDS-beloppet. Om fältet **Källskatteallokering** är inställt på **Proportionellt**, beräknas avbetalningarna baserat på fakturans nettobelopp, efter avdrag av TDS-beloppet.

4. Ange andra uppgifter som behövs och stäng sidan.
