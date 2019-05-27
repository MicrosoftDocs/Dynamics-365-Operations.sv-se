---
title: Omedelbar lagerpåfyllnad
description: Det här avsnittet beskriver hur du kan använda direkt påfyllnad för att fylla på lagret när ett platsdirektiv inte kan fördela lager.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: ab1f06951d5daceaf002b2cc23236dd818457985
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543317"
---
# <a name="immediate-replenishment"></a><span data-ttu-id="cbf21-103">Omedelbar lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="cbf21-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbf21-104">Omedelbar lagerpåfyllnad gör det möjligt att fylla på lagret direkt efter att ett platsdirektiv för lagerställe misslyckas att tilldela lager.</span><span class="sxs-lookup"><span data-stu-id="cbf21-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="cbf21-105">Påfyllningen baseras på en enkel rad i inställningarna av platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="cbf21-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="cbf21-106">Om lagerbehållning inte finns är måttenheten som anges av den raden sker lagerpåfyllnad av den måttenheten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="cbf21-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="cbf21-107">Omedelbar lagerpåfyllnad är ett alternativ till metoden där allokering av lagret baseras på flera rader i platsdirektivet och där efterfrågan summeras i slutet av allokeringen och fylls på i måttenheten som har angetts i formuläret sista raden i platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="cbf21-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="cbf21-108">Fördelarna med omedelbar lagerpåfyllnad är att lagerpåfyllnad kan begränsas av specifika enheter och kvantiteten kan dirigeras till specifika platser.</span><span class="sxs-lookup"><span data-stu-id="cbf21-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="cbf21-109">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="cbf21-109">Business scenario</span></span>

<span data-ttu-id="cbf21-110">Exempelvis har du ett lagerställe som har separata plockområden för måttenheterna "ruta" och ”alla”.</span><span class="sxs-lookup"><span data-stu-id="cbf21-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="cbf21-111">Om du vill optimera plockningsprocessen genom att välja så många rutor som möjligt och plockning av resterande kvantiteter som är mindre än en ruta från området ”alla”.</span><span class="sxs-lookup"><span data-stu-id="cbf21-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="cbf21-112">I det här fallet kan du använda omedelbar lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="cbf21-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="cbf21-113">I platsdirektiv kan du ange omedelbart lagerpåfyllnad för rutorna så att lagerpåfyllnad för efterfrågan används när det blir brist på rutor som kan plockas för efterfrågekvantiteten.</span><span class="sxs-lookup"><span data-stu-id="cbf21-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="cbf21-114">På så sätt kan du optimera plockningsprocessen så att plockningen innehåller så många rutor som möjligt.</span><span class="sxs-lookup"><span data-stu-id="cbf21-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="cbf21-115">Omedelbar lagerpåfyllnad genererar lagerpåfyllnad av rutor och efterfrågan kommer inte att skickas vidare så att kvantiteterna som plockas i måttenheten ”alla”.</span><span class="sxs-lookup"><span data-stu-id="cbf21-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="cbf21-116">Med andra ord plockas endast den kvantitet som ska plockas i måttenheten ”alla” (dvs kvantiteter som är mindre än en ruta) från området ”alla”.</span><span class="sxs-lookup"><span data-stu-id="cbf21-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="cbf21-117">Om brist visas i området ”ruta” kan du välja så många rutor som möjligt från den totala efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="cbf21-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="cbf21-118">De återstående kvantiteterna plockas sedan från området ”alla”.</span><span class="sxs-lookup"><span data-stu-id="cbf21-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="cbf21-119">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="cbf21-119">Where it applies</span></span>

<span data-ttu-id="cbf21-120">Omedelbar påfyllning används under påfyllnadskörning om tilldelning misslyckas för en platsdirektivsrad som en påfyllnadsmall anges för.</span><span class="sxs-lookup"><span data-stu-id="cbf21-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="cbf21-121">Ange omedelbar lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="cbf21-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="cbf21-122">Gå till **lagerstyrning**\>**inställningar**\>**platsdirektiv**, och sedan till fliken **rader** i listan **omedelbar påfyllnadsmall** och välj en påfyllnadsmall för påfyllnadsbegäran.</span><span class="sxs-lookup"><span data-stu-id="cbf21-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="cbf21-123">Påfyllnadsmallen tillämpas om platsdirektivraden misslyckas att tilldelas en särskild måttenhet.</span><span class="sxs-lookup"><span data-stu-id="cbf21-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cbf21-124">Felsökning</span><span class="sxs-lookup"><span data-stu-id="cbf21-124">Troubleshooting</span></span>

<span data-ttu-id="cbf21-125">Om omedelbar lagerpåfyllnad har valts för en platsdirektivrad men inget påfyllnadsarbete genereras när du använder mallar för begäran om lagerpåfyllnad för den platsdirektivraden måste två huvudorsaker undersökas:</span><span class="sxs-lookup"><span data-stu-id="cbf21-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="cbf21-126">Kontrollera att påfyllnadsmallen för efterfrågan som används är konfigurerad till att använda rätt platsmallar och arbetsmallar för typen **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="cbf21-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="cbf21-127">Kontrollera att det inte finns tillräcklig lagerbehållning på platser där lagerpåfyllnadsmallen för efterfrågan söker efter lagerbehållning för påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="cbf21-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>
