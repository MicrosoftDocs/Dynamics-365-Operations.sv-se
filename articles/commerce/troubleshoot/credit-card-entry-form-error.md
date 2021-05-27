---
title: På en inmatningssida för kreditkort visas ett fel i kassan.
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när betalningsmetodavsnittet läses in och visar ett felmeddelande.
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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018516"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>På en inmatningssida för kreditkort visas ett fel i kassan.

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när avsnittet **betalningsmetod** läses in och visar ett felmeddelande.

## <a name="description"></a>beskrivning

När du öppnar utcheckningssidan för en onlinebutik läses avsnittet **Betalningsmetod** in och följande felmeddelande visas: "Något gick fel. Försök igen senare."

![Betalningsmodulfel](media/payment-module-error.jpg)

## <a name="resolution"></a>Upplösning

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Vänta tills Commerce Scale Unit cache upphöra att gälla

Betalningstjänstinställningarna på onlinebutikens utcheckningssida lagras i cacheminnet på Commerce Scale Unit och kan ta upp till 15 minuter att visa på webbplatsen för e-handel. Dessa inställningar innefattar ändringar av konto-ID:t för handlare, molnbaserad API-nyckel och olika konfigurationsinställningar som gäller betalningsmetoden.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en onlinekanal](../channel-setup-online.md)
