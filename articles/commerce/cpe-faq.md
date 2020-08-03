---
title: Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor
description: Det här avsnittet innehåller vanliga frågor och svar om utvärderingsmiljö för Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599780"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="3bd5b-103">Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="3bd5b-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3bd5b-104">Det här avsnittet innehåller vanliga frågor och svar om utvärderingsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="3bd5b-105">**Kan vi använda utvärderingsmiljön för Commerce som ett e-handelsskyltfönstret för kunder som för närvarande implementerar Retail?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="3bd5b-106">Nr.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-106">No.</span></span> <span data-ttu-id="3bd5b-107">Commerce utvärderingsmiljön är endast till för utvärdering.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="3bd5b-108">Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="3bd5b-109">**Kan utvärderingsmiljön för Commerce användas för att etablera e-handelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="3bd5b-110">Nej (oftast).</span><span class="sxs-lookup"><span data-stu-id="3bd5b-110">No (mostly).</span></span> <span data-ttu-id="3bd5b-111">Commerce utvärderingskomponenterna är bara tillgängliga för miljöer som matchar de konfigurationer som anges i guiden för förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="3bd5b-112">Dessutom är de nödvändiga grundläggande demodata inte tillgängliga i miljöer som distribuerades med en första utgåva som är tidigare än 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="3bd5b-113">**Vilka kostnader är inblandade i att distribuera utvärderingsmiljö för Commerce Microsoft Azure på Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="3bd5b-114">En traditionell Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce huvudkontoret demomiljö (virtuell dator \[VM\]) kommer att finnas i Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="3bd5b-115">Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="3bd5b-116">Andra komponenter, t.ex. Commerce Scale Unit, Commerce webbplatsskaparen och din e-handelswebbplats kommer att vara tillgängliga som en tjänst (SaaS) och värd från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="3bd5b-117">**Vilka Azure-geografiska områden stöds för närvarande i utvärderingsmiljön Commerce?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="3bd5b-118">Utvärderingsmiljö för Commerce kan endast distribueras i Nordamerikas geografi.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="3bd5b-119">**Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="3bd5b-120">Dynamics 365 Commerce och Commerce Scale Unit är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="3bd5b-121">**Hur länge kan utvärderingsmiljön för Commerce användas?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="3bd5b-122">Commerce utvärderingsmiljön har en tidsgräns på 30 dagar från det datum då SaaS-komponenter som Commerce Scale Unit, Commerce webbplatsskaparen och din e-handelswebbplats etableras.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="3bd5b-123">**Kan jag förlänga tidsgränsen för min utvärderingsmiljö för Commerce?**</span><span class="sxs-lookup"><span data-stu-id="3bd5b-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="3bd5b-124">Förlängning av tidsgränsen är ett undantag från normen och beaktas från fall till fall.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="3bd5b-125">Du bör kontakta din Microsoft-partnerkontakt för hjälp.</span><span class="sxs-lookup"><span data-stu-id="3bd5b-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3bd5b-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3bd5b-126">Additional resources</span></span>

[<span data-ttu-id="3bd5b-127">Dynamics 365 Commerce utvärderingsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="3bd5b-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="3bd5b-128">Etablera en Dynamics 365 Commerce utvärderingsmiljön</span><span class="sxs-lookup"><span data-stu-id="3bd5b-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="3bd5b-129">Konfigurera en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="3bd5b-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="3bd5b-130">Konfigurera BOPIS i en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="3bd5b-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="3bd5b-131">Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="3bd5b-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)
