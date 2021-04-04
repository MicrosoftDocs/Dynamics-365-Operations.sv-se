---
title: Kundförmånskort och belöningspoäng
description: I det här avsnittet beskrivs hur du integrerar data om kundförmånskort och belöningspoäng med dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568038"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="f4c19-103">Kundförmånskort och belöningspoäng</span><span class="sxs-lookup"><span data-stu-id="f4c19-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f4c19-104">Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster.</span><span class="sxs-lookup"><span data-stu-id="f4c19-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="f4c19-105">Exempelvis har Dynamics 365 Commerce infrastrukturen och funktionerna för att underlätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser.</span><span class="sxs-lookup"><span data-stu-id="f4c19-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="f4c19-106">När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Dataverse, kan kundengagemangsappar använda dessa data.</span><span class="sxs-lookup"><span data-stu-id="f4c19-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="f4c19-107">Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="f4c19-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="f4c19-108">Mallar</span><span class="sxs-lookup"><span data-stu-id="f4c19-108">Templates</span></span>

| <span data-ttu-id="f4c19-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="f4c19-109">Finance and Operations apps</span></span> | <span data-ttu-id="f4c19-110">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f4c19-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="f4c19-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f4c19-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="f4c19-112">Förmånskort</span><span class="sxs-lookup"><span data-stu-id="f4c19-112">Loyalty card</span></span>                | <span data-ttu-id="f4c19-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="f4c19-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="f4c19-114">Den här mallen synkroniserar information om förmånskort.</span><span class="sxs-lookup"><span data-stu-id="f4c19-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="f4c19-115">Förmånsbelöningspoäng</span><span class="sxs-lookup"><span data-stu-id="f4c19-115">Loyalty reward points</span></span>       | <span data-ttu-id="f4c19-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="f4c19-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="f4c19-117">Den här mallen synkroniserar information om kundbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="f4c19-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]