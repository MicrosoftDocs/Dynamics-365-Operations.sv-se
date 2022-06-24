---
title: Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen
description: Denna artikel innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren inte visas som ett alternativ när du skapar näthandelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny näthandelsklient.
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 797df828df16547eb3aef1f9865a663281fb9224
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899025"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren inte visas som ett alternativ när du skapar näthandelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny näthandelsklient.

## <a name="description"></a>beskrivning

När du skapar näthandelskomponenterna som en del i processen med att distribuera en ny näthandelsklient som inkluderar komponenten Commerce-webbplatsbyggaren, visas inte Azure AD säkerhetsgruppen som ett alternativ i dialogrutan.

## <a name="resolution"></a>Upplösning

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Tillhandahålla näthandelsplatsen till en användare med rätt innehavare

1. Gå till [Azure-portal](https://portal.azure.com/).
1. Följ instruktionerna i den innehavare som LCS-projektet för din näthandelssida tillhandahölls [Skapa en basgrupp och lägg till medlemmar med Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Gå till [LCS](https://lcs.dynamics.com/) och logga in med ett konto som delar samma innehavare som den Azure AD-säkerhetsgrupp du just skapat. Kontot måste ha åtkomst för att kunna visa Azure AD säkerhetsgruppen.
1. Utför inställningsstegen för att konfigurera webbplatsen för näthandel. När du bestäm näthandelskomponenterna ska säkerhetsgruppen nu visas som ett alternativ i dialogrutan.

> [!NOTE]
> Om du vill vara säker på att fältet i dialogrutan är ifyllt med listan över säkerhetsgrupper måste du välja **Ange** när du har ange namnet på den Azure AD säkerhetsgrupp som du har skapat. I sökresultatet listas alla Azure AD säkerhetsgrupper som börjar med söktexten och som användaren har åtkomst till. Du kan använda en kortare sökord om du vill tillåta sökning med andra sökresultat.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en basgrupp och lägg till medlemmar med Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Distribuera en ny klientorganisation för näthandel](../deploy-ecommerce-site.md)