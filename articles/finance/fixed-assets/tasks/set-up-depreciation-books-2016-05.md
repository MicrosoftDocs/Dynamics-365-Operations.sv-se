---
title: Ställ in avskrivningsregler
description: Den här proceduren guidar genom processen att skapa en ny avskrivningsregel och associera den med en anläggningstillgångsgrupp.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0ab7f9332e3224c3dadd62aae532ccffb05c82a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815606"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="5b65f-103">Ställ in avskrivningsregler</span><span class="sxs-lookup"><span data-stu-id="5b65f-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5b65f-104">Den här proceduren guidar genom processen att skapa en ny avskrivningsregel och associera den med en anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5b65f-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="5b65f-105">Skapa en avskrivningsregel</span><span class="sxs-lookup"><span data-stu-id="5b65f-105">Create a depreciation book</span></span>
1. <span data-ttu-id="5b65f-106">Gå till Anläggningstillgångar > Inställningar > Avskrivningsböcker.</span><span class="sxs-lookup"><span data-stu-id="5b65f-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="5b65f-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5b65f-107">Click New.</span></span>
3. <span data-ttu-id="5b65f-108">Skriv ett värde i fältet Avskrivningsregler.</span><span class="sxs-lookup"><span data-stu-id="5b65f-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="5b65f-109">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b65f-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5b65f-110">Markera eller avmarkera kryssrutan Beräkna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b65f-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="5b65f-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="5b65f-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5b65f-112">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="5b65f-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5b65f-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ avskrivningsprofil.</span><span class="sxs-lookup"><span data-stu-id="5b65f-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="5b65f-115">Hitta och markera önskad avskrivningsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="5b65f-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5b65f-117">Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter.</span><span class="sxs-lookup"><span data-stu-id="5b65f-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="5b65f-118">Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.</span><span class="sxs-lookup"><span data-stu-id="5b65f-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="5b65f-119">Markera eller avmarkera kryssrutan Skapa avskrivningsjusteringar med basjusteringar.</span><span class="sxs-lookup"><span data-stu-id="5b65f-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="5b65f-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="5b65f-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="5b65f-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="5b65f-122">Koppla avskrivningsregler till en anläggningstillgångsgrupp</span><span class="sxs-lookup"><span data-stu-id="5b65f-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="5b65f-123">Klicka på Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5b65f-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="5b65f-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5b65f-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5b65f-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="5b65f-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b65f-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5b65f-127">Välj alternativ i fältet Avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="5b65f-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="5b65f-128">I fältet Tjänstelivstid, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="5b65f-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="5b65f-129">Värdet i fältet Avskrivningsperioder beräknas efter att du har angett tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="5b65f-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]