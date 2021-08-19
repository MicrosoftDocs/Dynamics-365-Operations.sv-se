---
title: Betalningar kvittas automatiskt innan order faktureras eller levereras
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.
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
ms.openlocfilehash: cc5167be43cccfd024ffdc65eb5f4dcac7e187288522d95be2385f8e7fdf106e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718657"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Betalningar kvittas automatiskt innan order faktureras eller levereras

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.

## <a name="description"></a>beskrivning

Efter att en beställning har gjorts avvecklas betalningen omedelbart i Adyen-portalen, även om försäljningsordern inte har fakturerats eller skickats.

## <a name="resolution"></a>Upplösning

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen

Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen med dessa steg.

1. Logga in på Adyen-portal.
1. Välj ditt butikskonto för e-handelskanal i övre högra hörnet.
1. Välj **Konto** i det övre navigeringsfältet och välj **Inställningar**.
1. I fältet **Insamlingsfördröjning** välj **manuell**.

    ![Inställning för registreringsfördröjning i Adyen-portalen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Ytterligare resurser

[Adyen-betalningsinsamling](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector för Adyen](../dev-itpro/adyen-connector.md)

[Ställ in Adyen betalningskoppling för Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
