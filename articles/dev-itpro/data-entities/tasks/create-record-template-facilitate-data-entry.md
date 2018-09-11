--- 
title: "Skapa en postmall för att förenkla datainmatning"
description: "Den här proceduren visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post."
author: margoc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: d64f32de2fb90397a72d938b937bd1f90e675287
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="82826-103">Skapa en postmall för att förenkla datainmatning</span><span class="sxs-lookup"><span data-stu-id="82826-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="82826-104">Den här proceduren visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post.</span><span class="sxs-lookup"><span data-stu-id="82826-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="82826-105">I den här proceduren ska du skapa en ny post för nya bärbara datorer som ska läggas till bland anläggningstillgångarna.</span><span class="sxs-lookup"><span data-stu-id="82826-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="82826-106">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="82826-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="82826-107">Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.</span><span class="sxs-lookup"><span data-stu-id="82826-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="82826-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="82826-108">Click New.</span></span>
3. <span data-ttu-id="82826-109">I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="82826-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="82826-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="82826-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="82826-111">Ange till exempel "Bärbar dator för företags-lead".</span><span class="sxs-lookup"><span data-stu-id="82826-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="82826-112">Ange ett värde i fältet Söknamn.</span><span class="sxs-lookup"><span data-stu-id="82826-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="82826-113">Ange till exempel "Bärbar dator".</span><span class="sxs-lookup"><span data-stu-id="82826-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="82826-114">Expandera avsnittet Teknisk information.</span><span class="sxs-lookup"><span data-stu-id="82826-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="82826-115">Ange ett värde i fältet Fabrikat.</span><span class="sxs-lookup"><span data-stu-id="82826-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="82826-116">Ange ett värde i fältet Modell.</span><span class="sxs-lookup"><span data-stu-id="82826-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="82826-117">Ange ett värde i fältet Modellår.</span><span class="sxs-lookup"><span data-stu-id="82826-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="82826-118">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82826-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="82826-119">Klicka på Postinfo.</span><span class="sxs-lookup"><span data-stu-id="82826-119">Click Record info.</span></span>
12. <span data-ttu-id="82826-120">Klicka på Användarmall.</span><span class="sxs-lookup"><span data-stu-id="82826-120">Click User template.</span></span>
13. <span data-ttu-id="82826-121">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="82826-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="82826-122">Ange till exempel "Bärbar företagsdator".</span><span class="sxs-lookup"><span data-stu-id="82826-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="82826-123">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="82826-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="82826-124">Ange till exempel "Bärbar företagsdator".</span><span class="sxs-lookup"><span data-stu-id="82826-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="82826-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="82826-125">Click OK.</span></span>
16. <span data-ttu-id="82826-126">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="82826-126">Click Close.</span></span>


