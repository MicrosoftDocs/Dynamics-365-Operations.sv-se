---
title: Konfigurera arbetsflöden för leasinggodkännande
description: I det här ämnet beskrivs hur du konfigurerar ett godkännandearbetsflöde som ska köras när en ny leasing skapas.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e7280bbf60901266c81a0c89395c5183f991425
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881672"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="a59d7-103">Konfigurera arbetsflöden för leasinggodkännande</span><span class="sxs-lookup"><span data-stu-id="a59d7-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a59d7-104">I det här ämnet beskrivs hur du konfigurerar ett godkännandearbetsflöde som ska köras när en ny leasing skapas.</span><span class="sxs-lookup"><span data-stu-id="a59d7-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="a59d7-105">Mer information om hur du använder arbetsflödet finns i [Använda arbetsflöden för leasinggodkännande](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="a59d7-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="a59d7-106">Gå till **Leasing av tillgångar \> Konfigurera \> Leasingarbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="a59d7-107">Välj **Nytt** på sidan **Leasingarbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="a59d7-108">I dialogrutan som visas, **Arbetsflödestyp**, väljer du länken **Leasingarbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="a59d7-109">Programmet öppnas.</span><span class="sxs-lookup"><span data-stu-id="a59d7-109">The application is opened.</span></span> <span data-ttu-id="a59d7-110">När det har körts, logga in på Azure Active Directory (Azure AD) för att omdirigeras till arbetsflödesprogrammet.</span><span class="sxs-lookup"><span data-stu-id="a59d7-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="a59d7-111">Dra elementet **Arbetsflödesgodkännande av leasing** till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="a59d7-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="a59d7-112">Anslut en nod från **Start** till **Arbetsflödesgodkännande av leasing**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="a59d7-113">Anslut sedan **Arbetsflödesgodkännande av leasing** till **Slut**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="a59d7-114">Dubbelklicka på **Arbetsflödesgodkännande av leasing**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="a59d7-115">Välj **Egenskaper** och ange ett namn på arbetsflödet under **Grundinställningar**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="a59d7-116">På den här sidan kan du också konfigurera fler parametrar för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="a59d7-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="a59d7-117">Om du har aktiverat **Automatiska åtgärder** kommer systemet automatiskt att vidta en särskild åtgärd.</span><span class="sxs-lookup"><span data-stu-id="a59d7-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="a59d7-118">Meddelanden kan skickas om de har angetts på fliken **Meddelanden**. På fliken **Avancerade inställningar** kan du ange en slutlig godkännare, ange en tidsgräns och ange specifika åtgärder som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="a59d7-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="a59d7-119">Välj **Stäng** när du är klar med att ange arbetsflödesparametrarna.</span><span class="sxs-lookup"><span data-stu-id="a59d7-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="a59d7-120">Välj **Steg 1** och sedan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="a59d7-121">Under **Grundinställningar** anger du ett namn på steget, skapar en ämnesrad för godkännandet och anger sedan instruktioner för godkännandet.</span><span class="sxs-lookup"><span data-stu-id="a59d7-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="a59d7-122">Välj en tilldelningstyp på sidan **Tilldelning**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="a59d7-123">Om du vill tilldela specifika användare till godkännandet väljer du **Användare**, väljer de användare som godkänner leasingar och väljer sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="a59d7-124">Välj **Spara och stäng** för att skapa arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="a59d7-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="a59d7-125">Välj sedan **OK** när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="a59d7-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="a59d7-126">Välj **Stäng** på sidan **Skapa arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="a59d7-127">Välj det nya arbetsflödet och välj sedan **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="a59d7-128">Välj sedan **Aktivera** för att säkerställa att arbetsflödet är aktivt.</span><span class="sxs-lookup"><span data-stu-id="a59d7-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="a59d7-129">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="a59d7-129">Select **Close**.</span></span> <span data-ttu-id="a59d7-130">Den nya aktiva versionen visas.</span><span class="sxs-lookup"><span data-stu-id="a59d7-130">The new active version appears.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
