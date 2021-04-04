---
title: Fel vid ordersynkronisering relaterad till standardbetalningstjänsten
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.
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
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585531"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Fel vid ordersynkronisering relaterad till standardbetalningstjänsten

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.

## <a name="description"></a>beskrivning

När du synkroniserar en onlineorder visas följande felmeddelande: "Det måste finnas en standardbetalningstjänst för att bearbeta kreditkortstransaktioner."

![Standardbetalningstjänstfel saknas](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Upplösning

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration

Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration, följ dessa steg.

1. Gå till **Kundfordringar \> Betalningsinställning \> Betaltjänster**.
1. Se till att alternativet **Standardföretag för nya kreditkort** anges till **Ja** för en betalningstjänst.

## <a name="additional-resources"></a>Ytterligare resurser

[Inställning, auktorisering och registrering av kreditkort](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
