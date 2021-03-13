---
title: Ändra rapporteringsrelationer för en befattning
description: I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 652893dfef22b6ba694ef20a81d88c85d26f05a2
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127065"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="23b28-103">Ändra rapporteringsrelationer för en befattning</span><span class="sxs-lookup"><span data-stu-id="23b28-103">Modify reporting relationships for a position</span></span>



<span data-ttu-id="23b28-104">I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="23b28-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="23b28-105">Rapporteringsrelationen kan användas för att dirigera dokument genom arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="23b28-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="23b28-106">Proceduren visar även hur du tilldelar medarbetaren till ytterligare hierarkier.</span><span class="sxs-lookup"><span data-stu-id="23b28-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="23b28-107">En medarbetare kan till exempel vara en del av en projektteam med en informell rapporteringsrelation till en projektansvarig.</span><span class="sxs-lookup"><span data-stu-id="23b28-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="23b28-108">Fler rapporteringsrelationer kan definieras för befattningen för att kunna hantera olika projekt eller matrisscenarier.</span><span class="sxs-lookup"><span data-stu-id="23b28-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="23b28-109">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="23b28-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="23b28-110">Gå till Personal > Befattningar > Befattningar.</span><span class="sxs-lookup"><span data-stu-id="23b28-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="23b28-111">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="23b28-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="23b28-112">Filtrera till exempel fältet Befattning med värdet 000091.</span><span class="sxs-lookup"><span data-stu-id="23b28-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="23b28-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="23b28-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="23b28-114">Expandera avsnittet Rapporter till befattning.</span><span class="sxs-lookup"><span data-stu-id="23b28-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="23b28-115">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="23b28-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="23b28-116">I fältet Rapporter till fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="23b28-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="23b28-117">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="23b28-117">Click Create.</span></span>
8. <span data-ttu-id="23b28-118">Utöka avsnittet Relationer.</span><span class="sxs-lookup"><span data-stu-id="23b28-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="23b28-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="23b28-119">Click Add.</span></span>
10. <span data-ttu-id="23b28-120">Markera kryssrutan till vänster om rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b28-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="23b28-121">I fältet Hierarkinamn, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="23b28-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="23b28-122">Exempel: projekt</span><span class="sxs-lookup"><span data-stu-id="23b28-122">Example: Project</span></span>  
12. <span data-ttu-id="23b28-123">I fältet Rapporter till befattning, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="23b28-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="23b28-124">Exempel: 000437</span><span class="sxs-lookup"><span data-stu-id="23b28-124">Example:  000437</span></span>
13. <span data-ttu-id="23b28-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23b28-125">Click Save.</span></span>

