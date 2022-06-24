---
title: Moms på online-order beräknas felaktigt
description: Denna artikel ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.
author: Reza-Assadi
ms.date: 02/16/2022
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
ms.openlocfilehash: eefcfc983a7b3861caa4b4362d2813082b7963a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901631"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Moms på online-order beräknas felaktigt

[!include [banner](../../includes/banner.md)]

Denna artikel ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.

## <a name="description"></a>beskrivning

När en näthandelsorder läggs beräknas momsen på fel sätt, eller också ställs momsgruppen på försäljningsraden in på fel sätt.

## <a name="resolution"></a>Lösning

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Konfigurera allmänna momsgrupper i Commerce headquarters

För att konfigurera allmänna momsgrupper i Commerce headquarters, följ dessa steg.

1. Gå till **Skatt \> Indirekta skatter \> Moms \> Momsgrupper**.
1. Välj den fönster momsgrupp du vill konfigurera i den vänstra navigeringen.
1. På snabbfliken **Destinationsbaserad skatt för detaljhandel** konfigurera skatterna för momsgruppen.

> [!NOTE]
> För frakt som inte inkluderar moms som bestäms av kundens adress bestämmer leveransadressen för raden och målbaserad moms som är konfigurerad för momsgruppen. Mer information finns i [Konfigurera moms för onlinebutiker baserat på destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Konfigurera momsen för en butiksbutik i Commerce headquarters

Konfigurera momsen för en butiksbutik i Commerce headquartersmed dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Alla butiker**.
1. Välj den butik du vill konfigurera moms för.
1. Snabbfliken **Allmänt** i avsnittet **Moms**, konfigurera moms för butiken.

> [!NOTE]
> För produktupphämtning från en butik kommer momsgruppen från den butik som är vald för upphämtning. För mer information, se [Ställa in övriga momsalternativ för butiker](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Konfigurera momsen för en kunds adress i Commerce headquarters

Konfigurera momsen för en kundens adress i Commerce headquartersmed dessa steg.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund du vill konfigurera moms för.
1. På snabbfliken **Adresser**, välj adressen att konfigurera moms för, välj **Fler alternativ** och sedan **Avancerat**.
1. På snabbfliken **Allmänt**, välj **Momsgrupp**.
1. I fältet **Moms**, välj lämpligt värde.

> [!NOTE]
> För leverans som omfattar moms på kundens adress bestämmer leveransadressen för raden momsgruppen för raden. Om kunden levererar till en befintlig adress som har en momsgrupp som redan konfigurerats, används den befintliga skattegruppen. Som standard har adresserna ingen momsgrupp när de skapas.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera moms för onlinebeställningar](../sales-tax-config.md)
