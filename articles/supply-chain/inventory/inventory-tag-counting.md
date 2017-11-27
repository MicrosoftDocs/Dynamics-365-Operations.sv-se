---
title: "Lagermärkesinventering"
description: "Det här avsnittet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0687058bc76c3ed0dad57b76d54ad57c00987f42
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-tag-counting"></a><span data-ttu-id="fcc21-103">Lagermärkesinventering</span><span class="sxs-lookup"><span data-stu-id="fcc21-103">Inventory tag counting</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="fcc21-104">Det här avsnittet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen.</span><span class="sxs-lookup"><span data-stu-id="fcc21-104">This article provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="fcc21-105">Genom att skapa rader på sidan **Märkesinventering** sätter du ett märkesnummer på varje artikel i lager, t.ex. ett tal mellan 1 och 500.</span><span class="sxs-lookup"><span data-stu-id="fcc21-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="fcc21-106">I samband med inventeringen anger du artikelnumret och kvantiteten på ett motsvarande märke.</span><span class="sxs-lookup"><span data-stu-id="fcc21-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="fcc21-107">Denna etikett kan sedan användas som bas för inmatning i märkesinventeringsjournalen.</span><span class="sxs-lookup"><span data-stu-id="fcc21-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="fcc21-108">När du bokför journalen för märkesinventering, skapas en ny inventeringsjournal baserad på sidan **Inventering**.</span><span class="sxs-lookup"><span data-stu-id="fcc21-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="fcc21-109">Den nya journalen är baserad på journalraderna för märkesinventeringen som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="fcc21-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="fcc21-110">Om du vill märkesinventera artiklar efter en viss lagerdimension väljer du dimensionen på sidan **Visa dimension** som visas när du skapar märkesinventeringsjournalen.</span><span class="sxs-lookup"><span data-stu-id="fcc21-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="fcc21-111">Inventera artiklar på exempelvis ett visst lagerställe genom att markera **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="fcc21-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="fcc21-112">Om skjutreglager **Lås artiklar under inventeringen** på sidan **Parametrar för hantering av lager och lagerstyrning** är markerad, kan inte artiklar uppdateras fysiskt under inventering.</span><span class="sxs-lookup"><span data-stu-id="fcc21-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="fcc21-113">Artiklar i märkesinventeringsjournaler inte dock inte låsta under inventering.</span><span class="sxs-lookup"><span data-stu-id="fcc21-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="fcc21-114">Lagertransaktioner skapas inte förrän märkesinventeringsraderna bokförs och överförs till en inventeringsjournal.</span><span class="sxs-lookup"><span data-stu-id="fcc21-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="fcc21-115">Om märkena anges slumpmässigt och du vill identifiera märken som saknas, klickar du på kolumnrubriken **Märke** för att sortera raderna efter märke.</span><span class="sxs-lookup"><span data-stu-id="fcc21-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

<a name="see-also"></a><span data-ttu-id="fcc21-116">Se även</span><span class="sxs-lookup"><span data-stu-id="fcc21-116">See also</span></span>
--------

[<span data-ttu-id="fcc21-117">Rullande inventering</span><span class="sxs-lookup"><span data-stu-id="fcc21-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)

