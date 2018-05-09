--- 
title: "Ställ in avskrivningsregler "
description: "Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: 3e2c3bfdde6fd06bfe9e22f215f691e0c92fa8ee
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-depreciation-books"></a><span data-ttu-id="d7443-103">Ställ in avskrivningsregler </span><span class="sxs-lookup"><span data-stu-id="d7443-103">Set up depreciation books</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7443-104">Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d7443-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="d7443-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="d7443-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="d7443-106">Skapa en avskrivningsregel</span><span class="sxs-lookup"><span data-stu-id="d7443-106">Create a depreciation book</span></span>
1. <span data-ttu-id="d7443-107">Gå till Anläggningstillgångar > Inställningar > Avskrivningsböcker.</span><span class="sxs-lookup"><span data-stu-id="d7443-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="d7443-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d7443-108">Click New.</span></span>
3. <span data-ttu-id="d7443-109">Skriv ett värde i fältet Avskrivningsregler.</span><span class="sxs-lookup"><span data-stu-id="d7443-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="d7443-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d7443-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d7443-111">Markera eller avmarkera kryssrutan Beräkna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d7443-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="d7443-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="d7443-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d7443-113">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="d7443-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d7443-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="d7443-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d7443-116">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="d7443-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d7443-118">Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter.</span><span class="sxs-lookup"><span data-stu-id="d7443-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="d7443-119">Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.</span><span class="sxs-lookup"><span data-stu-id="d7443-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="d7443-120">Markera eller avmarkera kryssrutan Skapa avskrivningsjusteringar med basjusteringar.</span><span class="sxs-lookup"><span data-stu-id="d7443-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="d7443-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="d7443-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d7443-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="d7443-123">Koppla avskrivningsregler till en anläggningstillgångsgrupp</span><span class="sxs-lookup"><span data-stu-id="d7443-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="d7443-124">Klicka på Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="d7443-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="d7443-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d7443-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d7443-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d7443-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d7443-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d7443-128">Välj alternativ i fältet Avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="d7443-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="d7443-129">I fältet Tjänstelivstid, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="d7443-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="d7443-130">Värdet i fältet Avskrivningsperioder beräknas efter att du har angett tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="d7443-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  


