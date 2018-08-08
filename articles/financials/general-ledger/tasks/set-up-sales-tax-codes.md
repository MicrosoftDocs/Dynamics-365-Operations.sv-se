--- 
title: "Ställ in momskoder"
description: "Momskoder skapas för varje indirekt moms eller skatt som den juridiska personen ska beräkna, samla in och betala till skattemyndigheterna."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 44e0033ff75a28c5480feb24b6d3fd191829bca5
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="91dba-103">Ställ in momskoder</span><span class="sxs-lookup"><span data-stu-id="91dba-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91dba-104">Momskoder skapas för varje indirekt moms eller skatt som den juridiska personen ska beräkna, samla in och betala till skattemyndigheterna.</span><span class="sxs-lookup"><span data-stu-id="91dba-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="91dba-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="91dba-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="91dba-106">Gå till Skatt > Indirekta skatter > Moms > Momskoder.</span><span class="sxs-lookup"><span data-stu-id="91dba-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="91dba-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91dba-107">Click New.</span></span>
3. <span data-ttu-id="91dba-108">I fältet Momskod, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="91dba-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="91dba-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="91dba-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="91dba-110">Välj en kvittningsperiod för att ange vilken skattemyndighet och i vilka intervall denna moms ska rapporteras och betalas.</span><span class="sxs-lookup"><span data-stu-id="91dba-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="91dba-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="91dba-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="91dba-112">Välj en bokföringgrupp för att ange huvudkonton för att bokföra moms i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="91dba-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="91dba-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="91dba-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="91dba-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="91dba-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="91dba-115">Expandera snabbfliken Beräkning.</span><span class="sxs-lookup"><span data-stu-id="91dba-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="91dba-116">Beräkningssnabbfliken har flera fält som kontrollerar hur momsbelopp ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="91dba-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="91dba-117">Klicka på Momskod i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="91dba-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="91dba-118">Klicka på Värden.</span><span class="sxs-lookup"><span data-stu-id="91dba-118">Click Values.</span></span>
13. <span data-ttu-id="91dba-119">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="91dba-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="91dba-120">Ange värdet för momskoden.</span><span class="sxs-lookup"><span data-stu-id="91dba-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="91dba-121">På beräkningssnabbfliken i fältet Ursprung, om belopp per enhet är markerat, kommer värdet multipliceras med kvantiteten på transaktionen för att beräkna momsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="91dba-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="91dba-122">Om momskoden inte är en enhetsbaserad moms är värdet en procentsats som används som ursprung för att denna momskod ska kunna beräkna momsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="91dba-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="91dba-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91dba-123">Click Save.</span></span>
16. <span data-ttu-id="91dba-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91dba-124">Close the page.</span></span>
17. <span data-ttu-id="91dba-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91dba-125">Click Save.</span></span>


