--- 
title: "Ställ in hubbens tilläggsavgifter och tilläggsmallar"
description: "I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6381416640ffacf0a9d96d7da96bc33612ca7137
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="c3116-103">Ställ in hubbens tilläggsavgifter och tilläggsmallar</span><span class="sxs-lookup"><span data-stu-id="c3116-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3116-104">I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.</span><span class="sxs-lookup"><span data-stu-id="c3116-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="c3116-105">Proceduren använder USMF-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c3116-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="c3116-106">Den här inställningen görs vanligtvis av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="c3116-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="c3116-107">Ställa in ett hubbhuvud</span><span class="sxs-lookup"><span data-stu-id="c3116-107">Set up a hub master</span></span>
1. <span data-ttu-id="c3116-108">Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.</span><span class="sxs-lookup"><span data-stu-id="c3116-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="c3116-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c3116-109">Click New.</span></span>
3. <span data-ttu-id="c3116-110">Skriv ett värde i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="c3116-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="c3116-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3116-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c3116-112">Välj "Hubb" i fältet Tilläggstyp.</span><span class="sxs-lookup"><span data-stu-id="c3116-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="c3116-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c3116-113">Click Save.</span></span>
7. <span data-ttu-id="c3116-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c3116-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="c3116-115">Ställa in en tilläggsavgift för hubb</span><span class="sxs-lookup"><span data-stu-id="c3116-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="c3116-116">Gå till Transporthantering > Inställningar > Klassificering > Hubbens tilläggsavgifter.</span><span class="sxs-lookup"><span data-stu-id="c3116-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="c3116-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c3116-117">Click New.</span></span>
3. <span data-ttu-id="c3116-118">Skriv ett värde i fältet Hubbens tilläggs-ID.</span><span class="sxs-lookup"><span data-stu-id="c3116-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="c3116-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.</span><span class="sxs-lookup"><span data-stu-id="c3116-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c3116-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c3116-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="c3116-121">Välj ett alternativ i fältet Hubbplats.</span><span class="sxs-lookup"><span data-stu-id="c3116-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="c3116-122">Du kan antingen skapa tillägget som en hämtning eller lämning.</span><span class="sxs-lookup"><span data-stu-id="c3116-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="c3116-123">Beroende på ditt val ska tillägget tillämpas på motsvarande transportsegmentet i ditt flöde.</span><span class="sxs-lookup"><span data-stu-id="c3116-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="c3116-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="c3116-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="c3116-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c3116-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c3116-126">Välj den mall du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="c3116-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="c3116-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c3116-127">Click Save.</span></span>
10. <span data-ttu-id="c3116-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c3116-128">Close the page.</span></span>


