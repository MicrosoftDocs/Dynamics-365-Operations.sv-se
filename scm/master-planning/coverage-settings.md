---
title: "Disponeringsinställningar"
description: "Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fb11a470d98a9742749daaac3244a5bb0d3a689c
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="coverage-settings"></a><span data-ttu-id="dfea6-103">Disponeringsinställningar</span><span class="sxs-lookup"><span data-stu-id="dfea6-103">Coverage settings</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dfea6-104">Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="dfea6-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="dfea6-105">Du kan ange disponeringsinställningar på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="dfea6-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="dfea6-106">Ange disponeringsinställningar för en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="dfea6-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="dfea6-107">Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="dfea6-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="dfea6-108">Klicka på **Huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper** för att skapa en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="dfea6-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="dfea6-109">Du kan koppla en disponeringsgrupp till en produkt.</span><span class="sxs-lookup"><span data-stu-id="dfea6-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="dfea6-110">Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="dfea6-111">Om länken är allmänn, oavsett produktdimensionerna, använder du **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan.</span><span class="sxs-lookup"><span data-stu-id="dfea6-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="dfea6-112">Om du inte länkar en disponeringsgrupp till en produkt, använder du den **Huvudplaneringsgrupp** som anges på sidan **Huvudplaneringsparametrar** sidan som standardinställning.</span><span class="sxs-lookup"><span data-stu-id="dfea6-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="dfea6-113">Ange disponeringsinställningar för en produkt.</span><span class="sxs-lookup"><span data-stu-id="dfea6-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="dfea6-114">Du kan skapa disponeringsinställningar för en specifik produkt.</span><span class="sxs-lookup"><span data-stu-id="dfea6-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="dfea6-115">Klicka på **Hantering av produktinformation &gt; Produkter &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="dfea6-116">Välj produkt och gå sedan till **Åtgärdsfönster**, på fliken **Planera**, i **Disponeringsgrupp**, och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="dfea6-117">Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="dfea6-118">Disponeringinställningarna på sidan**Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="dfea6-119">Ange disponeringsinställningar för en produkt med hjälp av en guide.</span><span class="sxs-lookup"><span data-stu-id="dfea6-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="dfea6-120">Guiden innehåller steg-för-steg-instruktioner för att hjälpa dig ställa in de primära parametrarna för artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="dfea6-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="dfea6-121">På sidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

-   <span data-ttu-id="dfea6-122">Ange disponeringsinställningar för en dimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="dfea6-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="dfea6-123">Klicka på **Produktinformationshantering &gt; Allmänt &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="dfea6-124">På sidan **Frisläppt produktdetalj **, på fliken **Allmänt**, i gruppen **Administration** klickar du på länken **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="dfea6-124">On the **Released product detail **page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="dfea6-125">På fältet **Lagringsdimensionsgrupp** väljer du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen.</span><span class="sxs-lookup"><span data-stu-id="dfea6-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="dfea6-126">Alla produktdimensioner, till exempel konfiguration, färg, storlek, och utförande, måste ha fältet **Disponera per dimension** markerat.</span><span class="sxs-lookup"><span data-stu-id="dfea6-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="dfea6-127">Se även</span><span class="sxs-lookup"><span data-stu-id="dfea6-127">See also</span></span>
--------

[<span data-ttu-id="dfea6-128">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="dfea6-128">Master plans</span></span>](master-plans.md)




