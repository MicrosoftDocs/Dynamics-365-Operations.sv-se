---
title: Förbereda en juridisk person för konsolideringsprocessen
description: I samband med en konsolidering samlas transaktioner in från flera uppsättningar konton för juridiska personer till en enda uppsättning av konton för juridiska personer. I detta ämne beskrivs hur du förbereder en juridisk person för en konsolidering.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 07988e71276c6439e392bce2087f3a8923f5f40b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230212"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="63253-104">Förbereda en juridisk person för konsolideringsprocessen</span><span class="sxs-lookup"><span data-stu-id="63253-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63253-105">I samband med en konsolidering samlas transaktioner in från flera uppsättningar konton för juridiska personer till en enda uppsättning av konton för juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="63253-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="63253-106">I detta ämne beskrivs hur du förbereder en juridisk person för en konsolidering.</span><span class="sxs-lookup"><span data-stu-id="63253-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="63253-107">Vi rekommenderar att du använder Management Reporter för Microsoft Dynamics 365 Finance för att kombinera ekonomiska resultat för flera juridiska personer i ett konsoliderat format.</span><span class="sxs-lookup"><span data-stu-id="63253-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="63253-108">I Management Reporter kan du skapa konsoliderade ekonomiska rapporter för juridiska personer, använda Excel för att importera konsolideringsdata från andra källor, samt översätta belopp till valfritt antal rapporteringsvalutor utan att behöva köra konsolideringsprocessen i Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="63253-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="63253-109">Du kan skriva ut rapporter, till exempel bokslut, från den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="63253-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="63253-110">Du kan dock inte använda den konsoliderade juridiska personen för dagliga transaktioner.</span><span class="sxs-lookup"><span data-stu-id="63253-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="63253-111">Du kan konsolidera data från juridiska personer som använder andra databaser än databasen för den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="63253-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="63253-112">Denna konsolideringsprocess kallas för en *importkonsolidering*.</span><span class="sxs-lookup"><span data-stu-id="63253-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="63253-113">Alternativt kan de juridiska personerna använda samma databas som den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="63253-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="63253-114">Denna konsolideringsprocess kallas för en *onlinekonsolidering*.</span><span class="sxs-lookup"><span data-stu-id="63253-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="63253-115">Den konsoliderade juridiska personen samlar in resultat och saldon för dotterbolagen.</span><span class="sxs-lookup"><span data-stu-id="63253-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="63253-116">För att förbereda en konsoliderad juridisk person för en konsolidering måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="63253-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="63253-117">Gå till **Redovisning \> Inställningar \> Organisation \> Juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="63253-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="63253-118">Välj **Ny** för att skapa den juridiska person som ska utgöra konsoliderande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="63253-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="63253-119">Markera kryssrutan **Använd för ekonomisk konsolideringsprocess** och ange sedan information om den konsoliderade juridiska entiteten.</span><span class="sxs-lookup"><span data-stu-id="63253-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="63253-120">Se till att ange följande information exakt så som du vill att den ska visas i bokslut för den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="63253-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="63253-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63253-121">Close the page.</span></span>
5. <span data-ttu-id="63253-122">Välj den konsoliderade juridiska personen i fältet i sidans övre högra hörn och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="63253-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="63253-123">Gå till **Redovisning \> Inställningar \> Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="63253-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="63253-124">Välj kontoplanen, räkenskapskalendern, redovisningsvalutan, en valfri rapportvaluta och standardvalutakursen för den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="63253-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="63253-125">Gå till **Redovisning \> Inställningar \> Valuta \> Valutakurser**.</span><span class="sxs-lookup"><span data-stu-id="63253-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="63253-126">Ställa in valutakurser i relevanta perioder för valutor i juridiska personer för dotterbolag.</span><span class="sxs-lookup"><span data-stu-id="63253-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="63253-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63253-127">Close the page.</span></span>
11. <span data-ttu-id="63253-128">Om den konsoliderade juridiska personen har dotterbolag som använder utländska valutor följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="63253-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="63253-129">Gå till **Redovisning \> Inställningar \> Bokföring \> Konton för automatiska transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="63253-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="63253-130">I fältet **Bokföringstyp** väljer du ett lämpligt konto:</span><span class="sxs-lookup"><span data-stu-id="63253-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="63253-131">Om den juridiska personen har utländska dotterbolag som är ekonomiskt eller verksamhetsmässigt ömsesidigt beroende av den överordnade juridiska personen, ska du välja ett lämpligt konto för bokföringstypen **Vinst- och förlustkonto för konsolideringsdifferenser**.</span><span class="sxs-lookup"><span data-stu-id="63253-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="63253-132">Om du konsoliderar ett dotterbolag som är ekonomiskt och verksamhetsmässigt oberoende av den överordnade juridiska personen, eller en juridisk person som innehåller resultaten från flera dotterbolag som är ekonomiskt och verksamhetsmässigt oberoende av den överordnade juridiska personen, och om du använder konverteringsmetoder för konsolidering av data, ska du välja ett lämpligt konto för bokföringstypen **Saldokonto för konsolideringsskillnader**.</span><span class="sxs-lookup"><span data-stu-id="63253-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="63253-133">I fältet **Huvudkonto** väljer du det huvudkonto som ska användas för justeringar av omräkning i utländsk valuta.</span><span class="sxs-lookup"><span data-stu-id="63253-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="63253-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63253-134">Close the page.</span></span>

    <span data-ttu-id="63253-135">Om du skapar den konsoliderade juridiska personen tidigt under perioden kan du omvärdera de utländska valutabeloppen som valutakursändringar under konsolideringsperioden.</span><span class="sxs-lookup"><span data-stu-id="63253-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="63253-136">Den konsoliderade juridiska personen har nu ställts in för det periodiska jobbet **Konsolidera**.</span><span class="sxs-lookup"><span data-stu-id="63253-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="63253-137">Du kan antingen göra en importkonsolidering eller en onlinekonsolidering.</span><span class="sxs-lookup"><span data-stu-id="63253-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="63253-138">Om du vill göra en importkonsolidering går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Importera från\]**.</span><span class="sxs-lookup"><span data-stu-id="63253-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="63253-139">Om du vill göra en onlinekonsolidering går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="63253-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="63253-140">Innan du kan bearbeta konsolideringen måste du förbereda dotterbolagens juridiska personer för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="63253-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="63253-141">Mer information finns i [Skapa en juridisk person för dotterbolag för konsolidering](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="63253-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]