---
title: Betalningstypen måste vara kreditkortsfel på försäljningsordersidan
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585538"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Betalningstypen måste vara kreditkortsfel på försäljningsordersidan

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.

## <a name="description"></a>beskrivning

När du öppnar försäljningsordersidan efter att du synkroniserat en order visas följande felmeddelande: "Betalningstypen måste vara kreditkort, eftersom kreditkortsnumret har angetts."

![Betalningstypen måste vara kreditkortsfel](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Upplösning

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Ställ in betalningstypen i Commerce-administration

1. Gå till **Kundreskontra \> Betalningsinställning \> Betalningsvillkor**.
1. Välj betalningsvillkor i den vänstra navigeringen.
1. I fältet **Betalningstyp**, se till att **kreditkort** är valt.

## <a name="additional-resources"></a>Ytterligare resurser

[Bokföring av försäljningar och betalningar online](../tasks/posting-online-sales-payments.md)
