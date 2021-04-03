---
title: Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren visas inte som ett alternativ när du skapar e-handelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny e-handelsklient.
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36ea43e19f395e3914d3eda1a9b8f5487b0926c5
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585540"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren visas inte som ett alternativ när du skapar e-handelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny e-handelsklient.

## <a name="description"></a>beskrivning

När du skapar e-handelskomponenterna som en del i processen med att distribuera en ny e-handelsklient som inkluderar komponenten Commerce-webbplatsbyggaren, visas inte Azure AD säkerhetsgruppen som ett alternativ i dialogrutan.

## <a name="resolution"></a>Upplösning

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Tillhandahålla e-handelsplatsen till en användare med rätt innehavare

1. Gå till [Azure-portal](https://portal.azure.com/).
1. Följ instruktionerna i den innehavare som LCS-projektet för din e-handelssida tillhandahölls [Skapa en basgrupp och lägg till medlemmar med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Gå till [LCS](https://lcs.dynamics.com/) och logga in med ett konto som delar samma innehavare som den Azure AD-säkerhetsgrupp du just skapat. Kontot måste ha åtkomst för att kunna visa Azure AD säkerhetsgruppen.
1. Utför inställningsstegen för att konfigurera webbplatsen för e-handel. När du bestäm e-handelskomponenterna ska säkerhetsgruppen nu visas som ett alternativ i dialogrutan.

> [!NOTE]
> Om du vill vara säker på att fältet i dialogrutan är ifyllt med listan över säkerhetsgrupper måste du välja **Ange** när du har ange namnet på den Azure AD säkerhetsgrupp som du har skapat. I sökresultatet listas alla Azure AD säkerhetsgrupper som börjar med söktexten och som användaren har åtkomst till. Du kan använda en kortare sökord om du vill tillåta sökning med andra sökresultat.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en basgrupp och lägg till medlemmar med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Distribuera en ny klientorganisation för näthandel](../deploy-ecommerce-site.md)
