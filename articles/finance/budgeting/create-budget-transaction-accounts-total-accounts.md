---
title: Skapa en budget av transaktionskonton och totalkonton
description: Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton. Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f60963bee790737c85161dff03278df0572e3abc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448129"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="e797b-104">Skapa en budget av transaktionskonton och totalkonton</span><span class="sxs-lookup"><span data-stu-id="e797b-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e797b-105">Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton.</span><span class="sxs-lookup"><span data-stu-id="e797b-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="e797b-106">Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs.</span><span class="sxs-lookup"><span data-stu-id="e797b-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="e797b-107">Dokument för båda budgetplanposter och budgetregisterposter tillåter budgetering på huvudkonton som har typen **Summa**.</span><span class="sxs-lookup"><span data-stu-id="e797b-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="e797b-108">Utfall kan bara bokföras på transaktionshuvudkonton.</span><span class="sxs-lookup"><span data-stu-id="e797b-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="e797b-109">För den periodiska processen **Generera budgetplan från huvudbok** på fliken **Källa** kan du ange huvudkontotypen **Summa** som villkor.</span><span class="sxs-lookup"><span data-stu-id="e797b-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="e797b-110">I det här fallet kommer varje summahuvudkonto inkluderas i målbudgetplanen, och beloppet är lika med det totala beloppet i intervallet för valda huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="e797b-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="e797b-111">Du kan aktivera budgetkontroll för huvudkonton med typen **Summa**.</span><span class="sxs-lookup"><span data-stu-id="e797b-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="e797b-112">Den här funktionen stöds genom användning av budgetgrupper.</span><span class="sxs-lookup"><span data-stu-id="e797b-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="e797b-113">För varje summahuvudkonto måste budgeten som ska kontrolleras för en budgetgrupp skapas på sidan **Budgetkontrollkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e797b-113">For each total main account, the budget that should be controlled for a budget group must be created on the \*\*Budget control configuration \*\*page.</span></span> <span data-ttu-id="e797b-114">De kriterier som du anger måste innehålla summahuvudkontot och kontointervallet.</span><span class="sxs-lookup"><span data-stu-id="e797b-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="e797b-115">För att påskynda processen med att skapa budgetgrupper kan du använda datatabellen för budgetkontrollgrupper.</span><span class="sxs-lookup"><span data-stu-id="e797b-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="e797b-116">När en budget används i rapporteringen, till exempel ett bokslut, består budgetsumman för saldokontot av följande belopp:</span><span class="sxs-lookup"><span data-stu-id="e797b-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="e797b-117">Budgetarna som skapar av varje transaktionsredovisning i intervallet för saldokontot.</span><span class="sxs-lookup"><span data-stu-id="e797b-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="e797b-118">Budgetbeloppet som anges direkt på saldokontot.</span><span class="sxs-lookup"><span data-stu-id="e797b-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="e797b-119">Därför kan du skapa separata budgetar för de viktigaste transaktionskontona i intervallet för saldokontot och sedan lägga till det tillgängliga budgetbeloppet på saldokontot.</span><span class="sxs-lookup"><span data-stu-id="e797b-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>



