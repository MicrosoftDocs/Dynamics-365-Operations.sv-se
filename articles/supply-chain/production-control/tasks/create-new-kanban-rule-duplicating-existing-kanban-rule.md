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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3aef2725152d39e49070f33d0c56089200c94353
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837816"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="52513-103">Skapa en ny kanban-regel genom att duplicera en befintlig kanban-regel</span><span class="sxs-lookup"><span data-stu-id="52513-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52513-104">Den här proceduren fokuserar på att skapa en dubblett för en befintlig kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="52513-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="52513-105">Detta är användbart om du vill skapa nya kanban-regler som baseras på befintliga kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="52513-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="52513-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="52513-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="52513-107">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen för ett modifierat produktionsflöde eller en ny återanskaffningsregel.</span><span class="sxs-lookup"><span data-stu-id="52513-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="52513-108">Välj en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="52513-108">Select a kanban rule</span></span>
1. <span data-ttu-id="52513-109">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="52513-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="52513-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="52513-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="52513-111">Välj kanban-regel 000017 för produkten M0006.</span><span class="sxs-lookup"><span data-stu-id="52513-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="52513-112">Duplicera en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="52513-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="52513-113">Klicka på Duplicera kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="52513-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="52513-114">När du duplicerar en kanban-regel går det att ändra typ, datum, aktiviteter och produktval.</span><span class="sxs-lookup"><span data-stu-id="52513-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="52513-115">Ändra produkten för den här proceduren i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="52513-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="52513-116">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="52513-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="52513-117">Välj M0007.</span><span class="sxs-lookup"><span data-stu-id="52513-117">Select M0007.</span></span>  
3. <span data-ttu-id="52513-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="52513-118">Click OK.</span></span>
    * <span data-ttu-id="52513-119">Observera att en dubblett av kanban-regel 000017 skapas.</span><span class="sxs-lookup"><span data-stu-id="52513-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

