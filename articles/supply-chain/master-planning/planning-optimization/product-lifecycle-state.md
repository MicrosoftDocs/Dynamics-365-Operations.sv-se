---
title: Uteslut produkter som har specifika produktlivscykeltillstånd
description: I det här avsnittet beskrivs hur du utesluter produkter baserat på deras livscykeltillstånd när funktionen för optimering av planeringen används.
author: ChristianRytt
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7028a509aa884589958542f7ec627d69dffcfcec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839257"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="3c8c7-103">Uteslut produkter som har specifika produktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="3c8c7-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c8c7-104">Frisläppta produkter och frisläppta produktversioner inkluderar fältet **produkt livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="3c8c7-105">I det här fältet kan du bland annat bestämma vilka produkter som ska inkluderas under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="3c8c7-106">Du kan lägga till, ta bort och redigera livscykeltillstånd efter behov genom att gå till **produktinformationshanterings \> installation \> produktcykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="3c8c7-107">Ställ in för varje produkts livscykeltillstånd alternativet **Är aktiv för planering** till *Ja* om produkter som har den staten ska inkluderas under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="3c8c7-108">När alternativet är inställt på *Nej*, kommer associerade produkter och varianter att undantas från all huvudplanering och alla beräkningar på strukturnivån.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="3c8c7-109">Släppta produkter och varianter där fältet **Produktens livscykeltillstånd** lämnas tomt behandlas som om de har ett tillstånd för produktens livscykel där **Är aktiv för planering** anges till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="3c8c7-110">De kommer med andra ord att inkluderas under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="3c8c7-111">För att undvika onödiga förslag på leveranser rekommenderar vi starkt att du associerar alla föråldrade släppta produkter och varianter till ett produktlivscykeltillstånd där **Är aktiv för planering** anges till *Nej*.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="3c8c7-112">Den här metoden är särskilt viktig när du arbetar med varianter av produktkonfiguration som inte kan återanvändas, eftersom det bidrar till att undvika avfall.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3c8c7-113">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="3c8c7-113">Related resources</span></span>

<span data-ttu-id="3c8c7-114">Mer information om tillstånd för produktens livscykel finns i [Produktens livscykeltillstånd - översikt](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="3c8c7-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="3c8c7-115">Detaljerad information som inkluderar steg för hur du använder produktlivscykeltillstånd för att undanta produkter från huvudplanering och strukturlistenivåberäkningar, se [skapa ett produktlivscykeltillstånd från huvudplaneringen](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="3c8c7-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]