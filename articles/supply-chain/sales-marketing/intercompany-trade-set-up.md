---
title: Ställ in koncernintern handel
description: Det här avsnittet innehåller information om hur du ställer in koncernintern handel
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5080267568f4d0626d2c727efb533295e7d8e397
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669416"
---
# <a name="set-up-intercompany-trade"></a>Ställ in koncernintern handel

[!include [banner](../../includes/banner.md)]

Om du vill att Microsoft Dynamics 365 Supply Chain Management ska köra koncernintern handel måste du ställa in kunder och leverantörer att köra koncernintern handel. Du måste också ställ leverantörsreskontra, kundreskontra, anskaffning och källa och försäljning och marknadsföring.

## <a name="before-you-set-up-intercompany-trade"></a>Innan du ställer in koncernintern handel

Innan du ställer in koncernintern handel måste du bestämma dig för vilka kunder som är koncerninterna och vilka leverantörer som är koncerninterna. För varje juridisk person i Microsoft Dynamics 365 Supply Chain Management måste du bestämma vilken handelspolicy som ska gälla för den koncerninterna handelsrelationen till den koncerninterna kunden eller leverantören.

Vi rekommenderar att du och din organisation bekanta er med de koncerninterna parametrarna.

- Diskutera inställningarnas inverkan med de chefer som är ansvariga för koncernintern handel inom varje juridisk person.
- Ställ in lämpliga värden för varje juridisk person.

## <a name="set-up-trading-relations"></a>Ställ in handelsrelationer

Ställ in koncernintern handel för kunder och leverantörer genom att följa dessa steg.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj ett kundkonto.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Ange koncerninterna inställningsparametrar för kundkontot. Dessa parametrar inkluderar den juridiska personen som innehåller motsvarande leverantörs- och leverantörskonto. Parametrarna inkluderar också inköpsorderpolicyer, försäljningsorderpolicyer, värdemappning och policyer för försäljningsavtal och inköpsavtal. Du anger också om du vill använda grunddatavärden från kundkontot eller från leverantörskontot i den andra juridiska personen.
1. Upprepa steg 1 till 4 för de koncerninterna kunder som återstår i den juridiska personen.
1. Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer**.
1. Välj ett leverantörskonto.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Ange koncerninterna inställningsparametrar för leverantörskontot. Dessa parametrar inkluderar den juridiska personen som innehåller motsvarande kund- och kundkonto. Parametrarna inkluderar också försäljningsorderpolicyer, inköpsorderpolicyer, värdemappning och policyer för inköpsavtal och försäljningsavtal. Du anger också om du vill använda grunddatavärden från leverantörskontot eller från kundkontot i den andra juridiska personen.
1. Upprepa steg 6 till 9 för de koncerninterna leverantörer som återstår i den juridiska personen.

## <a name="set-up-products"></a>Ställ in produkter

Ställ in koncernintern handel för kunder och leverantörer genom att följa dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Alla produkter och produktmallar**.
1. Definiera de produkter som frisläpps till de juridiska personer där du vill göra koncernintern handel.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
