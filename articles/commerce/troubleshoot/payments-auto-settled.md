---
title: Betalningar kvittas automatiskt innan order faktureras eller levereras
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas i Adyen-portalen omedelbart efter det att en order har lagts detta , trots att försäljningsordern inte har fakturerats eller levererats.
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
ms.openlocfilehash: c01a2fda54e198a43fa84ae83686fc1701958b6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890279"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Betalningar kvittas automatiskt innan order faktureras eller levereras

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas i Adyen-portalen omedelbart efter det att en order har lagts detta , trots att försäljningsordern inte har fakturerats eller levererats.

## <a name="description"></a>beskrivning

Efter att en beställning har gjorts avvecklas betalningen omedelbart i Adyen-portalen, även om försäljningsordern inte har fakturerats eller skickats.

## <a name="resolution"></a>Upplösning

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Konfigurera manuella insamling för näthandelsbetalningar i Adyen-portalen

Konfigurera manuella insamling för näthandelsbetalningar i Adyen-portalen med dessa steg.

1. Logga in på Adyen-portal.
1. Välj ditt butikskonto för näthandelskanal i övre högra hörnet.
1. Välj **Konto** i det övre navigeringsfältet och välj **Inställningar**.
1. I fältet **Insamlingsfördröjning** välj **manuell**.

    ![Inställning för registreringsfördröjning i Adyen-portalen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Ytterligare resurser

[Adyen-betalningsinsamling](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector för Adyen](../dev-itpro/adyen-connector.md)

[Ställ in Adyen betalningskoppling för Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
