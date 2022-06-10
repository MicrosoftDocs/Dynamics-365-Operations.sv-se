---
title: Delsumman för beställningssammanfattningen inkluderar inte skatter på avgifter vid användning av anpassade moduler för ordersammanfattning
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när du använder anpassade ordersammanfattningsmoduler och ordersammanfattningens delsummor inkluderar inte skatter på avgifter i scenariot "priset inkluderar moms".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 1a47561a3ac984bc554b5b93546592237c16cf18
ms.sourcegitcommit: 48d094d083c1bd45c3d72f8b666926b48ec7ae35
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2022
ms.locfileid: "8767972"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>Delsumman för beställningssammanfattningen inkluderar inte skatter på avgifter vid användning av anpassade moduler för ordersammanfattning

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när du använder anpassade ordersammanfattningsmoduler och ordersammanfattningens delsummor inkluderar inte skatter på avgifter i scenariot "priset inkluderar moms".

## <a name="description"></a>Beskrivning

Från och med Microsoft Dynamics 365 Commerce version 10.0.27 har följande ändringar gjorts i scenariot "pris inkluderar moms" för att ge en konsekvent erfarenhet i ordersammanfattningsmoduler för samtliga näthandelsplats.

- Två nya fält har lagts till: **TaxOnShippingCharge** och **TaxOnNonShippingCharges**.
- **GetSalesOrderBySalesId** och **GetSalesOrderByTransactionId** API (application programming interfaces) ha korrekta värden för följande fält i scenariot "Priset inkluderar moms":

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Om du använder anpassade moduler för ordersammanfattning kan dessa ändringar dock påverka ordersammanfattningens delsummor genom att inte inkludera moms för avgifter.

## <a name="resolution"></a>Lösning

Om du använder anpassade moduler för ordersammanfattning och inte vill ärva de ändringar som gjorts i scenariot "pris inkluderar moms" i Commerce-version 10.0.27 och senare följer du instruktionerna i det här avsnittet.

Genom att återgå till föregående (före version 10.0.27) ordersammanfattningsbeteende för fältet **salesTransaction.SubtotalAmount** och **salesTransaction.SubtotalAmountWithoutTax** du återställer inkluderingen av det totala skattebeloppet (**TaxOnShippingCharge** och **TaxOnNonShippingCharges**) i delsummor (**SubtotalAmount** och **SubtotalAmountWithoutTax**).

Du går tillbaka till sammanfattningen av föregående order genom att följa dessa steg.

1. I Commerce headquarters, öppna Commerce parametersida (**Butik och handel \> Administrationsinställning \> Parametrar \> Commerce-parametrar**).
1. I det vänstra navigeringsfönstret, välj **Konfigurationsparametrar**.
1. Lägg till följande konfigurationsparametrar och ange värdet för var och en av dem till **sant**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Om du tidigare har använt konfigurationsparametern **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** och vill behålla samma beteende för egenskaper **order.NetAmountWithoutTax** bör du också lägga till **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** konfigurationsparameter och ställ in dess värde till **true**.

## <a name="additional-resources"></a>Ytterligare resurser

[Dölj momsuppdelningsinformation i ordersammanfattningar](../hide-taxes-breakup.md)
