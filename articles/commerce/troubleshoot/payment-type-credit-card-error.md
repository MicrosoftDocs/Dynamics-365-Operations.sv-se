---
title: Betalningstypen måste vara kreditkortsfel på försäljningsordersidan
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.
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
ms.openlocfilehash: 03bcbedb12b95a00141d27e9a93186a7fa7dabba70147177524f604dd10ed252
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750682"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Betalningstypen måste vara kreditkortsfel på försäljningsordersidan

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.

## <a name="description"></a>beskrivning

När du öppnar försäljningsordersidan efter att du synkroniserat en order visas följande felmeddelande: "Betalningstypen måste vara kreditkort, eftersom kreditkortsnumret har angetts."

![Betalningstypen måste vara kreditkort-fel.](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Lösning

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Ställ in betalningstypen i Commerce-administration

1. Gå till **Kundreskontra \> Betalningsinställning \> Betalningsvillkor**.
1. Välj betalningsvillkor i den vänstra navigeringen.
1. I fältet **Betalningstyp**, se till att **kreditkort** är valt.

## <a name="additional-resources"></a>Ytterligare resurser

[Bokföring av försäljningar och betalningar online](../tasks/posting-online-sales-payments.md)
