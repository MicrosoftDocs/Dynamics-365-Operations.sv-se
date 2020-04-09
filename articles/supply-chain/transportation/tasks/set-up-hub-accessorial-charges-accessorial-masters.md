---
title: Ställ in hubbens tilläggsavgifter och tilläggsmallar
description: I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ea59326a85d97d53795104f80486f2fac24148a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148541"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="6890c-103">Ställ in hubbens tilläggsavgifter och tilläggsmallar</span><span class="sxs-lookup"><span data-stu-id="6890c-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6890c-104">I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.</span><span class="sxs-lookup"><span data-stu-id="6890c-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="6890c-105">Proceduren använder USMF-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="6890c-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="6890c-106">Den här inställningen görs vanligtvis av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="6890c-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="6890c-107">Ställa in ett hubbhuvud</span><span class="sxs-lookup"><span data-stu-id="6890c-107">Set up a hub master</span></span>
1. <span data-ttu-id="6890c-108">Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.</span><span class="sxs-lookup"><span data-stu-id="6890c-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="6890c-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="6890c-109">Click New.</span></span>
3. <span data-ttu-id="6890c-110">Skriv ett värde i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="6890c-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="6890c-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="6890c-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6890c-112">Välj "Hubb" i fältet Tilläggstyp.</span><span class="sxs-lookup"><span data-stu-id="6890c-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="6890c-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="6890c-113">Click Save.</span></span>
7. <span data-ttu-id="6890c-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6890c-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="6890c-115">Ställa in en tilläggsavgift för hubb</span><span class="sxs-lookup"><span data-stu-id="6890c-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="6890c-116">Gå till Transporthantering > Inställningar > Klassificering > Hubbens tilläggsavgifter.</span><span class="sxs-lookup"><span data-stu-id="6890c-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="6890c-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="6890c-117">Click New.</span></span>
3. <span data-ttu-id="6890c-118">Skriv ett värde i fältet Hubbens tilläggs-ID.</span><span class="sxs-lookup"><span data-stu-id="6890c-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="6890c-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.</span><span class="sxs-lookup"><span data-stu-id="6890c-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6890c-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6890c-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="6890c-121">Välj ett alternativ i fältet Hubbplats.</span><span class="sxs-lookup"><span data-stu-id="6890c-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="6890c-122">Du kan antingen skapa tillägget som en hämtning eller lämning.</span><span class="sxs-lookup"><span data-stu-id="6890c-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="6890c-123">Beroende på ditt val ska tillägget tillämpas på motsvarande transportsegmentet i ditt flöde.</span><span class="sxs-lookup"><span data-stu-id="6890c-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="6890c-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="6890c-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="6890c-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="6890c-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6890c-126">Välj den mall du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="6890c-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="6890c-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="6890c-127">Click Save.</span></span>
10. <span data-ttu-id="6890c-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6890c-128">Close the page.</span></span>

