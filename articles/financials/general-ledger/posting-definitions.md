---
title: Bokföringsdefinitioner
description: Det här avsnittet innehåller information om bokföringsdefinitioner och hur du definierar och länkar dem. För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88e9d1e593f58e8fc9e12ddac7664b6e67ecda6a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561024"
---
# <a name="posting-definitions"></a><span data-ttu-id="562d6-104">Bokföringsdefinitioner</span><span class="sxs-lookup"><span data-stu-id="562d6-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="562d6-105">Det här avsnittet innehåller information om bokföringsdefinitioner och hur du definierar och länkar dem.</span><span class="sxs-lookup"><span data-stu-id="562d6-105">This article provides information about posting definitions, and how to define and link them.</span></span> <span data-ttu-id="562d6-106">För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="562d6-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span>

<span data-ttu-id="562d6-107">För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="562d6-107">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="562d6-108">Du kan visa dokumenten och bokföringstyperna på sidan **Bokföringsdefinitioner för transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="562d6-108">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="562d6-109">Börja använda bokföringsdefinitionerna genom att välja **Använd bokföringsdefinitioner** på sidan **Allmänna huvudboksparametrar**.</span><span class="sxs-lookup"><span data-stu-id="562d6-109">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="562d6-110">Även om du använder bokföringsdefinitioner måste du fortfarande definiera bokföringsprofiler för de ursprungliga posterna och bokföringstyper och dokument som inte stöds.</span><span class="sxs-lookup"><span data-stu-id="562d6-110">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="562d6-111">Du måste använda bokföringsdefinitioner för att kunna aktivera inteckningsredovisning för inköpsorder och förinteckningsredovisning för inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="562d6-111">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="562d6-112">Definiera bokföringsdefinitioner</span><span class="sxs-lookup"><span data-stu-id="562d6-112">Defining posting definitions</span></span>
<span data-ttu-id="562d6-113">Använd sidan **Bokföringsdefinitioner** för att ange matchningsvillkoren och definiera de poster som ska genereras när en matchning inträffar.</span><span class="sxs-lookup"><span data-stu-id="562d6-113">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="562d6-114">Matchningsvillkoren utvärderas för de ursprungliga posterna som redovisningsfördelningar.</span><span class="sxs-lookup"><span data-stu-id="562d6-114">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="562d6-115">På sidan **Bokföringsdefinitioner** kan du också tilldela prioritetnummer till postrader för att styra ordningen som raderna utvärderas i.</span><span class="sxs-lookup"><span data-stu-id="562d6-115">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="562d6-116">Raderna som har lägst prioritet utvärderas först.</span><span class="sxs-lookup"><span data-stu-id="562d6-116">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="562d6-117">Exempelvis utvärderas alla rader som har prioriteten 1, sedan raderna med prioriteten 2 osv.</span><span class="sxs-lookup"><span data-stu-id="562d6-117">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="562d6-118">När en matchning hittas ignoreras de andra matchvillkoren.</span><span class="sxs-lookup"><span data-stu-id="562d6-118">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="562d6-119">Dessutom är det endast kriterierna i gruppen som matchar den ursprungliga transaktionen som resulterar i genererade poster.</span><span class="sxs-lookup"><span data-stu-id="562d6-119">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="562d6-120">Du kan validera dina bokföringsdefinitioner med guiden **Testbokföringsdefinition**.</span><span class="sxs-lookup"><span data-stu-id="562d6-120">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="562d6-121">När du har definierat ett prov från posten för en bokföringsdefinition visas de genererade posterna.</span><span class="sxs-lookup"><span data-stu-id="562d6-121">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="562d6-122">Du kan använda bokföringsdefinitionsversioner tillsammans med giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="562d6-122">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="562d6-123">Du kan till exempel skapa en kommande version av en bokföringsdefinition när du vill bokföra på ett annat redovisningskonto i ett nytt räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="562d6-123">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="562d6-124">Använd sidan **Bokföringsdefinitioner för transaktioner** för att koppla bokföringsdefinitioner till transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="562d6-124">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="562d6-125">Länka bokföringsdefinitioner</span><span class="sxs-lookup"><span data-stu-id="562d6-125">Linking posting definitions</span></span>
<span data-ttu-id="562d6-126">Du kan länka från en bokföringsdefinition till en annan när du skapar bokföringsdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="562d6-126">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="562d6-127">Villkoren för definitionen som du länkar till beaktas sedan tillsammans med villkoren för den aktuella bokföringsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="562d6-127">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="562d6-128">Den här funktionen gör att du kan du spara tid, eftersom du inte behöver ange kriterier igen på snabbfliken **Poster** på sidan **Bokföringsdefinitioner** för den aktuella bokföringsdefinitionen, om du redan har angett raderna för en annan definition.</span><span class="sxs-lookup"><span data-stu-id="562d6-128">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="562d6-129">Inkludera eventuella länkar som du kan använda i diagrammen eller registren.</span><span class="sxs-lookup"><span data-stu-id="562d6-129">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="562d6-130">Undvik konflikter med den aktuella bokföringsdefinitionen genom att se till att raderna i alla bokföringsdefinitioner som du länkar är unika.</span><span class="sxs-lookup"><span data-stu-id="562d6-130">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="562d6-131">Följande restriktioner gäller när du skapar länkar i bokföringsdefinitioner:</span><span class="sxs-lookup"><span data-stu-id="562d6-131">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="562d6-132">En bokföringsdefinition kan antingen länka till en annan bokföringsdefinition eller länkas till från en annan bokföringsdefinition, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="562d6-132">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="562d6-133">Du kan dock länka en bokföringsdefinition till flera bokföringsdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="562d6-133">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="562d6-134">Du kan bara ställa in länkar mellan bokföringsdefinitioner som finns i samma modulen.</span><span class="sxs-lookup"><span data-stu-id="562d6-134">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="562d6-135">Du kan koppla en bokföringsdefinition till en valfri transaktionstyp, men transaktionstypen måste finnas i samma modul som bokföringsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="562d6-135">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="562d6-136">Använd sidan **Bokföringsdefinitioner för transaktioner** för att se vilken modul en transaktionstyp finns i.</span><span class="sxs-lookup"><span data-stu-id="562d6-136">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="562d6-137">Mer information finns i [Exempel på bokföringsdefinitioner](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="562d6-137">For more information, see [Posting definitions examples](example-posting-definitions.md).</span></span> 


