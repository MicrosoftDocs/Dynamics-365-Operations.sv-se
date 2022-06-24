---
title: Spara för min nästa betalningsalternativ visas inte
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara till nästa betalning inte visas under Betalningsmetod på en näthandelsplatsens kassasida.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: efa04c87f78c376fd00da1b26aedb9e8b428dfa5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871565"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>Spara för min nästa betalningsalternativ visas inte

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan **Spara till nästa betalning** inte visas under **Betalningsmetod** på en näthandelsplats kassasida.

## <a name="description"></a>beskrivning

Kryssrutan **Spara för nästa betalning** visas inte i avsnittet **Betalningsmetod** på en näthandelsplats kassasida.

Följande illustration visar ett exempel på en kassasida som innehåller kryssrutan **Spara för nästa betalning**.

![Kryssrutan Spara till min nästa betalning i modulen Betalning.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Lösning

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce headquarters

Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce headquarters med stegen.

1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj onlinebutik.
1. Kontrollera att snabbflikarna **Betalningskonton** se till att fältet **Tillåt att spara betalningsinformation i näthandel** ange till **True**.

![Tillåt att betalningsinformation sparas i fältet näthandel i Commerce headquarters.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Ytterligare resurser

[Betalningsmodul](../payment-module.md)

[Spara betalningsinstrument online med anslutningsprogrammet Adyen](../dev-itpro/adyen-connector-listPI.md)
