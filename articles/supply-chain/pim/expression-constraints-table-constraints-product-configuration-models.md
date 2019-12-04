---
title: Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller.
description: I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar. Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder. Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91eb5f166633f5be0ad68c039d3e538e4060ea0b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815075"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="999cc-105">Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="999cc-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="999cc-106">I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="999cc-107">Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="999cc-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="999cc-108">Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="999cc-109">Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="999cc-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="999cc-110">Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="999cc-111">Vad är uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="999cc-111">What are expression constraints?</span></span>
<span data-ttu-id="999cc-112">Uttrycksbegränsningar karakteriseras av ett uttryck som använder aritmetiska och booleska operatorer och funktioner.</span><span class="sxs-lookup"><span data-stu-id="999cc-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="999cc-113">En uttrycksbegränsning skrivs för en viss komponent i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="999cc-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="999cc-114">Den kan inte återanvändas av eller delas med en annan komponent.</span><span class="sxs-lookup"><span data-stu-id="999cc-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="999cc-115">Uttryckbegränsningarna för en komponent kan dock referera till attribut i komponentens delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="999cc-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="999cc-116">Vad är registerbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="999cc-116">What are table constraints?</span></span>
<span data-ttu-id="999cc-117">Registerbegränsningar anger de kombinationer av värden som tillåts för attribut när du konfigurerar en produkt.</span><span class="sxs-lookup"><span data-stu-id="999cc-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="999cc-118">Registerbegränsningdefinitioner kan användas i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="999cc-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="999cc-119">När du skapar en registerbegränsning för en komponent i en modell för produktkonfiguration, väljer du en registerbegränsningsdefinition.</span><span class="sxs-lookup"><span data-stu-id="999cc-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="999cc-120">Om du vill skapa de tillåtna kombinationerna, lägger du till attribut för specifika typer till komponenterna.</span><span class="sxs-lookup"><span data-stu-id="999cc-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="999cc-121">Varje attributtyp har ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="999cc-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="999cc-122">Exempel på registerbegränsning.</span><span class="sxs-lookup"><span data-stu-id="999cc-122">Example of a table constraint</span></span>

<span data-ttu-id="999cc-123">I det här exemplet visas hur du kan begränsa konfigurationen för en högtalare till specifika kabinettfinish och framdelar.</span><span class="sxs-lookup"><span data-stu-id="999cc-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="999cc-124">Den första tabellen visar storlekar och typer av kabinettfinish och framdelar som är allmänt tillgängliga för konfiguration.</span><span class="sxs-lookup"><span data-stu-id="999cc-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="999cc-125">Du definierar värdena för attributtyperna **Kabinettfinish** och **Frontgaller**.</span><span class="sxs-lookup"><span data-stu-id="999cc-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="999cc-126">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="999cc-126">Attribute type</span></span> | <span data-ttu-id="999cc-127">Värden</span><span class="sxs-lookup"><span data-stu-id="999cc-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="999cc-128">Kabinettfinish</span><span class="sxs-lookup"><span data-stu-id="999cc-128">Cabinet finish</span></span> | <span data-ttu-id="999cc-129">Svart ek, rosenträ, vitt</span><span class="sxs-lookup"><span data-stu-id="999cc-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="999cc-130">Frontgaller</span><span class="sxs-lookup"><span data-stu-id="999cc-130">Front grill</span></span>    | <span data-ttu-id="999cc-131">Svart, Metall, Vitt</span><span class="sxs-lookup"><span data-stu-id="999cc-131">Black, Metal, White</span></span>         |

<span data-ttu-id="999cc-132">Nästa tabell visar kombinationerna som definieras av registerbegränsningen i **Färg och finish**.</span><span class="sxs-lookup"><span data-stu-id="999cc-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="999cc-133">Med hjälp av den här registerbegränsningen kan du konfigurera en högtalare, som har ekfinish och svart galler, en rosenträregisterbegränsning och ett vitt galler, osv.</span><span class="sxs-lookup"><span data-stu-id="999cc-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="999cc-134">Slutför</span><span class="sxs-lookup"><span data-stu-id="999cc-134">Finish</span></span>         | <span data-ttu-id="999cc-135">Galler</span><span class="sxs-lookup"><span data-stu-id="999cc-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="999cc-136">Ek</span><span class="sxs-lookup"><span data-stu-id="999cc-136">Oak</span></span>            | <span data-ttu-id="999cc-137">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-137">Black</span></span>                       |
| <span data-ttu-id="999cc-138">Rosenträ</span><span class="sxs-lookup"><span data-stu-id="999cc-138">Rosewood</span></span>       | <span data-ttu-id="999cc-139">Vit</span><span class="sxs-lookup"><span data-stu-id="999cc-139">White</span></span>                       |
| <span data-ttu-id="999cc-140">Vit</span><span class="sxs-lookup"><span data-stu-id="999cc-140">White</span></span>          | <span data-ttu-id="999cc-141">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-141">Black</span></span>                       |
| <span data-ttu-id="999cc-142">Vit</span><span class="sxs-lookup"><span data-stu-id="999cc-142">White</span></span>          | <span data-ttu-id="999cc-143">Vit</span><span class="sxs-lookup"><span data-stu-id="999cc-143">White</span></span>                       |
| <span data-ttu-id="999cc-144">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-144">Black</span></span>          | <span data-ttu-id="999cc-145">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-145">Black</span></span>                       |
| <span data-ttu-id="999cc-146">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-146">Black</span></span>          | <span data-ttu-id="999cc-147">Metall</span><span class="sxs-lookup"><span data-stu-id="999cc-147">Metal</span></span>                       | 

<span data-ttu-id="999cc-148">Du kan skapa systemdefinierade och användardefinierade registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="999cc-149">Mer information finns i [Systemdefinierade och användardefinierade registerbegränsningar](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="999cc-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="999cc-150">Vilken syntax bör användas för att skriva begränsningar i ?</span><span class="sxs-lookup"><span data-stu-id="999cc-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="999cc-151">Du måste använda OML-syntaxen (Optimization Modeling Language) när du skriver begränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="999cc-152">Systemet använder Microsoft Solver Foundation-begränsning för att lösa begränsningarna.</span><span class="sxs-lookup"><span data-stu-id="999cc-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="999cc-153">Ska jag använda registerbegränsningar eller uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="999cc-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="999cc-154">Du kan använda antingen uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="999cc-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="999cc-155">Du uppbyggnad en begränsning register som en vektor, medan en begränsning uttryck är ett enskilt utdrag.</span><span class="sxs-lookup"><span data-stu-id="999cc-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="999cc-156">När du konfigurerar en produkt spelar det ingen roll vilken typ av begränsning som används.</span><span class="sxs-lookup"><span data-stu-id="999cc-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="999cc-157">I följande exempel visas hur de två metoderna skiljer sig.</span><span class="sxs-lookup"><span data-stu-id="999cc-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="999cc-158">När du konfigurerar en produkt, genom att använda följande begränsninginställningar, är dessa kombinationer tillåtna:</span><span class="sxs-lookup"><span data-stu-id="999cc-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="999cc-159">En produkt i färgen svart och i storlek 30 eller 50</span><span class="sxs-lookup"><span data-stu-id="999cc-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="999cc-160">En produkt i färgen röd och i storlek 20</span><span class="sxs-lookup"><span data-stu-id="999cc-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="999cc-161">Registerbegränsningskonfiguration</span><span class="sxs-lookup"><span data-stu-id="999cc-161">Table constraint setup</span></span>

| <span data-ttu-id="999cc-162">Färg</span><span class="sxs-lookup"><span data-stu-id="999cc-162">Color</span></span> | <span data-ttu-id="999cc-163">Storlek</span><span class="sxs-lookup"><span data-stu-id="999cc-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="999cc-164">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-164">Black</span></span> | <span data-ttu-id="999cc-165">30</span><span class="sxs-lookup"><span data-stu-id="999cc-165">30</span></span>   |
| <span data-ttu-id="999cc-166">Svart</span><span class="sxs-lookup"><span data-stu-id="999cc-166">Black</span></span> | <span data-ttu-id="999cc-167">50</span><span class="sxs-lookup"><span data-stu-id="999cc-167">50</span></span>   |
| <span data-ttu-id="999cc-168">Röd</span><span class="sxs-lookup"><span data-stu-id="999cc-168">Red</span></span>   | <span data-ttu-id="999cc-169">20</span><span class="sxs-lookup"><span data-stu-id="999cc-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="999cc-170">Inställning av uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="999cc-170">Expression constraint setup</span></span>

<span data-ttu-id="999cc-171">(Färg == "Svart" & (storlek == "30" | storlek == "50")) | (färg == "Rör" & storlek = "20")</span><span class="sxs-lookup"><span data-stu-id="999cc-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="999cc-172">Ska jag använda operatorer eller infixnotation när jag skriver uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="999cc-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="999cc-173">Du kan ange ett begränsningsuttryck, antingen genom att använda de tillgängliga prefixoperatorerna eller genom att använda infixnotation.</span><span class="sxs-lookup"><span data-stu-id="999cc-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="999cc-174">För operatorerna **Min**, **Max**, och **Abs** kan du inte använda en infixnotation.</span><span class="sxs-lookup"><span data-stu-id="999cc-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="999cc-175">Dessa operatorer inkluderas som standard i de flesta programspråk.</span><span class="sxs-lookup"><span data-stu-id="999cc-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="999cc-176">Vilka operatorer eller infixnotationer kan jag använda när jag skriver uttrycksbegränsningar?</span><span class="sxs-lookup"><span data-stu-id="999cc-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="999cc-177">I följande tabeller visas operatorerna och infixnotationerna som du kan använda när du skriver en uttrycksbegränsning för en komponent i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="999cc-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="999cc-178">I exemplen i den första tabellen ser du hur du kan skriva ett uttryck genom att använda infixnotation eller operatorer.</span><span class="sxs-lookup"><span data-stu-id="999cc-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="999cc-179">Operatör</span><span class="sxs-lookup"><span data-stu-id="999cc-179">Operator</span></span></th>
<th><span data-ttu-id="999cc-180">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="999cc-180">Description</span></span></th>
<th><span data-ttu-id="999cc-181">Syntax</span><span class="sxs-lookup"><span data-stu-id="999cc-181">Syntax</span></span></th>
<th><span data-ttu-id="999cc-182">Exempel</span><span class="sxs-lookup"><span data-stu-id="999cc-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="999cc-183">Medför</span><span class="sxs-lookup"><span data-stu-id="999cc-183">Implies</span></span></td>
<td><span data-ttu-id="999cc-184">Detta gäller om det första villkoret är falskt, det andra villkoret är sant eller båda.</span><span class="sxs-lookup"><span data-stu-id="999cc-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="999cc-185">Medför[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="999cc-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-186"><strong>Operatör:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="999cc-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="999cc-187"><strong>Infixnotation:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="999cc-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="999cc-188">Och</span><span class="sxs-lookup"><span data-stu-id="999cc-188">And</span></span></td>
<td><span data-ttu-id="999cc-189">Detta gäller endast om alla villkor är sanna.</span><span class="sxs-lookup"><span data-stu-id="999cc-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="999cc-190">Om antalet villkor är 0 (noll), ger det <strong>Sant</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="999cc-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="999cc-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-192"><strong>Operatör:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="999cc-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="999cc-193"><strong>Infixnotation:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="999cc-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="999cc-194">Eller</span><span class="sxs-lookup"><span data-stu-id="999cc-194">Or</span></span></td>
<td><span data-ttu-id="999cc-195">Detta gäller om något villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="999cc-195">This is true if any condition is true.</span></span> <span data-ttu-id="999cc-196">Om antalet villkor är 0 (noll), ger det <strong>Falskt</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="999cc-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="999cc-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-198"><strong>Operatör:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="999cc-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="999cc-199"><strong>Infixnotation:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="999cc-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="999cc-200">Plustecken</span><span class="sxs-lookup"><span data-stu-id="999cc-200">Plus</span></span></td>
<td><span data-ttu-id="999cc-201">Detta summerar dess villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-201">This sums its conditions.</span></span> <span data-ttu-id="999cc-202">Om antalet villkor är 0 (noll), ger det <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="999cc-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="999cc-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-204"><strong>Operatör:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="999cc-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="999cc-205"><strong>Infixnotation:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="999cc-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="999cc-206">Minus</span><span class="sxs-lookup"><span data-stu-id="999cc-206">Minus</span></span></td>
<td><span data-ttu-id="999cc-207">Detta upphäver dess argument.</span><span class="sxs-lookup"><span data-stu-id="999cc-207">This negates its argument.</span></span> <span data-ttu-id="999cc-208">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="999cc-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="999cc-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-210"><strong>Operatör:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="999cc-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="999cc-211"><strong>Infixnotation:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="999cc-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="999cc-212">Abs</span><span class="sxs-lookup"><span data-stu-id="999cc-212">Abs</span></span></td>
<td><span data-ttu-id="999cc-213">Detta tar absolutvärdet av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="999cc-214">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="999cc-215">Abs [expr]</span><span class="sxs-lookup"><span data-stu-id="999cc-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="999cc-216"><strong>Operatör:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="999cc-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="999cc-217">Tider</span><span class="sxs-lookup"><span data-stu-id="999cc-217">Times</span></span></td>
<td><span data-ttu-id="999cc-218">Detta tar produkten av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-218">This takes the product of its conditions.</span></span> <span data-ttu-id="999cc-219">Om antalet villkor är 0 (noll), ger det <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="999cc-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="999cc-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-221"><strong>Operatör:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="999cc-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="999cc-222"><strong>Infixnotation:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="999cc-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="999cc-223">Effekt</span><span class="sxs-lookup"><span data-stu-id="999cc-223">Power</span></span></td>
<td><span data-ttu-id="999cc-224">Detta tar en exponential.</span><span class="sxs-lookup"><span data-stu-id="999cc-224">This takes an exponential.</span></span> <span data-ttu-id="999cc-225">Detta gäller exponentiering från höger till vänster.</span><span class="sxs-lookup"><span data-stu-id="999cc-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="999cc-226">(Med andra ord är det rättighetsförenande) Därför är <strong>Power[a, b, c] </strong>det samma som <strong>Power[a, Power[b, c]].</strong></span><span class="sxs-lookup"><span data-stu-id="999cc-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="999cc-227"><strong>Effekt</strong> kan bara användas med en positiv konstant som exponent.</span><span class="sxs-lookup"><span data-stu-id="999cc-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="999cc-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="999cc-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-229"><strong>Operatör:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="999cc-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="999cc-230"><strong>Infixnotation:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="999cc-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="999cc-231">Max.</span><span class="sxs-lookup"><span data-stu-id="999cc-231">Max</span></span></td>
<td><span data-ttu-id="999cc-232">Detta ger det största villkoret.</span><span class="sxs-lookup"><span data-stu-id="999cc-232">This produces the largest condition.</span></span> <span data-ttu-id="999cc-233">Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="999cc-234">Maximal [args]</span><span class="sxs-lookup"><span data-stu-id="999cc-234">Max[args]</span></span></td>
<td><span data-ttu-id="999cc-235"><strong>Operatör:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="999cc-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="999cc-236">Min.</span><span class="sxs-lookup"><span data-stu-id="999cc-236">Min</span></span></td>
<td><span data-ttu-id="999cc-237">Detta ger det minsta villkoret.</span><span class="sxs-lookup"><span data-stu-id="999cc-237">This produces the smallest condition.</span></span> <span data-ttu-id="999cc-238">Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</span><span class="sxs-lookup"><span data-stu-id="999cc-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="999cc-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="999cc-239">Min[args]</span></span></td>
<td><span data-ttu-id="999cc-240"><strong>Operatör:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="999cc-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="999cc-241">Inte</span><span class="sxs-lookup"><span data-stu-id="999cc-241">Not</span></span></td>
<td><span data-ttu-id="999cc-242">Detta producerar den logiska motsatsen av dess villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="999cc-243">Detta måste ha exakt ett villkor.</span><span class="sxs-lookup"><span data-stu-id="999cc-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="999cc-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="999cc-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="999cc-245"><strong>Operatör:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="999cc-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="999cc-246"><strong>Infixnotation:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="999cc-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="999cc-247">Exemplen i följande tabell visar hur du skriver en infixnotation.</span><span class="sxs-lookup"><span data-stu-id="999cc-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="999cc-248">Infixnotation</span><span class="sxs-lookup"><span data-stu-id="999cc-248">Infix notation</span></span>   |                                          <span data-ttu-id="999cc-249">beskrivning</span><span class="sxs-lookup"><span data-stu-id="999cc-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="999cc-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="999cc-250">x + y + z</span></span>     |                                           <span data-ttu-id="999cc-251">Tillägg</span><span class="sxs-lookup"><span data-stu-id="999cc-251">Addition</span></span>                                            |
|    <span data-ttu-id="999cc-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="999cc-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="999cc-253">Multiplikation</span><span class="sxs-lookup"><span data-stu-id="999cc-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="999cc-254">x - y</span><span class="sxs-lookup"><span data-stu-id="999cc-254">x - y</span></span>       | <span data-ttu-id="999cc-255">Binär subtraktion översätts liksom binär addition med negerad andra term.</span><span class="sxs-lookup"><span data-stu-id="999cc-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="999cc-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="999cc-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="999cc-257">Högerassociativ exponentiering</span><span class="sxs-lookup"><span data-stu-id="999cc-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="999cc-258">!x</span><span class="sxs-lookup"><span data-stu-id="999cc-258">!x</span></span>         |                                          <span data-ttu-id="999cc-259">Booleskt inte</span><span class="sxs-lookup"><span data-stu-id="999cc-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="999cc-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="999cc-260">x -: y</span></span>       |                                      <span data-ttu-id="999cc-261">Boolesk implikation</span><span class="sxs-lookup"><span data-stu-id="999cc-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="999cc-262">x</span><span class="sxs-lookup"><span data-stu-id="999cc-262">x</span></span>         |                                               <span data-ttu-id="999cc-263">y</span><span class="sxs-lookup"><span data-stu-id="999cc-263">y</span></span>                                               |
|     <span data-ttu-id="999cc-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="999cc-264">x & y & z</span></span>     |                                          <span data-ttu-id="999cc-265">Booleskt och</span><span class="sxs-lookup"><span data-stu-id="999cc-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="999cc-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="999cc-266">x == y == z</span></span>    |                                           <span data-ttu-id="999cc-267">Likhet</span><span class="sxs-lookup"><span data-stu-id="999cc-267">Equality</span></span>                                            |
|    <span data-ttu-id="999cc-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="999cc-268">x != y != z</span></span>    |                                           <span data-ttu-id="999cc-269">Distinkt</span><span class="sxs-lookup"><span data-stu-id="999cc-269">Distinct</span></span>                                            |
|  <span data-ttu-id="999cc-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="999cc-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="999cc-271">Mindre än</span><span class="sxs-lookup"><span data-stu-id="999cc-271">Less than</span></span>                                           |
|  <span data-ttu-id="999cc-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="999cc-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="999cc-273">Större än</span><span class="sxs-lookup"><span data-stu-id="999cc-273">Greater than</span></span>                                          |
| <span data-ttu-id="999cc-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="999cc-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="999cc-275">Mindre än eller lika med</span><span class="sxs-lookup"><span data-stu-id="999cc-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="999cc-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="999cc-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="999cc-277">Större än eller lika med</span><span class="sxs-lookup"><span data-stu-id="999cc-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="999cc-278">(x)</span><span class="sxs-lookup"><span data-stu-id="999cc-278">(x)</span></span>        |                           <span data-ttu-id="999cc-279">Standardprioritet för åsidosättande av parenteser.</span><span class="sxs-lookup"><span data-stu-id="999cc-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="999cc-280">Varför kan inte mina uttryckbegränsningar verifieras korrekt?</span><span class="sxs-lookup"><span data-stu-id="999cc-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="999cc-281">Du kan inte använda reserverade nyckelord som solvernamn för attribut, komponenter eller delkomponenter i produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="999cc-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span><span data-ttu-id="999cc-282"> Följande lista innehåller de reserverade nyckelord som du inte kan använda:</span><span class="sxs-lookup"><span data-stu-id="999cc-282"> Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="999cc-283">Tak</span><span class="sxs-lookup"><span data-stu-id="999cc-283">Ceiling</span></span>
-   <span data-ttu-id="999cc-284">Element</span><span class="sxs-lookup"><span data-stu-id="999cc-284">Element</span></span>
-   <span data-ttu-id="999cc-285">Lika</span><span class="sxs-lookup"><span data-stu-id="999cc-285">Equal</span></span>
-   <span data-ttu-id="999cc-286">Våning</span><span class="sxs-lookup"><span data-stu-id="999cc-286">Floor</span></span>
-   <span data-ttu-id="999cc-287">Om det </span><span class="sxs-lookup"><span data-stu-id="999cc-287">If</span></span>
-   <span data-ttu-id="999cc-288">Mindre</span><span class="sxs-lookup"><span data-stu-id="999cc-288">Less</span></span>
-   <span data-ttu-id="999cc-289">Större</span><span class="sxs-lookup"><span data-stu-id="999cc-289">Greater</span></span>
-   <span data-ttu-id="999cc-290">Medför</span><span class="sxs-lookup"><span data-stu-id="999cc-290">Implies</span></span>
-   <span data-ttu-id="999cc-291">Logg</span><span class="sxs-lookup"><span data-stu-id="999cc-291">Log</span></span>
-   <span data-ttu-id="999cc-292">Max.</span><span class="sxs-lookup"><span data-stu-id="999cc-292">Max</span></span>
-   <span data-ttu-id="999cc-293">Min</span><span class="sxs-lookup"><span data-stu-id="999cc-293">Min</span></span>
-   <span data-ttu-id="999cc-294">Minus</span><span class="sxs-lookup"><span data-stu-id="999cc-294">Minus</span></span>
-   <span data-ttu-id="999cc-295">Plustecken</span><span class="sxs-lookup"><span data-stu-id="999cc-295">Plus</span></span>
-   <span data-ttu-id="999cc-296">Effekt</span><span class="sxs-lookup"><span data-stu-id="999cc-296">Power</span></span>
-   <span data-ttu-id="999cc-297">Tider</span><span class="sxs-lookup"><span data-stu-id="999cc-297">Times</span></span>
-   <span data-ttu-id="999cc-298">Fack</span><span class="sxs-lookup"><span data-stu-id="999cc-298">Slot</span></span>
-   <span data-ttu-id="999cc-299">Modell</span><span class="sxs-lookup"><span data-stu-id="999cc-299">Model</span></span>
-   <span data-ttu-id="999cc-300">Beslut</span><span class="sxs-lookup"><span data-stu-id="999cc-300">Decision</span></span>
-   <span data-ttu-id="999cc-301">Mål</span><span class="sxs-lookup"><span data-stu-id="999cc-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="999cc-302">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="999cc-302">Additional resources</span></span>
--------

[<span data-ttu-id="999cc-303">Skapa en uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="999cc-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="999cc-304">Lägg till en beräkning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="999cc-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)



