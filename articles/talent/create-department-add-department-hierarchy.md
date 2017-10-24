---
title: Skapa en avdelning och associera den med avdelningens hierarki
description: "En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adf3dbf8b7ffa906c872a6b66d9cb43eb8e02805
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a><span data-ttu-id="77f8a-106">Skapa en avdelning och associera den med avdelningens hierarki</span><span class="sxs-lookup"><span data-stu-id="77f8a-106">Create a department and associate it with the department hierarchy</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="77f8a-107">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="77f8a-107">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="77f8a-108">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="77f8a-108">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="77f8a-109">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="77f8a-109">You can use departments to report on functional areas.</span></span> <span data-ttu-id="77f8a-110">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="77f8a-110">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="77f8a-111">En avdelning kan omfatta en grupp kostnadsställen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-111">A department might include a group of cost centers.</span></span> <span data-ttu-id="77f8a-112">Positionerna kan tilldelas avdelningar.</span><span class="sxs-lookup"><span data-stu-id="77f8a-112">Positions can be assigned to departments.</span></span> <span data-ttu-id="77f8a-113">Klicka på **Personal** &gt; **Avdelningar** &gt; **Avdelning**.</span><span class="sxs-lookup"><span data-stu-id="77f8a-113">To create a department, click **Human Resources** &gt; **Departments** &gt; **Department**.</span></span> <span data-ttu-id="77f8a-114">Följande register beskriver de fält som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="77f8a-114">The following table describes the fields that are available.</span></span>

| <span data-ttu-id="77f8a-115">Fält</span><span class="sxs-lookup"><span data-stu-id="77f8a-115">Field</span></span>               | <span data-ttu-id="77f8a-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="77f8a-116">Description</span></span>                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="77f8a-117">Namn</span><span class="sxs-lookup"><span data-stu-id="77f8a-117">Name</span></span>                | <span data-ttu-id="77f8a-118">Ange ett namn på avdelningen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-118">Enter a name for the department.</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="77f8a-119">Avdelningsnummer</span><span class="sxs-lookup"><span data-stu-id="77f8a-119">Department number</span></span>   | <span data-ttu-id="77f8a-120">Ett standardvärde kan genereras automatiskt om en nummersekvens kod tilldelas **organisationsnummer** hänvisning på **nummersekvens** sida.</span><span class="sxs-lookup"><span data-stu-id="77f8a-120">A default value might be generated automatically if a number sequence code is assigned to the **Organization number** reference on the **Number sequences** page.</span></span>                                                 |
| <span data-ttu-id="77f8a-121">Söknamn</span><span class="sxs-lookup"><span data-stu-id="77f8a-121">Search name</span></span>         | <span data-ttu-id="77f8a-122">Ange ett namn eller en förkortning som kan användas för sökning för avdelningen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-122">Enter a name or acronym that can be used to search for the department.</span></span>                                                                                                                                            |
| <span data-ttu-id="77f8a-123">Anteckning</span><span class="sxs-lookup"><span data-stu-id="77f8a-123">Memo</span></span>                | <span data-ttu-id="77f8a-124">Ange eventuellt ytterligare information här.</span><span class="sxs-lookup"><span data-stu-id="77f8a-124">Enter any additional information here.</span></span>                                                                                                                                                                            |
| <span data-ttu-id="77f8a-125">I hierarki</span><span class="sxs-lookup"><span data-stu-id="77f8a-125">In hierarchy</span></span>        | <span data-ttu-id="77f8a-126">En vald kryssruta anger att avdelningen ingår i avdelningen hierarki.</span><span class="sxs-lookup"><span data-stu-id="77f8a-126">A selected check box indicates that the department is included in the department hierarchy.</span></span> <span data-ttu-id="77f8a-127">För information om hur man lägger till en avdelning till avdelning hierarki, se information senare i denna artikel.</span><span class="sxs-lookup"><span data-stu-id="77f8a-127">For information about how to add a department to the department hierarchy, see the information later in this article.</span></span> |
| <span data-ttu-id="77f8a-128">DUNS-nummer</span><span class="sxs-lookup"><span data-stu-id="77f8a-128">DUNS number</span></span>         | <span data-ttu-id="77f8a-129">DUNS står för Data Universal antal System.</span><span class="sxs-lookup"><span data-stu-id="77f8a-129">DUNS stands for Data Universal Number System.</span></span> <span data-ttu-id="77f8a-130">Detta är en 9-siffrig kod som är utfärdade av Dun & Bradstreet.</span><span class="sxs-lookup"><span data-stu-id="77f8a-130">This is a nine-digit number that is issued by Dun & Bradstreet.</span></span>                                                                                                     |
| <span data-ttu-id="77f8a-131">Chef</span><span class="sxs-lookup"><span data-stu-id="77f8a-131">Manager</span></span>             | <span data-ttu-id="77f8a-132">Ange den persona som hanterar avdelningen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-132">Enter the persona that manages the department.</span></span>                                                                                                                                                                    |
| <span data-ttu-id="77f8a-133">Adresser</span><span class="sxs-lookup"><span data-stu-id="77f8a-133">Addresses</span></span>           | <span data-ttu-id="77f8a-134">Lägga till adressinformation för avdelningen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-134">Add the address information for the department.</span></span> <span data-ttu-id="77f8a-135">Lägg till exempel till postadress till byggnaden där avdelningen finns.</span><span class="sxs-lookup"><span data-stu-id="77f8a-135">For example, add the mailing address for the building that the department is located in.</span></span>                                                                          |
| <span data-ttu-id="77f8a-136">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="77f8a-136">Contact information</span></span> | <span data-ttu-id="77f8a-137">Lägg till kontaktinformation för avdelningen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-137">Add contact information for the department.</span></span> <span data-ttu-id="77f8a-138">Lägg till ett telefonnummer till avdelningens servicedesk, till exempel.</span><span class="sxs-lookup"><span data-stu-id="77f8a-138">For example, add a telephone number for the service desk in the department.</span></span>                                                                                           |

<span data-ttu-id="77f8a-139">Om du vill lägga till en avdelning till avdelning hierarki, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="77f8a-139">To add a department to the department hierarchy, follow these steps.</span></span>

1.  <span data-ttu-id="77f8a-140">Klicka **Personal** &gt; **Avdelningar** &gt; **Avdelningshierarki**.</span><span class="sxs-lookup"><span data-stu-id="77f8a-140">Click **Human Resources** &gt; **Departments** &gt; **Department hierarchy**.</span></span>
2.  <span data-ttu-id="77f8a-141">Klicka på **Redigera**och välj sedan organisationen att avdelningen ska vara.</span><span class="sxs-lookup"><span data-stu-id="77f8a-141">Click **Edit**, and then select the organization that the department should be under.</span></span>
3.  <span data-ttu-id="77f8a-142">Klicka på **Infoga**och välj den **avdelning** i listan.</span><span class="sxs-lookup"><span data-stu-id="77f8a-142">Click **Insert**, and select **Department** in the list.</span></span>
4.  <span data-ttu-id="77f8a-143">I listan över enheter som visas, välj den avdelning som du vill lägga till i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="77f8a-143">In the list of departments that appears, select the department to add to the hierarchy.</span></span>
5.  <span data-ttu-id="77f8a-144">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="77f8a-144">Save your changes.</span></span> <span data-ttu-id="77f8a-145">Du får ett meddelande om att ett utkast av hierarkin har skapats.</span><span class="sxs-lookup"><span data-stu-id="77f8a-145">You receive a message that a draft version of the hierarchy has been created.</span></span>
6.  <span data-ttu-id="77f8a-146">När du är klar klickar du på **Publicera** i hierarkidesignern.</span><span class="sxs-lookup"><span data-stu-id="77f8a-146">When you're ready, click **Publish** in the hierarchy designer.</span></span> <span data-ttu-id="77f8a-147">Du kan ange ett giltighetsdatum som anger när hierarkin ska publiceras.</span><span class="sxs-lookup"><span data-stu-id="77f8a-147">You can enter an effective date that indicates when the hierarchy should be published.</span></span> <span data-ttu-id="77f8a-148">Om du exempelvis vill lägga till en ny avdelning i början av nästa kalenderår, ställ in datumet 1 januari på det nya kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="77f8a-148">For example, to add a new department at the beginning of the next calendar year, set the effective date to January 1 of the new calendar year.</span></span> <span data-ttu-id="77f8a-149">Ändringarna i hierarkin kommer att träda i kraft den dagen.</span><span class="sxs-lookup"><span data-stu-id="77f8a-149">The changes to the hierarchy will take effect on that date.</span></span>





