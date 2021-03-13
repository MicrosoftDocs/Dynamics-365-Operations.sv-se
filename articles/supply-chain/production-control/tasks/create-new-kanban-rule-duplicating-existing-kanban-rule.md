---
title: Skapa en ny kanban-regel genom att duplicera en befintlig kanban-regel
description: Den här proceduren fokuserar på att skapa en dubblett för en befintlig kanban-regel.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a1fda7e00c64f18e8078805a98cba8cdb1c4309
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011007"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="bc03f-103">Skapa en ny kanban-regel genom att duplicera en befintlig kanban-regel</span><span class="sxs-lookup"><span data-stu-id="bc03f-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc03f-104">Den här proceduren fokuserar på att skapa en dubblett för en befintlig kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="bc03f-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="bc03f-105">Detta är användbart om du vill skapa nya kanban-regler som baseras på befintliga kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="bc03f-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="bc03f-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="bc03f-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bc03f-107">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen för ett modifierat produktionsflöde eller en ny återanskaffningsregel.</span><span class="sxs-lookup"><span data-stu-id="bc03f-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="bc03f-108">Välj en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="bc03f-108">Select a kanban rule</span></span>
1. <span data-ttu-id="bc03f-109">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="bc03f-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="bc03f-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bc03f-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bc03f-111">Välj kanban-regel 000017 för produkten M0006.</span><span class="sxs-lookup"><span data-stu-id="bc03f-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="bc03f-112">Duplicera en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="bc03f-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="bc03f-113">Klicka på Duplicera kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="bc03f-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="bc03f-114">När du duplicerar en kanban-regel går det att ändra typ, datum, aktiviteter och produktval.</span><span class="sxs-lookup"><span data-stu-id="bc03f-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="bc03f-115">Ändra produkten för den här proceduren i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="bc03f-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="bc03f-116">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="bc03f-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="bc03f-117">Välj M0007.</span><span class="sxs-lookup"><span data-stu-id="bc03f-117">Select M0007.</span></span>  
3. <span data-ttu-id="bc03f-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bc03f-118">Click OK.</span></span>
    * <span data-ttu-id="bc03f-119">Observera att en dubblett av kanban-regel 000017 skapas.</span><span class="sxs-lookup"><span data-stu-id="bc03f-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

