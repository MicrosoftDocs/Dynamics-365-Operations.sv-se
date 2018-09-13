--- 
title: Skapa en organisationshierarki.
description: "Använd följande procedur för att skapa en organisationshierarki."
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: abd59b96a2e5dceb2492c2db2c617485b332fbd3
ms.openlocfilehash: 203a586b06a13a7c67f246384152d17627e22041
ms.contentlocale: sv-se
ms.lasthandoff: 09/13/2018

---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="bfbd0-103">Skapa en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-103">Create an organization hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bfbd0-104">Använd följande procedur för att skapa en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="bfbd0-105">Du kan använda organisationens hierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="bfbd0-106">Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="bfbd0-107">Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 



<span data-ttu-id="bfbd0-108">Innan du skapar en organisationshierarki måste du skapa organisationer.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="bfbd0-109">Mer information finns i uppgifterna "Skapa en juridisk person” eller ”Skapa en driftenhet”.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-109">For more information, see the “Create a legal entity” or “Create an operating unit” tasks.</span></span> <span data-ttu-id="bfbd0-110">Du kan också skapa avdelningar och team.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-110">You can also create departments and teams.</span></span> 



<span data-ttu-id="bfbd0-111">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-111">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-hierarchy"></a><span data-ttu-id="bfbd0-112">Skapa en hierarki</span><span class="sxs-lookup"><span data-stu-id="bfbd0-112">Create a hierarchy</span></span>
1. <span data-ttu-id="bfbd0-113">Gå till Organisationsadministration > Organisationer > Organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-113">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
2. <span data-ttu-id="bfbd0-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-114">Click New.</span></span>
3. <span data-ttu-id="bfbd0-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-115">In the Name field, type a value.</span></span>
4. <span data-ttu-id="bfbd0-116">Klicka på Tilldela syfte.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-116">Click Assign purpose.</span></span>
5. <span data-ttu-id="bfbd0-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bfbd0-118">Välj ett syfte att tilldela till din organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="bfbd0-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-119">Click Add.</span></span>
7. <span data-ttu-id="bfbd0-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bfbd0-121">Hitta hierarki som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="bfbd0-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-122">Click OK.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="bfbd0-123">Lägg till organisationer i hierarkin</span><span class="sxs-lookup"><span data-stu-id="bfbd0-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="bfbd0-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-124">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bfbd0-125">Välj hierarki.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="bfbd0-126">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="bfbd0-126">Click View hierarchy.</span></span>
    * <span data-ttu-id="bfbd0-127">Lägg till fler organisationer efter behov.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-127">Add organizations, as necessary.</span></span>  
    * <span data-ttu-id="bfbd0-128">Klicka på Redigera och sedan Sätt in om du vill lägga till en organisation.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-128">To add an organization, click Edit and then Insert to add the organization.</span></span>     <span data-ttu-id="bfbd0-129">När du är klar med ändringar, kan du spara ett utkast och/eller publicera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="bfbd0-129">When you are done making changes you can save a draft and/or publish the changes.</span></span>  


