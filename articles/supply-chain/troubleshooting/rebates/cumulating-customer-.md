---
title: Ackumulation av kundrabatter misslyckas när artikelrabattgrupper används
description: När du använder kundrabattavtal i kombination med artikelrabattgrupper beräknas rabatter, men ackumulationen misslyckas.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026905"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="2ddd1-103">Ackumulation av kundrabatter misslyckas när artikelrabattgrupper används</span><span class="sxs-lookup"><span data-stu-id="2ddd1-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="2ddd1-104">KB-nummer: 4611372</span><span class="sxs-lookup"><span data-stu-id="2ddd1-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="2ddd1-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2ddd1-105">Symptoms</span></span>

<span data-ttu-id="2ddd1-106">När du använder kundrabattavtal (av typen *belopp*) i kombination med artikelrabattgrupper beräknas rabatter, men ackumulationen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="2ddd1-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="2ddd1-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2ddd1-107">Resolution</span></span>

<span data-ttu-id="2ddd1-108">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="2ddd1-108">The system is behaving as designed.</span></span> <span data-ttu-id="2ddd1-109">Artikelgrupper grupperar bara objekt som har samma tröskelvärdesvillkor.</span><span class="sxs-lookup"><span data-stu-id="2ddd1-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="2ddd1-110">Rabattvillkoret (tröskelvärdet) ställs mot beloppet för varje artikel, inte mot det ackumulerade beloppet för någon artikel i artikelgruppen.</span><span class="sxs-lookup"><span data-stu-id="2ddd1-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
