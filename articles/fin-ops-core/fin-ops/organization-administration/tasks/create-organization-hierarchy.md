---
title: Skapa en organisationshierarki.
description: Använd följande procedur för att skapa en organisationshierarki.
author: sericks007
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dde06f758be57fb646696c861218565476abcadc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140569"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="1ce33-103">Skapa en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1ce33-103">Create an organization hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ce33-104">Använd följande procedur för att skapa en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1ce33-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="1ce33-105">Du kan använda organisationens hierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="1ce33-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="1ce33-106">Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering.</span><span class="sxs-lookup"><span data-stu-id="1ce33-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="1ce33-107">Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering.</span><span class="sxs-lookup"><span data-stu-id="1ce33-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="1ce33-108">Innan du skapar en organisationshierarki måste du skapa organisationer.</span><span class="sxs-lookup"><span data-stu-id="1ce33-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="1ce33-109">Mer information finns i uppgifterna "Skapa en juridisk person” eller ”Skapa en driftenhet”.</span><span class="sxs-lookup"><span data-stu-id="1ce33-109">For more information, see the "Create a legal entity" or "Create an operating unit" tasks.</span></span> <span data-ttu-id="1ce33-110">Du kan också skapa avdelningar och team.</span><span class="sxs-lookup"><span data-stu-id="1ce33-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="1ce33-111">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="1ce33-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="1ce33-112">Skapa en hierarki</span><span class="sxs-lookup"><span data-stu-id="1ce33-112">Create a hierarchy</span></span>
1. <span data-ttu-id="1ce33-113">Gå till **Navigeringsfönster > Moduler > Organisationsadministration > Organisationer > Organisationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="1ce33-114">Klicka på **Nytt** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="1ce33-115">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="1ce33-116">I avsnittet **Syfte**, klicka på **Tilldela syfte**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="1ce33-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1ce33-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="1ce33-118">Välj ett syfte att tilldela till din organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1ce33-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="1ce33-119">Klicka på **Lägg till** i avsnittet **Tilldelade hierarkier**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-119">In the **Assigned hierarchies** sectiom, click **Add**.</span></span>
7. <span data-ttu-id="1ce33-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1ce33-120">In the list, mark the selected row.</span></span> <span data-ttu-id="1ce33-121">Hitta hierarki som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="1ce33-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="1ce33-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="1ce33-123">Lägg till organisationer i hierarkin</span><span class="sxs-lookup"><span data-stu-id="1ce33-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="1ce33-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1ce33-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="1ce33-125">Välj hierarki.</span><span class="sxs-lookup"><span data-stu-id="1ce33-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="1ce33-126">Klicka på **Visa hierarki** i avsnittet **Tilldelade hierarkier**.</span><span class="sxs-lookup"><span data-stu-id="1ce33-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="1ce33-127">Lägg till fler organisationer efter behov.</span><span class="sxs-lookup"><span data-stu-id="1ce33-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="1ce33-128">Klicka på **Redigera** och sedan **Infoga** om du vill lägga till en organisation.</span><span class="sxs-lookup"><span data-stu-id="1ce33-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="1ce33-129">När du är klar med ändringar, kan du **spara** ett utkast och/eller **publicera** ändringarna.</span><span class="sxs-lookup"><span data-stu-id="1ce33-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  

