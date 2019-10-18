---
title: Bearbeta allokeringar
description: Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem i Microsoft Dynamics 365 Finance och hur de kan användas vid budgetplanering. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf889169357ea0598a3fe24b09a6eb565209b9c0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186358"
---
# <a name="process-allocations"></a><span data-ttu-id="4ed26-105">Bearbeta allokeringar</span><span class="sxs-lookup"><span data-stu-id="4ed26-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ed26-106">Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem och hur de kan användas vid budgetplanering.</span><span class="sxs-lookup"><span data-stu-id="4ed26-106">This article provides information about allocations, the options for processing them, and how they can be used in budget planning.</span></span> <span data-ttu-id="4ed26-107">Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer.</span><span class="sxs-lookup"><span data-stu-id="4ed26-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="4ed26-108">De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="4ed26-108">They help ensure that expenses or revenues are charged to the correct object in accounting.</span></span>

<span data-ttu-id="4ed26-109">Följande funktioner stöder den här processen:</span><span class="sxs-lookup"><span data-stu-id="4ed26-109">The following capabilities support this process:</span></span>

-   <span data-ttu-id="4ed26-110">Fördela transaktionsbelopp manuellt genom att använda uppdelningsåtgärden i redovisningsfördelningarna eller genom att använda standardmallarna för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="4ed26-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="4ed26-111">Mer information finns i [Redovisningsfördelningar](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="4ed26-111">For more information, see [Accounting distributions.](../accounts-payable/accounting-distributions.md)</span></span>
-   <span data-ttu-id="4ed26-112">Fördela transaktionsbelopp automatiskt baserat på allokeringsvillkor som definieras för individuella huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="4ed26-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="4ed26-113">Allokeringskontoposter skapas för varje journal som baseras på procentsats och målhuvudbokskontot, när en redovisningspost uppfyller kriterierna som definieras som källhuvudbokskontot.</span><span class="sxs-lookup"><span data-stu-id="4ed26-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span>
-   <span data-ttu-id="4ed26-114">Fördela redovisningssaldon eller fasta belopp automatiskt baserat på redovisningsallokeringsregler.</span><span class="sxs-lookup"><span data-stu-id="4ed26-114">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="4ed26-115">Redovisningsallokeringsreglerna bearbetas periodvis med hjälp av allokeringsjournaler.</span><span class="sxs-lookup"><span data-stu-id="4ed26-115">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> 

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="4ed26-116">Allokeringar i budgetplanering</span><span class="sxs-lookup"><span data-stu-id="4ed26-116">Allocations in budget planning</span></span>

<span data-ttu-id="4ed26-117">Redovisningsallokeringsregler kan användas för budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="4ed26-117">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="4ed26-118">När du använder allokeringsregler för redovisning i budgetplanering kommer allokeringsreglerna att fungera på samma sätt som i redovisningen, men källdata och måldata kommer från budgetplanen.</span><span class="sxs-lookup"><span data-stu-id="4ed26-118">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="4ed26-119">Du kan manuellt välja redovisningsallokeringsregler som ska användas för budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="4ed26-119">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="4ed26-120">Alternativt kan du använda ett allokeringsschema som körs som en del i en arbetsflödesprocess.</span><span class="sxs-lookup"><span data-stu-id="4ed26-120">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="4ed26-121">Du kan inte använda koncerninterna redovisningsallokeringsregler för budgetplanering.</span><span class="sxs-lookup"><span data-stu-id="4ed26-121">You can’t use intercompany ledger allocation rules for budget planning.</span></span>





