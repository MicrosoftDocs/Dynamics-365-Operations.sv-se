---
title: Skapa en plan för en plats
description: Produktionstadsplaneraren beräknar material- och kapacitetsbehov för att producera en specifik artikel.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf3016e289248acafc3bc6b79d853fd9de8c5417
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841657"
---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="53a53-103">Skapa en plan för en plats</span><span class="sxs-lookup"><span data-stu-id="53a53-103">Create a plan for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53a53-104">Produktionstadsplaneraren beräknar material- och kapacitetsbehov för att producera en specifik artikel.</span><span class="sxs-lookup"><span data-stu-id="53a53-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="53a53-105">När anskaffningsförslagen har skapats, hittar han order på siten för vilken han planerar och bekräftar order med start från de mest brådskande.</span><span class="sxs-lookup"><span data-stu-id="53a53-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="53a53-106">De mest brådskande order är de som måste bekräftas på det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="53a53-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="53a53-107">Använd demonstrationdataföretaget USMF för att utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="53a53-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="53a53-108">Skapa material och kapacitetsplan för en artikel</span><span class="sxs-lookup"><span data-stu-id="53a53-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="53a53-109">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="53a53-109">Click Master planning.</span></span>
    * <span data-ttu-id="53a53-110">Du måste navigera till Standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="53a53-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="53a53-111">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="53a53-111">Click Run.</span></span>
3. <span data-ttu-id="53a53-112">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="53a53-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="53a53-113">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="53a53-113">Click Filter.</span></span>
5. <span data-ttu-id="53a53-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="53a53-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="53a53-115">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="53a53-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="53a53-116">Exempel: D0001</span><span class="sxs-lookup"><span data-stu-id="53a53-116">Example: D0001</span></span>  
7. <span data-ttu-id="53a53-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53a53-117">Click OK.</span></span>
8. <span data-ttu-id="53a53-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53a53-118">Click OK.</span></span>
    * <span data-ttu-id="53a53-119">Detta kan ta några minuter.</span><span class="sxs-lookup"><span data-stu-id="53a53-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="53a53-120">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="53a53-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="53a53-121">Identifiera brådskande planerade order för artikeln</span><span class="sxs-lookup"><span data-stu-id="53a53-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="53a53-122">Öppna artikelnummerkolumnfiltret.</span><span class="sxs-lookup"><span data-stu-id="53a53-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="53a53-123">Använd ett filter för fältet ”artikelnummer”, med värdet ”D0001", med hjälp av filteroperatorn ”börjar med”.</span><span class="sxs-lookup"><span data-stu-id="53a53-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="53a53-124">Öppna Kolumnfilter för orderdatum.</span><span class="sxs-lookup"><span data-stu-id="53a53-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="53a53-125">Tillämpa ett filter i fältet ”Orderdatum", med ett värde av aktuellt datum med filteroperatorn "Är exakt".</span><span class="sxs-lookup"><span data-stu-id="53a53-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="53a53-126">Bekräfta alla brådskande planerade order för artikeln</span><span class="sxs-lookup"><span data-stu-id="53a53-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="53a53-127">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="53a53-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="53a53-128">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="53a53-128">Click Firm.</span></span>
3. <span data-ttu-id="53a53-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53a53-129">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]