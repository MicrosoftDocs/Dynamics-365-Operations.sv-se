---
title: Moms på online-order beräknas felaktigt
description: Det här ämnet ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.
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
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021113"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Moms på online-order beräknas felaktigt

[!include [banner](../../includes/banner.md)]

Det här ämnet ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.

## <a name="description"></a>beskrivning

När en e-handelsorder läggs beräknas momsen på fel sätt, eller också ställs momsgruppen på försäljningsraden in på fel sätt.

## <a name="resolution"></a>Upplösning

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Konfigurera momsen för en butiksbutik i Commerce -administration

Konfigurera momsen för en butiksbutik i Commerce-administrationmed dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Alla butiker**.
1. Välj den butik du vill konfigurera moms för.
1. Snabbfliken **Allmänt** i avsnittet **Moms**, konfigurera moms för butiken.

> [!NOTE]
> För produktupphämtning från en butik kommer momsgruppen från den butik som är vald för upphämtning. För mer information, se [Ställa in övriga momsalternativ för butiker](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Konfigurera momsen för en kunds adress i Commerce -administration

Konfigurera momsen för en kundens adress i Commerce-administrationmed dessa steg.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund du vill konfigurera moms för.
1. På snabbfliken **Adresser**, välj adressen att konfigurera moms för, välj **Fler alternativ** och sedan **Avancerat**.
1. På snabbfliken **Allmänt**, välj **Momsgrupp**.
1. I fältet **Moms**, välj lämpligt värde.

> [!NOTE]
> För leverans som omfattar moms på kundens adress bestämmer leveransadressen för raden momsgruppen för raden. Om kunden levererar till en befintlig adress som har en momsgrupp som redan konfigurerats, används den befintliga skattegruppen. Som standard har adresserna ingen momsgrupp när de skapas.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Konfigurera allmänna momsgrupper i Commerce-administration

För att konfigurera allmänna momsgrupper i Commerce-administration, följ dessa steg.

1. Gå till **Skatt \> Indirekta skatter \> Moms \> Momsgrupper**.
1. Välj den momsgrupp du vill konfigurera i den vänstra navigeringen.
1. På snabbfliken **Destinationsbaserad skatt för detaljhandel** konfigurera skatterna för momsgruppen.

> [!NOTE]
> För leverans som inte innefattar moms på kundens adress bestämmer leveransadressen för raden och målbaserad moms som är konfigurerad för momsgruppen. Mer information finns i [Konfigurera moms för onlinebutiker baserat på destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera moms för onlinebeställningar](../sales-tax-config.md)