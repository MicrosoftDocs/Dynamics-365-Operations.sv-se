---
title: Dynamics 365 Commerce bedömningsmiljö – vanliga frågor
description: Det här avsnittet innehåller vanliga frågor och svar om bedömningsmiljö för Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 6b8d7d7364087dacf3b4479ab008609ecffeaacb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000985"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="6a71a-103">Dynamics 365 Commerce bedömningsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="6a71a-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6a71a-104">Det här avsnittet innehåller vanliga frågor och svar om bedömningsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a71a-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="6a71a-105">**Kan vi använda bedömningsmiljön för Commerce som ett näthandelsskyltfönstret för kunder som för närvarande implementerar Retail?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="6a71a-106">Nr.</span><span class="sxs-lookup"><span data-stu-id="6a71a-106">No.</span></span> <span data-ttu-id="6a71a-107">Commerce bedömningsmiljön är endast till för utvärdering.</span><span class="sxs-lookup"><span data-stu-id="6a71a-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="6a71a-108">Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a71a-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="6a71a-109">**Kan bedömningsmiljön för Commerce användas för att etablera näthandelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="6a71a-110">Nej (oftast).</span><span class="sxs-lookup"><span data-stu-id="6a71a-110">No (mostly).</span></span> <span data-ttu-id="6a71a-111">Commerce bedömningskomponenterna är bara tillgängliga för miljöer som matchar de konfigurationer som anges i guiden för förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="6a71a-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="6a71a-112">Dessutom är de nödvändiga grundläggande demodata inte tillgängliga i miljöer som distribuerades med en första utgåva som är tidigare än 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="6a71a-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="6a71a-113">**Vilka kostnader är inblandade i att distribuera bedömningsmiljö för Commerce Microsoft Azure på Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="6a71a-114">En traditionell Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce huvudkontoret demomiljö (virtuell dator \[VM\]) kommer att finnas i Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="6a71a-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="6a71a-115">Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.</span><span class="sxs-lookup"><span data-stu-id="6a71a-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="6a71a-116">Andra komponenter, t.ex. Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt kommer att vara tillgängliga som en tjänst (SaaS) och värd från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a71a-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="6a71a-117">**Vilka Azure-geografiska områden stöds för närvarande i bedömningsmiljön Commerce?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="6a71a-118">Bedömningsmiljö för Commerce kan endast distribueras i Nordamerikas geografi.</span><span class="sxs-lookup"><span data-stu-id="6a71a-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="6a71a-119">**Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="6a71a-120">Dynamics 365 Commerce och Commerce Scale Unit är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="6a71a-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="6a71a-121">**Hur länge kan bedömningsmiljön för Commerce användas?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="6a71a-122">Commerce bedömningsmiljön har en tidsgräns på 30 dagar från det datum då SaaS-komponenter som Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt etableras.</span><span class="sxs-lookup"><span data-stu-id="6a71a-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="6a71a-123">**Kan jag förlänga tidsgränsen för min bedömningsmiljö för Commerce?**</span><span class="sxs-lookup"><span data-stu-id="6a71a-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="6a71a-124">Förlängning av tidsgränsen är ett undantag från normen och beaktas från fall till fall.</span><span class="sxs-lookup"><span data-stu-id="6a71a-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="6a71a-125">Du bör kontakta din Microsoft-partnerkontakt för hjälp.</span><span class="sxs-lookup"><span data-stu-id="6a71a-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a71a-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6a71a-126">Additional resources</span></span>

[<span data-ttu-id="6a71a-127">Dynamics 365 Commerce bedömningsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="6a71a-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="6a71a-128">Etablera en Dynamics 365 Commerce bedömningsmiljön</span><span class="sxs-lookup"><span data-stu-id="6a71a-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="6a71a-129">Konfigurera en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="6a71a-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="6a71a-130">Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="6a71a-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="6a71a-131">Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="6a71a-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)
