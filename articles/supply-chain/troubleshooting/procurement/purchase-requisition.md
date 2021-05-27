---
title: Du kan inte lägga till en rad på en inköpsrekvisition efter att du har begärt en ändring
description: Systemet låter dig inte lägga till en rad på en inköpsrekvisition efter att du har begärt en ändring.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchReqTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jeyao
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5dbb55a6a352a7acf16729c1cfe1afdac2e2eef8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026920"
---
# <a name="you-cant-add-a-line-to-a-purchase-requisition-after-you-request-a-change"></a><span data-ttu-id="0e9b1-103">Du kan inte lägga till en rad på en inköpsrekvisition efter att du har begärt en ändring</span><span class="sxs-lookup"><span data-stu-id="0e9b1-103">You can't add a line to a purchase requisition after you request a change</span></span>

<span data-ttu-id="0e9b1-104">KB-nummer: 4611211</span><span class="sxs-lookup"><span data-stu-id="0e9b1-104">KB number: 4611211</span></span>

## <a name="symptoms"></a><span data-ttu-id="0e9b1-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="0e9b1-105">Symptoms</span></span>

<span data-ttu-id="0e9b1-106">Systemet låter dig inte lägga till en rad på en inköpsrekvisition efter att du har begärt en ändring.</span><span class="sxs-lookup"><span data-stu-id="0e9b1-106">The system doesn't allow you to add a line to a purchase requisition after you request a change.</span></span>

## <a name="resolution"></a><span data-ttu-id="0e9b1-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="0e9b1-107">Resolution</span></span>

<span data-ttu-id="0e9b1-108">Du måste återkalla arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="0e9b1-108">You must recall the workflow.</span></span> <span data-ttu-id="0e9b1-109">När inköpsrekvisitionen har statusen *Utkast* kan du fortsätta att redigera den eller lägga till en rad i den.</span><span class="sxs-lookup"><span data-stu-id="0e9b1-109">After the purchase requisition is in *Draft* status, you can continue to edit it or add a line to it.</span></span>
