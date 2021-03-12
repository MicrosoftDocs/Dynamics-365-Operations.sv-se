---
title: Välj att använda omdömen och recensioner
description: Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 481a8750b2333d5dd5de2c05e175569804a6046f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985846"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Välj att använda omdömen och recensioner

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.

## <a name="overview"></a>Översikt

Klassificerings- och granskningslösningen är en flerkanalslösning som du kan göra tillgänglig i Dynamics 365 Commerce genom att använda Microsoft Dynamics Lifecycle Services (LCS). LCS är en administrationsportal som används av detaljhandlare för att hantera sina miljöer från etablering till avställning.

Om du vill använda klassificeringen och granska lösningen på din handelswebbplats, måste du välja om du vill ha omdömen och recensioner under distributionen av din näthandelssajt på Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Välj att använda omdömen och recensioner

Om du vill använda värderingar och recensioner på webbplatsen följer du stegen nedan.

1. Följ stegen i [distribuera en ny näthandelssajt](deploy-ecommerce-site.md).
1. När du fortfarande är i LCS går du till **Inställning av butiksdistribution \> Övriga inställningar**.
1. Ange alternativet **tjänsten aktivera klassificering och granska** till **Ja**.
1. I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner (ojekt-ID för säkerhetsgrupp)** ange ID för den Microsoft Azure Active Directory (Azure AD) äkerhetsgrupp som inkluderar moderatorer för omdömen och recensioner.

    ![Välj att använda omdömen och recensioner](media/LCS_RnR_Preference.png)

1. Slutför initieringsprocessen för näthandel.

> [!NOTE] 
> Om du är en befintlig Dynamics 365 Commerce-kund som redan har distribuerat en näthandelssajt utan att ha valt värderingar och recensioner och nu vill använda omdömen och recensioner från Dynamics 365 Commerce-paketet, måste du skicka en servicebegäran. Mer information om hur du skickar en servicebegäran finns i [skicka bearbeta serviceförfrågningar](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar i Dynamics 365 Commerce](sync-product-ratings.md)


