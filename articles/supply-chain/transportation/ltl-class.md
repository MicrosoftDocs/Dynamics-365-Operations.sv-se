---
title: Mindre än lastbilsklasser (LTL)
description: I det här avsnittet beskrivs vad mindre än "lastbilsklasser" (LTL; "truckload") är och hur du ställer in dem i Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941820"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="76b76-103">Mindre än lastbilsklasser (LTL)</span><span class="sxs-lookup"><span data-stu-id="76b76-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76b76-104">En klass som är mindre än truckload (LTL) är en fraktleveransklass som används för att klassificera artiklar som kan levereras.</span><span class="sxs-lookup"><span data-stu-id="76b76-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="76b76-105">I allmänhet har varje typ av produkt eller vara en kod för nationell motorfraktklassificering (NMFC) som motsvarar ett specifikt fraktklassnummer för LTL-försändelser.</span><span class="sxs-lookup"><span data-stu-id="76b76-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="76b76-106">LTL-fraktklasser representerar artikelkategorier, medan NMFC-koder rör specifika varor i var och en av de 18 fraktklasserna.</span><span class="sxs-lookup"><span data-stu-id="76b76-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="76b76-107">Denna funktion låter dig använda ditt system för att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="76b76-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="76b76-108">Definiera LTL-fraktklasserna som används i företaget.</span><span class="sxs-lookup"><span data-stu-id="76b76-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="76b76-109">Tilldela varje LTL-klass till en NMFC-kod på sidan **NMFC-koder**.</span><span class="sxs-lookup"><span data-stu-id="76b76-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="76b76-110">Mer information finns i [National Motor Freight Classification (NMFC)-koder](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="76b76-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="76b76-111">Tilldela en NMFC-kod (och därmed dess tillhörande LTL-kod) till respektive produkt på sidan **Produkter**.</span><span class="sxs-lookup"><span data-stu-id="76b76-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="76b76-112">Bedöma korrekt LTL-klass för respektive produkt som en NMFC-kod har tilldelats till.</span><span class="sxs-lookup"><span data-stu-id="76b76-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="76b76-113">Fastställ förpackningskraven för varje LTL-klass genom att kontrollera de internationella LTL-standarderna.</span><span class="sxs-lookup"><span data-stu-id="76b76-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="76b76-114">På detta sätt ser du till att dina produkter är väl skyddade och levereras säkert.</span><span class="sxs-lookup"><span data-stu-id="76b76-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="76b76-115">Få korrekta leveransuppskattningar, baserat på LTL-fraktklassen för respektive produkt.</span><span class="sxs-lookup"><span data-stu-id="76b76-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="76b76-116">I detta ämne beskrivs hur du skapar LTL-klasser i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76b76-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="76b76-117">Skapa en LTL-klass</span><span class="sxs-lookup"><span data-stu-id="76b76-117">Create an LTL class</span></span>

<span data-ttu-id="76b76-118">Gör så här om du vill skapa en LTL-klass:</span><span class="sxs-lookup"><span data-stu-id="76b76-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="76b76-119">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="76b76-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="76b76-120">Gå till **Lagerstyrning \> Inställningar \> Lager \> LTL-klasser**.</span><span class="sxs-lookup"><span data-stu-id="76b76-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="76b76-121">Gå till **Transporthantering \> Inställningar \> Transportstandarder \> LTL-klasser**.</span><span class="sxs-lookup"><span data-stu-id="76b76-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="76b76-122">I åtgärdsfönstret väljer du **Ny** för att skapa en LTL-klass.</span><span class="sxs-lookup"><span data-stu-id="76b76-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="76b76-123">Ange sedan följande fält:</span><span class="sxs-lookup"><span data-stu-id="76b76-123">Then set the following fields:</span></span>

    - <span data-ttu-id="76b76-124">**LTL-klass** – Ange företagets interna LTL-klassidentifierare (ID) för varutypen.</span><span class="sxs-lookup"><span data-stu-id="76b76-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="76b76-125">De flesta företag använder den internationella standarden.</span><span class="sxs-lookup"><span data-stu-id="76b76-125">Most companies use the international standard.</span></span> <span data-ttu-id="76b76-126">I sådana fall matchar värdet i det här fältet värdet för fältet **Klass**.</span><span class="sxs-lookup"><span data-stu-id="76b76-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="76b76-127">Om ditt företag använder sin egen standard anger du dock en kod som överensstämmer med den standarden.</span><span class="sxs-lookup"><span data-stu-id="76b76-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="76b76-128">**Namn** – Ange ett beskrivande namn som gör det möjligt för dig och andra användare att välja rätt LTL-klass för varje NMFC-kod.</span><span class="sxs-lookup"><span data-stu-id="76b76-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="76b76-129">**Klass** – Ange ID för internationell standard-LTL-klass för artikeltypen.</span><span class="sxs-lookup"><span data-stu-id="76b76-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="76b76-130">Koden du anger här måste överensstämma med den officiella standarden.</span><span class="sxs-lookup"><span data-stu-id="76b76-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="76b76-131">Exempel: Konfigurera LTL-klasser</span><span class="sxs-lookup"><span data-stu-id="76b76-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="76b76-132">Följande exempel visar hur du ställer in två olika LTL-klasser som du kan använda med olika produkttyper.</span><span class="sxs-lookup"><span data-stu-id="76b76-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="76b76-133">Gå till **Lagerstyrning \> Inställningar \> Lager \> LTL-klasser**.</span><span class="sxs-lookup"><span data-stu-id="76b76-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="76b76-134">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76b76-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="76b76-135">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76b76-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76b76-136">**LTL-klass:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="76b76-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="76b76-137">**Namn:** *Datorer, monitorer, kylskåp*</span><span class="sxs-lookup"><span data-stu-id="76b76-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="76b76-138">**Klass:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="76b76-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="76b76-139">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76b76-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="76b76-140">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76b76-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="76b76-141">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76b76-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76b76-142">**LTL-klass:** *125*</span><span class="sxs-lookup"><span data-stu-id="76b76-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="76b76-143">**Namn:** *Mindre hushållsmaskiner*</span><span class="sxs-lookup"><span data-stu-id="76b76-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="76b76-144">**Klass:** *125*</span><span class="sxs-lookup"><span data-stu-id="76b76-144">**Class:** *125*</span></span>

1. <span data-ttu-id="76b76-145">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76b76-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76b76-146">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="76b76-146">Additional resources</span></span>

- [<span data-ttu-id="76b76-147">National Motor Freight Classification (NMFC)-koder</span><span class="sxs-lookup"><span data-stu-id="76b76-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="76b76-148">Skapa en fraktsedel</span><span class="sxs-lookup"><span data-stu-id="76b76-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
