---
title: Ändra rapporteringsrelationer för en befattning
description: I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 78410347e7e6cf67f692c7e9193419ffd87e3057
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057102"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="2b0a6-103">Ändra rapporteringsrelationer för en befattning</span><span class="sxs-lookup"><span data-stu-id="2b0a6-103">Modify reporting relationships for a position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="2b0a6-104">I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="2b0a6-105">Rapporteringsrelationen kan användas för att dirigera dokument genom arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="2b0a6-106">Proceduren visar även hur du tilldelar medarbetaren till ytterligare hierarkier.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="2b0a6-107">En medarbetare kan till exempel vara en del av en projektteam med en informell rapporteringsrelation till en projektansvarig.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="2b0a6-108">Fler rapporteringsrelationer kan definieras för befattningen för att kunna hantera olika projekt eller matrisscenarier.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="2b0a6-109">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2b0a6-110">Gå till Personal > Befattningar > Befattningar.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="2b0a6-111">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2b0a6-112">Filtrera till exempel fältet Befattning med värdet 000091.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="2b0a6-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2b0a6-114">Expandera avsnittet Rapporter till befattning.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="2b0a6-115">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="2b0a6-116">I fältet Rapporter till fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="2b0a6-117">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-117">Click Create.</span></span>
8. <span data-ttu-id="2b0a6-118">Utöka avsnittet Relationer.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="2b0a6-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-119">Click Add.</span></span>
10. <span data-ttu-id="2b0a6-120">Markera kryssrutan till vänster om rutnätet.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="2b0a6-121">I fältet Hierarkinamn, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="2b0a6-122">Exempel: projekt</span><span class="sxs-lookup"><span data-stu-id="2b0a6-122">Example: Project</span></span>  
12. <span data-ttu-id="2b0a6-123">I fältet Rapporter till befattning, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="2b0a6-124">Exempel: 000437</span><span class="sxs-lookup"><span data-stu-id="2b0a6-124">Example:  000437</span></span>
13. <span data-ttu-id="2b0a6-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2b0a6-125">Click Save.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]