---
title: Workbench för lastuppbyggnad
description: I det här avsnittet beskrivs hur du arbetar med workbench för beläggningsbyggande.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 429a8bac5491a342ecbc8b67c59c71715a4b0889
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646437"
---
# <a name="load-building-workbench"></a><span data-ttu-id="cb5ea-103">Workbench för lastuppbyggnad</span><span class="sxs-lookup"><span data-stu-id="cb5ea-103">Load building workbench</span></span>

<span data-ttu-id="cb5ea-104">Med hjälp av workbench för beläggningsbyggande kan du använda hämtningsstrategier när du skapar laster.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="cb5ea-105">Skapa en lastuppbyggnadsstrategi</span><span class="sxs-lookup"><span data-stu-id="cb5ea-105">Create a load building strategy</span></span>

<span data-ttu-id="cb5ea-106">Du använder lastuppbyggnadsstrategier för att automatiskt skapa laster.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="cb5ea-107">Den här funktionen kan vara fördelaktig i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="cb5ea-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="cb5ea-108">Om du regelbundet levererar en viss produkt, laststrategier för att spara tid eftersom du inte behöver bygga samma last varje gång.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="cb5ea-109">Om du vill undvika en halv full last för att maximera effektiviteten kan du med hjälp av laststrategier fylla i varje last så mycket som möjligt.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="cb5ea-110">En klass för lastuppbyggnadsstrategi med namnet `TMSLoadBuildingVolumeStrategy` tillhandahåller en lastuppbyggnadsstrategi med namnet *volymbaserade belastningsbyggnadsstrategi*.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="cb5ea-111">Denna strategi låter dig använda de angivna maximivärdena som specificerats för höjd och vikt i lastmallen eller så kan du åsidosätta inställningarna genom att ange nya värden.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="cb5ea-112">Denna strategi är den enda strategi som medföljer.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="cb5ea-113">(Du kan dock ha vissa anpassade strategier.)</span><span class="sxs-lookup"><span data-stu-id="cb5ea-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="cb5ea-114">Om du vill använda den medföljande strategin *Volymbaserad lastuppbyggnadsstrategi* välj fältet **Lastuppbyggnadsstrategi** på sidan **Workbench för lastuppbyggnad** (**Transporthantering &gt; Planering &gt; Workbench för lastuppbyggnad**).</span><span class="sxs-lookup"><span data-stu-id="cb5ea-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="cb5ea-115">Följ dessa steg för att skapa en lastuppbyggnadsstrategi.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="cb5ea-116">Gå till **Transporthantering &gt; Installation &gt; Lastuppbyggnad &gt; Lastuppbyggnadsstrategier**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="cb5ea-117">I åtgärdsfönstret, välj **Generera klasslista** för att se till att du har de senaste versionerna av alla tillgängliga klasser.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="cb5ea-118">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="cb5ea-119">Ange ett unikt namn på strategin, välj klass för lastuppbyggnadsstrategi och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="cb5ea-120">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="cb5ea-121">Klicka på **Parametrar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="cb5ea-122">På sidan **Parametrar för lastuppbyggnadsstrategi**, välj **Volymkapacitet** i listan och sedan i fältet **Värde** ange procentandelen av lastens totala volymkapacitet som ska tillämpas för den nya lastuppbyggnadsstrategi.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="cb5ea-123">Välj **Viktkapacitet** i listan och sedan i fältet **Värde** ange procentandelen av lastens totala viktkapacitet som ska tillämpas för den nya lastuppbyggnadsstrategin.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="cb5ea-124">Stäng sidan **parametrar för lastuppbyggnadsstrategi**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="cb5ea-125">Stäng sidan **lastuppbyggnadsstrategier**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="cb5ea-126">Du kan nu tilldela lastuppbyggnadsstrategin till en lastuppbyggnadsmall.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="cb5ea-127">Alternativt kan du använda den direkt i workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="cb5ea-128">Använd en lastuppbyggnadsstrategi i workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="cb5ea-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="cb5ea-129">Gå till **Transporthantering &gt; Planering &gt; Workbench för lastuppbyggnad**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="cb5ea-130">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="cb5ea-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="cb5ea-131">Välj en strategi i fältet **lastuppbyggnadsstrategi**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="cb5ea-132">Om du har definierat en lastuppbyggnadsmall och tilldelat den lastuppbyggnadsstrategi, i åtgärdsfönstret, på **Hantera mallar** välj **Tillämpa mall**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="cb5ea-133">I den nedrullningsbara dialogrutan **Tillämpa lastuppbyggnadsmall**, välj en mall i fältet **Lastuppbyggnadens mallnamn**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="cb5ea-134">På snabbfliken **Lastmallsekvens**, välj en eller flera [lastmallar](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="cb5ea-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="cb5ea-135">Workbench kommer att försöka få plats med lasten i dessa typer av behållare i den ordning som anges här.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="cb5ea-136">Vanligtvis bör du placera de minsta behållarna överst i listan för att se till att den minsta möjliga behållaren väljs först.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="cb5ea-137">Välj **Föreslå laster** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="cb5ea-138">Granska de föreslagna laster och de föreslagna lastraderna.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="cb5ea-139">I åtgärdsfönstret **Skapa laster** för att skapa laster som är baserade på källdokumentraderna på snabbfliken **Föreslagna lastraderna**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="cb5ea-140">Stäng sidan **Workbench för lastuppbyggnad**.</span><span class="sxs-lookup"><span data-stu-id="cb5ea-140">Close the **Load building workbench** page.</span></span>
