---
title: Ställ in en Dynamics 365 Commerce utvärderingsmiljö – översikt
description: Det här ämnet ger en översikt över bedömningsmiljö i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cc6bffba6ee402c6b48d6a3c8f8356eb32b5423b
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478030"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="7ddf3-103">Ställ in en Dynamics 365 Commerce utvärderingsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="7ddf3-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7ddf3-104">Det här ämnet ger en översikt över bedömningsmiljö i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="7ddf3-105">Commerce bedömningsmiljöer är i allmänhet inte tillgängliga och ges till partners och kunder för varje enskild begäran.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="7ddf3-106">För mer information, kontakta din Microsoft-partnerkontakt.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-106">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="7ddf3-107">Commerce bedömningsmiljö är en valfri komplett miljö av Dynamics 365 Commerce som låter partners och potentiella kunder prova Commerce-produkten.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-107">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="7ddf3-108">Bedömningsmiljöer är delvis förkonfigurerade för att minska de nödvändiga åtgärderna efter etablering.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-108">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="7ddf3-109">Bortsett från några mindre begränsningar som inte påverkar funktioner eller funktioner, tillhandahåller bedömningsmiljö för Commerce den kompletta handels upplevelsen och kan användas av kunder och implementeringspartners för att utvärdera produkten, ge återkoppling och göra passform/gap-analys.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-109">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="7ddf3-110">Begränsningar i bedömningsmiljö Commerce</span><span class="sxs-lookup"><span data-stu-id="7ddf3-110">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="7ddf3-111">Även om bedömningsmiljö Commerce innehåller en fullständig uppsättning handelsfunktioner och funktioner finns det några mindre begränsningar:</span><span class="sxs-lookup"><span data-stu-id="7ddf3-111">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="7ddf3-112">Även om bedömningsmiljö Commerce inte har några geografiska begränsningar, kan komponenter i miljön, till exempel Retail Cloud Scale Unit (RCSU) och näthandelsprogram, endast etableras i USA.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-112">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="7ddf3-113">Användning av bedömningsmiljö för Commerce är begränsad till 30 dagar från det datum då näthandel etableras.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-113">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="7ddf3-114">Bedömningsmiljö för Commerce kan distribueras och initieras endast i en miljö som använder demotopologin, där alla komponenter i en miljö distribueras i en enda molnstyrd virtuell dator (VM).</span><span class="sxs-lookup"><span data-stu-id="7ddf3-114">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="7ddf3-115">Den huvudsakliga begränsningen för denna topologi är antalet samtidiga användare som miljön kan stödja.</span><span class="sxs-lookup"><span data-stu-id="7ddf3-115">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="7ddf3-116">Kom igång</span><span class="sxs-lookup"><span data-stu-id="7ddf3-116">Get started</span></span>

<span data-ttu-id="7ddf3-117">Om du vill etablera bedömningsmiljö för Commerce, se [Etablera en bedömningsmiljö för Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="7ddf3-117">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ddf3-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7ddf3-118">Additional resources</span></span>

[<span data-ttu-id="7ddf3-119">Etablera en Dynamics 365 Commerce bedömningsmiljön</span><span class="sxs-lookup"><span data-stu-id="7ddf3-119">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="7ddf3-120">Konfigurera en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="7ddf3-120">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="7ddf3-121">Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="7ddf3-121">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="7ddf3-122">Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="7ddf3-122">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="7ddf3-123">Dynamics 365 Commerce bedömningsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="7ddf3-123">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
