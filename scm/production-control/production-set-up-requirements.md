---
title: "Inställningskrav för produktion"
description: "Det här avsnittet innehåller information om inställningar som måste göras innan du kan arbeta med produktionsstyrningen."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b5df3c6c776a8dafdcfb3be7e2f273e01d70bcae
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="production-setup-requirements"></a><span data-ttu-id="0368c-103">Inställningskrav för produktion</span><span class="sxs-lookup"><span data-stu-id="0368c-103">Production setup requirements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0368c-104">Det här avsnittet innehåller information om inställningar som måste göras innan du kan arbeta med produktionsstyrningen.</span><span class="sxs-lookup"><span data-stu-id="0368c-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="0368c-105">Produktionskontroll integreras med funktioner i andra moduler.</span><span class="sxs-lookup"><span data-stu-id="0368c-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="0368c-106">Detta gör att du kan ändra tillverkningsorder och se till att de uppdateras automatiskt i alla andra relaterade processer och beräkningar i systemet.</span><span class="sxs-lookup"><span data-stu-id="0368c-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="0368c-107">Konfigurationsprocedurerna i det här avsnittet visas i den ordning som du ska utföra dem.</span><span class="sxs-lookup"><span data-stu-id="0368c-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="0368c-108">Baslinjeinställningar som krävs i andra moduler</span><span class="sxs-lookup"><span data-stu-id="0368c-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="0368c-109">En del information måste ställas in i andra moduler för att du ska kunna arbeta med produktionsmodulen.</span><span class="sxs-lookup"><span data-stu-id="0368c-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="0368c-110">Den här konfigurationen omfattar följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="0368c-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="0368c-111">Ställa in allmän företagsinformation.</span><span class="sxs-lookup"><span data-stu-id="0368c-111">Set up general company information.</span></span>
-   <span data-ttu-id="0368c-112">Ställ in redovisningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="0368c-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="0368c-113">Definiera artikelgrupper.</span><span class="sxs-lookup"><span data-stu-id="0368c-113">Define item groups.</span></span>
-   <span data-ttu-id="0368c-114">Ställ in redovisningskonton för artikelgrupper.</span><span class="sxs-lookup"><span data-stu-id="0368c-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="0368c-115">Ställ in lagerartikelregistret i Lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="0368c-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="0368c-116">Skapa strukturlistor och strukturlisteversioner i Lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="0368c-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="0368c-117">Kalender- och resursinställningar som krävs</span><span class="sxs-lookup"><span data-stu-id="0368c-117">Required calendar and resource setup</span></span>
<span data-ttu-id="0368c-118">Innan du använder Produktionskontroll öppnar du Organisationsadministration och skapar och definierar kalendern och verksamhetsresurserna i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="0368c-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="0368c-119">**Arbetstidsmallar** – Ställ in arbetstidsmallar för att definiera de tidsperioder som är tillgängliga för produktionsplanering.</span><span class="sxs-lookup"><span data-stu-id="0368c-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="0368c-120">**Kalendrar** – Ställ in arbetstidskalendrar för att definiera vilka dagar under året som är tillgängliga för produktionsplanering.</span><span class="sxs-lookup"><span data-stu-id="0368c-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="0368c-121">**Resursgrupper** – Ställ in resursgrupper för att gruppera verksamhetsresurserna så att du kan få en översikt över ledig kapacitet när du kör planeringen.</span><span class="sxs-lookup"><span data-stu-id="0368c-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="0368c-122">Det är inte nödvändigt att ställa in resursgrupper innan du ställer in verksamhetsresurser.</span><span class="sxs-lookup"><span data-stu-id="0368c-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="0368c-123">Men vi rekommenderar att du förstår hur du grupperar resurser när du ställer in Produktionskontroll.</span><span class="sxs-lookup"><span data-stu-id="0368c-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="0368c-124">**Resurser** – Ställ in verksamhetsresurser för att definiera de resurser som används för att genomföra produktionsprocessen och planera för kapacitet.</span><span class="sxs-lookup"><span data-stu-id="0368c-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="0368c-125">Inställningar av produktionsparametrar som krävs</span><span class="sxs-lookup"><span data-stu-id="0368c-125">Required production parameters setup</span></span>
<span data-ttu-id="0368c-126">**Produktionskontrollparametrar** – Ställ in grundläggande produktionsparametrar för att definiera hur systemet hanterar och bearbetar tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="0368c-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="0368c-127">Definiera hur produktionsorder skapas, uppskattas, planeras och förbrukas.</span><span class="sxs-lookup"><span data-stu-id="0368c-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="0368c-128">Du kan också ange vilken typ av återrapportering du vill använda och hur kostnadsredovisning ska utföras.</span><span class="sxs-lookup"><span data-stu-id="0368c-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="0368c-129">Journalnamns-ID krävs</span><span class="sxs-lookup"><span data-stu-id="0368c-129">Required journal name identification</span></span>
<span data-ttu-id="0368c-130">**Produktionsjournalnamn** – Ange de produktionsjournalnamn som används för att registrera och bokföra transaktioner.</span><span class="sxs-lookup"><span data-stu-id="0368c-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="0368c-131">Inställningar om du använder operationer</span><span class="sxs-lookup"><span data-stu-id="0368c-131">Setup if you use operations</span></span>
<span data-ttu-id="0368c-132">Operationer motsvarar de specifika aktiviteter som genomförs för att producera den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="0368c-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="0368c-133">**Obs!** Du måste veta vilka typer av aktiviteter som behövs för att producera artikeln, och aktiviteternas ordning och prioritet.</span><span class="sxs-lookup"><span data-stu-id="0368c-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="0368c-134">Du måste också veta vilka resurser som är inblandade, och hur många.</span><span class="sxs-lookup"><span data-stu-id="0368c-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="0368c-135">**Åtgärder** – Ställ in åtgärder som motsvarar de uppgifter som måste genomföras för att producera den färdiga artikeln.</span><span class="sxs-lookup"><span data-stu-id="0368c-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="0368c-136">**Relationer** – Ställ in operationsrelationer för att skapa detaljerade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="0368c-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="0368c-137">Definiera åtgärdsrelationer genom att klicka på **Relationer** på sidan **Operationer** .</span><span class="sxs-lookup"><span data-stu-id="0368c-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="0368c-138">Inställningar om du använder flöden</span><span class="sxs-lookup"><span data-stu-id="0368c-138">Setup if you use routes</span></span>
<span data-ttu-id="0368c-139">Om du arbetar med flöden måste operationerna definieras för varje produktionsflöde som du ställer in.</span><span class="sxs-lookup"><span data-stu-id="0368c-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="0368c-140">Flödet motsvarar den väg som artikeln följer från operation till operation, från början till slutet av produktionsprocessen.</span><span class="sxs-lookup"><span data-stu-id="0368c-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="0368c-141">**Kostnadskategorier** – Ställ in kostnadskategorier för att definiera kostnaden per timme för angivna processer och inställningstider.</span><span class="sxs-lookup"><span data-stu-id="0368c-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="0368c-142">**Kostnadsgrupper** – Ställ in kostnadsgrupper för att skapa och underhålla olika typer av kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="0368c-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="0368c-143">**Flödesgrupper** – Ställ in flödesgrupper för att definiera parametrar som gäller för grupper med flöden.</span><span class="sxs-lookup"><span data-stu-id="0368c-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="0368c-144">Du måste ställa in flödesgrupper innan du skapar produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="0368c-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="0368c-145">**Flöden** – Ställ in produktionsflöden och definiera standardinställningar för att styra planering, kostnadsredovisning och priser för flödesoperationer, samt att kontrollera förloppsrapporter.</span><span class="sxs-lookup"><span data-stu-id="0368c-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="0368c-146">**Flöden** – Ställ in flödesversioner för att möjliggöra artikelvariationer under produktionen.</span><span class="sxs-lookup"><span data-stu-id="0368c-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="0368c-147">Valfria avancerade inställningar</span><span class="sxs-lookup"><span data-stu-id="0368c-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="0368c-148">**Produktionsgrupper** – Ställ in produktionsgrupper för att skapa relationer mellan tillverkningsordern och redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="0368c-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="0368c-149">Redovisningskontona används för att bokföra eller gruppera order för rapportering.</span><span class="sxs-lookup"><span data-stu-id="0368c-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="0368c-150">**Produktionspooler** – Skapa produktionspooler för att gruppera produktionsorder så att du kan bearbeta brådskande produktionsorder, eller för att ta bort eller bokföra grupper med order.</span><span class="sxs-lookup"><span data-stu-id="0368c-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="0368c-151">**Egenskaper** – Definiera egenskaper för att skapa särskilda attribut som du kan tilldela till resurser för att styra ordningen för produktioner.</span><span class="sxs-lookup"><span data-stu-id="0368c-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="0368c-152">De här attributen är kopplade till arbetstidsmallen.</span><span class="sxs-lookup"><span data-stu-id="0368c-152">These attributes are connected to the working time template.</span></span>





