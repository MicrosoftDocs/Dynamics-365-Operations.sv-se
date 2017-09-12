--- 
title: "Ändra rapporteringsrelationer för en befattning"
description: "I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare."
author: ShielaSogge
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 002fffc7e8c3186eedf9060d36d2b4a77749da98
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="d04e8-103">Ändra rapporteringsrelationer för en befattning</span><span class="sxs-lookup"><span data-stu-id="d04e8-103">Modify reporting relationships for a position</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d04e8-104">I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d04e8-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="d04e8-105">Rapporteringsrelationen kan användas för att dirigera dokument genom arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d04e8-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="d04e8-106">Proceduren visar även hur du tilldelar medarbetaren till ytterligare hierarkier.</span><span class="sxs-lookup"><span data-stu-id="d04e8-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="d04e8-107">En medarbetare kan till exempel vara en del av en projektteam med en informell rapporteringsrelation till en projektansvarig.</span><span class="sxs-lookup"><span data-stu-id="d04e8-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="d04e8-108">Fler rapporteringsrelationer kan definieras för befattningen för att kunna hantera olika projekt eller matrisscenarier.</span><span class="sxs-lookup"><span data-stu-id="d04e8-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="d04e8-109">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d04e8-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="d04e8-110">Gå till Personal > Befattningar > Befattningar.</span><span class="sxs-lookup"><span data-stu-id="d04e8-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="d04e8-111">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="d04e8-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d04e8-112">Filtrera till exempel fältet Befattning med värdet 000091.</span><span class="sxs-lookup"><span data-stu-id="d04e8-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="d04e8-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d04e8-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d04e8-114">Expandera avsnittet Rapporter till befattning.</span><span class="sxs-lookup"><span data-stu-id="d04e8-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="d04e8-115">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="d04e8-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="d04e8-116">I fältet Rapporter till fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="d04e8-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="d04e8-117">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="d04e8-117">Click Create.</span></span>
8. <span data-ttu-id="d04e8-118">Utöka avsnittet Relationer.</span><span class="sxs-lookup"><span data-stu-id="d04e8-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="d04e8-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d04e8-119">Click Add.</span></span>
10. <span data-ttu-id="d04e8-120">Markera kryssrutan till vänster om rutnätet.</span><span class="sxs-lookup"><span data-stu-id="d04e8-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="d04e8-121">I fältet Hierarkinamn, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="d04e8-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="d04e8-122">Exempel: projekt</span><span class="sxs-lookup"><span data-stu-id="d04e8-122">Example: Project</span></span>  
12. <span data-ttu-id="d04e8-123">I fältet Rapporter till befattning, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="d04e8-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="d04e8-124">Exempel: 000437</span><span class="sxs-lookup"><span data-stu-id="d04e8-124">Example:  000437</span></span>
13. <span data-ttu-id="d04e8-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d04e8-125">Click Save.</span></span>


