---
title: Konfigurera avdrag
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010620"
---
# <a name="configure-deductions"></a><span data-ttu-id="9bb66-102">Konfigurera avdrag</span><span class="sxs-lookup"><span data-stu-id="9bb66-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="9bb66-103">Använd avdrag i Microsoft Dynamics 365 Human Resources för att fastställa hur mycket, om det finns någon, dra av från en medarbetares lön för varje förmån.</span><span class="sxs-lookup"><span data-stu-id="9bb66-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="9bb66-104">Avdrag har giltighetsdatum så att du kan spara en historisk post med avdragsinformation.</span><span class="sxs-lookup"><span data-stu-id="9bb66-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="9bb66-105">I arbetsytan **Förmånshantering** under **inställningar**, välj **avdrag**.</span><span class="sxs-lookup"><span data-stu-id="9bb66-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="9bb66-106">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9bb66-106">Select **New**.</span></span>

3. <span data-ttu-id="9bb66-107">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="9bb66-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="9bb66-108">Fält</span><span class="sxs-lookup"><span data-stu-id="9bb66-108">Field</span></span> | <span data-ttu-id="9bb66-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9bb66-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9bb66-110">Avdrag</span><span class="sxs-lookup"><span data-stu-id="9bb66-110">Deduction</span></span> | <span data-ttu-id="9bb66-111">Ett unikt ID som används för att identifiera förmånsavdrag.</span><span class="sxs-lookup"><span data-stu-id="9bb66-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="9bb66-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9bb66-112">Description</span></span> | <span data-ttu-id="9bb66-113">En beskrivning för avdraget.</span><span class="sxs-lookup"><span data-stu-id="9bb66-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="9bb66-114">Giltighet</span><span class="sxs-lookup"><span data-stu-id="9bb66-114">Effective</span></span> | <span data-ttu-id="9bb66-115">Startdatumet.</span><span class="sxs-lookup"><span data-stu-id="9bb66-115">The start date.</span></span> <span data-ttu-id="9bb66-116">Standardvärdet är det aktuella systemdatumet.</span><span class="sxs-lookup"><span data-stu-id="9bb66-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="9bb66-117">Förfallotid</span><span class="sxs-lookup"><span data-stu-id="9bb66-117">Expiration</span></span> | <span data-ttu-id="9bb66-118">Slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="9bb66-118">The end date.</span></span> <span data-ttu-id="9bb66-119">Standardvärdet är 12/31/2154, vilket betyder aldrig.</span><span class="sxs-lookup"><span data-stu-id="9bb66-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="9bb66-120">Rubrik</span><span class="sxs-lookup"><span data-stu-id="9bb66-120">Heading</span></span> | <span data-ttu-id="9bb66-121">Den rubrikkod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="9bb66-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="9bb66-122">Detta används när du använder en tredje parts löneleverantör.</span><span class="sxs-lookup"><span data-stu-id="9bb66-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="9bb66-123">Referens för medarbetarens löneavdrag</span><span class="sxs-lookup"><span data-stu-id="9bb66-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="9bb66-124">Den avdragskod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="9bb66-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="9bb66-125">Beloppsrubrik</span><span class="sxs-lookup"><span data-stu-id="9bb66-125">Amount heading</span></span> | <span data-ttu-id="9bb66-126">Den rubrikkod från lönesystemet som det här avdragsbelopp använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning.</span><span class="sxs-lookup"><span data-stu-id="9bb66-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="9bb66-127">Detta används normalt när du använder en tredje parts löneleverantör.</span><span class="sxs-lookup"><span data-stu-id="9bb66-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="9bb66-128">Kan radera</span><span class="sxs-lookup"><span data-stu-id="9bb66-128">Can delete</span></span> | <span data-ttu-id="9bb66-129">Anger om ett exporterat värde från Dynamics 365 for Finance and Operations kan orsaka att värdet raderas i lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="9bb66-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="9bb66-130">Sammankopplade kolumner</span><span class="sxs-lookup"><span data-stu-id="9bb66-130">Paired columns</span></span> | <span data-ttu-id="9bb66-131">Anger om huvud- och avdragsbelopp i kopplade angränsande kolumner till lönesystemet ska exporteras.</span><span class="sxs-lookup"><span data-stu-id="9bb66-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="9bb66-132">Ändringens giltighetsdatum</span><span class="sxs-lookup"><span data-stu-id="9bb66-132">Change effective date</span></span> | <span data-ttu-id="9bb66-133">Det datum när ändringar i förmånsavdragen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="9bb66-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="9bb66-134">På detta datum ändrar systemet automatiskt avdraget av förmånen och uppdaterar alla förmånsplaner som associeras med detta avdrag, förutsatt att du kör en ändring av uppdateringsprocessen för avdragsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9bb66-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="9bb66-135">Ändringen av avdrag har slutförts</span><span class="sxs-lookup"><span data-stu-id="9bb66-135">Deduction change completed</span></span> | <span data-ttu-id="9bb66-136">Kryssrutan Ändring av avdrag kommer att markeras automatiskt när ändringen av förmånsavdrag har slutförts genom Bearbetning av uppdaterade prisändringar.</span><span class="sxs-lookup"><span data-stu-id="9bb66-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="9bb66-137">Om du vill spåra och underhålla ändringar i inställningarna för förmånsgrad **åtgärder** och välj sedan **underhåll versioner**.</span><span class="sxs-lookup"><span data-stu-id="9bb66-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="9bb66-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bb66-138">Select **Save**.</span></span> 
