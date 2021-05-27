---
title: Du kan inte fakturera en kundutställd försäljningsorder
description: Du kan inte längre fakturera den ursprungliga försäljningsordern och den ursprungliga inköpsordern för direktleverans när du har aktiverat alternativet Bokför faktura automatiskt.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026911"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="89c2e-103">Du kan inte fakturera en kundutställd försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="89c2e-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="89c2e-104">KB-nummer: 4611793</span><span class="sxs-lookup"><span data-stu-id="89c2e-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="89c2e-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="89c2e-105">Symptoms</span></span>

<span data-ttu-id="89c2e-106">Du kan inte längre fakturera den ursprungliga försäljningsordern och den ursprungliga inköpsordern för direktleverans när du har aktiverat alternativet **Bokför faktura automatiskt** på sidan **Koncernintern** för en leverantör.</span><span class="sxs-lookup"><span data-stu-id="89c2e-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="89c2e-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="89c2e-107">Resolution</span></span>

<span data-ttu-id="89c2e-108">Synkroniseringsbeteendet för koncerninterna och direkta leveransorderfakturor styrs och tvingas av de parametrar som beskrivs i [Ställ in parametrar för att bokföra en koncernintern order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="89c2e-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="89c2e-109">När du har angett dessa parametrar måste du fakturera den koncerninterna försäljningsordern först.</span><span class="sxs-lookup"><span data-stu-id="89c2e-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="89c2e-110">Ursprungliga försäljningsorder och inköpsorder synkroniseras sedan.</span><span class="sxs-lookup"><span data-stu-id="89c2e-110">The original sales orders and purchase orders will then be synchronized.</span></span>
