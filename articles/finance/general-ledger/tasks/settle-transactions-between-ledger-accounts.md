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
ms.openlocfilehash: bb53e9fee35712343f034389f00f3d4539cc652d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144684"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="4f02e-103">Kvitta transaktioner mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="4f02e-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f02e-104">Proceduren visar hur det går till att kvitta transaktioner mellan huvudbokskonton och avbryta en redovisningskvittning.</span><span class="sxs-lookup"><span data-stu-id="4f02e-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="4f02e-105">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="4f02e-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="4f02e-106">Kvitta transaktion mellan redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="4f02e-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="4f02e-107">Gå till Redovisning > Periodiska uppgifter > Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="4f02e-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="4f02e-108">Leta reda på transaktionen i listan du vill kvitta.</span><span class="sxs-lookup"><span data-stu-id="4f02e-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4f02e-109">Beloppsaldot måste vara noll.</span><span class="sxs-lookup"><span data-stu-id="4f02e-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="4f02e-110">Klicka på Inkludera.</span><span class="sxs-lookup"><span data-stu-id="4f02e-110">Click Include.</span></span>
4. <span data-ttu-id="4f02e-111">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="4f02e-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="4f02e-112">Avbryt en redovisningskvittning</span><span class="sxs-lookup"><span data-stu-id="4f02e-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="4f02e-113">Gå till Redovisning > Förfrågningar och rapporter > Råbalans.</span><span class="sxs-lookup"><span data-stu-id="4f02e-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="4f02e-114">Klicka på Parametrar för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="4f02e-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="4f02e-115">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="4f02e-115">Click Update.</span></span>
4. <span data-ttu-id="4f02e-116">Leta reda på kontot i listan där den kvittade transaktionen finns.</span><span class="sxs-lookup"><span data-stu-id="4f02e-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="4f02e-117">Klicka på Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="4f02e-117">Click All transactions.</span></span>
6. <span data-ttu-id="4f02e-118">Använd ett filter för att enkelt hitta transaktionen i listan.</span><span class="sxs-lookup"><span data-stu-id="4f02e-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="4f02e-119">Klicka på Redovisningskvittningar.</span><span class="sxs-lookup"><span data-stu-id="4f02e-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="4f02e-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4f02e-120">In the list, mark the selected row.</span></span>

