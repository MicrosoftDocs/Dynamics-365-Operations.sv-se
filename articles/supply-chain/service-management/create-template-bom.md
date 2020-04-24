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
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 815b6b726e9a76a9294995bc5689b030cf623ec0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202593"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="b9943-103">Skapa en strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="b9943-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b9943-104">Du kan skapa en strukturlistemall med följande metoder.</span><span class="sxs-lookup"><span data-stu-id="b9943-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="b9943-105">För samtliga metoder gäller att fälten **Från datum** och **Till datum** är valfria och endast till för information.</span><span class="sxs-lookup"><span data-stu-id="b9943-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="b9943-106">Skapa en strukturlistemall manuellt</span><span class="sxs-lookup"><span data-stu-id="b9943-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="b9943-107">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="b9943-108">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="b9943-109">Under **Kopiera strukturlisterader från referens**markerar du alternativ **manuell**.</span><span class="sxs-lookup"><span data-stu-id="b9943-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="b9943-110">I fältet **Artikelnummer** anger du en artikel av typen **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="b9943-111">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b9943-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="b9943-112">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="b9943-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="b9943-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9943-113">Click **OK**.</span></span>

<span data-ttu-id="b9943-114">En ny tom strukturlistemall skapas.</span><span class="sxs-lookup"><span data-stu-id="b9943-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="b9943-115">Skapa en strukturlistemall som baseras på en annan strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="b9943-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="b9943-116">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="b9943-117">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="b9943-118">Under **Kopiera strukturlisterader från referens**markerar du alternativ **Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="b9943-119">I fältet **Referensnummer** väljer du en befintlig strukturlistemall att kopiera till din nya strukturlistemall.</span><span class="sxs-lookup"><span data-stu-id="b9943-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="b9943-120">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b9943-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="b9943-121">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="b9943-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="b9943-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9943-122">Click **OK**.</span></span>

<span data-ttu-id="b9943-123">En ny strukturlistemall skapas med rader som motsvarar raderna i den ursprungliga strukturlistemallen.</span><span class="sxs-lookup"><span data-stu-id="b9943-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="b9943-124">Skapa en strukturlistemall som baseras på en artikelstrukturlista</span><span class="sxs-lookup"><span data-stu-id="b9943-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="b9943-125">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="b9943-126">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="b9943-127">Under **Kopiera strukturlisterader från referens** väljer du **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="b9943-128">I fältet **referensnummer** väljer du en strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="b9943-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="b9943-129">En artikel av typen Strukturlista kopieras till **artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="b9943-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="b9943-130">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b9943-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="b9943-131">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="b9943-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="b9943-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9943-132">Click **OK**.</span></span>

<span data-ttu-id="b9943-133">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlistor**.</span><span class="sxs-lookup"><span data-stu-id="b9943-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="b9943-134">Skapa en strukturlistemall som baseras på en produktionsstrukturlista</span><span class="sxs-lookup"><span data-stu-id="b9943-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="b9943-135">Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="b9943-136">Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="b9943-137">Under **Kopiera strukturlisterader från referens** väljer du **Produktion**.</span><span class="sxs-lookup"><span data-stu-id="b9943-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="b9943-138">I fältet **referensnummer** väljer du en produktionsstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="b9943-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="b9943-139">Ange ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b9943-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="b9943-140">I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="b9943-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="b9943-141">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9943-141">Click **OK**.</span></span>

<span data-ttu-id="b9943-142">En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="b9943-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9943-143">Se även</span><span class="sxs-lookup"><span data-stu-id="b9943-143">See also</span></span>

[<span data-ttu-id="b9943-144">Strukturlistemallar </span><span class="sxs-lookup"><span data-stu-id="b9943-144">Template BOMs</span></span>](template-boms.md)

  


