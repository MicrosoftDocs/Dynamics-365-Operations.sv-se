---
title: Aktivera manuell publicering av omdömen och recensioner genom en moderator
description: I denna artikel beskrivs hur du aktiverar manuell publicering av omdömen och recensioner genom en moderator i Microsoft Dynamics 365 Commerce och hur du publicerar omdömen och recensioner manuellt.
author: gvrmohanreddy
ms.date: 09/03/2021
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
ms.openlocfilehash: 6591e18ff8e83ec9030d91d8348271b8113e453f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276786"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Aktivera manuell publicering av omdömen och recensioner genom en moderator

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du aktiverar manuell publicering av omdömen och recensioner genom en moderator i Microsoft Dynamics 365 Commerce och hur du publicerar omdömen och recensioner manuellt.

Dynamics 365 Commerce-lösningen för omdömen och recensioner använder Azure Cognitive Services för att ta bort svordomar i titlar och innehåll för recensioner, och för att publicera omdömen och recensioner. Därför krävs det ingen manuell inblandning för att granska och publicera omdömen och recensioner på din näthandelsplats.

En del företag kanske föredrar att moderatorer manuellt granskar och godkänner recensioner innan de publiceras. Om du vill aktivera manuell publicering av omdömen och recensioner genom en moderator måste du aktivera **Kräv moderator för omdömen och recensioner** i Commerce-webbplatsbyggaren.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Aktivera funktionen Kräv moderator för omdömen och recensioner i Commerce-webbplatsbyggaren

Följ stegen nedan för att aktivera funktionen **Kräv moderator för omdömen och recensioner** i Commerce-webbplatsbyggaren.

1. Gå till **Start \> Recensioner \> Inställningar**.
1. Ange alternativet **Kräv moderator för omdömen och recensioner** som **På**.

> [!NOTE]
> Genom att aktivera funktionen **Kräv moderator för omdömen och recensioner** kan du stoppa den automatiska publiceringen av omdömen och recensioner så att manuell publicering nu krävs. Azure Cognitive Services kommer dock att fortsätta att ta bort svordomar i recensioners rubriker och innehåll.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Publicera omdömen och recensioner

När du aktiverar **Kräv moderator för omdömen och recensioner** måste en moderator granska och publicera omdömen och recensioner manuellt för att de ska visas på näthandelsplatsen.

Om du vill visa granska och publicera omdömen och recensioner i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till **Recensioner \> Moderator**.
1. Om fältet **Status** för en rad i rutnätet har inställningen **Opublicerad** har omdömet och recensionen på den raden inte publicerats ännu. Om du bara vill visa opublicerade omdömen och recensioner väljer du **Status: Behöver granskas** i statusfiltret ovanför rutnätet.
1. Välj en eller flera omdömen och recensioner som har statusen **Opublicerad** och välj sedan **Publicera** i kommandofältet. De valda omdömena och recensionerna läggs till i publiceringskön och visas på näthandelsplatsen när de har publicerats.

> [!NOTE]
> - När ett omdöme och en recension har publicerats ändras statusvärdet från **Opublicerad** till ett nullvärde (tomt fält).
> - Om du väljer flera omdömen och recensioner som har blandade statusar och sedan väljer **Publicera**, kommer omdömen och recensioner som inte har publiceras ännu att publiceras. Omdömen och recensioner som redan har publiceras kommer dock inte att publiceras igen.

I följande bild visas ett exempel där tre opublicerade omdömen och recensioner väljs på sidan **Moderator** i Commerce-webbplatsbyggaren.

![Tre opublicerade omdömen och recensioner som har valts på sidan Moderator i Commerce-webbplatsbyggaren.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar](sync-product-ratings.md)

[Importera och exportera värderingar och granskningar](import-export-reviews.md)

[Konfigurera tjänst-till-tjänst-autentisering](service-to-service-auth.md)

[Vanliga frågor och svar om omdömen och recensioner](ratings-reviews-faq.md)
