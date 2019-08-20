---
title: Ändra avskrivningspraxis för flera anläggningstillgångar
description: Uppgiften uppdaterar avskrivningspraxis för en viss grupp av anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21baf3692cbcb87f6ed37459848376a1fa87a438
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840083"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="fd21d-103">Ändra avskrivningspraxis för flera anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="fd21d-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fd21d-104">Uppgiften uppdaterar avskrivningspraxis för en viss grupp av anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="fd21d-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="fd21d-105">I den här uppgiftsguiden används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fd21d-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="fd21d-106">Gå till Anläggningstillgångar > Periodiska uppgifter > Massuppdatering</span><span class="sxs-lookup"><span data-stu-id="fd21d-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="fd21d-107">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsbok.</span><span class="sxs-lookup"><span data-stu-id="fd21d-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="fd21d-108">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fd21d-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fd21d-109">Ange datum i fältet Satt i tjänst - start.</span><span class="sxs-lookup"><span data-stu-id="fd21d-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="fd21d-110">Ange datum i fältet Satt i tjänst - slut.</span><span class="sxs-lookup"><span data-stu-id="fd21d-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="fd21d-111">Endast tillgångar som är del av den valda avskrivningsboken och som har satts i tjänst under denna tid kommer att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="fd21d-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="fd21d-112">Välj alternativ i fältet Aktuell avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="fd21d-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="fd21d-113">Endast tillgångar som har aktuell avskrivningspraxis uppdateras.</span><span class="sxs-lookup"><span data-stu-id="fd21d-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="fd21d-114">Välj alternativ i fältet Ny avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="fd21d-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="fd21d-115">Bekräfta att rapporten skrivs ut till valt mål.</span><span class="sxs-lookup"><span data-stu-id="fd21d-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="fd21d-116">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="fd21d-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="fd21d-117">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="fd21d-117">Click Filter.</span></span>
10. <span data-ttu-id="fd21d-118">Välj Anläggningstillgångsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="fd21d-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="fd21d-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="fd21d-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="fd21d-120">Markera den valda anläggningstillgångsgruppen.</span><span class="sxs-lookup"><span data-stu-id="fd21d-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="fd21d-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fd21d-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="fd21d-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fd21d-122">Click OK.</span></span>
15. <span data-ttu-id="fd21d-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fd21d-123">Click OK.</span></span>
    *  <span data-ttu-id="fd21d-124">Resultatet av processen visas på massuppdateringrapporten.</span><span class="sxs-lookup"><span data-stu-id="fd21d-124">Results of the process are shown on the Mass update report.</span></span>     

