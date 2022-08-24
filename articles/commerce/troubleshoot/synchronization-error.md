---
title: Fel vid ordersynkronisering relaterad till standardbetalningstjänsten
description: Denna artikel innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.
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
ms.openlocfilehash: aa57366fb8f351a8275c947220de78fe809b7b5a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276700"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Fel vid ordersynkronisering relaterad till standardbetalningstjänsten

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.

## <a name="description"></a>beskrivning

När du synkroniserar en onlineorder visas följande felmeddelande: "Det måste finnas en standardbetalningstjänst för att bearbeta kreditkortstransaktioner."

![Standardfel för betalningstjänst saknas.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Lösning

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Bekräfta eller ställ in standardbetalningstjänsten i Commerce headquarters

Bekräfta eller ställ in standardbetalningstjänsten i Commerce headquarters, följ dessa steg.

1. Gå till **Kundfordringar \> Betalningsinställning \> Betaltjänster**.
1. Se till att alternativet **Standardföretag för nya kreditkort** anges till **Ja** för en betalningstjänst.

## <a name="additional-resources"></a>Ytterligare resurser

[Inställning, auktorisering och registrering av kreditkort](../../finance/accounts-receivable/credit-card-authorizations.md)
