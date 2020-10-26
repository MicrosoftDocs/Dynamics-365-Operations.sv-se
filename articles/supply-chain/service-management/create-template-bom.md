---
title: Skapa en strukturlistemall
description: Du kan skapa en strukturlistemall med följande metoder.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2e06283f3b95c5ff6b4376bba63cf5a42d5feeb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981827"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="f9468-103">Skapa en strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="f9468-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f9468-104">Du kan skapa en strukturlistemall med följande metoder.</span><span class="sxs-lookup"><span data-stu-id="f9468-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="f9468-105">För samtliga metoder gäller att fälten **Från datum** och **Till datum** är valfria och endast till för information.</span><span class="sxs-lookup"><span data-stu-id="f9468-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="f9468-106">Skapa en strukturlistemall manuellt</span><span class="sxs-lookup"><span data-stu-id="f9468-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="f9468-107">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f9468-108">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f9468-109">Under **Kopiera strukturlisterader från referens**markerar du alternativ **manuell**.</span><span class="sxs-lookup"><span data-stu-id="f9468-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="f9468-110">I fältet **Artikelnummer** anger du en artikel av typen **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="f9468-111">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f9468-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f9468-112">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9468-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f9468-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9468-113">Click **OK**.</span></span>

<span data-ttu-id="f9468-114">En ny tom strukturlistemall skapas.</span><span class="sxs-lookup"><span data-stu-id="f9468-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="f9468-115">Skapa en strukturlistemall som baseras på en annan strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="f9468-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="f9468-116">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f9468-117">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f9468-118">Under **Kopiera strukturlisterader från referens**markerar du alternativ **Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="f9468-119">I fältet **Referensnummer** väljer du en befintlig strukturlistemall att kopiera till din nya strukturlistemall.</span><span class="sxs-lookup"><span data-stu-id="f9468-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="f9468-120">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f9468-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f9468-121">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9468-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f9468-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9468-122">Click **OK**.</span></span>

<span data-ttu-id="f9468-123">En ny strukturlistemall skapas med rader som motsvarar raderna i den ursprungliga strukturlistemallen.</span><span class="sxs-lookup"><span data-stu-id="f9468-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="f9468-124">Skapa en strukturlistemall som baseras på en artikelstrukturlista</span><span class="sxs-lookup"><span data-stu-id="f9468-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="f9468-125">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f9468-126">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f9468-127">Under **Kopiera strukturlisterader från referens** väljer du **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="f9468-128">I fältet **referensnummer** väljer du en strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="f9468-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="f9468-129">En artikel av typen Strukturlista kopieras till **artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="f9468-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="f9468-130">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f9468-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f9468-131">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9468-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f9468-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9468-132">Click **OK**.</span></span>

<span data-ttu-id="f9468-133">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlistor**.</span><span class="sxs-lookup"><span data-stu-id="f9468-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="f9468-134">Skapa en strukturlistemall som baseras på en produktionsstrukturlista</span><span class="sxs-lookup"><span data-stu-id="f9468-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="f9468-135">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f9468-136">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f9468-137">Under **Kopiera strukturlisterader från referens** väljer du **Produktion**.</span><span class="sxs-lookup"><span data-stu-id="f9468-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="f9468-138">I fältet **referensnummer** väljer du en produktionsstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="f9468-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="f9468-139">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f9468-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f9468-140">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9468-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f9468-141">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9468-141">Click **OK**.</span></span>

<span data-ttu-id="f9468-142">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="f9468-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9468-143">Se även</span><span class="sxs-lookup"><span data-stu-id="f9468-143">See also</span></span>

[<span data-ttu-id="f9468-144">Strukturlistemallar </span><span class="sxs-lookup"><span data-stu-id="f9468-144">Template BOMs</span></span>](template-boms.md)

  


