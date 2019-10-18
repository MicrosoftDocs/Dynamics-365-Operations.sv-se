---
title: Ställ in momskoder
description: Det här avsnittet innehåller information om hur du ställer in momskoder i Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45a4a7a20b20961d707e43b35d61c10a08c74943
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185990"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="01781-103">Ställ in momskoder</span><span class="sxs-lookup"><span data-stu-id="01781-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="01781-104">Det här avsnittet innehåller information om hur du ställer in momskoder.</span><span class="sxs-lookup"><span data-stu-id="01781-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="01781-105">Momskoder skapas för varje indirekt moms eller skatt som den juridiska personen ska beräkna, samla in och betala till skattemyndigheterna.</span><span class="sxs-lookup"><span data-stu-id="01781-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="01781-106">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="01781-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="01781-107">Gå till **Navigeringsfönster > Moms > Indirekta skatter > Moms > Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="01781-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="01781-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="01781-108">Select **New**.</span></span>
3. <span data-ttu-id="01781-109">I fältet **Momskod**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="01781-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="01781-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="01781-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="01781-111">Välj en **kvittningsperiod** genom att öppna rullgardinslistan för att ange vilken skattemyndighet och i vilka intervall denna moms ska rapporteras och betalas.</span><span class="sxs-lookup"><span data-stu-id="01781-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="01781-112">Välj en **bokföringgrupp** för att ange huvudkonton för att bokföra moms i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="01781-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="01781-113">Expandera snabbfliken **Beräkning**.</span><span class="sxs-lookup"><span data-stu-id="01781-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="01781-114">Detta inkluderar flera fält som kontrollerar hur momsbelopp ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="01781-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="01781-115">Fyll i dessa fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="01781-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="01781-116">I **åtgärdsfönstret** överst i gränssnittet, välj **momskod**.</span><span class="sxs-lookup"><span data-stu-id="01781-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="01781-117">Markera **värden**.</span><span class="sxs-lookup"><span data-stu-id="01781-117">Select **Values**.</span></span>
10. <span data-ttu-id="01781-118">Ange värdet för den här momskoden i kolumnen **värde**.</span><span class="sxs-lookup"><span data-stu-id="01781-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="01781-119">På snabbfliken **Beräkning** i fältet Ursprung, om belopp per enhet är markerat, kommer värdet multipliceras med kvantiteten på transaktionen för att beräkna momsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="01781-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="01781-120">Om momskoden inte är en enhetsbaserad moms är värdet en procentsats som används som ursprung för att denna momskod ska kunna beräkna momsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="01781-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="01781-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01781-121">Select **Save**.</span></span>
12. <span data-ttu-id="01781-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="01781-122">Close the page.</span></span>
13. <span data-ttu-id="01781-123">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01781-123">Select **Save**.</span></span>

