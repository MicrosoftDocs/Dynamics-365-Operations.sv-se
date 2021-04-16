---
title: Skapa och uppdatera öppettider
description: I det här avsnittet beskrivs hur du skapar och uppdaterar öppettider i administration för Handel.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 862b032c75145594be78fb2f4e27ea5616605c4d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792939"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="c999e-103">Skapa och uppdatera öppettider</span><span class="sxs-lookup"><span data-stu-id="c999e-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="c999e-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="c999e-104">Overview</span></span>

<span data-ttu-id="c999e-105">Från en enda plats kan återförsäljare skapa, underhålla och hantera öppettiderna för olika butiker över geografiska regioner.</span><span class="sxs-lookup"><span data-stu-id="c999e-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="c999e-106">Öppettiderna kan sedan visas på kassaterminalerna.</span><span class="sxs-lookup"><span data-stu-id="c999e-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="c999e-107">På så sätt kan kassörerna dela med sig av öppettiderna till kunder och bättre hjälpa dem som är intresserade av lager i andra butiker.</span><span class="sxs-lookup"><span data-stu-id="c999e-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="c999e-108">Öppettiderna kan också skrivas ut på kvitton om kunder vill gå tillbaka till butiken senare.</span><span class="sxs-lookup"><span data-stu-id="c999e-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="c999e-109">Det går att konfigurera flera öppettider för olika kanaler.</span><span class="sxs-lookup"><span data-stu-id="c999e-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="c999e-110">Dessa kanaler är bland annat fysiska butiker, kundtjänster, mobila enheter och näthandelsplatser.</span><span class="sxs-lookup"><span data-stu-id="c999e-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="c999e-111">Om en kund har en upphämtningsorder för en annan butik, kan kassören välja datum när upphämtningen blir tillgänglig i den butiken.</span><span class="sxs-lookup"><span data-stu-id="c999e-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="c999e-112">Butikssökningen ger en referens till datumen och öppettiderna.</span><span class="sxs-lookup"><span data-stu-id="c999e-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="c999e-113">Kassören kan välja ett datum och en plats, och kan också skriva ut ett upphämtningskvitto som inkluderar öppettiderna.</span><span class="sxs-lookup"><span data-stu-id="c999e-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="c999e-114">Den här funktionen är tillgänglig i Microsoft Dynamics 365 Retail version 8.1.2 och senare versioner.</span><span class="sxs-lookup"><span data-stu-id="c999e-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="c999e-115">Konfigurera butikens öppettider</span><span class="sxs-lookup"><span data-stu-id="c999e-115">Configure store hours</span></span>

<span data-ttu-id="c999e-116">Om du vill konfigurera butikens öppettider, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c999e-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="c999e-117">Gå till **Butik och handel** \> **Kanalinställningar** \> **Butikens öppettider**.</span><span class="sxs-lookup"><span data-stu-id="c999e-117">Go to **Retail and Commerce** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="c999e-118">Välj **Ny** om du vill skapa en ny mall för butikens öppettider.</span><span class="sxs-lookup"><span data-stu-id="c999e-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="c999e-119">Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="c999e-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="c999e-120">I dialogrutan **Lägg till intervall** definierar du datumintervallet, öppettiderna och eventuella helgdagar som krävs.</span><span class="sxs-lookup"><span data-stu-id="c999e-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="c999e-121">Om öppettiderna inte ändras väljer du **Slutar aldrig** i fältet **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="c999e-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="c999e-122">Om öppettiderna gäller en viss månad, vecka eller dag ställer du in lämpliga datum i fälten **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="c999e-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c999e-123">Du kan skapa flera mallar med överlappande start- och slutdatum.</span><span class="sxs-lookup"><span data-stu-id="c999e-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="c999e-124">Därför kan du t.ex. definiera öppettider för butiker i olika tidszoner.</span><span class="sxs-lookup"><span data-stu-id="c999e-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="c999e-125">![Dialogrutan Lägg till intervall](../dev-itpro/media/Storehours1.png "Dialogrutan Lägg till intervall")</span><span class="sxs-lookup"><span data-stu-id="c999e-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="c999e-126">Associera mallen för öppettider med butikerna där den ska användas.</span><span class="sxs-lookup"><span data-stu-id="c999e-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="c999e-127">I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.</span><span class="sxs-lookup"><span data-stu-id="c999e-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="c999e-128">Det går bara att associera en öppettidsmall till varje butik.</span><span class="sxs-lookup"><span data-stu-id="c999e-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="c999e-129">Välj butiker, regioner eller organisationer med pilknapparna.</span><span class="sxs-lookup"><span data-stu-id="c999e-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="c999e-130">Kalendern kommer att vara tillgänglig för butikerna eller butiksgrupperna och den visas i kassan för referens.</span><span class="sxs-lookup"><span data-stu-id="c999e-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="c999e-131">![Dialogrutan Välj organisationsnoder](../dev-itpro/media/Storehours2.png "Dialogrutan Välj organisationsnoder")</span><span class="sxs-lookup"><span data-stu-id="c999e-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="c999e-132">På sidan **Distributionsschema**, kör du jobben **1070** och **1090** för att göra öppettiderna tillgängliga för kassan.</span><span class="sxs-lookup"><span data-stu-id="c999e-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="c999e-133">Lägga till öppettider på utskrivna kvitton</span><span class="sxs-lookup"><span data-stu-id="c999e-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="c999e-134">Följ dessa steg för att lägga till öppettider på de utskrivna kassakvittona.</span><span class="sxs-lookup"><span data-stu-id="c999e-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="c999e-135">Öppna kvittodesignern.</span><span class="sxs-lookup"><span data-stu-id="c999e-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="c999e-136">Välj **Sidfot** i det nedre vänstra hörnet.</span><span class="sxs-lookup"><span data-stu-id="c999e-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="c999e-137">Dra elementet **Butikens öppettider** från det vänstra fönstret till sidfoten längst ned i kvittomallen.</span><span class="sxs-lookup"><span data-stu-id="c999e-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="c999e-138">Du kan redigera standardetiketten i elementet **Butikens öppettider** efter behov.</span><span class="sxs-lookup"><span data-stu-id="c999e-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="c999e-139">Spara kvittot och stäng kvittodesignern.</span><span class="sxs-lookup"><span data-stu-id="c999e-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="c999e-140">På sidan **Distributionsschema** kör du jobben **1070** och **1090**.</span><span class="sxs-lookup"><span data-stu-id="c999e-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="c999e-141">Logga in i kassan.</span><span class="sxs-lookup"><span data-stu-id="c999e-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="c999e-142">Slutför en försäljning och välj att skriva ut ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="c999e-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="c999e-143">I kassakvitton ingår nu butikens öppettider.</span><span class="sxs-lookup"><span data-stu-id="c999e-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="c999e-144">Om helgdagar inkluderades i mallen visas de på kvittot.</span><span class="sxs-lookup"><span data-stu-id="c999e-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="c999e-145">![Kvittoexempel](../dev-itpro/media/Storehours3.png "Kvittoexempel")</span><span class="sxs-lookup"><span data-stu-id="c999e-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]