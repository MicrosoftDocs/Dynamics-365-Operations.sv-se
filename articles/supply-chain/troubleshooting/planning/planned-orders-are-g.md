---
title: Huvudplanering genererar planerade order för fiktiva produkter
description: Planerade order genereras för fiktiva produkter när huvudplaneringen har körts.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026922"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="2b725-103">Huvudplanering genererar planerade order för fiktiva produkter</span><span class="sxs-lookup"><span data-stu-id="2b725-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="2b725-104">KB-nummer: 4614729</span><span class="sxs-lookup"><span data-stu-id="2b725-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="2b725-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2b725-105">Symptoms</span></span>

<span data-ttu-id="2b725-106">Planerade order genereras för fiktiva produkter när huvudplaneringen har körts.</span><span class="sxs-lookup"><span data-stu-id="2b725-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="2b725-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2b725-107">Resolution</span></span>

<span data-ttu-id="2b725-108">Inställningen för alternativet **Fiktiv** för frisläppta produkter bestämmer standardradtypen i strukturlistan (BOM).</span><span class="sxs-lookup"><span data-stu-id="2b725-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="2b725-109">När alternativet **Fiktiv** är inställt på *Ja* skapar systemet fortfarande planerade order för artikeln, men alternativet **Direkt härlett behov** för varje planerad order ställs in på *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2b725-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="2b725-110">Därför kan den planerade produktionsordern inte bekräftas på egen hand.</span><span class="sxs-lookup"><span data-stu-id="2b725-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="2b725-111">I stället inkluderas den alltid automatiskt när den överordnade produktionsordern blir bekräftad.</span><span class="sxs-lookup"><span data-stu-id="2b725-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="2b725-112">Strukturlisteraderna för den planerade fiktiva ordern inkluderas dessutom i strukturlistan för den överordnade produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="2b725-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
