---
title: Serviceobjektrelationer
description: Du kan skapa serviceobjektrelationer mellan ett serviceobjekt och ett serviceavtal eller en serviceorder.
author: ShylaThompson
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1984e4c2d57a03ad27c1f6d417209b806f7d6be6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835856"
---
# <a name="service-object-relations"></a><span data-ttu-id="90cee-103">Serviceobjektrelationer</span><span class="sxs-lookup"><span data-stu-id="90cee-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90cee-104">Du kan skapa serviceobjektrelationer mellan ett serviceobjekt och ett serviceavtal eller en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="90cee-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="90cee-105">När du skapar en relation kopplar du serviceobjektet till serviceavtalet eller serviceordern.</span><span class="sxs-lookup"><span data-stu-id="90cee-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="90cee-106">Efter att relationen är skapad kan du koppla serviceobjektet till alla rader i serviceavtalet eller serviceordern.</span><span class="sxs-lookup"><span data-stu-id="90cee-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="90cee-107">Strukturlistemallar</span><span class="sxs-lookup"><span data-stu-id="90cee-107">Template BOMs</span></span>

<span data-ttu-id="90cee-108">Du kan även ange en strukturlistemall för objektrelationen.</span><span class="sxs-lookup"><span data-stu-id="90cee-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="90cee-109">Strukturlistemallen är en strukturlista för det objekt på vilket tjänsten utförs.</span><span class="sxs-lookup"><span data-stu-id="90cee-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="90cee-110">Om du ersätter en komponentdel av serviceobjektet under ett servicebesök kan du registrera denna ändring i servicestrukturlistan genom att använda formuläret för serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="90cee-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="90cee-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="90cee-111">Example</span></span>

<span data-ttu-id="90cee-112">Du skapar ett serviceavtal för att tillhandahålla service för två hissar på en kunds anläggning.</span><span class="sxs-lookup"><span data-stu-id="90cee-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="90cee-113">Serviceavtalet har identifikations-ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="90cee-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="90cee-114">I formuläret är hissarna inställda som objekt EL-S/1000 och EL-L/1000 i formuläret för serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="90cee-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="90cee-115">Du kopplar serviceobjekten, EL-S/1000 och EL-L/1000, till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="90cee-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="90cee-116">Du vill registrera ändringar i strukturlistan för serviceobjektet när du byter ut komponenter i objektet, så du kopplar en servicestrukturlista till serviceobjektrelationen enligt beskrivningen i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90cee-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="90cee-117">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="90cee-117">Service object</span></span> | <span data-ttu-id="90cee-118">Relation – Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="90cee-118">Relation – Service agreement</span></span> | <span data-ttu-id="90cee-119">Servicestrukturlista</span><span class="sxs-lookup"><span data-stu-id="90cee-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="90cee-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-120">EL-S/1000</span></span>      | <span data-ttu-id="90cee-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="90cee-121">ID SAL-001</span></span>                   | <span data-ttu-id="90cee-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="90cee-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-123">EL-L/1000</span></span>      | <span data-ttu-id="90cee-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="90cee-124">ID SAL-001</span></span>                   | <span data-ttu-id="90cee-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="90cee-126">Eftersom det finns serviceobjektrelationer för avtalet kan du nu skapa serviceavtalsrader med dessa objekt, enligt beskrivningen som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="90cee-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="90cee-127">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="90cee-127">Transaction type</span></span> | <span data-ttu-id="90cee-128">Kategori</span><span class="sxs-lookup"><span data-stu-id="90cee-128">Category</span></span>           | <span data-ttu-id="90cee-129">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="90cee-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="90cee-130">Timme</span><span class="sxs-lookup"><span data-stu-id="90cee-130">Hour</span></span>             | <span data-ttu-id="90cee-131">Inspektion</span><span class="sxs-lookup"><span data-stu-id="90cee-131">Inspection</span></span>         | <span data-ttu-id="90cee-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-132">EL-S/1000</span></span>      |
| <span data-ttu-id="90cee-133">Timme</span><span class="sxs-lookup"><span data-stu-id="90cee-133">Hour</span></span>             | <span data-ttu-id="90cee-134">Rengöring av växellåda</span><span class="sxs-lookup"><span data-stu-id="90cee-134">Gear box cleaning</span></span>  | <span data-ttu-id="90cee-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-135">EL-S/1000</span></span>      |
| <span data-ttu-id="90cee-136">Artikel</span><span class="sxs-lookup"><span data-stu-id="90cee-136">Item</span></span>             | <span data-ttu-id="90cee-137">Rengöringsmaterial</span><span class="sxs-lookup"><span data-stu-id="90cee-137">Cleaning materials</span></span> | <span data-ttu-id="90cee-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-138">EL-S/1000</span></span>      |
| <span data-ttu-id="90cee-139">Timme</span><span class="sxs-lookup"><span data-stu-id="90cee-139">Hour</span></span>             | <span data-ttu-id="90cee-140">Inspektion</span><span class="sxs-lookup"><span data-stu-id="90cee-140">Inspection</span></span>         | <span data-ttu-id="90cee-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-141">EL-L/1000</span></span>      |
| <span data-ttu-id="90cee-142">Timme</span><span class="sxs-lookup"><span data-stu-id="90cee-142">Hour</span></span>             | <span data-ttu-id="90cee-143">Rengöring av växellåda</span><span class="sxs-lookup"><span data-stu-id="90cee-143">Gearbox cleaning</span></span>   | <span data-ttu-id="90cee-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-144">EL-L/1000</span></span>      |
| <span data-ttu-id="90cee-145">Artikel</span><span class="sxs-lookup"><span data-stu-id="90cee-145">Item</span></span>             | <span data-ttu-id="90cee-146">Rengöringsmaterial</span><span class="sxs-lookup"><span data-stu-id="90cee-146">Cleaning materials</span></span> | <span data-ttu-id="90cee-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="90cee-147">EL-L/1000</span></span>      |

<span data-ttu-id="90cee-148">Vid ett servicebesök måste du byta ut växellådan på hissen EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="90cee-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="90cee-149">Om du vill byta ut en komponent i objektet kan du öppna Strukturlistedesignern genom att använda den serviceobjektrelation du ställt in för det aktuella serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="90cee-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="90cee-150">Öppna Strukturlistedesignern genom att använda en serviceobjektrelation</span><span class="sxs-lookup"><span data-stu-id="90cee-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="90cee-151">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="90cee-151">Service agreements</span></span>
2. <span data-ttu-id="90cee-152">Dubbelklicka på ett serviceavtal eller klicka på serviceavtal om du vill skapa ett nytt serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="90cee-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="90cee-153">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="90cee-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="90cee-154">Om du vill koppla en mallstrukturlista till ett serviceavtal klickar du på serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="90cee-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="90cee-155">I formuläret serviceobjekt klicka på Designer för att öppna formuläret Designer och ändra mallstrukturlistan.</span><span class="sxs-lookup"><span data-stu-id="90cee-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="90cee-156">Automatiskt skapade serviceorder</span><span class="sxs-lookup"><span data-stu-id="90cee-156">Automatically created service orders</span></span>

<span data-ttu-id="90cee-157">Om en eller flera serviceorder skapas automatiskt för ett serviceavtal överförs även avtalets serviceobjektrelationer till de serviceorder som skapats.</span><span class="sxs-lookup"><span data-stu-id="90cee-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]