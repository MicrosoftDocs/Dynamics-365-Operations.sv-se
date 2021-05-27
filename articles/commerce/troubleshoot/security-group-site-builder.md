---
title: Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren visas inte som ett alternativ när du skapar e-handelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny e-handelsklient.
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
ms.openlocfilehash: d29e560d0f7b2bbc2415d7a0f6fe18f2ca17dc7c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020742"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="2a36b-103">Det går inte att konfigurera en säkerhetsgrupp för Commerce-webbplatsbyggaren under den första distributionen</span><span class="sxs-lookup"><span data-stu-id="2a36b-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a36b-104">Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp för Commerce-webbplatsbyggaren visas inte som ett alternativ när du skapar e-handelskomponenter i Microsoft Dynamics Lifecycle Services (LCS) under första distributionen av en ny e-handelsklient.</span><span class="sxs-lookup"><span data-stu-id="2a36b-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="2a36b-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a36b-105">Description</span></span>

<span data-ttu-id="2a36b-106">När du skapar e-handelskomponenterna som en del i processen med att distribuera en ny e-handelsklient som inkluderar komponenten Commerce-webbplatsbyggaren, visas inte Azure AD säkerhetsgruppen som ett alternativ i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2a36b-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="2a36b-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2a36b-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="2a36b-108">Tillhandahålla e-handelsplatsen till en användare med rätt innehavare</span><span class="sxs-lookup"><span data-stu-id="2a36b-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="2a36b-109">Gå till [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2a36b-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="2a36b-110">Följ instruktionerna i den innehavare som LCS-projektet för din e-handelssida tillhandahölls [Skapa en basgrupp och lägg till medlemmar med Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2a36b-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="2a36b-111">Gå till [LCS](https://lcs.dynamics.com/) och logga in med ett konto som delar samma innehavare som den Azure AD-säkerhetsgrupp du just skapat.</span><span class="sxs-lookup"><span data-stu-id="2a36b-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="2a36b-112">Kontot måste ha åtkomst för att kunna visa Azure AD säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="2a36b-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="2a36b-113">Utför inställningsstegen för att konfigurera webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="2a36b-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="2a36b-114">När du bestäm e-handelskomponenterna ska säkerhetsgruppen nu visas som ett alternativ i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2a36b-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="2a36b-115">Om du vill vara säker på att fältet i dialogrutan är ifyllt med listan över säkerhetsgrupper måste du välja **Ange** när du har ange namnet på den Azure AD säkerhetsgrupp som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="2a36b-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="2a36b-116">I sökresultatet listas alla Azure AD säkerhetsgrupper som börjar med söktexten och som användaren har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="2a36b-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="2a36b-117">Du kan använda en kortare sökord om du vill tillåta sökning med andra sökresultat.</span><span class="sxs-lookup"><span data-stu-id="2a36b-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a36b-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2a36b-118">Additional resources</span></span>

[<span data-ttu-id="2a36b-119">Skapa en basgrupp och lägg till medlemmar med Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a36b-119">Create a basic group and add members using Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="2a36b-120">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="2a36b-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)