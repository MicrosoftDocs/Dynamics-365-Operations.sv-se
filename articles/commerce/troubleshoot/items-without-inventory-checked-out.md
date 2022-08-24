---
title: Artiklar utan lager kan checkas ut
description: Denna artikel innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till kassan.
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
ms.openlocfilehash: 3bc924e44077886b942e19b25a84f0f1d4298c13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282745"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Artiklar utan lager kan checkas ut

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till kassan.

## <a name="description"></a>beskrivning

Användarna kan lägga till en artikel i vagnen trots att det inte finns någon lagerbehållning i butiken och sedan gå vidare till kassasidan.

## <a name="resolution"></a>Upplösning

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Aktivera egenskapen Visa fel av typen Slut i lager i Commerce-webbplatsbyggaren

Aktivera egenskapen **Visa fel av typen Slut i lager** i Commerce-webbplatsbyggaren med dessa steg.

1. Välj den webbplats som du arbetar på.
1. I navigeringsfönstret till vänster, välj **sidor**.
1. Välj **CartPage** för att öppna den.
1. Markera kortplatsen **Vagn 1** välj **Redigera** och markera sedan kryssrutan **Visa fel av typen Slut i lager**.
1. Spara och publicera sidan.

## <a name="additional-resources"></a>Ytterligare resurser

[Använd lagerinställningar](../inventory-settings.md)

[Beräkna lagertillgänglighet för butikskanaler](../calculated-inventory-retail-channels.md)

[Konfigurera lagerkvantiteter och lagernivåer](../inventory-buffers-levels.md)
