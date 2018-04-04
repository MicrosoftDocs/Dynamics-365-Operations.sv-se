---
title: Skapa serviceavtal
description: "I det här avsnittet beskrivs hur du använder funktioner i modulerna servicehantering och projekthantering och redovisning för att skapa serviceavtal."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2a46173a3566a56a21add9d42c111d456b1ae7c1
ms.openlocfilehash: 517bc1b9de9b2512f42e4f32b4a19e517e349e8e
ms.contentlocale: sv-se
ms.lasthandoff: 02/19/2018

---

# <a name="create-service-agreements"></a><span data-ttu-id="e543f-103">Skapa serviceavtal</span><span class="sxs-lookup"><span data-stu-id="e543f-103">Create service agreements</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e543f-104">I det här avsnittet beskrivs hur du använder funktioner i modulerna servicehantering och projekthantering och redovisning för att skapa serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="e543f-104">This topic describes how to use features in the Service management and the Project management and accounting modules to create service agreements.</span></span>

## <a name="create-a-service-agreement-from-service-management"></a><span data-ttu-id="e543f-105">Skapa en serviceorder från ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="e543f-105">Create a service agreement from Service management</span></span>

1. <span data-ttu-id="e543f-106">Gå till **servicehantering**.</span><span class="sxs-lookup"><span data-stu-id="e543f-106">Navigate to **Service management**.</span></span>
2. <span data-ttu-id="e543f-107">Klicka på **serviceavtal** om du vill skapa en ny serviceavtalsrad i sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="e543f-107">Click **Service agreements** to create a new service agreement line in the page header.</span></span> 
3. <span data-ttu-id="e543f-108">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e543f-108">Click **New**.</span></span> <span data-ttu-id="e543f-109">Ange en beskrivning, välj en referens till ett projekt i fältet **projekt-ID** och fyll i resten av fälten och raderna för serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e543f-109">Enter a description, select a reference to a project in the **Project ID** field, and fill in the rest of the fields and lines for the service agreement.</span></span> <span data-ttu-id="e543f-110">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e543f-110">Click **Save**.</span></span>
4. <span data-ttu-id="e543f-111">I fliken **relationer** välj **serviceobjekt** eller **serviceuppgifter** när du vill skapa relationer för serviceobjekt eller serviceuppgifter i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e543f-111">On the **Relations** tab, select **Service objects** or **Service tasks** to create service object relations or service task relations for the service agreement.</span></span> <span data-ttu-id="e543f-112">Serviceobjekten och uppgifterna som du har skapat relationer för, kan kopplas till rader för serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e543f-112">The service objects and tasks that you have created relations for can be attached on the lines of the service agreement.</span></span>
5. <span data-ttu-id="e543f-113">Skapa serviceavtalsrader på den nedre halvan av sidan genom att kopiera rader från en servicemall, ett annat serviceavtal eller genom att skapa serviceavtalsraderna manuellt.</span><span class="sxs-lookup"><span data-stu-id="e543f-113">In the lower half of the page, create service agreement lines by copying lines from a service template, another service agreement, or manually creating the service-agreement lines.</span></span>

> [!NOTE]
> <span data-ttu-id="e543f-114">Om du kopierar rader till serviceavtalet från ett annat serviceavtal kan du ange om du även vill kopiera serviceobjekt- och serviceuppgiftsrelationer.</span><span class="sxs-lookup"><span data-stu-id="e543f-114">If you copy lines into the service agreement from another service agreement, you can indicate whether you also want to copy service object and service task relations.</span></span> <span data-ttu-id="e543f-115">Om du kopierar dessa relationer läggs de till i eventuella befintliga relationer i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e543f-115">If you copy these relations, they are added to any existing relations on the service agreement.</span></span> <span data-ttu-id="e543f-116">Om du kopierar serviceavtalsrader från en servicemall kopieras serviceobjekt- och serviceuppgiftsrelationerna automatiskt i form av serviceobjektrelationer och serviceuppgiftsrelationer till de nya serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="e543f-116">If you copy service-agreement lines from a service template, the service-object and service-task relations are automatically copied as service-object relations and service-task relations on the new service-agreement lines.</span></span>

## <a name="create-service-agreement-lines-manually"></a><span data-ttu-id="e543f-117">Skapa serviceavtalsrader manuellt</span><span class="sxs-lookup"><span data-stu-id="e543f-117">Create service agreement lines manually</span></span>

1. <span data-ttu-id="e543f-118">Från sidan för **serviceavtal** kan du lägga till en serviceavtalsrad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e543f-118">From the **Service agreements** page, add a service agreement line in the lines grid.</span></span> 
2. <span data-ttu-id="e543f-119">Ange önskad information för serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="e543f-119">Enter the appropriate information for the service agreement line.</span></span> 
3. <span data-ttu-id="e543f-120">Tryck på **CTRL+S** för att spara raden och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e543f-120">Press **CTRL+S** to save the line, and then close the page.</span></span>

## <a name="create-a-service-agreement-from-project"></a><span data-ttu-id="e543f-121">Skapa ett serviceavtal från Projekt</span><span class="sxs-lookup"><span data-stu-id="e543f-121">Create a service agreement from Project</span></span>

1. <span data-ttu-id="e543f-122">Klicka på **projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="e543f-122">Click **Project management and accounting**.</span></span>
2. <span data-ttu-id="e543f-123">Klicka på **alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="e543f-123">Click **All projects**.</span></span>
3. <span data-ttu-id="e543f-124">Välj projekt i listan.</span><span class="sxs-lookup"><span data-stu-id="e543f-124">Select the project from the list.</span></span>
4. <span data-ttu-id="e543f-125">Klicka på **Hantera** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="e543f-125">On the **Action Pane**, click **Manage**.</span></span> <span data-ttu-id="e543f-126">I den **nya** åtgärdsgruppen, klickar du på **service** och markerar **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="e543f-126">In the **New** Action group, click **Service** and select **Service agreement**.</span></span>
5. <span data-ttu-id="e543f-127">Följ anvisningarna i avsnittet **skapa ett serviceavtal** som beskrevs tidigare i det här avsnittet om du vill ange projektreferensen.</span><span class="sxs-lookup"><span data-stu-id="e543f-127">Follow the steps in the section titled **Create a service agreement** as described earlier in this topic to enter the project reference.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e543f-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e543f-128">Related topics</span></span>

[<span data-ttu-id="e543f-129">Serviceavtal </span><span class="sxs-lookup"><span data-stu-id="e543f-129">Service agreements</span></span>](service-agreements.md)


