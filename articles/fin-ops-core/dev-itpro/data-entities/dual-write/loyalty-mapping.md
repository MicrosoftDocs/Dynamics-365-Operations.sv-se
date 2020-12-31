---
title: Kundförmånskort och belöningspoäng
description: I det här avsnittet beskrivs hur du integrerar data om kundförmånskort och belöningspoäng med dubbelriktad skrivning.
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
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683508"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="c6a5a-103">Kundförmånskort och belöningspoäng</span><span class="sxs-lookup"><span data-stu-id="c6a5a-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c6a5a-104">Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="c6a5a-105">Exempelvis har Dynamics 365 Commerce infrastrukturen och funktionerna för att underlätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="c6a5a-106">När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Dataverse, kan kundengagemangsappar använda dessa data.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="c6a5a-107">Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="c6a5a-108">Mallar</span><span class="sxs-lookup"><span data-stu-id="c6a5a-108">Templates</span></span>

| <span data-ttu-id="c6a5a-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="c6a5a-109">Finance and Operations apps</span></span> | <span data-ttu-id="c6a5a-110">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c6a5a-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="c6a5a-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c6a5a-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="c6a5a-112">Förmånskort</span><span class="sxs-lookup"><span data-stu-id="c6a5a-112">Loyalty card</span></span>                | <span data-ttu-id="c6a5a-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="c6a5a-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="c6a5a-114">Den här mallen synkroniserar information om förmånskort.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="c6a5a-115">Förmånsbelöningspoäng</span><span class="sxs-lookup"><span data-stu-id="c6a5a-115">Loyalty reward points</span></span>       | <span data-ttu-id="c6a5a-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="c6a5a-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="c6a5a-117">Den här mallen synkroniserar information om kundbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="c6a5a-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
