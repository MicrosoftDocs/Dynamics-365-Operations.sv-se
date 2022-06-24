---
title: Återbetalning på en returorder avvisas
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en återbetalning av en returorder avvisas eftersom det kreditkort som används för fakturering skiljer sig från det kort som användes i den ursprungliga betalningsauktoriseringen.
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
ms.openlocfilehash: 8360be76fe5ef5ddfbcf290cf6272825bc1849f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879987"
---
# <a name="refund-on-a-return-order-is-declined"></a>Återbetalning på en returorder avvisas

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en återbetalning av en returorder avvisas eftersom det kreditkort som används för fakturering skiljer sig från det kort som användes i den ursprungliga betalningsauktoriseringen.

## <a name="description"></a>beskrivning

En återbetalning avvisas när kreditkortet som används för att fakturera en returorder avviker från det kort som användes i den ursprungliga betalningsauktoriseringen. Du får följande felmeddelande: "Vissa betalningar har inte rätt status för bokföring. Validera statusen för alla betalningar före fakturering på ett annat sätt."

Detaljer om betalningsauktoriseringen innehåller följande felmeddelande: "Adyen gateway SendRequest() misslyckades med statusen InternalServerError'.22144; Tomt svar som returnerats från Adyen. (22001);"

![Avvisad återbetalning vid ett returorderfel.](media/refund-order-decline.jpg)

## <a name="resolution"></a>Lösning

### <a name="enable-blind-returns-in-adyen"></a>Aktivera blinda returer i Adyen

Om du vill aktivera blinda returer följer du stegen i [Felsöka Dynamics 365 Payment Connector för Adyen problem](adyen-support.md) för att kontakta Adyens supportteam och begära att blinda returer aktiveras på ditt Adyen-handelskonto.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365-betalningskoppling för Adyen](../dev-itpro/adyen-connector.md)

[Ställ in Adyen betalningskoppling för Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
