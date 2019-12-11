---
title: Välj att använda omdömen och recensioner
description: Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697990"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Välj att använda omdömen och recensioner

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.

## <a name="overview"></a>Översikt

Klassificerings- och granskningslösningen är en flerkanalslösning som du kan göra tillgänglig i Dynamics 365 Commerce genom att använda Microsoft Dynamics Lifecycle Services (LCS). LCS är en administrationsportal som används av detaljhandlare för att hantera sina miljöer från etablering till avställning.

Om du vill använda klassificeringen och granska lösningen på din näthandelsplats måste du först anmäla den.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Välj att använda omdömen och recensioner

Om du vill använda värderingar och recensioner på webbplatsen följer du stegen nedan.

1. Följ stegen i [distribuera en ny näthandelsplats](deploy-ecommerce-site.md).
1. När du fortfarande är i LCS går du till **Inställning av butiksdistribution \> Övriga inställningar**.
1. Ange alternativet **tjänsten aktivera klassificering och granska** till **Ja**.
1. I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner (ojekt-ID för säkerhetsgrupp)** ange ID för den Microsoft Azure Active Directory (Azure AD) äkerhetsgrupp som inkluderar moderatorer för omdömen och recensioner.

    ![Välj att använda omdömen och recensioner](media/LCS_RnR_Preference.png)

1. Slutför initieringsprocessen för e-handel.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar i Dynamics 365 Retail](sync-product-ratings.md)
