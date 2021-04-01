---
title: Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller.
description: I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar. Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder. Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 989981e6ca8c1075367776ceafe5b88429e004d2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243235"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="8eedf-105">Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="8eedf-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8eedf-106">I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="8eedf-107">Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8eedf-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="8eedf-108">Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="8eedf-109">Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8eedf-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="8eedf-110">Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="8eedf-111">Vad är uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="8eedf-111">What are expression constraints?</span></span>
<span data-ttu-id="8eedf-112">Uttrycksbegränsningar karakteriseras av ett uttryck som använder aritmetiska och booleska operatorer och funktioner.</span><span class="sxs-lookup"><span data-stu-id="8eedf-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="8eedf-113">En uttrycksbegränsning skrivs för en viss komponent i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="8eedf-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="8eedf-114">Den kan inte återanvändas av eller delas med en annan komponent.</span><span class="sxs-lookup"><span data-stu-id="8eedf-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="8eedf-115">Uttryckbegränsningarna för en komponent kan dock referera till attribut i komponentens delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="8eedf-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="8eedf-116">Vad är registerbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="8eedf-116">What are table constraints?</span></span>
<span data-ttu-id="8eedf-117">Registerbegränsningar anger de kombinationer av värden som tillåts för attribut när du konfigurerar en produkt.</span><span class="sxs-lookup"><span data-stu-id="8eedf-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="8eedf-118">Registerbegränsningdefinitioner kan användas i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="8eedf-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="8eedf-119">När du skapar en registerbegränsning för en komponent i en modell för produktkonfiguration, väljer du en registerbegränsningsdefinition.</span><span class="sxs-lookup"><span data-stu-id="8eedf-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="8eedf-120">Om du vill skapa de tillåtna kombinationerna, lägger du till attribut för specifika typer till komponenterna.</span><span class="sxs-lookup"><span data-stu-id="8eedf-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="8eedf-121">Varje attributtyp har ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="8eedf-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="8eedf-122">Exempel på registerbegränsning.</span><span class="sxs-lookup"><span data-stu-id="8eedf-122">Example of a table constraint</span></span>

<span data-ttu-id="8eedf-123">I det här exemplet visas hur du kan begränsa konfigurationen för en högtalare till specifika kabinettfinish och framdelar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="8eedf-124">Den första tabellen visar storlekar och typer av kabinettfinish och framdelar som är allmänt tillgängliga för konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8eedf-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="8eedf-125">Du definierar värdena för attributtyperna **Kabinettfinish** och **Frontgaller**.</span><span class="sxs-lookup"><span data-stu-id="8eedf-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="8eedf-126">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="8eedf-126">Attribute type</span></span> | <span data-ttu-id="8eedf-127">Värden</span><span class="sxs-lookup"><span data-stu-id="8eedf-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="8eedf-128">Kabinettfinish</span><span class="sxs-lookup"><span data-stu-id="8eedf-128">Cabinet finish</span></span> | <span data-ttu-id="8eedf-129">Svart ek, rosenträ, vitt</span><span class="sxs-lookup"><span data-stu-id="8eedf-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="8eedf-130">Frontgaller</span><span class="sxs-lookup"><span data-stu-id="8eedf-130">Front grill</span></span>    | <span data-ttu-id="8eedf-131">Svart, Metall, Vitt</span><span class="sxs-lookup"><span data-stu-id="8eedf-131">Black, Metal, White</span></span>         |

<span data-ttu-id="8eedf-132">Nästa tabell visar kombinationerna som definieras av registerbegränsningen i **Färg och finish**.</span><span class="sxs-lookup"><span data-stu-id="8eedf-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="8eedf-133">Med hjälp av den här registerbegränsningen kan du konfigurera en högtalare, som har ekfinish och svart galler, en rosenträregisterbegränsning och ett vitt galler, osv.</span><span class="sxs-lookup"><span data-stu-id="8eedf-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="8eedf-134">Slutför</span><span class="sxs-lookup"><span data-stu-id="8eedf-134">Finish</span></span>         | <span data-ttu-id="8eedf-135">Galler</span><span class="sxs-lookup"><span data-stu-id="8eedf-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="8eedf-136">Ek</span><span class="sxs-lookup"><span data-stu-id="8eedf-136">Oak</span></span>            | <span data-ttu-id="8eedf-137">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-137">Black</span></span>                       |
| <span data-ttu-id="8eedf-138">Rosenträ</span><span class="sxs-lookup"><span data-stu-id="8eedf-138">Rosewood</span></span>       | <span data-ttu-id="8eedf-139">Vit</span><span class="sxs-lookup"><span data-stu-id="8eedf-139">White</span></span>                       |
| <span data-ttu-id="8eedf-140">Vit</span><span class="sxs-lookup"><span data-stu-id="8eedf-140">White</span></span>          | <span data-ttu-id="8eedf-141">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-141">Black</span></span>                       |
| <span data-ttu-id="8eedf-142">Vit</span><span class="sxs-lookup"><span data-stu-id="8eedf-142">White</span></span>          | <span data-ttu-id="8eedf-143">Vit</span><span class="sxs-lookup"><span data-stu-id="8eedf-143">White</span></span>                       |
| <span data-ttu-id="8eedf-144">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-144">Black</span></span>          | <span data-ttu-id="8eedf-145">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-145">Black</span></span>                       |
| <span data-ttu-id="8eedf-146">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-146">Black</span></span>          | <span data-ttu-id="8eedf-147">Metall</span><span class="sxs-lookup"><span data-stu-id="8eedf-147">Metal</span></span>                       | 

<span data-ttu-id="8eedf-148">Du kan skapa systemdefinierade och användardefinierade registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="8eedf-149">Mer information finns i [Systemdefinierade och användardefinierade registerbegränsningar](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="8eedf-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="8eedf-150">Vilken syntax bör användas för att skriva begränsningar i ?</span><span class="sxs-lookup"><span data-stu-id="8eedf-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="8eedf-151">Du måste använda OML-syntaxen (Optimization Modeling Language) när du skriver begränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="8eedf-152">Systemet använder Microsoft Solver Foundation-begränsning för att lösa begränsningarna.</span><span class="sxs-lookup"><span data-stu-id="8eedf-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="8eedf-153">Ska jag använda registerbegränsningar eller uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="8eedf-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="8eedf-154">Du kan använda antingen uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="8eedf-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="8eedf-155">Du uppbyggnad en begränsning register som en vektor, medan en begränsning uttryck är ett enskilt utdrag.</span><span class="sxs-lookup"><span data-stu-id="8eedf-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="8eedf-156">När du konfigurerar en produkt spelar det ingen roll vilken typ av begränsning som används.</span><span class="sxs-lookup"><span data-stu-id="8eedf-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="8eedf-157">I följande exempel visas hur de två metoderna skiljer sig.</span><span class="sxs-lookup"><span data-stu-id="8eedf-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="8eedf-158">När du konfigurerar en produkt, genom att använda följande begränsninginställningar, är dessa kombinationer tillåtna:</span><span class="sxs-lookup"><span data-stu-id="8eedf-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="8eedf-159">En produkt i färgen svart och i storlek 30 eller 50</span><span class="sxs-lookup"><span data-stu-id="8eedf-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="8eedf-160">En produkt i färgen röd och i storlek 20</span><span class="sxs-lookup"><span data-stu-id="8eedf-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="8eedf-161">Registerbegränsningskonfiguration</span><span class="sxs-lookup"><span data-stu-id="8eedf-161">Table constraint setup</span></span>

| <span data-ttu-id="8eedf-162">Färg</span><span class="sxs-lookup"><span data-stu-id="8eedf-162">Color</span></span> | <span data-ttu-id="8eedf-163">Storlek</span><span class="sxs-lookup"><span data-stu-id="8eedf-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="8eedf-164">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-164">Black</span></span> | <span data-ttu-id="8eedf-165">30</span><span class="sxs-lookup"><span data-stu-id="8eedf-165">30</span></span>   |
| <span data-ttu-id="8eedf-166">Svart</span><span class="sxs-lookup"><span data-stu-id="8eedf-166">Black</span></span> | <span data-ttu-id="8eedf-167">50</span><span class="sxs-lookup"><span data-stu-id="8eedf-167">50</span></span>   |
| <span data-ttu-id="8eedf-168">Röd</span><span class="sxs-lookup"><span data-stu-id="8eedf-168">Red</span></span>   | <span data-ttu-id="8eedf-169">20</span><span class="sxs-lookup"><span data-stu-id="8eedf-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="8eedf-170">Inställning av uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="8eedf-170">Expression constraint setup</span></span>

<span data-ttu-id="8eedf-171">(Färg == "Svart" & (storlek == "30" | storlek == "50")) | (färg == "Rör" & storlek = "20")</span><span class="sxs-lookup"><span data-stu-id="8eedf-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="8eedf-172">Ska jag använda operatorer eller infixnotation när jag skriver uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="8eedf-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="8eedf-173">Du kan ange ett begränsningsuttryck, antingen genom att använda de tillgängliga prefixoperatorerna eller genom att använda infixnotation.</span><span class="sxs-lookup"><span data-stu-id="8eedf-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="8eedf-174">För operatorerna **Min**, **Max**, och **Abs** kan du inte använda en infixnotation.</span><span class="sxs-lookup"><span data-stu-id="8eedf-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="8eedf-175">Dessa operatorer inkluderas som standard i de flesta programspråk.</span><span class="sxs-lookup"><span data-stu-id="8eedf-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="8eedf-176">Vilka operatorer eller infixnotationer kan jag använda när jag skriver uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="8eedf-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="8eedf-177">I följande tabeller visas operatorerna och infixnotationerna som du kan använda när du skriver en uttrycksbegränsning för en komponent i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="8eedf-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="8eedf-178">I exemplen i den första tabellen ser du hur du kan skriva ett uttryck genom att använda infixnotation eller operatorer.</span><span class="sxs-lookup"><span data-stu-id="8eedf-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eedf-179">Operatör</span><span class="sxs-lookup"><span data-stu-id="8eedf-179">Operator</span></span></th>
<th><span data-ttu-id="8eedf-180">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8eedf-180">Description</span></span></th>
<th><span data-ttu-id="8eedf-181">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eedf-181">Syntax</span></span></th>
<th><span data-ttu-id="8eedf-182">Exempel</span><span class="sxs-lookup"><span data-stu-id="8eedf-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8eedf-183">Medför</span><span class="sxs-lookup"><span data-stu-id="8eedf-183">Implies</span></span></td>
<td><span data-ttu-id="8eedf-184">Detta gäller om det första villkoret är falskt, det andra villkoret är sant eller båda.</span><span class="sxs-lookup"><span data-stu-id="8eedf-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="8eedf-185">Medför[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="8eedf-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-186"><strong>Operatör:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="8eedf-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="8eedf-187"><strong>Infixnotation:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="8eedf-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8eedf-188">Och</span><span class="sxs-lookup"><span data-stu-id="8eedf-188">And</span></span></td>
<td><span data-ttu-id="8eedf-189">Detta gäller endast om alla villkor är sanna.</span><span class="sxs-lookup"><span data-stu-id="8eedf-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="8eedf-190">Om antalet villkor är 0 (noll), ger det <strong>Sant</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="8eedf-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-192"><strong>Operatör:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="8eedf-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="8eedf-193"><strong>Infixnotation:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="8eedf-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8eedf-194">Eller</span><span class="sxs-lookup"><span data-stu-id="8eedf-194">Or</span></span></td>
<td><span data-ttu-id="8eedf-195">Detta gäller om något villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="8eedf-195">This is true if any condition is true.</span></span> <span data-ttu-id="8eedf-196">Om antalet villkor är 0 (noll), ger det <strong>Falskt</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="8eedf-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-198"><strong>Operatör:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="8eedf-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="8eedf-199"><strong>Infixnotation:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="8eedf-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8eedf-200">Plustecken</span><span class="sxs-lookup"><span data-stu-id="8eedf-200">Plus</span></span></td>
<td><span data-ttu-id="8eedf-201">Detta summerar dess villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-201">This sums its conditions.</span></span> <span data-ttu-id="8eedf-202">Om antalet villkor är 0 (noll), ger det <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="8eedf-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-204"><strong>Operatör:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="8eedf-205"><strong>Infixnotation:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8eedf-206">Minus</span><span class="sxs-lookup"><span data-stu-id="8eedf-206">Minus</span></span></td>
<td><span data-ttu-id="8eedf-207">Detta upphäver dess argument.</span><span class="sxs-lookup"><span data-stu-id="8eedf-207">This negates its argument.</span></span> <span data-ttu-id="8eedf-208">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="8eedf-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="8eedf-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-210"><strong>Operatör:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="8eedf-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="8eedf-211"><strong>Infixnotation:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="8eedf-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8eedf-212">Abs</span><span class="sxs-lookup"><span data-stu-id="8eedf-212">Abs</span></span></td>
<td><span data-ttu-id="8eedf-213">Detta tar absolutvärdet av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="8eedf-214">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="8eedf-215">Abs [expr]</span><span class="sxs-lookup"><span data-stu-id="8eedf-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="8eedf-216"><strong>Operatör:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="8eedf-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8eedf-217">Tider</span><span class="sxs-lookup"><span data-stu-id="8eedf-217">Times</span></span></td>
<td><span data-ttu-id="8eedf-218">Detta tar produkten av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-218">This takes the product of its conditions.</span></span> <span data-ttu-id="8eedf-219">Om antalet villkor är 0 (noll), ger det <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="8eedf-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-221"><strong>Operatör:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="8eedf-222"><strong>Infixnotation:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8eedf-223">Effekt</span><span class="sxs-lookup"><span data-stu-id="8eedf-223">Power</span></span></td>
<td><span data-ttu-id="8eedf-224">Detta tar en exponential.</span><span class="sxs-lookup"><span data-stu-id="8eedf-224">This takes an exponential.</span></span> <span data-ttu-id="8eedf-225">Detta gäller exponentiering från höger till vänster.</span><span class="sxs-lookup"><span data-stu-id="8eedf-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="8eedf-226">(Med andra ord är det rättighetsförenande) Därför är <strong>Power[a, b, c] </strong>det samma som <strong>Power[a, Power[b, c]].</strong></span><span class="sxs-lookup"><span data-stu-id="8eedf-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="8eedf-227"><strong>Effekt</strong> kan bara användas med en positiv konstant som exponent.</span><span class="sxs-lookup"><span data-stu-id="8eedf-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="8eedf-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="8eedf-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-229"><strong>Operatör:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="8eedf-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="8eedf-230"><strong>Infixnotation:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="8eedf-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8eedf-231">Max.</span><span class="sxs-lookup"><span data-stu-id="8eedf-231">Max</span></span></td>
<td><span data-ttu-id="8eedf-232">Detta ger det största villkoret.</span><span class="sxs-lookup"><span data-stu-id="8eedf-232">This produces the largest condition.</span></span> <span data-ttu-id="8eedf-233">Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-234">Maximal [args]</span><span class="sxs-lookup"><span data-stu-id="8eedf-234">Max[args]</span></span></td>
<td><span data-ttu-id="8eedf-235"><strong>Operatör:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8eedf-236">Min.</span><span class="sxs-lookup"><span data-stu-id="8eedf-236">Min</span></span></td>
<td><span data-ttu-id="8eedf-237">Detta ger det minsta villkoret.</span><span class="sxs-lookup"><span data-stu-id="8eedf-237">This produces the smallest condition.</span></span> <span data-ttu-id="8eedf-238">Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</span><span class="sxs-lookup"><span data-stu-id="8eedf-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="8eedf-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="8eedf-239">Min[args]</span></span></td>
<td><span data-ttu-id="8eedf-240"><strong>Operatör:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8eedf-241">Inte</span><span class="sxs-lookup"><span data-stu-id="8eedf-241">Not</span></span></td>
<td><span data-ttu-id="8eedf-242">Detta producerar den logiska motsatsen av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="8eedf-243">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="8eedf-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="8eedf-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="8eedf-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="8eedf-245"><strong>Operatör:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="8eedf-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="8eedf-246"><strong>Infixnotation:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="8eedf-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8eedf-247">Exemplen i följande tabell visar hur du skriver en infixnotation.</span><span class="sxs-lookup"><span data-stu-id="8eedf-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="8eedf-248">Infixnotation</span><span class="sxs-lookup"><span data-stu-id="8eedf-248">Infix notation</span></span>   |                                          <span data-ttu-id="8eedf-249">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8eedf-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="8eedf-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="8eedf-250">x + y + z</span></span>     |                                           <span data-ttu-id="8eedf-251">Tillägg</span><span class="sxs-lookup"><span data-stu-id="8eedf-251">Addition</span></span>                                            |
|    <span data-ttu-id="8eedf-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="8eedf-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="8eedf-253">Multiplikation</span><span class="sxs-lookup"><span data-stu-id="8eedf-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="8eedf-254">x - y</span><span class="sxs-lookup"><span data-stu-id="8eedf-254">x - y</span></span>       | <span data-ttu-id="8eedf-255">Binär subtraktion översätts liksom binär addition med negerad andra term.</span><span class="sxs-lookup"><span data-stu-id="8eedf-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="8eedf-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="8eedf-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="8eedf-257">Högerassociativ exponentiering</span><span class="sxs-lookup"><span data-stu-id="8eedf-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="8eedf-258">!x</span><span class="sxs-lookup"><span data-stu-id="8eedf-258">!x</span></span>         |                                          <span data-ttu-id="8eedf-259">Booleskt inte</span><span class="sxs-lookup"><span data-stu-id="8eedf-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="8eedf-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="8eedf-260">x -: y</span></span>       |                                      <span data-ttu-id="8eedf-261">Boolesk implikation</span><span class="sxs-lookup"><span data-stu-id="8eedf-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="8eedf-262">x</span><span class="sxs-lookup"><span data-stu-id="8eedf-262">x</span></span>         |                                               <span data-ttu-id="8eedf-263">y</span><span class="sxs-lookup"><span data-stu-id="8eedf-263">y</span></span>                                               |
|     <span data-ttu-id="8eedf-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="8eedf-264">x & y & z</span></span>     |                                          <span data-ttu-id="8eedf-265">Booleskt och</span><span class="sxs-lookup"><span data-stu-id="8eedf-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="8eedf-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="8eedf-266">x == y == z</span></span>    |                                           <span data-ttu-id="8eedf-267">Likhet</span><span class="sxs-lookup"><span data-stu-id="8eedf-267">Equality</span></span>                                            |
|    <span data-ttu-id="8eedf-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="8eedf-268">x != y != z</span></span>    |                                           <span data-ttu-id="8eedf-269">Distinkt</span><span class="sxs-lookup"><span data-stu-id="8eedf-269">Distinct</span></span>                                            |
|  <span data-ttu-id="8eedf-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="8eedf-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="8eedf-271">Mindre än</span><span class="sxs-lookup"><span data-stu-id="8eedf-271">Less than</span></span>                                           |
|  <span data-ttu-id="8eedf-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="8eedf-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="8eedf-273">Större än</span><span class="sxs-lookup"><span data-stu-id="8eedf-273">Greater than</span></span>                                          |
| <span data-ttu-id="8eedf-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="8eedf-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="8eedf-275">Mindre än eller lika med</span><span class="sxs-lookup"><span data-stu-id="8eedf-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="8eedf-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="8eedf-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="8eedf-277">Större än eller lika med</span><span class="sxs-lookup"><span data-stu-id="8eedf-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="8eedf-278">(x)</span><span class="sxs-lookup"><span data-stu-id="8eedf-278">(x)</span></span>        |                           <span data-ttu-id="8eedf-279">Standardprioritet för åsidosättande av parenteser.</span><span class="sxs-lookup"><span data-stu-id="8eedf-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="8eedf-280">Varför kan inte mina uttryckbegränsningar verifieras korrekt?</span><span class="sxs-lookup"><span data-stu-id="8eedf-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="8eedf-281">Du kan inte använda reserverade nyckelord som solvernamn för attribut, komponenter eller delkomponenter i produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="8eedf-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="8eedf-282">Följande lista innehåller de reserverade nyckelord som du inte kan använda:</span><span class="sxs-lookup"><span data-stu-id="8eedf-282">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="8eedf-283">Tak</span><span class="sxs-lookup"><span data-stu-id="8eedf-283">Ceiling</span></span>
-   <span data-ttu-id="8eedf-284">Element</span><span class="sxs-lookup"><span data-stu-id="8eedf-284">Element</span></span>
-   <span data-ttu-id="8eedf-285">Lika</span><span class="sxs-lookup"><span data-stu-id="8eedf-285">Equal</span></span>
-   <span data-ttu-id="8eedf-286">Våning</span><span class="sxs-lookup"><span data-stu-id="8eedf-286">Floor</span></span>
-   <span data-ttu-id="8eedf-287">Om det </span><span class="sxs-lookup"><span data-stu-id="8eedf-287">If</span></span>
-   <span data-ttu-id="8eedf-288">Mindre</span><span class="sxs-lookup"><span data-stu-id="8eedf-288">Less</span></span>
-   <span data-ttu-id="8eedf-289">Större</span><span class="sxs-lookup"><span data-stu-id="8eedf-289">Greater</span></span>
-   <span data-ttu-id="8eedf-290">Medför</span><span class="sxs-lookup"><span data-stu-id="8eedf-290">Implies</span></span>
-   <span data-ttu-id="8eedf-291">Logg</span><span class="sxs-lookup"><span data-stu-id="8eedf-291">Log</span></span>
-   <span data-ttu-id="8eedf-292">Max.</span><span class="sxs-lookup"><span data-stu-id="8eedf-292">Max</span></span>
-   <span data-ttu-id="8eedf-293">Min</span><span class="sxs-lookup"><span data-stu-id="8eedf-293">Min</span></span>
-   <span data-ttu-id="8eedf-294">Minus</span><span class="sxs-lookup"><span data-stu-id="8eedf-294">Minus</span></span>
-   <span data-ttu-id="8eedf-295">Plustecken</span><span class="sxs-lookup"><span data-stu-id="8eedf-295">Plus</span></span>
-   <span data-ttu-id="8eedf-296">Effekt</span><span class="sxs-lookup"><span data-stu-id="8eedf-296">Power</span></span>
-   <span data-ttu-id="8eedf-297">Tider</span><span class="sxs-lookup"><span data-stu-id="8eedf-297">Times</span></span>
-   <span data-ttu-id="8eedf-298">Fack</span><span class="sxs-lookup"><span data-stu-id="8eedf-298">Slot</span></span>
-   <span data-ttu-id="8eedf-299">Modell</span><span class="sxs-lookup"><span data-stu-id="8eedf-299">Model</span></span>
-   <span data-ttu-id="8eedf-300">Beslut</span><span class="sxs-lookup"><span data-stu-id="8eedf-300">Decision</span></span>
-   <span data-ttu-id="8eedf-301">Mål</span><span class="sxs-lookup"><span data-stu-id="8eedf-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="8eedf-302">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8eedf-302">Additional resources</span></span>
--------

[<span data-ttu-id="8eedf-303">Skapa en uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="8eedf-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="8eedf-304">Lägg till en beräkning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="8eedf-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]