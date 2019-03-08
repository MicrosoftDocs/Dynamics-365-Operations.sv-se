---
title: Skapa en försäljningsorder för en konfigurerbar produkt
description: Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 882198bf07233867b54579b986f93f5c1b46c1b6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "364751"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="c2582-103">Skapa en försäljningsorder för en konfigurerbar produkt</span><span class="sxs-lookup"><span data-stu-id="c2582-103">Create a sales order for a configurable product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2582-104">Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c2582-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="c2582-105">Detta exempel använder högtalarmodellen D0006 i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="c2582-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="c2582-106">Vanligtvis använder en försäljningsorderbehandlare denna procedur.</span><span class="sxs-lookup"><span data-stu-id="c2582-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="c2582-107">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c2582-107">Create a sales order</span></span>
1. <span data-ttu-id="c2582-108">Klicka på Bearbetning och förfrågan om försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c2582-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="c2582-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2582-109">Click New.</span></span>
3. <span data-ttu-id="c2582-110">Klicka på Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c2582-110">Click Sales order.</span></span>
4. <span data-ttu-id="c2582-111">Välj US-001 i fältet Customer account.</span><span class="sxs-lookup"><span data-stu-id="c2582-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="c2582-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c2582-112">Click OK.</span></span>
6. <span data-ttu-id="c2582-113">Välj D0006 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="c2582-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="c2582-114">För den här uppgiften måste du välja en konfigurerbar produkt.</span><span class="sxs-lookup"><span data-stu-id="c2582-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="c2582-115">Klicka på Produkt och leverans.</span><span class="sxs-lookup"><span data-stu-id="c2582-115">Click Product and supply.</span></span>
8. <span data-ttu-id="c2582-116">Klicka på Konfigurera rad.</span><span class="sxs-lookup"><span data-stu-id="c2582-116">Click Configure line.</span></span>
    * <span data-ttu-id="c2582-117">Observera att priset har ändrats baserat på den konfiguration som valdes, och att fältet Include cable nu anges som true.</span><span class="sxs-lookup"><span data-stu-id="c2582-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="c2582-118">Observera valt standardpris och valda inställningar för kabeln.</span><span class="sxs-lookup"><span data-stu-id="c2582-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="c2582-119">Klicka på Ladda mall..</span><span class="sxs-lookup"><span data-stu-id="c2582-119">Click Load template.</span></span>
    * <span data-ttu-id="c2582-120">I det här exemplet visas hur du kan använda en mall för att välja en fördefinierad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c2582-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="c2582-121">Om du använder den här proceduren som en uppgiftsguide och vill se andra tillgängliga attributvärden, måste du klicka på knappen Unlock.</span><span class="sxs-lookup"><span data-stu-id="c2582-121">If you’re using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="c2582-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c2582-122">Click OK.</span></span>
11. <span data-ttu-id="c2582-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c2582-123">Click OK.</span></span>
12. <span data-ttu-id="c2582-124">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="c2582-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="c2582-125">Klicka på fliken Produkt.</span><span class="sxs-lookup"><span data-stu-id="c2582-125">Click the Product tab.</span></span>
    * <span data-ttu-id="c2582-126">Artikelns konfiguration anges nu under produktdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="c2582-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="c2582-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c2582-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="c2582-128">Välj produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c2582-128">Select the product configuration</span></span>

