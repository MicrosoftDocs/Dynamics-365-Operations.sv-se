---
title: Prisrapporter för Retail
description: Det här avsnittet innehåller en översikt över prisrapportfunktionen som kan användas för att visa kommande prisändringarna för de utvalda produkterna.
author: shajain
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 6db6d1c6b6eb1d69b40fe75d97eeb71564986707
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "353067"
---
# <a name="retail-price-reports"></a><span data-ttu-id="e5266-103">Prisrapporter för Retail</span><span class="sxs-lookup"><span data-stu-id="e5266-103">Retail price reports</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]


<span data-ttu-id="e5266-104">För att kunna förse kunderna med konkurrenskraftiga priser ändrar återförsäljare ofta priserna på produkter.</span><span class="sxs-lookup"><span data-stu-id="e5266-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="e5266-105">Butikschefer vill ha möjlighet att enkelt komma åt tidigare eller kommande prisändringar så att de kan planera för resurserna som krävs för att uppdatera prisetiketterna som visas på butikshyllorna.</span><span class="sxs-lookup"><span data-stu-id="e5266-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="e5266-106">Med versionen 10.0 av Dynamics 365 for Retail kan butikschefen öppna rapporten **Pris** genom att gå till **Alla butiker \> Butik \> Prisrapport** och visa de uppdaterade priserna för produkter som är kopplade till butiken.</span><span class="sxs-lookup"><span data-stu-id="e5266-106">With release 10.0 of Dynamics 365 for Retail, a store manager can open the **Price** report by navigating to **All retail stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="e5266-107">För att aktivera prisrapporten måste parametern **Aktivera prisrapport för butik** vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e5266-107">To enable the price report, the **Enable price report for Retail store** parameter must be turned on.</span></span> <span data-ttu-id="e5266-108">Denna parameter finns på fliken **Butiksparametrar \> Rabatter \> Ddiverse**. När du öppnar sidan **Prisrapport** visas en dialogruta med olika konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e5266-108">This parameter is located on the **Retail parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="e5266-109">Nedan finns tillgängliga konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e5266-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="e5266-110">Inställningar</span><span class="sxs-lookup"><span data-stu-id="e5266-110">Configuration</span></span> | <span data-ttu-id="e5266-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="e5266-111">Description</span></span> |
|---|---|
| <span data-ttu-id="e5266-112">Datum från/datum till</span><span class="sxs-lookup"><span data-stu-id="e5266-112">From date / To date</span></span>| <span data-ttu-id="e5266-113">Datumintervallet som prisrapporten ska genereras för.</span><span class="sxs-lookup"><span data-stu-id="e5266-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="e5266-114">Varaktigheten är för närvarande begränsad till 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="e5266-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="e5266-115">Kanal</span><span class="sxs-lookup"><span data-stu-id="e5266-115">Channel</span></span>| <span data-ttu-id="e5266-116">Butiken som prisrapporten ska genereras för.</span><span class="sxs-lookup"><span data-stu-id="e5266-116">The retail store for which the price report should be generated.</span></span> |
| <span data-ttu-id="e5266-117">Visa produkter med tillgängligt lager</span><span class="sxs-lookup"><span data-stu-id="e5266-117">Display products with available inventory</span></span>| <span data-ttu-id="e5266-118">Om detta anges till **Ja** visas priserna för produkter som för närvarande har fysiskt lager tillgängligt i butiken.</span><span class="sxs-lookup"><span data-stu-id="e5266-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="e5266-119">Visa priser för varianter</span><span class="sxs-lookup"><span data-stu-id="e5266-119">Display prices for variants</span></span> | <span data-ttu-id="e5266-120">Om detta anges till **Ja** visas priser för varianterna tillsammans med produktmallarna.</span><span class="sxs-lookup"><span data-stu-id="e5266-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="e5266-121">Detta bör endast aktiveras till **På** om du har variantspecifika priser eftersom antalet rader blir mycket stort.</span><span class="sxs-lookup"><span data-stu-id="e5266-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="e5266-122">I framtida versioner kan vi aktivera dimensionsbaserade priser så att butikschefen kan välja dimensioner som priserna ska visas för.</span><span class="sxs-lookup"><span data-stu-id="e5266-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="e5266-123">Visa produkter med prisändringar</span><span class="sxs-lookup"><span data-stu-id="e5266-123">Display products with price changes</span></span> | <span data-ttu-id="e5266-124">Om du anger detta till **Ja** visas priserna endast för de datum då priset har ändrats.</span><span class="sxs-lookup"><span data-stu-id="e5266-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="e5266-125">Priset för *en dag före* det valda **från datumet** kommer alltid att visas, så att butikschefen enkelt kan identifiera de produkter som inte har ändrade priser under hela valda varaktigheten och kan också visa det aktuella priset.</span><span class="sxs-lookup"><span data-stu-id="e5266-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="e5266-126">När rapporten har skapats kan Excel-filen hämtas för eventuella ytterligare filtreringsbehov.</span><span class="sxs-lookup"><span data-stu-id="e5266-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="e5266-127">Prisrapporten kan också användas för att kontrollera historiska priser för produkter för tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="e5266-127">The price report can also be used to check the historical prices of products for past dates.</span></span>
