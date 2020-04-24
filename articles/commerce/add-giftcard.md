---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261591"
---
# <a name="gift-card-module"></a>Presentkortsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Presentkort är en vanlig typ av betalning och presentkortsmodulen kan användas i en betalningsmodul för att ta emot presentkort. Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort. SVS och Givex presentkort löses in via Adyen betalningsförmedlaren.

Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md)

## <a name="module-properties"></a>Modulegenskaper

- **Visa ytterligare fält** – den här egenskapen definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard. Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum. Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.

Värden som stöds:
-   PIN-kod
-   Utgångsdatum
-   PIN och utgångsdatum 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Platsinställningar för presentkortsmoduler

I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**. Den här inställningen har stöd för tre värden:
- **Dynamics 365 presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av Dynamics 365-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.
- **SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av SVS- och Givex-presentkort. Den här inställningen stöds för inloggade anonyma användare på webbplatsen för e-handel.
- **Dynamics 365, SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet inlösen av Dynamics 365, Givex och SVS-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.

## <a name="add-a-gift-card-module-to-a-page"></a>Lägg till presentkortmodulen på en ny sida

Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Kassamodul](add-checkout-module.md)

[Stöd för externa presentkort](./dev-itpro/gift-card.md)
