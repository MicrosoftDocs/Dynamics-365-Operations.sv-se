---
title: Förhandsversionsmiljö för Commerce – översikt
description: Det här ämnet ger en översikt över förhandsversionsmiljö i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906080"
---
# <a name="commerce-preview-environment-overview"></a><span data-ttu-id="04438-103">Förhandsversionsmiljö för Commerce – översikt</span><span class="sxs-lookup"><span data-stu-id="04438-103">Commerce preview environment overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="04438-104">Det här ämnet ger en översikt över förhandsversionsmiljö i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="04438-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="04438-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="04438-105">Overview</span></span>

<span data-ttu-id="04438-106">Commerce förhandsversionsmiljön är en valfri förhandsversionsmiljö av Dynamics 365 Commerce som låter potentiella kunder prova Commerce-produkten innan den allmänna utgåvan släpps till allmänheten.</span><span class="sxs-lookup"><span data-stu-id="04438-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="04438-107">Bortsett från några mindre begränsningar som inte påverkar funktioner eller funktioner, tillhandahåller förhandsversionsmiljön för Commerce den kompletta handels upplevelsen och kan användas av kunder och implementeringspartners för att utvärdera produkten, ge återkoppling och göra passform/gap-analys.</span><span class="sxs-lookup"><span data-stu-id="04438-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="04438-108">Begränsningar i förhandsversionsmiljö Commerce</span><span class="sxs-lookup"><span data-stu-id="04438-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="04438-109">Även om förhandsversionsmiljön Commerce innehåller en fullständig uppsättning handelsfunktioner och funktioner finns det några mindre begränsningar:</span><span class="sxs-lookup"><span data-stu-id="04438-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="04438-110">Även om förhandsversionsmiljö Commerce inte har några geografiska begränsningar, kan komponenter i miljön, till exempel Retail Cloud Scale Unit (RCSU) och e-handelsprogram, endast etableras i USA.</span><span class="sxs-lookup"><span data-stu-id="04438-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="04438-111">Användning av förhandsversionsmiljö för Commerce är begränsad till 30 dagar från det datum då e-handel etableras.</span><span class="sxs-lookup"><span data-stu-id="04438-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="04438-112">Förhandsversionsmiljö för Commerce kan distribueras och initieras endast i en miljö som använder demotopologin, där alla komponenter i en miljödistribueras i en enda virtuell dator (VM).</span><span class="sxs-lookup"><span data-stu-id="04438-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="04438-113">Den huvudsakliga begränsningen för denna OneBox VM-topologi är antalet samtidiga användare som förhandsversionen miljön kan stödja.</span><span class="sxs-lookup"><span data-stu-id="04438-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="04438-114">Förhandsversionsmiljö för Commerce kan endast utvärderas till den allmänna tillgängligheten (GA) för Commerce-produkten.</span><span class="sxs-lookup"><span data-stu-id="04438-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="04438-115">Nya demomiljöer kommer att finnas tillgängliga efter GA.</span><span class="sxs-lookup"><span data-stu-id="04438-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="04438-116">Kom igång</span><span class="sxs-lookup"><span data-stu-id="04438-116">Get started</span></span>

<span data-ttu-id="04438-117">Om du vill etablera förhandsversionsmiljö för Commerce, se [Etablera en förhandsversionsmiljö för Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="04438-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04438-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="04438-118">Additional resources</span></span>

[<span data-ttu-id="04438-119">Etablera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="04438-119">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="04438-120">Konfigurera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="04438-120">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="04438-121">Konfigurera valfria funktioner för en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="04438-121">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="04438-122">Förhandsversionsmiljö för Commerce – vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="04438-122">Commerce preview environment FAQ</span></span>](cpe-faq.md)
