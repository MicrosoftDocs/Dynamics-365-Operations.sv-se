---
title: "Stäng redovisningen vid periodslutet"
description: "Det här avsnittet beskriver de uppgifter som normalt slutförs vid en periodstängning av redovisningen."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5643a06cb23eedd7c8676ad48be2ad2e78cdfc9b
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="b17e0-103">Stäng redovisningen vid periodslutet</span><span class="sxs-lookup"><span data-stu-id="b17e0-103">Close the general ledger at period end</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b17e0-104">Det här avsnittet beskriver de uppgifter som normalt slutförs vid en periodstängning av redovisningen.</span><span class="sxs-lookup"><span data-stu-id="b17e0-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="b17e0-105">I redovisningen kan du slutföra stängningsprocedurerna för en period eller ett år.</span><span class="sxs-lookup"><span data-stu-id="b17e0-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="b17e0-106">Stängningsprocesser förbereder systemet för en ny period.</span><span class="sxs-lookup"><span data-stu-id="b17e0-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="b17e0-107">För att förbereda systemet för ett nytt år måste du köra processen för årsslutet.</span><span class="sxs-lookup"><span data-stu-id="b17e0-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="b17e0-108">Varje organisation har olika processer och steg som utförs i samband med ett periodslut.</span><span class="sxs-lookup"><span data-stu-id="b17e0-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="b17e0-109">Här följer några valfria steg för periodslut:</span><span class="sxs-lookup"><span data-stu-id="b17e0-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="b17e0-110">Slutför alla uppgifter i alla andra moduler, som Kundreskontra, Leverantörsreskontra och Lager.</span><span class="sxs-lookup"><span data-stu-id="b17e0-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="b17e0-111">Kontrollera att alla journaler har bokförts.</span><span class="sxs-lookup"><span data-stu-id="b17e0-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="b17e0-112">Kör omräkningen i utländsk valuta för att skapa belopp för orealiserad vinst eller förlust.</span><span class="sxs-lookup"><span data-stu-id="b17e0-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="b17e0-113">Kvitta transaktioner för varje huvudbokskonto.</span><span class="sxs-lookup"><span data-stu-id="b17e0-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="b17e0-114">Behandla alla obligatorisk allokeringar.</span><span class="sxs-lookup"><span data-stu-id="b17e0-114">Process any required allocations.</span></span>
-   <span data-ttu-id="b17e0-115">Bokför periodslutsjusteringar manuellt.</span><span class="sxs-lookup"><span data-stu-id="b17e0-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="b17e0-116">Journalför transaktioner och granska rapporten **Redovisningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="b17e0-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="b17e0-117">Utför en konsolidering genom att använda ett konsolideringsföretag eller en ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="b17e0-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="b17e0-118">Generera bokslut för periodslutet genom att använda ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="b17e0-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="b17e0-119">Ställ in redovisningsperioder på **Spärrad** så att ingen ytterligare bokföring sker.</span><span class="sxs-lookup"><span data-stu-id="b17e0-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="b17e0-120">Du kan även begränsa en period till en viss användargrupp medan periodslutsaktiviteter sker för bättre kontroll.</span><span class="sxs-lookup"><span data-stu-id="b17e0-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="b17e0-121">Det är ingen god idé att ange en period som **Permanent stängd**, detta eftersom du inte på nytt kan öppna en period som har stängts.</span><span class="sxs-lookup"><span data-stu-id="b17e0-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="b17e0-122">Arbetsytan för ett finansiellt periodslut kan användas för att organisera och spåra de aktiviteter som krävs för olika periodslutsprocesser.</span><span class="sxs-lookup"><span data-stu-id="b17e0-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="b17e0-123">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b17e0-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="b17e0-124">Arbetsyta för räkenskapsperiodens stängning</span><span class="sxs-lookup"><span data-stu-id="b17e0-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="b17e0-125">Årsbokslut</span><span class="sxs-lookup"><span data-stu-id="b17e0-125">Year end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="b17e0-126">Masstäng räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="b17e0-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)





