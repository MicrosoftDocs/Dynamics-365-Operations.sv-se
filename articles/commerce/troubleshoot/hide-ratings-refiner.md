---
title: Omdömesförfinaren visas i sökresultat och på kategorisidor när lösningen för omdömen och recensioner inte är aktiverad
description: Det här avsnittet innehåller felsökningsvägledning om hur du döljer omdömesförfinaren på sökresultat och kategorisidor när Microsoft Dynamics 365 Commerce-lösningen för omdömen och recensioner inte har aktiverats för en näthandelsplats.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9f2f815299335a88663311caaa243f854610f885
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674813"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Omdömesförfinaren visas i sökresultat och på kategorisidor när lösningen för omdömen och recensioner inte är aktiverad

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning om hur du döljer omdömesförfinaren på sökresultat och kategorisidor när Microsoft Dynamics 365 Commerce-lösningen för omdömen och recensioner inte har aktiverats för en näthandelsplats.

## <a name="description"></a>beskrivning

Omdömesförfinaren visas i sökresultat och på kategorisidor i näthandelskanaler som inte använder lösningen för omdömen och recensioner.

## <a name="resolution"></a>Lösning

### <a name="enable-the-hide-rating-setting-in-commerce-site-builder"></a>Aktivera inställningen Dölj värdering i Commerce-webbplatsbyggaren

Aktivera inställningen **Dölj värdering** i Commerce-webbplatsbyggaren så att omdömesförfinaren döljs på sökresultat och kategorisidor genom att följa stegen nedan.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Markera kryssrutan **Dölj värdering** under **Omdömen och recensioner**.
1. Välj **Spara och publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](../ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](../opt-in-ratings-reviews.md)