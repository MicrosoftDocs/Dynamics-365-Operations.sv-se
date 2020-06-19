---
title: Konfigurera avdrag
description: Använd avdrag i Microsoft Dynamics 365 Human Resources för att fastställa hur mycket, om det finns någon, dra av från en medarbetares lön för varje förmån.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c59fa09e83ca91e0ad866e5875ff06370b7491d
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430703"
---
# <a name="configure-deductions"></a><span data-ttu-id="6c36d-103">Konfigurera avdrag</span><span class="sxs-lookup"><span data-stu-id="6c36d-103">Configure deductions</span></span>

<span data-ttu-id="6c36d-104">Använd avdrag i Microsoft Dynamics 365 Human Resources för att fastställa hur mycket, om det finns någon, dra av från en medarbetares lön för varje förmån.</span><span class="sxs-lookup"><span data-stu-id="6c36d-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="6c36d-105">Avdrag har giltighetsdatum så att du kan spara en historisk post med avdragsinformation.</span><span class="sxs-lookup"><span data-stu-id="6c36d-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="6c36d-106">I arbetsytan **Förmånshantering** under **inställningar**, välj **avdrag**.</span><span class="sxs-lookup"><span data-stu-id="6c36d-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="6c36d-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6c36d-107">Select **New**.</span></span>

3. <span data-ttu-id="6c36d-108">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="6c36d-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6c36d-109">Fält</span><span class="sxs-lookup"><span data-stu-id="6c36d-109">Field</span></span> | <span data-ttu-id="6c36d-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c36d-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6c36d-111">**Avdrag**</span><span class="sxs-lookup"><span data-stu-id="6c36d-111">**Deduction**</span></span> | <span data-ttu-id="6c36d-112">Ett unikt ID som används för att identifiera förmånsavdrag.</span><span class="sxs-lookup"><span data-stu-id="6c36d-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="6c36d-113">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="6c36d-113">**Description**</span></span> | <span data-ttu-id="6c36d-114">En beskrivning för avdraget.</span><span class="sxs-lookup"><span data-stu-id="6c36d-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="6c36d-115">**Giltighet**</span><span class="sxs-lookup"><span data-stu-id="6c36d-115">**Effective**</span></span> | <span data-ttu-id="6c36d-116">Startdatumet.</span><span class="sxs-lookup"><span data-stu-id="6c36d-116">The start date.</span></span> <span data-ttu-id="6c36d-117">Standardvärdet är det aktuella systemdatumet.</span><span class="sxs-lookup"><span data-stu-id="6c36d-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="6c36d-118">**Förfallotid**</span><span class="sxs-lookup"><span data-stu-id="6c36d-118">**Expiration**</span></span> | <span data-ttu-id="6c36d-119">Slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="6c36d-119">The end date.</span></span> <span data-ttu-id="6c36d-120">Standardvärdet är 12/31/2154, vilket betyder aldrig.</span><span class="sxs-lookup"><span data-stu-id="6c36d-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="6c36d-121">**Rubrik**</span><span class="sxs-lookup"><span data-stu-id="6c36d-121">**Heading**</span></span> | <span data-ttu-id="6c36d-122">Den rubrikkod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="6c36d-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="6c36d-123">Detta används när du använder en tredje parts löneleverantör.</span><span class="sxs-lookup"><span data-stu-id="6c36d-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="6c36d-124">**Referens för medarbetarens löneavdrag**</span><span class="sxs-lookup"><span data-stu-id="6c36d-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="6c36d-125">Den avdragskod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="6c36d-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="6c36d-126">**Beloppsrubrik**</span><span class="sxs-lookup"><span data-stu-id="6c36d-126">**Amount heading**</span></span> | <span data-ttu-id="6c36d-127">Den rubrikkod från lönesystemet som det här avdragsbelopp använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="6c36d-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="6c36d-128">Detta används normalt när du använder en tredje parts löneleverantör.</span><span class="sxs-lookup"><span data-stu-id="6c36d-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="6c36d-129">**Kan radera**</span><span class="sxs-lookup"><span data-stu-id="6c36d-129">**Can delete**</span></span> | <span data-ttu-id="6c36d-130">Anger om ett exporterat värde från Dynamics 365 for Finance and Operations kan orsaka att värdet raderas i lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="6c36d-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="6c36d-131">**Sammankopplade kolumner**</span><span class="sxs-lookup"><span data-stu-id="6c36d-131">**Paired columns**</span></span> | <span data-ttu-id="6c36d-132">Anger om huvud- och avdragsbelopp i kopplade angränsande kolumner till lönesystemet ska exporteras.</span><span class="sxs-lookup"><span data-stu-id="6c36d-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="6c36d-133">**Ändringens giltighetsdatum**</span><span class="sxs-lookup"><span data-stu-id="6c36d-133">**Change effective date**</span></span> | <span data-ttu-id="6c36d-134">Det datum när ändringar i förmånsavdragen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="6c36d-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="6c36d-135">På detta datum ändrar systemet automatiskt avdraget av förmånen och uppdaterar alla förmånsplaner som associeras med detta avdrag, förutsatt att du kör en **uppdatering av ändring av avdrag**.</span><span class="sxs-lookup"><span data-stu-id="6c36d-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="6c36d-136">**Ändringen av avdrag har slutförts**</span><span class="sxs-lookup"><span data-stu-id="6c36d-136">**Deduction change completed**</span></span> | <span data-ttu-id="6c36d-137">Kryssrutan **Ändring av avdrag slutförd** kommer att markeras automatiskt när ändringen av förmånsavdrag har slutförts genom Bearbetning av uppdaterade prisändringar.</span><span class="sxs-lookup"><span data-stu-id="6c36d-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="6c36d-138">Om du vill spåra och underhålla ändringar i inställningarna för förmånsgrad **åtgärder** och välj sedan **underhåll versioner**.</span><span class="sxs-lookup"><span data-stu-id="6c36d-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="6c36d-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6c36d-139">Select **Save**.</span></span> 
