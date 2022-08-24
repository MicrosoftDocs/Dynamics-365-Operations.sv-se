---
title: Omdömesförfinaren visas i sökresultat och på kategorisidor när lösningen för omdömen och recensioner inte är aktiverad
description: Denna artikel innehåller felsökningsvägledning om hur du döljer omdömesförfinaren på sökresultat och kategorisidor när Microsoft Dynamics 365 Commerce-lösningen för omdömen och recensioner inte har aktiverats för en näthandelsplats.
author: gvrmohanreddy
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
manager: annbe
ms.openlocfilehash: 28a3cefd6aab81f5e7907bda457763f2306e5a1d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267388"
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
