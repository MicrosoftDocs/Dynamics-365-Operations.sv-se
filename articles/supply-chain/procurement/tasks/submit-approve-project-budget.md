--- 
title: "Skicka och godkänn projektbudget"
description: "Den här proceduren visar hur du skapar och skickar in en budget för ett projekt."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: f727e19d3f8c424b1c59e52602b7e907151f4492
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="bd518-103">Skicka och godkänn projektbudget</span><span class="sxs-lookup"><span data-stu-id="bd518-103">Submit and approve project budget</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd518-104">Den här proceduren visar hur du skapar och skickar in en budget för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="bd518-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="bd518-105">När du skapar en projektbudget kan du ange uppskattade intäkter och kostnader för ett projekt, och sedan använda dem för att styra faktiska projekttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="bd518-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="bd518-106">Inom projektbudgetering måste alla ursprungliga budgetar och ändringar skickas till ett projektarbetsflöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="bd518-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="bd518-107">Arbetsflöden ger dig ökad kontroll över processerna och skapar en post för ändringshistorik.</span><span class="sxs-lookup"><span data-stu-id="bd518-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="bd518-108">Denna uppgift har skapats med USSI-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="bd518-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="bd518-109">Gå till Projekthantering och redovisning > Projekt > Alla projekt.</span><span class="sxs-lookup"><span data-stu-id="bd518-109">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="bd518-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bd518-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bd518-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bd518-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bd518-112">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bd518-112">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="bd518-113">Klicka på Projektbudget.</span><span class="sxs-lookup"><span data-stu-id="bd518-113">Click Project budget.</span></span>
6. <span data-ttu-id="bd518-114">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="bd518-114">In the Description field, type a value.</span></span>
7. <span data-ttu-id="bd518-115">Expandera avsnittet Kostnader</span><span class="sxs-lookup"><span data-stu-id="bd518-115">Expand the Cost section</span></span>
8. <span data-ttu-id="bd518-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bd518-116">Click New.</span></span>
9. <span data-ttu-id="bd518-117">Välj ett alternativ i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="bd518-117">In the Transaction type field, select an option.</span></span>
10. <span data-ttu-id="bd518-118">I fältet Kategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd518-118">In the Category field, enter or select a value.</span></span>
11. <span data-ttu-id="bd518-119">Ange ett nummer i fältet Ursprunglig budget.</span><span class="sxs-lookup"><span data-stu-id="bd518-119">In the Original budget field, enter a number.</span></span>
12. <span data-ttu-id="bd518-120">Expandera avsnittet Intäkter.</span><span class="sxs-lookup"><span data-stu-id="bd518-120">Expand the Revenues section.</span></span>
13. <span data-ttu-id="bd518-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bd518-121">Click New.</span></span>
14. <span data-ttu-id="bd518-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bd518-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="bd518-123">Välj ett alternativ i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="bd518-123">In the Transaction type field, select an option.</span></span>
16. <span data-ttu-id="bd518-124">I fältet Kategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd518-124">In the Category field, enter or select a value.</span></span>
17. <span data-ttu-id="bd518-125">Ange ett nummer i fältet Ursprunglig budget.</span><span class="sxs-lookup"><span data-stu-id="bd518-125">In the Original budget field, enter a number.</span></span>
18. <span data-ttu-id="bd518-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bd518-126">Click Save.</span></span>
19. <span data-ttu-id="bd518-127">Klicka på Arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="bd518-127">Click Workflow.</span></span>
20. <span data-ttu-id="bd518-128">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="bd518-128">Click Submit.</span></span>
21. <span data-ttu-id="bd518-129">Ange ett värde i fältet Kommentar.</span><span class="sxs-lookup"><span data-stu-id="bd518-129">In the Comment field, type a value.</span></span>
22. <span data-ttu-id="bd518-130">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="bd518-130">Click Submit.</span></span>


