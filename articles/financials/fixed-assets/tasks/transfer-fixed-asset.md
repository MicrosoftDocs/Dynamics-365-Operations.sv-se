--- 
title: "Överför en anläggningstillgång"
description: "Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d3a0c4dcee5d57dedf418c8f5df9edd2f7e1b648
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="1234a-103">Överför en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1234a-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1234a-104">Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="1234a-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="1234a-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="1234a-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="1234a-106">Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1234a-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="1234a-107">Hitta och välj den anläggningstillgång som ska överföras.</span><span class="sxs-lookup"><span data-stu-id="1234a-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="1234a-108">Klicka på Anläggningstillgång i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1234a-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="1234a-109">Överför Överför fasta anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="1234a-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="1234a-110">I fältet Överföringsdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="1234a-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="1234a-111">Ange en kommentar som beskriver överföringen.</span><span class="sxs-lookup"><span data-stu-id="1234a-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="1234a-112">Den här listan visar samtliga böcker för anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="1234a-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="1234a-113">Välj de böcker som du vill överföra till en ny ekonomisk dimensionsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="1234a-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="1234a-114">Listan visar de befintliga ekonomiska dimensionsvärdena för den valda boken.</span><span class="sxs-lookup"><span data-stu-id="1234a-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="1234a-115">Välj den ekonomiska dimension som du vill uppdatera för den valda tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="1234a-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="1234a-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="1234a-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="1234a-117">Ange andra värden för ekonomisk dimension om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="1234a-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="1234a-118">Alla värden för ekonomisk dimension ändras när en överföring uppstår, om ett värde har angetts eller lämnats tomt.</span><span class="sxs-lookup"><span data-stu-id="1234a-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="1234a-119">Till exempel, om du anger ett värde för BusinessUnit och lämnar de ekonomiska dimensionerna CostCenter och Avdelning tomma.</span><span class="sxs-lookup"><span data-stu-id="1234a-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="1234a-120">Om din kontostruktur tillåter toma värden för CostCenter och Avdelning leder överföringen till att varje värdemodell har det nya värdet för BusinessUnit och ett tomt värde för CostCenter och Avdelning.</span><span class="sxs-lookup"><span data-stu-id="1234a-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="1234a-121">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="1234a-121">Click Update.</span></span>
    * <span data-ttu-id="1234a-122">Du har möjlighet att granska ändringar innan du slutför överföringen.</span><span class="sxs-lookup"><span data-stu-id="1234a-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="1234a-123">Granska resultaten innan du överför tillgångsförteckningarna.</span><span class="sxs-lookup"><span data-stu-id="1234a-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="1234a-124">Klicka på Överför.</span><span class="sxs-lookup"><span data-stu-id="1234a-124">Click Transfer.</span></span>


