---
title: Utgiftsrapporter och flera granskare
description: "Det här avsnittet innehåller information om utgiftsrapporter som kräver godkännande av flera personer."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 0f7592c580a21040c8b630885939ceaab3855c2c
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="8a051-103">Utgiftsrapporter och flera granskare</span><span class="sxs-lookup"><span data-stu-id="8a051-103">Expense reports and multiple approvers</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8a051-104">Beroende på företagets policy för godkännande av projektutgifter kanske mer än en person måste godkänna utgiftsrapporter som har skickats av en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="8a051-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="8a051-105">När du anger arbetsflödesprocessen för godkännande av utgiftsrapport kan du lägga till arbetsflödeselement som inkluderar uppgifter eller steg för en eller flera godkännare av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="8a051-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="8a051-106">Du kan till exempel kräva att alla utgiftsrapporter först godkänns av chefen för medarbetaren som skickade rapporten och av sedan leverantörsreskontrakoordinatorn.</span><span class="sxs-lookup"><span data-stu-id="8a051-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="8a051-107">Om du bestämmer dig för att kräva flera godkännare av utgiftsrapporter kan du lägga till olika arbetsflödeselement på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="8a051-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="8a051-108">Lägg till ett godkännandeelement som har ett steg.</span><span class="sxs-lookup"><span data-stu-id="8a051-108">Add one approval element that has one step.</span></span> <span data-ttu-id="8a051-109">Steget kan till exempel kräva att en utgiftsrapport tilldelas en användargrupp och att den godkänns av 50 procent av medlemmarna i användargruppen.</span><span class="sxs-lookup"><span data-stu-id="8a051-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="8a051-110">Lägg till ett godkännandeelement som har flera steg.</span><span class="sxs-lookup"><span data-stu-id="8a051-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="8a051-111">Godkännandeelementet kan till exempel ha följande steg:</span><span class="sxs-lookup"><span data-stu-id="8a051-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="8a051-112">Chefen för medarbetarens som skickade utgiftsrapporten godkänner den.</span><span class="sxs-lookup"><span data-stu-id="8a051-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="8a051-113">Leverantörsreskontraansvarig verifierar kvitton och rapportens utgiftsposter.</span><span class="sxs-lookup"><span data-stu-id="8a051-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="8a051-114">Budgetägaren godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8a051-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="8a051-115">Lägg till flera godkännandeelement, var och en har ett steg.</span><span class="sxs-lookup"><span data-stu-id="8a051-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="8a051-116">Till exempel kan du lägga till ett separat godkännandeelement för var och ett av följande steg:</span><span class="sxs-lookup"><span data-stu-id="8a051-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="8a051-117">Medarbetarens chef godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8a051-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="8a051-118">Budgetägaren godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8a051-118">The budget owner approves the expense report.</span></span>

