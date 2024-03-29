---
title: Spara för min nästa betalningsalternativ visas inte
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara till nästa betalning inte visas under Betalningsmetod på en näthandelsplatsens kassasida.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d0b398a4ffc5fb698ea04ba8642d05ccd4caf04c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287495"
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
