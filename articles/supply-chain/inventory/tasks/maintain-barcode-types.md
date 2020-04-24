---
title: Underhålla streckkodstyper
description: I den här proceduren visas hur du ställer in en ny streckkoddefinition som sedan kan användas som en del av plocklistarapporten.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 979726a1d094146b546bbc6d31963367de2c59f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204089"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="4ea2c-103">Underhålla streckkodstyper</span><span class="sxs-lookup"><span data-stu-id="4ea2c-103">Maintain barcode types</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4ea2c-104">I den här proceduren visas hur du ställer in en ny streckkoddefinition som sedan kan användas som en del av plocklistarapporten.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="4ea2c-105">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="4ea2c-106">Om du använder USMF, kan du använda exempelvärdena som visas.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="4ea2c-107">Dessa uppgifter utförs vanligtvis av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="4ea2c-108">Gå till Streckkoder.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="4ea2c-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-109">Click New.</span></span>
3. <span data-ttu-id="4ea2c-110">Ange ett värde i fältet Streckkodsinställningar.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="4ea2c-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4ea2c-112">Välj ett alternativ i fältet Streckkodstyp.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="4ea2c-113">Om du använder USMF kan du välja Code 39.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="4ea2c-114">Ange ett värde i fältet Storlek.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="4ea2c-115">Ange ett värde i fältet Maximal längd.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="4ea2c-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-116">Click Save.</span></span>
9. <span data-ttu-id="4ea2c-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-117">Close the page.</span></span>
10. <span data-ttu-id="4ea2c-118">Gå till parametrarna för hantering av lager och lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="4ea2c-119">Ange eller välj ett värde i fältet Streckkodsinställningar.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="4ea2c-120">Välj den streckkodskonfiguration du skapade tidigare, men tänk på att streckkodformatet måste matcha formatet för den unika identifieraren för posttypen som används i processen.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="4ea2c-121">För exempelvis plockflöden ska streckkodformatet matcha formatet för plockflödereferensen, som vanligtvis är en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="4ea2c-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-122">Click Save.</span></span>
13. <span data-ttu-id="4ea2c-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4ea2c-123">Close the page.</span></span>

