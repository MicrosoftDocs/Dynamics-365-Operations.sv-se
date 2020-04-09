---
title: Ställ in arbetsflöden för utgiftshantering
description: Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd4d69cb86da12e4a265f89c021c238d00cad08
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154004"
---
# <a name="set-up-workflows-for-expense-management"></a><span data-ttu-id="39d47-103">Ställ in arbetsflöden för utgiftshantering</span><span class="sxs-lookup"><span data-stu-id="39d47-103">Set up workflows for Expense management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39d47-104">Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument.</span><span class="sxs-lookup"><span data-stu-id="39d47-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="39d47-105">De dokument för vilka arbetsflöden kan definieras inkluderar utgiftsrapporter, reserekvisitioner samt begäranden om förskott.</span><span class="sxs-lookup"><span data-stu-id="39d47-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="39d47-106">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="39d47-106">A workflow represents a business process.</span></span> <span data-ttu-id="39d47-107">Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="39d47-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="39d47-108">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="39d47-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="39d47-109">**Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="39d47-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="39d47-110">Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="39d47-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="39d47-111">Processerna blir synliga – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="39d47-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="39d47-112">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="39d47-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="39d47-113">Centraliserad arbetslista – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="39d47-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="39d47-114">**De typer av arbetsflöden du kan skapa**</span><span class="sxs-lookup"><span data-stu-id="39d47-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="39d47-115">Följande tabell listar de typer av arbetsflöden som du kan skapa under **Utgift**.</span><span class="sxs-lookup"><span data-stu-id="39d47-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="39d47-116"><strong>Typ</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="39d47-117"><strong>Använd den här typen för att</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="39d47-118"><strong>Utgiftsrapport</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="39d47-119">Skapa arbetsflöden för godkännande av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="39d47-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="39d47-120"><strong>Automatisk bokföring av utgiftsrapport</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="39d47-121">Skapa automatiska arbetsflöden för bokföring av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="39d47-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="39d47-122"><strong>Utgiftsradartikel</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="39d47-123">Skapa arbetsflöden för godkännande av radobjekt i utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="39d47-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="39d47-124"><strong>Automatisk bokföring av utgiftsradartiklar</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="39d47-125">Skapa automatiska arbetsflöden för bokföring av radobjekt i utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="39d47-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="39d47-126"><strong>Reserekvisition</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="39d47-127">Skapa arbetsflöden för godkännande av reserekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="39d47-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="39d47-128"><strong>Förskottsbegäran</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="39d47-129">Skapa arbetsflöden för godkännande av begäranden om förskott.</span><span class="sxs-lookup"><span data-stu-id="39d47-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="39d47-130"><strong>Momsåterbetalning</strong></span><span class="sxs-lookup"><span data-stu-id="39d47-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="39d47-131">Skapa arbetsflöden för godkännande av återbetalande av moms</span><span class="sxs-lookup"><span data-stu-id="39d47-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

