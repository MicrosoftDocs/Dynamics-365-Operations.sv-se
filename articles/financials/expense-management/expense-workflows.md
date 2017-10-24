---
title: "Konfigurera arbetsflöden för utgifter"
description: "Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eb8ff11a03ba18b78595cd04f63b2456aec53bf2
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="77787-103">Konfigurera arbetsflöden för utgifter</span><span class="sxs-lookup"><span data-stu-id="77787-103">Set up workflows for expense</span></span>

[!include[banner](../includes/banner.md)]<span data-ttu-id="77787-104"> Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument.</span><span class="sxs-lookup"><span data-stu-id="77787-104"> You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="77787-105">De dokument för vilka arbetsflöden kan definieras inkluderar utgiftsrapporter, reserekvisitioner samt begäranden om förskott.</span><span class="sxs-lookup"><span data-stu-id="77787-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="77787-106">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="77787-106">A workflow represents a business process.</span></span> <span data-ttu-id="77787-107">Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="77787-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="77787-108">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="77787-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="77787-109">**Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="77787-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="77787-110">Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="77787-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="77787-111">Processerna blir synliga – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="77787-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="77787-112">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="77787-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="77787-113">Centraliserad arbetslista – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="77787-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="77787-114">**De typer av arbetsflöden du kan skapa**</span><span class="sxs-lookup"><span data-stu-id="77787-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="77787-115">Följande tabell listar de typer av arbetsflöden som du kan skapa under **Utgift**.</span><span class="sxs-lookup"><span data-stu-id="77787-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>

| <span data-ttu-id="77787-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="77787-116">**Type**</span></span>                           | <span data-ttu-id="77787-117">**Använd den här typen för att**</span><span class="sxs-lookup"><span data-stu-id="77787-117">**Use this type to**</span></span>                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| <span data-ttu-id="77787-118">**Utgiftsrapport**</span><span class="sxs-lookup"><span data-stu-id="77787-118">**Expense report**</span></span>                 | <span data-ttu-id="77787-119">Skapa arbetsflöden för godkännande av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="77787-119">Create approval workflows for expense reports.</span></span>                       |      
| <span data-ttu-id="77787-120">**Automatisk bokföring av utgiftsrapport**</span><span class="sxs-lookup"><span data-stu-id="77787-120">**Expense report auto posting**</span></span>    | <span data-ttu-id="77787-121">Skapa automatiska arbetsflöden för bokföring av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="77787-121">Create automatic posting workflows for expense reports.</span></span>              |     
| <span data-ttu-id="77787-122">**Utgiftsradartikel**</span><span class="sxs-lookup"><span data-stu-id="77787-122">**Expense line item**</span></span>              | <span data-ttu-id="77787-123">Skapa arbetsflöden för godkännande av radobjekt i utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="77787-123">Create approval workflows for line items on expense reports.</span></span>         |     
| <span data-ttu-id="77787-124">**Automatisk bokföring av utgiftsradartiklar**</span><span class="sxs-lookup"><span data-stu-id="77787-124">**Expense line item auto posting**</span></span> | <span data-ttu-id="77787-125">Skapa automatiska arbetsflöden för bokföring av radobjekt i utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="77787-125">Create automatic posting workflows for line items on expense reports.</span></span>|
| <span data-ttu-id="77787-126">**Reserekvisition**</span><span class="sxs-lookup"><span data-stu-id="77787-126">**Travel requisition**</span></span>             | <span data-ttu-id="77787-127">Skapa arbetsflöden för godkännande av reserekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="77787-127">Create approval workflows for travel requisitions.</span></span>                   |    
| <span data-ttu-id="77787-128">**Förskottsbegäran**</span><span class="sxs-lookup"><span data-stu-id="77787-128">**Cash advance request**</span></span>           | <span data-ttu-id="77787-129">Skapa arbetsflöden för godkännande av begäranden om förskott.</span><span class="sxs-lookup"><span data-stu-id="77787-129">Create approval workflows for cash advance requests.</span></span>                 |     
| <span data-ttu-id="77787-130">**Momsåterbetalning**</span><span class="sxs-lookup"><span data-stu-id="77787-130">**VAT tax recovery**</span></span>               | <span data-ttu-id="77787-131">Skapa arbetsflöden för godkännande av återbetalande av moms</span><span class="sxs-lookup"><span data-stu-id="77787-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span> |       

