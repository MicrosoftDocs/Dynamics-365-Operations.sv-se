---
title: Ställ in tilläggstilldelningar
description: I den här proceduren visas hur du ställer in en tilldelning av tillägg.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: b69bd2029914efd31569c57272339e27ef1bd6a3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "356632"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="f496d-103">Ställ in tilläggstilldelningar</span><span class="sxs-lookup"><span data-stu-id="f496d-103">Set up accessorial assignments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f496d-104">I den här proceduren visas hur du ställer in en tilldelning av tillägg.</span><span class="sxs-lookup"><span data-stu-id="f496d-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="f496d-105">Detta görs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="f496d-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="f496d-106">Innan du använder den här guiden måste du köra guiden "Ställ in hubbens tilläggsavgifter och tilläggsmallar".</span><span class="sxs-lookup"><span data-stu-id="f496d-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="f496d-107">Ställa in Tilldelning av tillägg</span><span class="sxs-lookup"><span data-stu-id="f496d-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="f496d-108">Gå till Transporthantering > Inställningar > Klassificering > Tilldelning av tillägg.</span><span class="sxs-lookup"><span data-stu-id="f496d-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="f496d-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f496d-109">Click New.</span></span>
3. <span data-ttu-id="f496d-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f496d-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="f496d-111">Växla expanderingen av avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="f496d-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="f496d-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.</span><span class="sxs-lookup"><span data-stu-id="f496d-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f496d-113">I listan väljer du den hubb som du har skapat en tilläggsmall för när du körde guiden "Ställ in hubbens tilläggsavgifter och tilläggsmallar".</span><span class="sxs-lookup"><span data-stu-id="f496d-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="f496d-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubbens tilläggs-ID.</span><span class="sxs-lookup"><span data-stu-id="f496d-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f496d-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f496d-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f496d-116">Växla expanderingen av avsnittet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="f496d-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="f496d-117">I avsnittet Kriterier kan du välja exakta kriterier för när avgiften ska tillämpas, baserat de olika värden som erbjuds här.</span><span class="sxs-lookup"><span data-stu-id="f496d-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="f496d-118">Ange alternativet Tillämpa alltid till Ja.</span><span class="sxs-lookup"><span data-stu-id="f496d-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="f496d-119">Välj ett alternativ i fältet Nivå för tilldelning av tillägg.</span><span class="sxs-lookup"><span data-stu-id="f496d-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="f496d-120">Växla expanderingen av avsnittet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="f496d-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="f496d-121">Välj "Fast" i fältet Typ av tilläggsavgift.</span><span class="sxs-lookup"><span data-stu-id="f496d-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="f496d-122">Typen av tilläggsavgift bestämmer hur du beräknar den verkliga avgiften.</span><span class="sxs-lookup"><span data-stu-id="f496d-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="f496d-123">I det här exemplet är det en fast avgift.</span><span class="sxs-lookup"><span data-stu-id="f496d-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="f496d-124">Ange ett nummer i fältet Tilläggsavgift.</span><span class="sxs-lookup"><span data-stu-id="f496d-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="f496d-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f496d-125">Click Save.</span></span>

