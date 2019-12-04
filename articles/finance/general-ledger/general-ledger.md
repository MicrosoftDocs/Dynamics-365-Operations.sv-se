---
title: Redovisning och ekonomisk rapportering – översikt
description: Använd redovisningen när du vill definiera och hantera den juridiska personens ekonomiska poster.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cad11bcd1b1674055a07b5093093e33d3ac556
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771809"
---
# <a name="general-ledger-and-financial-reporting-overview"></a><span data-ttu-id="88d1c-103">Redovisning och ekonomisk rapportering – översikt</span><span class="sxs-lookup"><span data-stu-id="88d1c-103">General ledger and Financial reporting overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88d1c-104">Använd redovisningen när du vill definiera och hantera den juridiska personens ekonomiska poster.</span><span class="sxs-lookup"><span data-stu-id="88d1c-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="88d1c-105">Redovisningen är ett register för debet- och kreditposter.</span><span class="sxs-lookup"><span data-stu-id="88d1c-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="88d1c-106">Dessa poster är klassificerade med hjälp av de konton som listas i en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="88d1c-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="88d1c-107">Planera kontoplanen</span><span class="sxs-lookup"><span data-stu-id="88d1c-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="88d1c-108">Huvudkontotyper</span><span class="sxs-lookup"><span data-stu-id="88d1c-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="88d1c-109">Du kan allokera, eller fördela, monetära belopp på ett eller flera konton eller konto-/ och dimensionskombinationer som baseras på allokeringsregler.</span><span class="sxs-lookup"><span data-stu-id="88d1c-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="88d1c-110">Det finns två typer av allokeringar: fasta och variabla.</span><span class="sxs-lookup"><span data-stu-id="88d1c-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="88d1c-111">Du kan också kvitta transaktioner mellan redovisningskonton och revalvera valutabelopp.</span><span class="sxs-lookup"><span data-stu-id="88d1c-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="88d1c-112">I slutet av ett räkenskapsår måste du skapa UB-transaktioner och förbereda redovisningssystemet för det nya räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="88d1c-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="88d1c-113">Du kan använda konsolideringsfunktionen för att kombinera de finansiella resultaten för flera juridiska personer till resultat för en enda, konsoliderad organisation.</span><span class="sxs-lookup"><span data-stu-id="88d1c-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="88d1c-114">Dotterbolagen kan finnas in samma databas eller i separata databaser.</span><span class="sxs-lookup"><span data-stu-id="88d1c-114">The subsidiaries can be in the same database or in separate databases.</span></span>

- [<span data-ttu-id="88d1c-115">Översikt över konsolidering och eliminering</span><span class="sxs-lookup"><span data-stu-id="88d1c-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="88d1c-116">Kontosaldon i redovisningskontot</span><span class="sxs-lookup"><span data-stu-id="88d1c-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="88d1c-117">Ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="88d1c-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="88d1c-118">[![Affärsprocess](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="88d1c-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="88d1c-119">Moms</span><span class="sxs-lookup"><span data-stu-id="88d1c-119">Sales tax</span></span>
<span data-ttu-id="88d1c-120">Alla företag samlar in och betalar moms till olika skattemyndigheter.</span><span class="sxs-lookup"><span data-stu-id="88d1c-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="88d1c-121">Reglerna och satserna varierar efter land/region, delstat, kommun och ort.</span><span class="sxs-lookup"><span data-stu-id="88d1c-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="88d1c-122">Dessutom måste reglerna uppdateras regelbundet när skattemyndigheter ändrar sina krav.</span><span class="sxs-lookup"><span data-stu-id="88d1c-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="88d1c-123">Momskoderna innehåller grundläggande information om hur mycket du samlar in och betalar till myndigheterna.</span><span class="sxs-lookup"><span data-stu-id="88d1c-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="88d1c-124">När du ställer in momskoder, definierar du de belopp eller procentsatser som ska samlas in.</span><span class="sxs-lookup"><span data-stu-id="88d1c-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="88d1c-125">Du anger även olika metod med de belopp eller procentsatser av tillämpas på transaktionsbelopp.</span><span class="sxs-lookup"><span data-stu-id="88d1c-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="88d1c-126">Det här avsnittet innehåller information om hur du ställer in momskoder för de metoder och satser som skattemyndigheterna kräver.</span><span class="sxs-lookup"><span data-stu-id="88d1c-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="88d1c-127">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="88d1c-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="88d1c-128">Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder</span><span class="sxs-lookup"><span data-stu-id="88d1c-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="88d1c-129">Momsbetalningar och avrundningsregler</span><span class="sxs-lookup"><span data-stu-id="88d1c-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="88d1c-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88d1c-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="88d1c-131">Vad är nytt och under utveckling</span><span class="sxs-lookup"><span data-stu-id="88d1c-131">What's new and in development</span></span>

<span data-ttu-id="88d1c-132">Gå till [Viktig information om Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) för att se vilka nya funktioner har planerats.</span><span class="sxs-lookup"><span data-stu-id="88d1c-132">Go to the [Microsoft Dynamics 365 release plans](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="88d1c-133">Bloggar</span><span class="sxs-lookup"><span data-stu-id="88d1c-133">Blogs</span></span>

<span data-ttu-id="88d1c-134">Det finns åsikter, nyheter och annan information i [bloggen om Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) och [bloggen om Microsoft Dynamics 365 Finance and Operations – Ekonomi](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="88d1c-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="88d1c-135">I [bloggen Microsoft Dynamics Operations Partner Community](https://community.dynamics.com/partner/b/operationspartnercommunityblog) får Microsoft Dynamics-partners en resurs där de kan få mer information om vad som är nytt och trendar i MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="88d1c-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="88d1c-136">Videoklipp</span><span class="sxs-lookup"><span data-stu-id="88d1c-136">Videos</span></span>

<span data-ttu-id="88d1c-137">Ta en titt på instruktionsfilmerna som finns i [Microsoft Dynamics 365-kanalen på YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="88d1c-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="88d1c-138">Bloggar</span><span class="sxs-lookup"><span data-stu-id="88d1c-138">Community blogs</span></span>

- [<span data-ttu-id="88d1c-139">Vad du bör veta om redovisningen i Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="88d1c-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

