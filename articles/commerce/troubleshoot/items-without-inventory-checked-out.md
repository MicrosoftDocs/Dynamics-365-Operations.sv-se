---
title: Artiklar utan lager kan checkas ut
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till utcheckning.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585535"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Artiklar utan lager kan checkas ut

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till utcheckning.

## <a name="description"></a>beskrivning

Användarna kan lägga till en artikel i vagnen trots att det inte finns någon lagerbehållning i butiken och sedan gå vidare till utcheckningssidan.

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
