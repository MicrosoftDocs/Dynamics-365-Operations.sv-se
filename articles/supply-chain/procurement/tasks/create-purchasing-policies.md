---
title: Skapa inköpspolicyer
description: I den här proceduren visas hur du skapar inköpspolicyer att justera med dina affärsprocesser för inköp.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3bd4d6f8625c91f2190e994f04cbec4548272f04
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "312909"
---
# <a name="create-purchasing-policies"></a><span data-ttu-id="1c95c-103">Skapa inköpspolicyer</span><span class="sxs-lookup"><span data-stu-id="1c95c-103">Create purchasing policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c95c-104">I den här proceduren visas hur du skapar inköpspolicyer att justera med dina affärsprocesser för inköp.</span><span class="sxs-lookup"><span data-stu-id="1c95c-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="1c95c-105">Innan du kan skapa inköpspolicyer måste du ställa in inköpspolicyparametrarna.</span><span class="sxs-lookup"><span data-stu-id="1c95c-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="1c95c-106">Det är möjligt att skapa, ändra och att överge en inköpspolicy, men du kan inte ta bort en inköpspolicy.</span><span class="sxs-lookup"><span data-stu-id="1c95c-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="1c95c-107">Denna procedur utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="1c95c-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="1c95c-108">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="1c95c-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="1c95c-109">Ställ in policyparametrar</span><span class="sxs-lookup"><span data-stu-id="1c95c-109">Set up policy parameters</span></span>
1. <span data-ttu-id="1c95c-110">Gå till Inköpspolicyer.</span><span class="sxs-lookup"><span data-stu-id="1c95c-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="1c95c-111">Klicka på Parametrar.</span><span class="sxs-lookup"><span data-stu-id="1c95c-111">Click Parameters.</span></span>
    * <span data-ttu-id="1c95c-112">Policyprioritetsregler gäller för olika nivåer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="1c95c-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="1c95c-113">Organisationsenheterna som visas beror på din organisationshierarki och på vilka nivåer i hierarkin som har tilldelats syftet med Intern anskaffningskontroll.</span><span class="sxs-lookup"><span data-stu-id="1c95c-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="1c95c-114">Till exempel kan din organisation ha juridiska personer, kostnadsställen, regioner och avdelningar, men det kan hända att bara några av dessa har ett hierarkiskt syfte av Intern anskaffningskontroll.</span><span class="sxs-lookup"><span data-stu-id="1c95c-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="1c95c-115">Som standard är organisationen av typen Företaget tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="1c95c-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="1c95c-116">Klicka på fliken Parametrar för policyregeltyp.</span><span class="sxs-lookup"><span data-stu-id="1c95c-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="1c95c-117">I trädet väljer du ”Inköpspolicy\Kontrollregel för inköpsrekvisition”.</span><span class="sxs-lookup"><span data-stu-id="1c95c-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="1c95c-118">Du definierar prioritetsordningen för policylösning på policynivå.</span><span class="sxs-lookup"><span data-stu-id="1c95c-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="1c95c-119">Men för vissa policytyper kan du åsidosätta prioritetsordningen för enskilda policyregeltyper.</span><span class="sxs-lookup"><span data-stu-id="1c95c-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="1c95c-120">Till exempel kan du definiera prioritet för inköpspolicyer i denna ordning till: kostnadsställe, avdelning, företag.</span><span class="sxs-lookup"><span data-stu-id="1c95c-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="1c95c-121">Men du kanske vill att prioritetsordningen för katalogpolicyregeln ska användas i denna ordning: avdelning, kostnadsställe, företag.</span><span class="sxs-lookup"><span data-stu-id="1c95c-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="1c95c-122">Då ändrar du prioritetsordningen för katalogpolicyregeln.</span><span class="sxs-lookup"><span data-stu-id="1c95c-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="1c95c-123">När en anställd skapar en rekvisition, bestäms katalogen som visas av de policyer som associeras med arbetarens avdelning, sedan deras kostnadsställe och sedan deras företag.</span><span class="sxs-lookup"><span data-stu-id="1c95c-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="1c95c-124">Om det finns fler än en angiven organisationsnivå, kan du använda de UPP/NED-pilarna för att ange prioritetsordningen för Kontrollregeln för inköpsrekvisition.</span><span class="sxs-lookup"><span data-stu-id="1c95c-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="1c95c-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1c95c-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="1c95c-126">Skapa en ny policy</span><span class="sxs-lookup"><span data-stu-id="1c95c-126">Create a new policy</span></span>
1. <span data-ttu-id="1c95c-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1c95c-127">Click New.</span></span>
2. <span data-ttu-id="1c95c-128">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="1c95c-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="1c95c-129">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="1c95c-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="1c95c-130">En enskild inköpspolicy kan gälla för endast en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1c95c-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="1c95c-131">Du kanske till exempel har en geografisk hierarki med namnet "Geografisk" och en kallad "Avdelning" och ha olika inköpspolicyer för varje.</span><span class="sxs-lookup"><span data-stu-id="1c95c-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="1c95c-132">Välj en organisation som policyn ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="1c95c-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="1c95c-133">Klicka på pilen för att lägga till den valda organisationen.</span><span class="sxs-lookup"><span data-stu-id="1c95c-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="1c95c-134">Du kan köra den här processen om du vill lägga till fler organisationer.</span><span class="sxs-lookup"><span data-stu-id="1c95c-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="1c95c-135">Lägg till en policyregel</span><span class="sxs-lookup"><span data-stu-id="1c95c-135">Add a policy rule</span></span>
1. <span data-ttu-id="1c95c-136">I listan Policyregeltyp väljer du Rekvisitionssyftesregel.</span><span class="sxs-lookup"><span data-stu-id="1c95c-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="1c95c-137">Du skapar en regel som anger standardinställningrekvisitionsyftet till Förbrukning men låter istället återanskaffningtypen markeras.</span><span class="sxs-lookup"><span data-stu-id="1c95c-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="1c95c-138">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="1c95c-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="1c95c-139">Välj Ja i fältet Tillåt manuell åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="1c95c-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="1c95c-140">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="1c95c-140">Click Close.</span></span>
    * <span data-ttu-id="1c95c-141">Nu kan du ställa in andra policyregler för inköpspolicyn.</span><span class="sxs-lookup"><span data-stu-id="1c95c-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="1c95c-142">Observera att en policyregeltyp inte kan ha överlappande regler som är aktiva samtidigt inom en enskild anskaffningpolicy.</span><span class="sxs-lookup"><span data-stu-id="1c95c-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="1c95c-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1c95c-143">Close the page.</span></span>
6. <span data-ttu-id="1c95c-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1c95c-144">Close the page.</span></span>

