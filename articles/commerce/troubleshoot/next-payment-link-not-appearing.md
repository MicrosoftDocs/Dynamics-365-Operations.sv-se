---
title: Spara för min nästa betalningsalternativ visas inte
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara för nästa betalning inte visas under Betalningsmetod på en e-handelsplatss utcheckningssida.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018444"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>Spara för min nästa betalningsalternativ visas inte

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan **Spara för nästa betalning** inte visas under **Betalningsmetod** på en e-handelsplatss utcheckningssida.

## <a name="description"></a>beskrivning

Kryssrutan **Spara för nästa betalning** visas inte i avsnittet **Betalningsmetod** på en e-handelsplats utcheckningssida.

Följande illustration visar ett exempel på en kassasida som innehåller kryssrutan **Spara för nästa betalning**.

![Spara nästa betalningskryssruta i modulen Betalning](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Upplösning

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration

Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration med stegen.

1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj onlinebutik.
1. Kontrollera att snabbflikarna **Betalningskonton** se till att fältet **Tillåt att spara betalningsinformation i näthandel** ange till **True**.

![Tillåt att betalningsinformation sparas i fältet e-handel i Commerce-administration](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Ytterligare resurser

[Betalningsmodul](../payment-module.md)

[Spara betalningsinstrument online med anslutningsprogrammet Adyen](../dev-itpro/adyen-connector-listPI.md)
