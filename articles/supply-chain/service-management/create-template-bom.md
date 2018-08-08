---
title: Skapa en strukturlistemall
description: "Du kan skapa en strukturlistemall med följande metoder."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 89c5d45ac27a8678c51fb63c0326c2802a094596
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-template-bom"></a><span data-ttu-id="0c1a1-103">Skapa en strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="0c1a1-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0c1a1-104">Du kan skapa en strukturlistemall med följande metoder.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="0c1a1-105">För samtliga metoder gäller att fälten **Från datum** och **Till datum** är valfria och endast till för information.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="0c1a1-106">Skapa en strukturlistemall manuellt</span><span class="sxs-lookup"><span data-stu-id="0c1a1-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="0c1a1-107">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="0c1a1-108">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="0c1a1-109">Under **Kopiera strukturlisterader från referens**markerar du alternativ **manuell**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="0c1a1-110">I fältet **Artikelnummer** anger du en artikel av typen **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="0c1a1-111">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="0c1a1-112">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="0c1a1-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-113">Click **OK**.</span></span>

<span data-ttu-id="0c1a1-114">En ny tom strukturlistemall skapas.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="0c1a1-115">Skapa en strukturlistemall som baseras på en annan strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="0c1a1-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="0c1a1-116">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="0c1a1-117">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="0c1a1-118">Under **Kopiera strukturlisterader från referens**markerar du alternativ **Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="0c1a1-119">I fältet **Referensnummer** väljer du en befintlig strukturlistemall att kopiera till din nya strukturlistemall.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="0c1a1-120">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="0c1a1-121">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="0c1a1-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-122">Click **OK**.</span></span>

<span data-ttu-id="0c1a1-123">En ny strukturlistemall skapas med rader som motsvarar raderna i den ursprungliga strukturlistemallen.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="0c1a1-124">Skapa en strukturlistemall som baseras på en artikelstrukturlista</span><span class="sxs-lookup"><span data-stu-id="0c1a1-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="0c1a1-125">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="0c1a1-126">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="0c1a1-127">Under **Kopiera strukturlisterader från referens** väljer du **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="0c1a1-128">I fältet **referensnummer** väljer du en strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="0c1a1-129">En artikel av typen Strukturlista kopieras till **artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="0c1a1-130">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="0c1a1-131">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="0c1a1-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-132">Click **OK**.</span></span>

<span data-ttu-id="0c1a1-133">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlistor**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="0c1a1-134">Skapa en strukturlistemall som baseras på en produktionsstrukturlista</span><span class="sxs-lookup"><span data-stu-id="0c1a1-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="0c1a1-135">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="0c1a1-136">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="0c1a1-137">Under **Kopiera strukturlisterader från referens** väljer du **Produktion**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="0c1a1-138">I fältet **referensnummer** väljer du en produktionsstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="0c1a1-139">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="0c1a1-140">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="0c1a1-141">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-141">Click **OK**.</span></span>

<span data-ttu-id="0c1a1-142">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="0c1a1-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c1a1-143">Se även</span><span class="sxs-lookup"><span data-stu-id="0c1a1-143">See also</span></span>

[<span data-ttu-id="0c1a1-144">Strukturlistemallar </span><span class="sxs-lookup"><span data-stu-id="0c1a1-144">Template BOMs</span></span>](template-boms.md)

  



