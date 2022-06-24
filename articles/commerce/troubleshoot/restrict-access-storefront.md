---
title: Begränsa åtkomsten till en butiksbutik under testning eller utveckling
description: I denna artikel beskrivs hur du begränsar åtkomsten till en Microsoft Dynamics 365 Commerce-butik medan intern testning eller utveckling sker.
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
ms.openlocfilehash: 77b652aafa6aea807ab11fe02209bc7de43fa446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898894"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Begränsa åtkomsten till en butiksbutik under testning eller utveckling

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du begränsar åtkomsten till en Microsoft Dynamics 365 Commerce-butik medan intern testning eller utveckling sker.

## <a name="description"></a>beskrivning

Under den interna testningen eller den aktiva utvecklingen kan du begränsa åtkomsten till webbplatsen så att externa användare inte kommer åt de publicerade butikssidorna.

## <a name="resolution"></a>Upplösning

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Ställa in Azure AD B2C med hjälp av standardanvändarflöden

Mer information om hur du konfigurerar Azure Active Directory B2C (Azure AD B2C) för din näthandelsplats finns i [Ställa in en B2C-innehavare i Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Begränsa användarnas åtkomst till butikssidor och blockera skapandet av nya användare

Om du vill begränsa användarens åtkomst till butikssidor i Commerce-webbplatsbyggaren gör du så här.

1. Gå till webbplatsen.
1. Välj **sidor** och välj sedan den sida som du vill begränsa användaråtkomsten för.
1. Markera modulen eller fragmentplatsen och välj **redigera**.
1. I egenskapsfönstret, välj **Kräver inloggning?** och välj **Slutför redigering**.
1. Markera **Publicera**.

Om du vill spärra skapandet av nya användare i Azure AD gör du så här.

1. Gå till [Azure-portal](https://portal.azure.com/).
1. Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.
1. I navigeringsfönstret till vänster, välj **Användarflöden**.
1. Längst upp på sidan **användarflöden** väljer du **Nytt användarflöde**.
1. På sidan **Välj en typ av användarflöde** välj **Förhandsgranskning**.
1. I mitten av sidan väljer du **inloggning v2**. Följ stegen i [Ställa in en B2C-innehavare i Commerce](../set-up-b2c-tenant.md) om du vill konfigurera flödet som webbplatsens standardanvändarflöde för Azure AD B2C under testning eller utveckling.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-klientorganisation i Commerce](../set-up-b2c-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](../custom-pages-user-logins.md)
