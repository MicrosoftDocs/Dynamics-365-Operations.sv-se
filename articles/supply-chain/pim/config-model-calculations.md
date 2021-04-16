---
title: Beräkningar för produktkonfigurationsmodell
description: Det här avsnittet beskriver hur man skapar beräkningar för attribut i en produktkonfigurationsmodell
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829628"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="b429b-103">Beräkningar för produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="b429b-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b429b-104">Det här avsnittet beskriver hur man skapar beräkningar för attribut i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="b429b-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b429b-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b429b-105">Prerequisites</span></span>

<span data-ttu-id="b429b-106">Beräkningar används i en produktkonfigurationsmodell för att beräkna konfigurationsvärden för en produkt.</span><span class="sxs-lookup"><span data-stu-id="b429b-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="b429b-107">Innan du kan börja ställa in beräkningar måste den relaterade produktkonfigurationsmodellen finnas.</span><span class="sxs-lookup"><span data-stu-id="b429b-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="b429b-108">En översikt över inställningsprocessen för konfigurationsmodeller och relaterade uppgifter finns i [Ställa in en produktkonfigurationsmodell](set-up-maintain-product-configuration-model.md). </span><span class="sxs-lookup"><span data-stu-id="b429b-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="b429b-109">Skapa en beräkning</span><span class="sxs-lookup"><span data-stu-id="b429b-109">Create a calculation</span></span>

<span data-ttu-id="b429b-110">En beräkning består av ett uttryck och ett målattribut.</span><span class="sxs-lookup"><span data-stu-id="b429b-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="b429b-111">För mer information, se [Frågor och Svar - Beräkningar för produktkonfigurationsmodeller](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="b429b-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="b429b-112">Följ de här stegen om du vill skapa en beräkning för en befintlig produktmodell.</span><span class="sxs-lookup"><span data-stu-id="b429b-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="b429b-113">Gå till **Produktinformationshantering \> Allmänt \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="b429b-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="b429b-114">Öppna en produktkonfigurationsmodell och klicka sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b429b-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="b429b-115">På snabbfliken **Beräkningar** välj **Lägg till** för att lägga till en beräkning och anger sedan följande fält:</span><span class="sxs-lookup"><span data-stu-id="b429b-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="b429b-116">**Namn** – Ange ett namn för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="b429b-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="b429b-117">**Beskrivning** – Ange en beskrivning av beräkningen.</span><span class="sxs-lookup"><span data-stu-id="b429b-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="b429b-118">**Målattribut** – Välj det attribut som du ska utföra beräkningen för.</span><span class="sxs-lookup"><span data-stu-id="b429b-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="b429b-119">Välj **Redigera uttryck**.</span><span class="sxs-lookup"><span data-stu-id="b429b-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="b429b-120">I dialogrutan **Ange en beräkning**, lägg till önskade attribut, operatorer och värden i uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b429b-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="b429b-121">Mer information om hur du arbetar med dessa element finns i [Uttrycksbegränsningar och registerbegränsningar i modeller för produktkonfiguration](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="b429b-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="b429b-122">När uttrycket är klart väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="b429b-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="b429b-123">Beräkningsexempel</span><span class="sxs-lookup"><span data-stu-id="b429b-123">Calculation examples</span></span>

<span data-ttu-id="b429b-124">Det här avsnittet innehåller några exempel som visar hur beräkningar fungerar.</span><span class="sxs-lookup"><span data-stu-id="b429b-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="b429b-125">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b429b-125">Example 1</span></span>

<span data-ttu-id="b429b-126">Målattributet är booleskt och beräkningen använder följande villkorliga uttryck:</span><span class="sxs-lookup"><span data-stu-id="b429b-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="b429b-127">Detta uttryck returnerar värdet *sant* till målattributet, om `decimalAttribute2` är större än eller lika med `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="b429b-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="b429b-128">Annars returnerar värdet *Falsk*.</span><span class="sxs-lookup"><span data-stu-id="b429b-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="b429b-129">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b429b-129">Example 2</span></span>

<span data-ttu-id="b429b-130">I det här exemplet används textattributet `textFixedList` som målattribut.</span><span class="sxs-lookup"><span data-stu-id="b429b-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="b429b-131">Detta attribut innehåller följande fasta listor.</span><span class="sxs-lookup"><span data-stu-id="b429b-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="b429b-132">Värde</span><span class="sxs-lookup"><span data-stu-id="b429b-132">Value</span></span> | <span data-ttu-id="b429b-133">Lösarvärde</span><span class="sxs-lookup"><span data-stu-id="b429b-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="b429b-134">A</span><span class="sxs-lookup"><span data-stu-id="b429b-134">A</span></span> | <span data-ttu-id="b429b-135">1a</span><span class="sxs-lookup"><span data-stu-id="b429b-135">1a</span></span> |
| <span data-ttu-id="b429b-136">B</span><span class="sxs-lookup"><span data-stu-id="b429b-136">B</span></span> | <span data-ttu-id="b429b-137">2b</span><span class="sxs-lookup"><span data-stu-id="b429b-137">2b</span></span> |
| <span data-ttu-id="b429b-138">C</span><span class="sxs-lookup"><span data-stu-id="b429b-138">C</span></span> | <span data-ttu-id="b429b-139">2c</span><span class="sxs-lookup"><span data-stu-id="b429b-139">2c</span></span> |

<span data-ttu-id="b429b-140">Följande skärmbild visar hur inställningarna för det här attributet kan se ut i systemet.</span><span class="sxs-lookup"><span data-stu-id="b429b-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="b429b-141">![Attributtypsinställningar, t.ex. 2](media/model-calculations-example2.png "Attributtypsinställningar, t.ex. 2")</span><span class="sxs-lookup"><span data-stu-id="b429b-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="b429b-142">Attributet används i följande villkorsutdrag:</span><span class="sxs-lookup"><span data-stu-id="b429b-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="b429b-143">Om `integerAttribute` är värdet mindre 150 returnerar den här satsen textvärdet för den första posten i den fasta listan, *A*. Annars returnerar det textvärdet för den tredje posten i den fasta listan, *C*.</span><span class="sxs-lookup"><span data-stu-id="b429b-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="b429b-144">Den fasta listan motsvarar en nollbaserad uppräkning (enum) och dess värden får åtkomst till av lämpligt heltalsvärde.</span><span class="sxs-lookup"><span data-stu-id="b429b-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="b429b-145">Därför matchas det första fasta listvärdet (*A*) matchas till *0*, det andra värdet (*B*) matchas till *1* och tredje värdet (*C*) matchas till *2*.</span><span class="sxs-lookup"><span data-stu-id="b429b-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="b429b-146">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="b429b-146">Example 3</span></span>

<span data-ttu-id="b429b-147">I det här exemplet används målattributet `textFixedList` från föregående exemplet.</span><span class="sxs-lookup"><span data-stu-id="b429b-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="b429b-148">Det använder även ett annat textattribut `textAttribute`, som innehåller följande fasta listor.</span><span class="sxs-lookup"><span data-stu-id="b429b-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="b429b-149">Värde</span><span class="sxs-lookup"><span data-stu-id="b429b-149">Value</span></span> | <span data-ttu-id="b429b-150">Lösarvärde</span><span class="sxs-lookup"><span data-stu-id="b429b-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="b429b-151">AA</span><span class="sxs-lookup"><span data-stu-id="b429b-151">AA</span></span> | <span data-ttu-id="b429b-152">1aa</span><span class="sxs-lookup"><span data-stu-id="b429b-152">1aa</span></span> |
| <span data-ttu-id="b429b-153">BB</span><span class="sxs-lookup"><span data-stu-id="b429b-153">BB</span></span> | <span data-ttu-id="b429b-154">2bb</span><span class="sxs-lookup"><span data-stu-id="b429b-154">2bb</span></span> |

<span data-ttu-id="b429b-155">Följande skärmbild visar hur inställningarna för det här attributet kan se ut i systemet.</span><span class="sxs-lookup"><span data-stu-id="b429b-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="b429b-156">![Attributtypsinställningar, t.ex. 3](media/model-calculations-example3.png "Attributtypsinställningar, t.ex. 3")</span><span class="sxs-lookup"><span data-stu-id="b429b-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="b429b-157">Värdet för `textFixedList` attributet beräknas med hjälp av följande villkorsutdrag:</span><span class="sxs-lookup"><span data-stu-id="b429b-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="b429b-158">Om värdet `textAttribute` har löst värdet som är lika med *1aa*, detta uttryck returnerar textvärdet för den första posten i `textFixedList` fast lista, *A*. Annars returnerar den textvärdet för den tredje posten i `textFixedList` fast lista, *C*.</span><span class="sxs-lookup"><span data-stu-id="b429b-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="b429b-159">I det villkorliga uttrycket måste solvervärdet i attributet användas.</span><span class="sxs-lookup"><span data-stu-id="b429b-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="b429b-160">Endast textattribut med fast lista kan användas i beräkningar.</span><span class="sxs-lookup"><span data-stu-id="b429b-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="b429b-161">Se även</span><span class="sxs-lookup"><span data-stu-id="b429b-161">See also</span></span>

- [<span data-ttu-id="b429b-162">Frågor och Svar - Beräkningar för produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="b429b-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="b429b-163">Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="b429b-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="b429b-164">Översikt över produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="b429b-164">Product configuration models overview</span></span>](product-configuration-models.md)
