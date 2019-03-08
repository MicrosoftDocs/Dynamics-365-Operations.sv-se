---
title: Skapa en ny kanban-regel genom att duplicera en befintlig kanban-regel
description: Den här proceduren fokuserar på att skapa en dubblett för en befintlig kanban-regel.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f72dbca0debf9e6a03ee700a979d4f4c110f819
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "350353"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="d0e52-103">Skapa en ny kanban-regel genom att duplicera en befintlig kanban-regel</span><span class="sxs-lookup"><span data-stu-id="d0e52-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d0e52-104">Den här proceduren fokuserar på att skapa en dubblett för en befintlig kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="d0e52-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="d0e52-105">Detta är användbart om du vill skapa nya kanban-regler som baseras på befintliga kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="d0e52-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="d0e52-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d0e52-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d0e52-107">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen för ett modifierat produktionsflöde eller en ny återanskaffningsregel.</span><span class="sxs-lookup"><span data-stu-id="d0e52-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="d0e52-108">Välj en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="d0e52-108">Select a kanban rule</span></span>
1. <span data-ttu-id="d0e52-109">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="d0e52-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="d0e52-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d0e52-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d0e52-111">Välj kanban-regel 000017 för produkten M0006.</span><span class="sxs-lookup"><span data-stu-id="d0e52-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="d0e52-112">Duplicera en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="d0e52-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="d0e52-113">Klicka på Duplicera kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="d0e52-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="d0e52-114">När du duplicerar en kanban-regel går det att ändra typ, datum, aktiviteter och produktval.</span><span class="sxs-lookup"><span data-stu-id="d0e52-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="d0e52-115">Ändra produkten för den här proceduren i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="d0e52-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="d0e52-116">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="d0e52-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="d0e52-117">Välj M0007.</span><span class="sxs-lookup"><span data-stu-id="d0e52-117">Select M0007.</span></span>  
3. <span data-ttu-id="d0e52-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d0e52-118">Click OK.</span></span>
    * <span data-ttu-id="d0e52-119">Observera att en dubblett av kanban-regel 000017 skapas.</span><span class="sxs-lookup"><span data-stu-id="d0e52-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

