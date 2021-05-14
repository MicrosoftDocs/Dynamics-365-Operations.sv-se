---
title: National Motor Freight Classification (NMFC)-koder
description: I det här ämnet beskrivs hur du arbetar med NMFC-koder (National Motor Freight Classification) i Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941892"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="aa94f-103">National Motor Freight Classification (NMFC)-koder</span><span class="sxs-lookup"><span data-stu-id="aa94f-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa94f-104">Med NMFC-koder (National Motor Freight Classification) kan du klassificera artiklar som kan levereras.</span><span class="sxs-lookup"><span data-stu-id="aa94f-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="aa94f-105">NMFC-koden är en beteckning som används för att gruppera varor.</span><span class="sxs-lookup"><span data-stu-id="aa94f-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="aa94f-106">Med den kan transportföretag utvärdera varor för leverans genom att klassificera artiklar utifrån hänsyn till exempelvis lastbilsegenskaper, lastningsproblem, hanteringsproblem och ömtålighet.</span><span class="sxs-lookup"><span data-stu-id="aa94f-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="aa94f-107">Varor grupperas i en av 18 fraktklasser med ett intervall av värden mellan 50 och 500.</span><span class="sxs-lookup"><span data-stu-id="aa94f-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="aa94f-108">Klassen som en vara grupperas i baseras på en utvärdering av fyra transportegenskaper: densitet, stuvbarhet, hantering och skuld.</span><span class="sxs-lookup"><span data-stu-id="aa94f-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="aa94f-109">Tillsammans fastställer dessa egenskaper artikelns transportbarhet.</span><span class="sxs-lookup"><span data-stu-id="aa94f-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="aa94f-110">En NMFC-kod associeras med alla artiklar som är mindre än "truckload" (LTL).</span><span class="sxs-lookup"><span data-stu-id="aa94f-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="aa94f-111">Till exempel kan en bärbar dator ha tilldelats ett NMFC-nummer som har klassen 2.5, medan eluttag kan tilldelas en NMFC-klass som är 65.</span><span class="sxs-lookup"><span data-stu-id="aa94f-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="aa94f-112">Denna funktion kan hjälpa medarbetare att använda NMFC-koder för att klassificera LTL-leveransartiklar.</span><span class="sxs-lookup"><span data-stu-id="aa94f-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="aa94f-113">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="aa94f-113">Here are some examples:</span></span>

- <span data-ttu-id="aa94f-114">Om ditt företag inkluderar en fraktbeskrivning på fraktsedeln (Bill of Lading, BOL), kommer transportföretaget att ha en uppfattning om vad frakten är.</span><span class="sxs-lookup"><span data-stu-id="aa94f-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="aa94f-115">Frakt är en viktig klassificering eftersom många transportföretag bygger sin verksamhet på de typer av frakt man levererar.</span><span class="sxs-lookup"><span data-stu-id="aa94f-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="aa94f-116">Denna klassificering kan vara viktig för ditt företag eftersom den används för att bestämma kostnaden för en viss last.</span><span class="sxs-lookup"><span data-stu-id="aa94f-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="aa94f-117">Ditt företag kan identifiera lönsamhet i ett LTL-logistik- och transportföretag.</span><span class="sxs-lookup"><span data-stu-id="aa94f-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="aa94f-118">I detta ämne beskrivs hur du arbetar med NMFC-koder i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aa94f-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa94f-119">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="aa94f-119">Prerequisites</span></span>

<span data-ttu-id="aa94f-120">Innan du kan skapa NMFC-koder måste du ställa in alla LTL-fraktklasser som måste mappas till dem.</span><span class="sxs-lookup"><span data-stu-id="aa94f-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="aa94f-121">LTL-fraktklasser representerar artikelkategorier, medan NMFC-koder rör specifika varor i var och en av de 18 fraktklasserna.</span><span class="sxs-lookup"><span data-stu-id="aa94f-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="aa94f-122">Mer information om hur du arbetar med LTL-klasser finns i [Klasser som understiger truckload (LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="aa94f-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="aa94f-123">Skapa en NMFC-kod</span><span class="sxs-lookup"><span data-stu-id="aa94f-123">Create an NMFC code</span></span>

<span data-ttu-id="aa94f-124">Gör så här om du vill skapa en NMFC-kod:</span><span class="sxs-lookup"><span data-stu-id="aa94f-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="aa94f-125">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="aa94f-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="aa94f-126">Gå till **Lagerstyrning \> Inställningar \> Lager \> NMFC-koder**.</span><span class="sxs-lookup"><span data-stu-id="aa94f-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="aa94f-127">Gå till **Transporthantering \> Inställningar \> Transportstandarder \> NMFC-koder**.</span><span class="sxs-lookup"><span data-stu-id="aa94f-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="aa94f-128">Välj **Ny** för att skapa en NMFC-kod.</span><span class="sxs-lookup"><span data-stu-id="aa94f-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="aa94f-129">Ange sedan följande fält:</span><span class="sxs-lookup"><span data-stu-id="aa94f-129">Then set the following fields:</span></span>

    - <span data-ttu-id="aa94f-130">**NMFC-kod** – Ange NMFC-koden för varutypen.</span><span class="sxs-lookup"><span data-stu-id="aa94f-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="aa94f-131">**Namn** – Ange ett namn för NMFC-koden.</span><span class="sxs-lookup"><span data-stu-id="aa94f-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="aa94f-132">**LTL-klass** – Välj den LTL-klass som är associerad med NMFC-koden.</span><span class="sxs-lookup"><span data-stu-id="aa94f-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="aa94f-133">**Hanteringsenhet för BOL** – Definiera standardhanteringstyp för försändelsen.</span><span class="sxs-lookup"><span data-stu-id="aa94f-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="aa94f-134">Exempel: Konfigurera NMFC-koder</span><span class="sxs-lookup"><span data-stu-id="aa94f-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="aa94f-135">Följande exempel visar hur du ställer in två olika NMFC-koder som kan användas med olika produkter.</span><span class="sxs-lookup"><span data-stu-id="aa94f-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="aa94f-136">Gå till **Lagerstyrning \> Inställningar \> Lager \> NMFC-koder**.</span><span class="sxs-lookup"><span data-stu-id="aa94f-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="aa94f-137">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aa94f-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="aa94f-138">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="aa94f-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="aa94f-139">**NMFC-kod:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="aa94f-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="aa94f-140">**Namn:** *Datorer*</span><span class="sxs-lookup"><span data-stu-id="aa94f-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="aa94f-141">**LTL-klass:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="aa94f-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="aa94f-142">**Hanteringsenhet för BOL:** *Enhet*</span><span class="sxs-lookup"><span data-stu-id="aa94f-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="aa94f-143">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aa94f-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="aa94f-144">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aa94f-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="aa94f-145">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="aa94f-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="aa94f-146">**NMFC-kod:** *125*</span><span class="sxs-lookup"><span data-stu-id="aa94f-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="aa94f-147">**Namn:** *Telefoner*</span><span class="sxs-lookup"><span data-stu-id="aa94f-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="aa94f-148">**LTL-klass:** *125*</span><span class="sxs-lookup"><span data-stu-id="aa94f-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="aa94f-149">**Hanteringsenhet för BOL:** *Enhet*</span><span class="sxs-lookup"><span data-stu-id="aa94f-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="aa94f-150">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aa94f-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa94f-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="aa94f-151">Additional resources</span></span>

- [<span data-ttu-id="aa94f-152">Mindre än lastbilsklasser (LTL)</span><span class="sxs-lookup"><span data-stu-id="aa94f-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="aa94f-153">Skapa en fraktsedel</span><span class="sxs-lookup"><span data-stu-id="aa94f-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
