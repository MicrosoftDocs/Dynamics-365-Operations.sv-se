---
title: Konfigurera och filtrera arbetsytor
description: "Det här avsnittet innehåller en översikt över hur du konfigurerar och filtrerar arbetsytor."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c90384c798023ac4fcab06502d77f832a8e4c4c2
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="configure-and-filter-workspaces"></a><span data-ttu-id="ff1c6-103">Konfigurera och filtrera arbetsytor</span><span class="sxs-lookup"><span data-stu-id="ff1c6-103">Configure and filter workspaces</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ff1c6-104">Det här avsnittet innehåller en översikt över hur du konfigurerar och filtrerar arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-104">This article provides an overview about how to configure and filter workspaces.</span></span>

<a name="configuring-a-workspace"></a><span data-ttu-id="ff1c6-105">Konfigurera arbetsyta</span><span class="sxs-lookup"><span data-stu-id="ff1c6-105">Configuring a workspace</span></span>
-----------------------

<span data-ttu-id="ff1c6-106">Du kan ändra utseende och beteende för vissa arbetsyto r genom att uppdatera inställningar som gäller för hela arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-106">You can change the appearance and behavior of some workspaces by updating settings that apply to the whole workspace.</span></span> <span data-ttu-id="ff1c6-107">När en arbetsyta kan konfigureras innehåller åtgärdsfönstret en knapp med en uppmaning till dig om att klicka på det för att göra konfigurationsändringar.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-107">When a workspace can be configured, the Action Pane includes a button that instructs you to click it to make configuration changes.</span></span> <span data-ttu-id="ff1c6-108">I exemplet i illustrationen nedan heter knappen **Konfigurera min arbetsyta**.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-108">For example, in the following illustration, the button is named **Configure my workspace**.</span></span> 

<span data-ttu-id="ff1c6-109">[![konfigurera-och-filtrera-arbetsytor](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="ff1c6-109">[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span></span>   

<span data-ttu-id="ff1c6-110">När du klickar på knappen visas en dialogruta där du kan ändra de fördefinierade inställningarna för arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-110">When you click the button, a dialog appears, where you can modify the predefined settings for the workspace.</span></span> <span data-ttu-id="ff1c6-111">De specifika inställningarna som du ser i den här dialogrutan varierar efter arbetsytan och beror på vilka specifika kontroller och affärsdata som är tillgängliga på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-111">The specific settings that you see in this dialog vary by workspace, and depend on the specific controls and business data that are available in the workspace.</span></span> 

<span data-ttu-id="ff1c6-112">[![konfigurera-min-arbetsyta](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span><span class="sxs-lookup"><span data-stu-id="ff1c6-112">[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span></span>

## <a name="filtering-a-workspace"></a><span data-ttu-id="ff1c6-113">Filtrera en arbetsyta</span><span class="sxs-lookup"><span data-stu-id="ff1c6-113">Filtering a workspace</span></span>
<span data-ttu-id="ff1c6-114">Många arbetsytor möjliggör filtrering av innehållet som visas i dem.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-114">Many workspaces let you filter the content that appears in them.</span></span> <span data-ttu-id="ff1c6-115">Kontrollerna som är tillgängliga kan möjliggöra filtrering av allt innehåll i arbetsytan eller enbart av innehållet i ett visst avsnitt av arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-115">The controls that are available might let you filter all the content in the workspace or only the content in a specific section of the workspace.</span></span> <span data-ttu-id="ff1c6-116">Filter på arbetsytor kan vara sökningar, kombinationsrutor, fritextfält eller andra typer av kontroller.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-116">The filters on workspaces can be lookups, combo boxes, free-form text fields, or other types of controls.</span></span> <span data-ttu-id="ff1c6-117">Varje typ av filter har dock samma effekter, i enlighet med beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-117">However, every type of filter has the same effects, as described in the following sections.</span></span>

### <a name="workspace-wide-filters"></a><span data-ttu-id="ff1c6-118">Filter på hela arbetsytan</span><span class="sxs-lookup"><span data-stu-id="ff1c6-118">Workspace-wide filters</span></span>

<span data-ttu-id="ff1c6-119">Du kan filtrera hela arbetsytan genom att använda ett filter för hela arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-119">You can filter the whole workspace by using a workspace-wide filter.</span></span> <span data-ttu-id="ff1c6-120">Ett filter för hela arbetsytan visas i det övre vänstra hörnet på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-120">A workspace-wide filter appears in the upper-left corner of the workspace.</span></span> <span data-ttu-id="ff1c6-121">När du väljer ett visst värde i filtrets listruta filtreras innehållet på arbetsytan baserat på det valet.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-121">When you select a specific value in the drop-down list, the contents of the workspace are filtered based on that selection.</span></span> 

<span data-ttu-id="ff1c6-122">[![filter-för-arbetsyta](./media/workspace-filter.png)](./media/workspace-filter.png)</span><span class="sxs-lookup"><span data-stu-id="ff1c6-122">[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)</span></span> 

<span data-ttu-id="ff1c6-123">När du klickar för att öppna filtret visas flera alternativ.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-123">When you click to open the filter, you're presented with several options.</span></span> 

<span data-ttu-id="ff1c6-124">[![expanderat-filter-för-arbetsyta](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span><span class="sxs-lookup"><span data-stu-id="ff1c6-124">[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span></span> 

<span data-ttu-id="ff1c6-125">Välj ett alternativ för att filtrera arbetsytan utifrån det alternativet.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-125">Select an option to filter the workspace based on that option.</span></span>

### <a name="workspace-section-filters"></a><span data-ttu-id="ff1c6-126">Filter för avsnitt av arbetsytan</span><span class="sxs-lookup"><span data-stu-id="ff1c6-126">Workspace section filters</span></span>

<span data-ttu-id="ff1c6-127">Om enskilda avsnitt i arbetsytan har filter kan du filtrera varje avsnitt separat.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-127">If individual sections of the workspace have filters, you can filter each section separately.</span></span> <span data-ttu-id="ff1c6-128">I följande illustration är filtret (fältet som innehåller texten Filter) ett exempel på ett filter för fritextfält.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-128">In the following illustration, the filter (the field that contains the text "Filter") is an example of a free-form text field filter.</span></span> 

<span data-ttu-id="ff1c6-129">[![avsnittsfilter-för-arbetsyta](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span><span class="sxs-lookup"><span data-stu-id="ff1c6-129">[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span></span> 

<span data-ttu-id="ff1c6-130">Välj eller ange ett värde i fältet för att filtrera innehållet i avsnittet på samma sätt som med filtret för hela arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="ff1c6-130">As with a workspace-wide filter, select or enter a value in the field to filter the contents of the section.</span></span>




