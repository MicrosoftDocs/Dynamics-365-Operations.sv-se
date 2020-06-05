---
title: Koncerninterna utgifter
description: En medarbetare som anställts av en juridisk entitet i en organisation kan utföra arbete för en annan juridisk person inom samma organisation. I denna situation kan du använda funktionen för företagsinterna utgifter för att tilldela medarbetarens utgifter till den juridiska person som arbetet utförts för.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390894"
---
# <a name="intercompany-expenses"></a><span data-ttu-id="074ba-104">Koncerninterna utgifter</span><span class="sxs-lookup"><span data-stu-id="074ba-104">Intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="074ba-105">En medarbetare som anställts av en juridisk entitet i en organisation kan utföra arbete för en annan juridisk person inom samma organisation.</span><span class="sxs-lookup"><span data-stu-id="074ba-105">A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization.</span></span> <span data-ttu-id="074ba-106">I denna situation kan du använda funktionen för företagsinterna utgifter för att tilldela medarbetarens utgifter till den juridiska person som arbetet utförts för.</span><span class="sxs-lookup"><span data-stu-id="074ba-106">In this situation, you can use the intercompany expense feature to assign the worker’s expenses to the legal entity for which the work was performed.</span></span> <span data-ttu-id="074ba-107">Den juridiska entiteten som anställer medarbetaren kallas för "utlånande juridisk person".</span><span class="sxs-lookup"><span data-stu-id="074ba-107">The legal entity that employs the worker is called the loaning legal entity.</span></span> <span data-ttu-id="074ba-108">Den juridiska entiteten som medarbetaren genererar utgifter för kallas "lånande juridisk person".</span><span class="sxs-lookup"><span data-stu-id="074ba-108">The legal entity for which the worker incurs expenses is called the borrowing legal entity.</span></span> 

<span data-ttu-id="074ba-109">Innan en medarbetare kan skapa och skicka in utgifter för arbete som utförs för en annan juridisk person måste du, på sidan **Parametrar för utgiftshantering**, välja alternativet **Tillåt företagsinterna utgiftsrader** i den utlånande juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="074ba-109">Before a worker can create and submit expenses for work that is performed for a different legal entity, in the loaning legal entity, on the **Expense management parameters** page, select the **Allow intercompany expense lines** option.</span></span> 

## <a name="tax-posting-for-intercompany-expenses"></a><span data-ttu-id="074ba-110">Momsbokföring för koncerninterna utgifter</span><span class="sxs-lookup"><span data-stu-id="074ba-110">Tax posting for intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="074ba-111">Om du vill använda momsgrupper som är kopplade till den utlånande juridiska personen (källan) i stället för den lånande juridiska personen (mål) i utgiftsrapporten måste du konfigurera den här inställningen i momsinställningarna för redovisningen.</span><span class="sxs-lookup"><span data-stu-id="074ba-111">If you want to use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you will need to configure this in the General ledger sales tax set up.</span></span> <span data-ttu-id="074ba-112">När redovisningsparametern **Juridisk person för koncernintern momsbokföring** är inställd på **Källa** och **Tillämpa momsskatt regler** ställs in på **Nej** kommer moms kombinationen för den lånande juridiska personen att användas.</span><span class="sxs-lookup"><span data-stu-id="074ba-112">When the General ledger parameter, **Legal entity for intercompany tax posting** is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity will be used.</span></span> <span data-ttu-id="074ba-113">När samma parameter anges som **Mål** kommer momskombinationen för lånande juridisk person att användas.</span><span class="sxs-lookup"><span data-stu-id="074ba-113">When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used.</span></span> <span data-ttu-id="074ba-114">För juridiska personer i USA gäller att när parametern är inställd på **Källa** måste även fältet **Momsfordran** konfigureras på den nya sidan **Bokföringsgrupper för redovisning**.</span><span class="sxs-lookup"><span data-stu-id="074ba-114">For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page.</span></span> <span data-ttu-id="074ba-115">Redovisningsmotorn kommer att använda informationen från det här fältet för att ange en skatterelaterad redovisningspost.</span><span class="sxs-lookup"><span data-stu-id="074ba-115">The accounting engine will use the information from this field for tax related accounting entry.</span></span>   
<span data-ttu-id="074ba-116">Beteendet är konsekvent för utgiftsrader som bokförts med eller utan projekt.</span><span class="sxs-lookup"><span data-stu-id="074ba-116">The behavior is consistent for expense lines posted with or without a project.</span></span>  
