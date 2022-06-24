---
title: På en inmatningssida för kreditkort visas ett fel i kassan.
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när betalningsmetodavsnittet läses in och visar ett felmeddelande.
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
ms.openlocfilehash: 6d1f7ba2d1a63430431af94ed4bed3222c85f14d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910453"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>På en inmatningssida för kreditkort visas ett fel i kassan.

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när avsnittet **Betalningsmetod** läses in och visar ett felmeddelande.

## <a name="description"></a>beskrivning

När du öppnar kassasidan för en onlinebutik läses avsnittet **Betalningsmetod** in och följande felmeddelande visas: "Något gick fel. Försök igen senare."

![Betalningsmodulfel.](media/payment-module-error.jpg)

## <a name="resolution"></a>Lösning

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Vänta tills Commerce Scale Unit cache upphöra att gälla

Betalningstjänstinställningarna på onlinebutikens kassasida lagras i cacheminnet på Commerce Scale Unit och kan ta upp till 15 minuter att visa på webbplatsen för näthandel. Dessa inställningar innefattar ändringar av konto-ID:t för handlare, molnbaserad API-nyckel och olika konfigurationsinställningar som gäller betalningsmetoden.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en onlinekanal](../channel-setup-online.md)
