---
title: Kundförmånskort och belöningspoäng
description: I det här avsnittet beskrivs hur du integrerar data om kundförmånskort och belöningspoäng mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998024"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="d21d8-103">Kundförmånskort och belöningspoäng</span><span class="sxs-lookup"><span data-stu-id="d21d8-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d21d8-104">Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster.</span><span class="sxs-lookup"><span data-stu-id="d21d8-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="d21d8-105">I Microsoft Dynamics 365 paket med appar, Dynamics 365 Commerce har infrastrukturen och funktionerna för att under lätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser.</span><span class="sxs-lookup"><span data-stu-id="d21d8-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="d21d8-106">När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Common Data Service, modellstyrda appar i Dynamics 365 använda dessa data.</span><span class="sxs-lookup"><span data-stu-id="d21d8-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="d21d8-107">Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="d21d8-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="d21d8-108">Mallar</span><span class="sxs-lookup"><span data-stu-id="d21d8-108">Templates</span></span>

| <span data-ttu-id="d21d8-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="d21d8-109">Finance and Operations apps</span></span> | <span data-ttu-id="d21d8-110">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d21d8-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d21d8-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d21d8-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="d21d8-112">Förmånskort</span><span class="sxs-lookup"><span data-stu-id="d21d8-112">Loyalty card</span></span>                | <span data-ttu-id="d21d8-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="d21d8-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="d21d8-114">Den här mallen synkroniserar information om förmånskort.</span><span class="sxs-lookup"><span data-stu-id="d21d8-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="d21d8-115">Förmånsbelöningspoäng</span><span class="sxs-lookup"><span data-stu-id="d21d8-115">Loyalty reward points</span></span>       | <span data-ttu-id="d21d8-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="d21d8-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="d21d8-117">Den här mallen synkroniserar information om kundbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="d21d8-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
