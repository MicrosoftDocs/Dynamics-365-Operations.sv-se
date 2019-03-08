---
title: Ställ in avskrivningsregler (maj 2016)
description: Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "355574"
---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="5fd20-103">Ställ in avskrivningsregler (maj 2016)</span><span class="sxs-lookup"><span data-stu-id="5fd20-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5fd20-104">Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5fd20-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="5fd20-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="5fd20-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="5fd20-106">Skapa en avskrivningsregel</span><span class="sxs-lookup"><span data-stu-id="5fd20-106">Create a depreciation book</span></span>
1. <span data-ttu-id="5fd20-107">Gå till Anläggningstillgångar > Inställningar > Avskrivningsböcker.</span><span class="sxs-lookup"><span data-stu-id="5fd20-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="5fd20-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5fd20-108">Click New.</span></span>
3. <span data-ttu-id="5fd20-109">Skriv ett värde i fältet Avskrivningsregler.</span><span class="sxs-lookup"><span data-stu-id="5fd20-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="5fd20-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fd20-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5fd20-111">Markera eller avmarkera kryssrutan Beräkna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fd20-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="5fd20-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="5fd20-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5fd20-113">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="5fd20-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5fd20-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="5fd20-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="5fd20-116">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="5fd20-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5fd20-118">Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter.</span><span class="sxs-lookup"><span data-stu-id="5fd20-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="5fd20-119">Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.</span><span class="sxs-lookup"><span data-stu-id="5fd20-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="5fd20-120">Markera eller avmarkera kryssrutan Skapa avskrivningsjusteringar med basjusteringar.</span><span class="sxs-lookup"><span data-stu-id="5fd20-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="5fd20-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="5fd20-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="5fd20-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="5fd20-123">Koppla avskrivningsregler till en anläggningstillgångsgrupp</span><span class="sxs-lookup"><span data-stu-id="5fd20-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="5fd20-124">Klicka på Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5fd20-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="5fd20-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5fd20-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5fd20-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="5fd20-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5fd20-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5fd20-128">Välj alternativ i fältet Avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="5fd20-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="5fd20-129">I fältet Tjänstelivstid, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="5fd20-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="5fd20-130">Värdet i fältet Avskrivningsperioder beräknas efter att du har angett tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="5fd20-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

