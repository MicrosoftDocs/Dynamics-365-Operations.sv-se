---
title: Skicka och godkänn projektbudget
description: Den här proceduren visar hur du skapar och skickar in en budget för ett projekt.
author: mkirknel
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14683554c45db72061ecbbf4a528656df3132692
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207467"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="ed50e-103">Skicka och godkänn projektbudget</span><span class="sxs-lookup"><span data-stu-id="ed50e-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ed50e-104">Den här proceduren visar hur du skapar och skickar in en budget för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="ed50e-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="ed50e-105">När du skapar en projektbudget kan du ange uppskattade intäkter och kostnader för ett projekt, och sedan använda dem för att styra faktiska projekttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ed50e-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="ed50e-106">Inom projektbudgetering måste alla ursprungliga budgetar och ändringar skickas till ett projektarbetsflöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="ed50e-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="ed50e-107">Arbetsflöden ger dig ökad kontroll över processerna och skapar en post för ändringshistorik.</span><span class="sxs-lookup"><span data-stu-id="ed50e-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="ed50e-108">Denna uppgift har skapats med USSI-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="ed50e-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="ed50e-109">I **navigeringsfönstret**, gå till  **Moduler > Projekthantering och redovisning > Projekt > Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="ed50e-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ed50e-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ed50e-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ed50e-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ed50e-112">Klicka på **Plan** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="ed50e-113">Klicka på **Projektbudget**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="ed50e-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ed50e-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="ed50e-115">Expandera snabbfliken **Kostnad**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="ed50e-116">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-116">Click **New**.</span></span>
9. <span data-ttu-id="ed50e-117">Välj ett alternativ i fältet **Transaktionstyp**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="ed50e-118">I fältet **Kategori**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ed50e-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="ed50e-119">Ange ett nummer i fältet **Ursprunglig budget**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="ed50e-120">Expandera snabbfliken **Intäkter**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="ed50e-121">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-121">Click **New**.</span></span>
14. <span data-ttu-id="ed50e-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ed50e-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="ed50e-123">Välj ett alternativ i fältet **Transaktionstyp**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="ed50e-124">I fältet **Kategori**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ed50e-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="ed50e-125">Ange ett nummer i fältet **Ursprunglig budget**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="ed50e-126">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-126">Click **Save**.</span></span>
19. <span data-ttu-id="ed50e-127">Klicka på **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="ed50e-128">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-128">Click **Submit**.</span></span>
21. <span data-ttu-id="ed50e-129">Ange ett värde i fältet **Kommentar**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="ed50e-130">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="ed50e-130">Click **Submit**.</span></span>

