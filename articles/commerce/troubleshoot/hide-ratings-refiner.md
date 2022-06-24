---
title: Omdömesförfinaren visas i sökresultat och på kategorisidor när lösningen för omdömen och recensioner inte är aktiverad
description: Denna artikel innehåller felsökningsvägledning om hur du döljer omdömesförfinaren på sökresultat och kategorisidor när Microsoft Dynamics 365 Commerce-lösningen för omdömen och recensioner inte har aktiverats för en näthandelsplats.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c35e176fc5673de194a81a3a4694a83f7bc9aa00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885068"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Omdömesförfinaren visas i sökresultat och på kategorisidor när lösningen för omdömen och recensioner inte är aktiverad

[!include [banner](../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning om hur du döljer omdömesförfinaren på sökresultat och kategorisidor när Microsoft Dynamics 365 Commerce-lösningen för omdömen och recensioner inte har aktiverats för en näthandelsplats.

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
