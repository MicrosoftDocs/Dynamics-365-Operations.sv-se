---
title: På en inmatningssida för kreditkort visas ett fel i kassan.
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när betalningsmetodavsnittet läses in och visar ett felmeddelande.
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
ms.openlocfilehash: 25f0dde83efff7c1d9a2a456270f5d48047f44ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269766"
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
