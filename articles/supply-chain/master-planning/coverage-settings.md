---
title: Disponeringsinställningar
description: Det här ämnet ger information om de disponeringsinställningar som huvudplaneringen använder för att beräkna artikelbehov.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538904"
---
# <a name="coverage-settings"></a><span data-ttu-id="9b226-103">Disponeringsinställningar</span><span class="sxs-lookup"><span data-stu-id="9b226-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b226-104">Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="9b226-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="9b226-105">Du kan ange disponeringsinställningar på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="9b226-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="9b226-106">Ange disponeringsinställningar för en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="9b226-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="9b226-107">Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9b226-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="9b226-108">För att skapa en täckningsgrupp, gå till **huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="9b226-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="9b226-109">Du kan koppla en disponeringsgrupp till en produkt.</span><span class="sxs-lookup"><span data-stu-id="9b226-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="9b226-110">Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="9b226-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="9b226-111">Om länken är allmänn, oavsett produktdimensionerna, använder du fältet **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan.</span><span class="sxs-lookup"><span data-stu-id="9b226-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="9b226-112">Som standard, om du inte länkar en täckningsgrupp till en produkt, använder du huvudplaneringen av den allmänna täckningsgruppen som anges på **Huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="9b226-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="9b226-113">Ange disponeringsinställningar för en produkt.</span><span class="sxs-lookup"><span data-stu-id="9b226-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="9b226-114">Du kan skapa disponeringsinställningar för en specifik produkt.</span><span class="sxs-lookup"><span data-stu-id="9b226-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="9b226-115">Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9b226-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9b226-116">Välj produkt och gå sedan till Åtgärdsfönster, på fliken **Plan** i grupp **Disponering** och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="9b226-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="9b226-117">Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**.</span><span class="sxs-lookup"><span data-stu-id="9b226-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="9b226-118">Disponeringinställningarna på sidan**Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="9b226-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="9b226-119">Ange disponeringsinställningar för en produkt med hjälp av en guide.</span><span class="sxs-lookup"><span data-stu-id="9b226-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="9b226-120">Guiden hjälper dig steg för steg genom processen att ställa in de primära parametrarna för artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="9b226-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="9b226-121">På åtgärdssidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.</span><span class="sxs-lookup"><span data-stu-id="9b226-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="9b226-122">Ange disponeringsinställningar för en dimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="9b226-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="9b226-123">Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9b226-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9b226-124">På sidan **Frisläppt produktdetalj** på snabbfliken **Allmänt** i avsnittet **Administration** klickar du på länken i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="9b226-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="9b226-125">På fältet **Lagringsdimensionsgrupper** markerar du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen.</span><span class="sxs-lookup"><span data-stu-id="9b226-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="9b226-126">Fält **Disponera per dimension** måste väljas för alla produktdimensioner, t.ex. konfiguration, färg, storlek och stil.</span><span class="sxs-lookup"><span data-stu-id="9b226-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b226-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9b226-127">Additional resources</span></span>

[<span data-ttu-id="9b226-128">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="9b226-128">Master plans</span></span>](master-plans.md)
