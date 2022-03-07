---
title: Spara för min nästa betalningsalternativ visas inte
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara för nästa betalning inte visas under Betalningsmetod på en e-handelsplatss utcheckningssida.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 7e3156d1aa9a05dc5d159b6f9b33ae341de640bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801709"
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
