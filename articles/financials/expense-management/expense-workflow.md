---
title: "Arbetsflöde för utgifter"
description: "Detta avsnitt förklarar hur du kan använda arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d60d2f462a1fd27d4655e68aab7f96fb28a34b77
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="expense-workflow"></a><span data-ttu-id="42af5-103">Arbetsflöde för utgifter</span><span class="sxs-lookup"><span data-stu-id="42af5-103">Expense workflow</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="42af5-104">Du kan använda arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren.</span><span class="sxs-lookup"><span data-stu-id="42af5-104">You can use the workflow system in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="42af5-105">Du kan skapa ett arbetsflöde som utnyttjar följande kriterier i syfte att avgöra vem som får godkänna utgiftsrapporter:</span><span class="sxs-lookup"><span data-stu-id="42af5-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="42af5-106">Rapporteringshierarki och fördefinierade godkännandenivåer för medarbetare</span><span class="sxs-lookup"><span data-stu-id="42af5-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="42af5-107">Godkännande på flera nivåer som stöder provisoriska godkännare samt en slutgiltig godkännare</span><span class="sxs-lookup"><span data-stu-id="42af5-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="42af5-108">Finansiella dimensioner och projektansvar</span><span class="sxs-lookup"><span data-stu-id="42af5-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="42af5-109">Tilldelning till specifika användare eller användargrupper</span><span class="sxs-lookup"><span data-stu-id="42af5-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="42af5-110">Godkännanden av arbetsflöden kan skapas för utgiftsrapporter, reserekvisitioner, förskott samt återkrävande av moms.</span><span class="sxs-lookup"><span data-stu-id="42af5-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="42af5-111">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="42af5-111">**Example**</span></span>

<span data-ttu-id="42af5-112">Följande process är ett exempel på arbetsflödet för utgiftshantering för en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="42af5-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="42af5-113">En medarbetare skapar och sparar en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="42af5-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="42af5-114">Medarbetaren skickar in utgiftsrapporten för godkännande.</span><span class="sxs-lookup"><span data-stu-id="42af5-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="42af5-115">Godkännaren identifieras baserat på de regler som angetts när arbetsflödet skapades.</span><span class="sxs-lookup"><span data-stu-id="42af5-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="42af5-116">Godkännaren får ett meddelande om att en utgiftsrapport är redo för godkännande.</span><span class="sxs-lookup"><span data-stu-id="42af5-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="42af5-117">Godkännaren granskar utgiftsrapporten och bekräftar att följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="42af5-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="42af5-118">Utgifterna bryter inte mot någon utgiftspolicy,</span><span class="sxs-lookup"><span data-stu-id="42af5-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="42af5-119">Om en utgift bryter mot någon policy, bekräftar godkännaren att utgiftsrapporten innehåller en giltig affärsmotivering.</span><span class="sxs-lookup"><span data-stu-id="42af5-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="42af5-120">Elektroniska kvitton bifogas till utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="42af5-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="42af5-121">Godkännaren godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="42af5-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="42af5-122">Utgiftsrapporten tilldelas till godkännaren för leverantörsreskontra för bokföring.</span><span class="sxs-lookup"><span data-stu-id="42af5-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="42af5-123">Beroende på om automatisk bokföring har ställts in eller inte, uppstår något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="42af5-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="42af5-124">Om automatisk bokföring har konfigurerats kommer utgiftsrapportern att behandlas för betalning, och utgiftsrapportens status uppdateras.</span><span class="sxs-lookup"><span data-stu-id="42af5-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="42af5-125">Om automatisk bokföring inte har konfigurerats, bekräftar koordinatorn för leverantörsreskontra att samtliga originalkvitton har lämnats in, samt att kvittona motsvarar utgifterna i utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="42af5-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="42af5-126">Samtliga momskoder som anges på utgiftsrapporten måste också bekräftas vara korrekta.</span><span class="sxs-lookup"><span data-stu-id="42af5-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="42af5-127">När dessa krav har bekräftats bokförs utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="42af5-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="42af5-128">När utgiftsrapporten har bokförts godkänns utbetalning för utgiftsrapporten, och medarbetaren får sin ersättning.</span><span class="sxs-lookup"><span data-stu-id="42af5-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>

