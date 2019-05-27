---
title: Utgiftsrapporter och flera granskare
description: Det här avsnittet innehåller information om utgiftsrapporter som kräver godkännande av flera personer.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1483de5405895d60f0cb302ab622758b2b05d2ca
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566994"
---
# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="8ceb9-103">Utgiftsrapporter och flera granskare</span><span class="sxs-lookup"><span data-stu-id="8ceb9-103">Expense reports and multiple approvers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ceb9-104">Beroende på företagets policy för godkännande av projektutgifter kanske mer än en person måste godkänna utgiftsrapporter som har skickats av en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="8ceb9-105">När du anger arbetsflödesprocessen för godkännande av utgiftsrapport kan du lägga till arbetsflödeselement som inkluderar uppgifter eller steg för en eller flera godkännare av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="8ceb9-106">Du kan till exempel kräva att alla utgiftsrapporter först godkänns av chefen för medarbetaren som skickade rapporten och av sedan leverantörsreskontrakoordinatorn.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="8ceb9-107">Om du bestämmer dig för att kräva flera godkännare av utgiftsrapporter kan du lägga till olika arbetsflödeselement på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="8ceb9-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="8ceb9-108">Lägg till ett godkännandeelement som har ett steg.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-108">Add one approval element that has one step.</span></span> <span data-ttu-id="8ceb9-109">Steget kan till exempel kräva att en utgiftsrapport tilldelas en användargrupp och att den godkänns av 50 procent av medlemmarna i användargruppen.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="8ceb9-110">Lägg till ett godkännandeelement som har flera steg.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="8ceb9-111">Godkännandeelementet kan till exempel ha följande steg:</span><span class="sxs-lookup"><span data-stu-id="8ceb9-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="8ceb9-112">Chefen för medarbetarens som skickade utgiftsrapporten godkänner den.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="8ceb9-113">Leverantörsreskontraansvarig verifierar kvitton och rapportens utgiftsposter.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="8ceb9-114">Budgetägaren godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="8ceb9-115">Lägg till flera godkännandeelement, var och en har ett steg.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="8ceb9-116">Till exempel kan du lägga till ett separat godkännandeelement för var och ett av följande steg:</span><span class="sxs-lookup"><span data-stu-id="8ceb9-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="8ceb9-117">Medarbetarens chef godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="8ceb9-118">Budgetägaren godkänner utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="8ceb9-118">The budget owner approves the expense report.</span></span>
