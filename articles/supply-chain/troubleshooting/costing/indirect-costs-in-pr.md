---
title: Rapporten Indirekta kostnader i processen innehåller borttagna produktionsorder
description: Rapporten Indirekta kostnader i processen innehåller information om produktionsorder som delvis bearbetats och senare tagits bort.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026916"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="70616-103">Rapporten Indirekta kostnader i processen innehåller borttagna produktionsorder</span><span class="sxs-lookup"><span data-stu-id="70616-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="70616-104">KB-nummer: 4612748</span><span class="sxs-lookup"><span data-stu-id="70616-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="70616-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="70616-105">Symptoms</span></span>

<span data-ttu-id="70616-106">Rapporten **Indirekta kostnader i processen** innehåller information om produktionsorder som delvis bearbetats och senare tagits bort.</span><span class="sxs-lookup"><span data-stu-id="70616-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="70616-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="70616-107">Resolution</span></span>

<span data-ttu-id="70616-108">När du återför en produktionsorder återför du också alla transaktioner i produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="70616-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="70616-109">När du tar bort produktionsordern bevarar redovisningstabellerna och redovisningen alla transaktioner som är relaterade till den.</span><span class="sxs-lookup"><span data-stu-id="70616-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="70616-110">Rapporterna visar transaktionerna i redovisningstabellerna.</span><span class="sxs-lookup"><span data-stu-id="70616-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="70616-111">För den specifika produktionsordern ska nettovärdet vara 0,00.</span><span class="sxs-lookup"><span data-stu-id="70616-111">For the specific production order, the net value should be 0.00.</span></span>
