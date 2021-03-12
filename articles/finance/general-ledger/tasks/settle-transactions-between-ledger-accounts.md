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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8220bacc8d683163e97956ec59a5af929b04319c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994425"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="5ea5c-103">Kvitta transaktioner mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="5ea5c-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5ea5c-104">Proceduren visar hur det går till att kvitta transaktioner mellan huvudbokskonton och avbryta en redovisningskvittning.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="5ea5c-105">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="5ea5c-106">Kvitta transaktion mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="5ea5c-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="5ea5c-107">Gå till Redovisning > Periodiska uppgifter > Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="5ea5c-108">Leta reda på transaktionen i listan du vill kvitta.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5ea5c-109">Beloppsaldot måste vara noll.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="5ea5c-110">Klicka på Inkludera.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-110">Click Include.</span></span>
4. <span data-ttu-id="5ea5c-111">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="5ea5c-112">Avbryt en redovisningskvittning</span><span class="sxs-lookup"><span data-stu-id="5ea5c-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="5ea5c-113">Gå till Redovisning > Förfrågningar och rapporter > Råbalans.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="5ea5c-114">Klicka på Parametrar för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="5ea5c-115">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-115">Click Update.</span></span>
4. <span data-ttu-id="5ea5c-116">Leta reda på kontot i listan där den kvittade transaktionen finns.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="5ea5c-117">Klicka på Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-117">Click All transactions.</span></span>
6. <span data-ttu-id="5ea5c-118">Använd ett filter för att enkelt hitta transaktionen i listan.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="5ea5c-119">Klicka på Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="5ea5c-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5ea5c-120">In the list, mark the selected row.</span></span>

