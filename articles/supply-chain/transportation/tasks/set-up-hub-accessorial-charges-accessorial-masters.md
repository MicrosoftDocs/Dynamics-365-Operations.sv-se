---
title: Ställ in hubbens tilläggsavgifter och tilläggsmallar
description: I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e012850a390f373088e758418b68c7eaae7ad53e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973995"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="60b46-103">Ställ in hubbens tilläggsavgifter och tilläggsmallar</span><span class="sxs-lookup"><span data-stu-id="60b46-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="60b46-104">I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.</span><span class="sxs-lookup"><span data-stu-id="60b46-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="60b46-105">Proceduren använder USMF-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="60b46-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="60b46-106">Den här inställningen görs vanligtvis av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="60b46-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="60b46-107">Ställa in ett hubbhuvud</span><span class="sxs-lookup"><span data-stu-id="60b46-107">Set up a hub master</span></span>
1. <span data-ttu-id="60b46-108">Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.</span><span class="sxs-lookup"><span data-stu-id="60b46-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="60b46-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="60b46-109">Click New.</span></span>
3. <span data-ttu-id="60b46-110">Skriv ett värde i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="60b46-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="60b46-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="60b46-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="60b46-112">Välj "Hubb" i fältet Tilläggstyp.</span><span class="sxs-lookup"><span data-stu-id="60b46-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="60b46-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="60b46-113">Click Save.</span></span>
7. <span data-ttu-id="60b46-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="60b46-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="60b46-115">Ställa in en tilläggsavgift för hubb</span><span class="sxs-lookup"><span data-stu-id="60b46-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="60b46-116">Gå till Transporthantering > Inställningar > Klassificering > Hubbens tilläggsavgifter.</span><span class="sxs-lookup"><span data-stu-id="60b46-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="60b46-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="60b46-117">Click New.</span></span>
3. <span data-ttu-id="60b46-118">Skriv ett värde i fältet Hubbens tilläggs-ID.</span><span class="sxs-lookup"><span data-stu-id="60b46-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="60b46-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.</span><span class="sxs-lookup"><span data-stu-id="60b46-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="60b46-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="60b46-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="60b46-121">Välj ett alternativ i fältet Hubbplats.</span><span class="sxs-lookup"><span data-stu-id="60b46-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="60b46-122">Du kan antingen skapa tillägget som en hämtning eller lämning.</span><span class="sxs-lookup"><span data-stu-id="60b46-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="60b46-123">Beroende på ditt val ska tillägget tillämpas på motsvarande transportsegmentet i ditt flöde.</span><span class="sxs-lookup"><span data-stu-id="60b46-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="60b46-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="60b46-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="60b46-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="60b46-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="60b46-126">Välj den mall du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="60b46-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="60b46-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="60b46-127">Click Save.</span></span>
10. <span data-ttu-id="60b46-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="60b46-128">Close the page.</span></span>

