---
title: Visa arbetsflödeshistorik
description: Det här avsnittet beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 325478ed89b9c650899001dd08d1c98550fce520
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798990"
---
# <a name="view-workflow-history"></a><span data-ttu-id="5565a-103">Visa arbetsflödeshistorik</span><span class="sxs-lookup"><span data-stu-id="5565a-103">View workflow history</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5565a-104">Det här avsnittet beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="5565a-104">This topic describes the steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="5565a-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5565a-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="5565a-106">Gå till **Navigeringsfönstret > Moduler > Allmänt > Förfrågningar > Arbetsflöde > Arbetsflödeshistorik**.</span><span class="sxs-lookup"><span data-stu-id="5565a-106">Go to **Navigation pane > Modules > Common > Inquiries > Workflow > Workflow history**.</span></span>
    - <span data-ttu-id="5565a-107">Använd det här formuläret för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="5565a-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    - <span data-ttu-id="5565a-108">**Instans-ID** är identifieringskoden för det arbetsflödesinstansen där dokumentet bearbetas eller har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="5565a-108">The **Instance ID** is the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="5565a-109">**Statusen** utgörs av dokumentets arbetsflödestatus.</span><span class="sxs-lookup"><span data-stu-id="5565a-109">The **Status** is the workflow status of the document.</span></span>  
    - <span data-ttu-id="5565a-110">**ID för arbetsflöde** är identifieringskoden för det arbetsflöde där dokumentet bearbetas eller har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="5565a-110">The **Workflow ID** is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="5565a-111">**Dokumentet** är dokumentets identifieringskod.</span><span class="sxs-lookup"><span data-stu-id="5565a-111">The **Document** is the identification code of the document.</span></span>  
    - <span data-ttu-id="5565a-112">**Dokumenttypen** är den typ av dokument som har skickats in för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="5565a-112">The **Document type** is the type of document that was submitted for processing.</span></span>  
    - <span data-ttu-id="5565a-113">**Arbetsflödet** är namnet på det arbetsflöde där dokumenten bearbetas eller har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="5565a-113">The **Workflow** is the name of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="5565a-114">**Versionen** är versionsnumret på det arbetsflöde där dokumentet bearbetas eller har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="5565a-114">The **Version** is the version number of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="5565a-115">**Skapat datum och tid** är det datum och den tidpunkt då dokumentet skickades.</span><span class="sxs-lookup"><span data-stu-id="5565a-115">The **Created date and time** is the date and time that the document was submitted.</span></span>  
    - <span data-ttu-id="5565a-116">**Förfluten tid** är den tid som har förflutit sedan dokumentet skickades.</span><span class="sxs-lookup"><span data-stu-id="5565a-116">The **Elapsed time** is the time that has passed since the document was submitted.</span></span>  
    - <span data-ttu-id="5565a-117">Knappen **Återuppta** låter dig fortsätta arbetsflödesprocessen för det valda dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5565a-117">The **Resume** button allows you to resume the workflow process for the selected document.</span></span>  
    - <span data-ttu-id="5565a-118">Med knappen **Återkalla** kan du återkalla det markerade dokumentet så att det inte behandlas.</span><span class="sxs-lookup"><span data-stu-id="5565a-118">The **Recall** button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="5565a-119">Klicka på länken på önskad rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5565a-119">In the list, select the link in the desired row.</span></span>
    - <span data-ttu-id="5565a-120">Kontrollera att avsnittet för **Arbetsuppgifter** expanderas.</span><span class="sxs-lookup"><span data-stu-id="5565a-120">Make sure the **Work items** section is expanded.</span></span> <span data-ttu-id="5565a-121">I det här avsnittet kan du visa arbetsuppgifter som är kopplade till det valda dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5565a-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="5565a-122">En uppgift kan till exempel behöva slutföras, eller också kanske dokumentet måste godkännas.</span><span class="sxs-lookup"><span data-stu-id="5565a-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    - <span data-ttu-id="5565a-123">Knappen **Tilldela om** öppnar en dialogruta där du kan tilldela en arbetsuppgift till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="5565a-123">The **Reassign** button will open a dialog box where you can reassign a work item to another user.</span></span>  
    - <span data-ttu-id="5565a-124">Kontrollera att avsnittet **Spårningsuppgifter** expanderas.</span><span class="sxs-lookup"><span data-stu-id="5565a-124">Make sure the **Tracking details** section is expanded.</span></span> <span data-ttu-id="5565a-125">I det här avsnittet kan du visa arbetsflödeshistoriken för det valda dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5565a-125">In this section you can view the workflow history of the selected document.</span></span>  

