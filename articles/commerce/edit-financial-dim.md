---
title: Redigera ekonomiska dimensioner för butikstransaktioner
description: Den här artikeln beskriver hur du redigerar ekonomiska dimensioner för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: b382907cd79a13319601dd694261319875565947
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268407"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Redigera ekonomiska dimensioner för butikstransaktioner

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du redigerar ekonomiska dimensioner för butikstransaktioner i Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Redigera ekonomiska dimensioner

Följ de här stegen om du vill redigera ekonomiska dimensioner för butikstransaktioner i Commerce-administration.

1. Öppna sidan **Konfiguration av ekonomisk dimension för integrering av program**.
1. Välj den aktiva posten för **Integration med standarddimension**.
1. Gå till snabbfliken **Ekonomiska dimensioner** och se till att alla de dimensioner som du vill redigera i Excel-kalkylbladet finns i listan **Valda**. Mer information finns i [Datatabeller](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).
1. Ladda ned och öppna Excel-filen från sidan **Utdrag**, sidan **Butikstransaktioner** eller panelen **Transaktionsvalideringsfel** i arbetsytan **Butiksekonomi**.
1. Om du vill ändra transaktionens ekonomiska dimension väljer **Design** och väljer sedan pennsymbolen bredvid raden **Transaktion (granskningsbar)**.
1. Sök efter och markera fältet **FinancialDimensionDisplayValue**, markera en cell i huvuddelen i Excel-kalkylbladet och välj sedan **Lägg till etikett**.
1. Markera en cell nedanför cellen som du markerade i föregående steg, välj **Lägg till värde** och välj sedan **Uppdatera**. De ekonomiska dimensionerna läggs till i Excel-kalkylbladet och de kan sedan redigeras och publiceras.
1. Om du vill ändra dimensionerna på transaktionsraderna markerar du raden **Försäljningstransaktioner (granskningsbara)**, väljer pennsymbolen och upprepar sedan steg 6 och 7.
1. Om du vill ändra dimensionerna på betalningsraderna markerar du raden **Betalningstransaktioner (granskningsbara)**, väljer pennsymbolen och upprepar sedan steg 6 och 7.

## <a name="additional-resources"></a>Ytterligare resurser

[Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering](edit-cash-trans.md)

[Redigera och granska onlineorder- och asynkrona kundordertransaktioner](edit-order-trans.md)

[Skapa en Excel-arbetsbok för att redigera butikstransaktioner](create-excel-edit.md)

[Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
