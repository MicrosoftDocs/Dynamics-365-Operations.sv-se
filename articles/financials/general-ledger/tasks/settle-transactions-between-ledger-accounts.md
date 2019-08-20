---
title: Kvitta transaktioner mellan redovisningskonton
description: Proceduren visar hur det går till att kvitta transaktioner mellan huvudbokskonton och avbryta en redovisningskvittning.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6ed76f82532d43a3c05b60b12176fe851e327956
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846233"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="3c9f3-103">Kvitta transaktioner mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="3c9f3-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c9f3-104">Proceduren visar hur det går till att kvitta transaktioner mellan huvudbokskonton och avbryta en redovisningskvittning.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="3c9f3-105">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="3c9f3-106">Kvitta transaktion mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="3c9f3-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="3c9f3-107">Gå till Redovisning > Periodiska uppgifter > Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="3c9f3-108">Leta reda på transaktionen i listan du vill kvitta.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3c9f3-109">Beloppsaldot måste vara noll.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="3c9f3-110">Klicka på Inkludera.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-110">Click Include.</span></span>
4. <span data-ttu-id="3c9f3-111">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="3c9f3-112">Avbryt en redovisningskvittning</span><span class="sxs-lookup"><span data-stu-id="3c9f3-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="3c9f3-113">Gå till Redovisning > Förfrågningar och rapporter > Råbalans.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="3c9f3-114">Klicka på Parametrar för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="3c9f3-115">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-115">Click Update.</span></span>
4. <span data-ttu-id="3c9f3-116">Leta reda på kontot i listan där den kvittade transaktionen finns.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="3c9f3-117">Klicka på Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-117">Click All transactions.</span></span>
6. <span data-ttu-id="3c9f3-118">Använd ett filter för att enkelt hitta transaktionen i listan.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="3c9f3-119">Klicka på Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="3c9f3-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-120">In the list, mark the selected row.</span></span>

