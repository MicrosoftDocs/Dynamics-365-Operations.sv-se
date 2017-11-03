---
title: "Frågor och Svar - Beräkningar för produktkonfigurationsmodeller"
description: "Det här avsnittet beskriver beräkningar för produktkonfigurationsmodeller och förklarar hur du använder beräkningar tillsammans med begränsningar."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 73de1658ed4f104008ff0654c999bdc2f3bfc8a8
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="calculations-for-product-configuration-models-faq"></a><span data-ttu-id="7b4ff-103">Frågor och Svar - Beräkningar för produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="7b4ff-103">Calculations for product configuration models FAQ</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7b4ff-104">Det här avsnittet beskriver beräkningar för produktkonfigurationsmodeller och förklarar hur du använder beräkningar tillsammans med begränsningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-104">This article describes calculations for product configuration models and explains how to use calculations together with constraints.</span></span>

<span data-ttu-id="7b4ff-105">Beräkningar kan användas för aritmetiska eller logiska operationer.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-105">Calculations can be used for arithmetic or logical operations.</span></span> <span data-ttu-id="7b4ff-106">De kompletterar uttryckbegränsningar i produktkonfigurationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-106">They complement expression constraints in product configuration models.</span></span> <span data-ttu-id="7b4ff-107">Du kan definiera beräkningar på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell** och sedan skapa uttryck för beräkningar i uttrycksredigeraren.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-107">You can define calculations on the **Constraint-based product configuration model details** page and then build expressions for the calculations in the expression editor.</span></span> <span data-ttu-id="7b4ff-108">Mer information finns i Skapa beräkningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-108">For more information, see Create calculations.</span></span>

## <a name="what-is-a-calculation"></a><span data-ttu-id="7b4ff-109">Vad är en beräkning?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-109">What is a calculation?</span></span>
<span data-ttu-id="7b4ff-110">En beräkning är ett element som du kan använda i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-110">A calculation is an element that you can use in a product configuration model.</span></span> <span data-ttu-id="7b4ff-111">Beräkningar kompletterar begränsningar genom att du kan använda decimaltal till beräkna värden med decimaltal när du konfigurerar en produkt.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-111">Calculations complement constraints by letting you use decimal numbers to calculate values when you configure a product.</span></span> <span data-ttu-id="7b4ff-112">Vidare har beräkningar en större uppsättning tillgängliga operatorer än begränsningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-112">Additionally, calculations have a larger set of available operators than constraints have.</span></span>  

<span data-ttu-id="7b4ff-113">Likt en begränsning associeras en beräkning med en viss komponent i en modell för produktkonfiguration, och den kan inte återanvändas av eller delas med en annan komponent.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-113">Like a constraint, a calculation is associated with a specific component in a product configuration model, and can’t be reused by or shared with another component.</span></span> <span data-ttu-id="7b4ff-114">En viktig skillnad mellan beräkningar och begränsningar är att beräkningar är absolut nödvändiga (enkelriktade), medan begränsningar är deklarativa (dubbelriktade).</span><span class="sxs-lookup"><span data-stu-id="7b4ff-114">One important difference between calculations and constraints is that calculations are imperative (unidirectional), whereas constraints are declarative (bi-directional).</span></span> <span data-ttu-id="7b4ff-115">Mer information om begränsningar finns i [Uttrycksbegränsningar och registerbegränsningar](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="7b4ff-115">For more information about constraints, see [Expression constraints and table constraints](expression-constraints-table-constraints-product-configuration-models.md).</span></span>  

<span data-ttu-id="7b4ff-116">En beräkning består av ett målattribut och ett beräkningsuttryck.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-116">A calculation consists of a target attribute and a calculation expression.</span></span>

## <a name="what-is-a-target-attribute"></a><span data-ttu-id="7b4ff-117">Vad är ett målattribut?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-117">What is a target attribute?</span></span>
<span data-ttu-id="7b4ff-118">Ett målattribut är ett attribut som tar emot beräkningens resultat i ett uttryck.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-118">A target attribute is an attribute that receives the result of the calculation expression.</span></span>  

<span data-ttu-id="7b4ff-119">I följande uttryck är målattributet ett bordsdukmått:</span><span class="sxs-lookup"><span data-stu-id="7b4ff-119">In the following expression, the target attribute is a tablecloth measurement:</span></span>  

<span data-ttu-id="7b4ff-120">**Uttryck:** Om\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]</span><span class="sxs-lookup"><span data-stu-id="7b4ff-120">**Expression:** If\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]</span></span>  

<span data-ttu-id="7b4ff-121">**DecimalAttribute1** är registerlängden, och **decimalAttribute2** är tablecloth-längden.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-121">**DecimalAttribute1** is the table length, and **decimalAttribute2** is the tablecloth length.</span></span> <span data-ttu-id="7b4ff-122">Detta uttryck returnerar värdet **Sant** till målattributet om **decimalAttribute2** är större än eller lika med **decimalAttribute1**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-122">The expression returns the value **True** to the target attribute if **decimalAttribute2** is greater than or equal to **decimalAttribute1**.</span></span> <span data-ttu-id="7b4ff-123">Annars returnerar uttrycket värdet **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-123">Otherwise, the expression returns **False**.</span></span> <span data-ttu-id="7b4ff-124">Så bordduksmåttet är godtagbart om borddukslängden är lika med eller överstiger längden på bordet.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-124">Therefore, the tablecloth measurement is acceptable if the tablecloth length is the same as or exceeds the length of the table.</span></span>

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a><span data-ttu-id="7b4ff-125">Vilka attributtyper kan ställas in som målattribut?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-125">What attribute types can be set to target attributes?</span></span>
<span data-ttu-id="7b4ff-126">Alla attributtyper som stöds för produktkonfigureraren kan anges som målattribut med undantag för text utan en fast lista.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-126">All attribute types that the product configurator supports can be set to target attributes, except text without a fixed list.</span></span>

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a><span data-ttu-id="7b4ff-127">Kan ett värde för målattributet begränsa värdena för indataattributen i en beräkning?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-127">Can the value of a target attribute restrict the values of the input attributes in a calculation?</span></span>
<span data-ttu-id="7b4ff-128">Nej, ett värde för målattributet kan inte begränsa värdena för indataattributen eftersom beräkningar är enkelriktade.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-128">No, the value of a target attribute can’t restrict the values of the input attributes, because calculations are unidirectional.</span></span> <span data-ttu-id="7b4ff-129">Därför anges värdet för målattributet utifrån ändringar i värdet för indataattributen, men en ändring i målets värde påverkar inte värdet för indataattributen.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-129">Therefore, the value of the target attribute is set based on changes in the value of the input attributes, but a change in the value of the target doesn’t affect the value of the input attributes.</span></span> <span data-ttu-id="7b4ff-130">Detta beteende skiljer sig från beteendet för begränsningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-130">This behavior differs from the behavior for constraints.</span></span> <span data-ttu-id="7b4ff-131">Begränsningar sker i båda riktningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-131">Constraints occur in both directions.</span></span>

### <a name="example"></a><span data-ttu-id="7b4ff-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="7b4ff-132">Example</span></span>

<span data-ttu-id="7b4ff-133">I följande uttryck är målet för beräkningen längden på en elsladd, och indatavärdet är en färg:</span><span class="sxs-lookup"><span data-stu-id="7b4ff-133">In the following expression, the target for the calculation is the length of a power cord, and the input value is a color:</span></span>  

<span data-ttu-id="7b4ff-134">**Uttryck:** \[If Color == "Green", 1.5, 1.0\]</span><span class="sxs-lookup"><span data-stu-id="7b4ff-134">**Expression:** \[If Color == "Green", 1.5, 1.0\]</span></span>  

<span data-ttu-id="7b4ff-135">När du konfigurerar artikeln, anges elsladdens längd som **1,5** om du anger **Grön** som värdet för färgattributet.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-135">When you configure the item, the length of the power cord is set to **1.5** if you specify **Green** as the value of color attribute.</span></span> <span data-ttu-id="7b4ff-136">Om du anger en annan färg, är längden **1,0**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-136">If you specify any other color, the length is set to **1.0**.</span></span> <span data-ttu-id="7b4ff-137">Eftersom beräkningar är enkelriktade ställer beräkningen inte in värdet för färgattributet till **Grön** när du anger en längd på **1,5**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-137">However, because calculations are unidirectional, the calculation doesn't set the value of the color attribute to **Green** if you specify a length of **1.5**.</span></span>

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a><span data-ttu-id="7b4ff-138">Vad händer om en beräkning har ett målattribut av heltalstypen men en beräkning skapar ett decimaltal?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-138">What happens if a calculation has a target attribute of the integer type but a calculation generates a decimal number?</span></span>
<span data-ttu-id="7b4ff-139">Om ett målattribut är av heltalstypen, men en beräkning skapar ett decimaltal, returneras bara heltalsdelen på det beräknade resultatet.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-139">If a target attribute is of the integer type, but a calculation generates a decimal number, only the integer part of the calculated result is returned.</span></span> <span data-ttu-id="7b4ff-140">Decimalerdelen tas bort och resultatet avrundas inte.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-140">The decimal part is removed, and the result isn't rounded.</span></span> <span data-ttu-id="7b4ff-141">Ett resultat på 12,70 visas till exempel som 12.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-141">For example, a result of 12.70 is shown as 12.</span></span>

## <a name="when-do-calculations-occur"></a><span data-ttu-id="7b4ff-142">När sker beräkningar?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-142">When do calculations occur?</span></span>
<span data-ttu-id="7b4ff-143">Beräkningar sker när ett värde har angetts för alla indataattribut.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-143">Calculations occur when a value has been provided for all input attributes.</span></span>

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a><span data-ttu-id="7b4ff-144">Kan jag skriva över värdet som beräknas för målattributet?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-144">Can I overwrite the value that is calculated for the target attribute?</span></span>
<span data-ttu-id="7b4ff-145">Du kan åsidosätta värdet som beräknas för målattributet, om inte målattributet är inställt som dolt eller skrivskyddat.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-145">You can overwrite the value that is calculated for the target attribute, unless the target attribute is set as hidden or read-only.</span></span>

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a><span data-ttu-id="7b4ff-146">Hur kan jag ange ett målattribut som dolt eller skrivskyddat?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-146">How do I set a target attribute as hidden or readonly?</span></span>
<span data-ttu-id="7b4ff-147">Om du vill ange ett attribut som dolt eller skrivskyddat, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="7b4ff-147">To set an attribute as hidden or read-only, follow these steps.</span></span>

1.  <span data-ttu-id="7b4ff-148">Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-148">Click **Product information management** &gt; **Common** &gt; **Product configuration models**.</span></span>
2.  <span data-ttu-id="7b4ff-149">Välj en modell för produkt, konfiguration och klicka sedan på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-149">Select a product configuration model, and then, on the Action Pane, click **Edit**.</span></span>
3.  <span data-ttu-id="7b4ff-150">På sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell** väljer du det attribut som du vill använda som målattribut.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-150">On the **Constraint-based product configuration model details** page, select the attribute to use as a target attribute.</span></span>
4.  <span data-ttu-id="7b4ff-151">På snabbfliken **Attribut** väljer du **Dolt** eller **Skrivskyddat**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-151">On the **Attributes** FastTab, select **Hidden** or **Read-only**.</span></span>

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a><span data-ttu-id="7b4ff-152">Kan en beräkning skriva över de värden som jag har angett?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-152">Can a calculation overwrite the values that I set?</span></span>
<span data-ttu-id="7b4ff-153">Nr.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-153">No.</span></span> <span data-ttu-id="7b4ff-154">De värden du anger när du konfigurerar en produkt är de värden som används.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-154">The values that you set when you configure a product are the values that are used.</span></span> <span data-ttu-id="7b4ff-155">Beräkningen som infaller när indatavärdena i beräkningen ändras kan inte skriva över värdena som du anger för ett visst attribut.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-155">The calculation that occurs when the input values in a calculation are changed can’t overwrite the values that you provide for a specific attribute.</span></span>

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a><span data-ttu-id="7b4ff-156">Vad händer om jag tar bort ett invärde i en beräkning?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-156">What happens if I remove an input value in a calculation?</span></span>
<span data-ttu-id="7b4ff-157">Om du tar bort ett invärde i en beräkning, tas värdet för målattributet också bort.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-157">If you remove an input value in a calculation, the value of the target attribute is also removed.</span></span>

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a><span data-ttu-id="7b4ff-158">Varför jag får ett felmeddelande om att min modell utgör en motsättning?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-158">Why do I receive an error message that says that my model is in contradiction?</span></span>
<span data-ttu-id="7b4ff-159">Detta meddelande visas när en beräkning innehåller ett fel eller om en motsättning förekommer i en eller flera begränsningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-159">This message is shown when a calculation includes an error, or when a contradiction exists in one or more constraints.</span></span> <span data-ttu-id="7b4ff-160">Mer information om motsägelser i begränsningar finns i [Uttrycksbegränsningar och registerbegränsningar](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="7b4ff-160">For more information about contradictions in constraints, see [Expression constraints and table constraints](expression-constraints-table-constraints-product-configuration-models.md).</span></span> <span data-ttu-id="7b4ff-161">Nedan följer några situationer där det kan uppstå fel i beräkningar:</span><span class="sxs-lookup"><span data-stu-id="7b4ff-161">Here are some situations where errors can occur in calculations:</span></span>

-   <span data-ttu-id="7b4ff-162">Ett värde delas med 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="7b4ff-162">A value is divided by 0 (zero).</span></span>
-   <span data-ttu-id="7b4ff-163">Det finns en konflikt mellan följande två element:</span><span class="sxs-lookup"><span data-stu-id="7b4ff-163">A conflict exists between the following two elements:</span></span>
    -   <span data-ttu-id="7b4ff-164">De värden som är tillgängliga för ett attribut och som har begränsningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-164">The values that are available for an attribute and are limited by a constraint</span></span>
    -   <span data-ttu-id="7b4ff-165">Ett värde som genereras av en beräkning.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-165">A value that is generated by a calculation</span></span>
-   <span data-ttu-id="7b4ff-166">Värdena som returneras av beräkningen ligger utanför domänen för attributet.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-166">The values that are returned by the calculation are outside the domain of the attribute.</span></span> <span data-ttu-id="7b4ff-167">Ett exempel är ett heltal mellan \[1..10\] som beräknas till 0.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-167">An example is an integer from \[1..10\] that is calculated to 0.</span></span>

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a><span data-ttu-id="7b4ff-168">Varför får jag ett felmeddelande även om jag validerade min produktmodell?</span><span class="sxs-lookup"><span data-stu-id="7b4ff-168">Why do I receive an error message even though I successfully validated my product model?</span></span>
<span data-ttu-id="7b4ff-169">Beräkningar inkluderas inte i valideringen.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-169">Calculations aren't included in the validation.</span></span> <span data-ttu-id="7b4ff-170">Du måste testa produktkonfigurationsmodellen för att hitta fel i beräkningar.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-170">You must test the product configuration model to find errors in calculations.</span></span> <span data-ttu-id="7b4ff-171">Följande steg beskriver hur man testar en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-171">To test a product configuration model, follow these steps.</span></span>

1.  <span data-ttu-id="7b4ff-172">Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-172">Click **Product information management** &gt; **Common** &gt; **Product configuration models**.</span></span>
2.  <span data-ttu-id="7b4ff-173">Välj en produktkonfigurationsmodell i åtgärdsfönstret och klicka sedan på gruppen **Kör**, klicka på **Test**.</span><span class="sxs-lookup"><span data-stu-id="7b4ff-173">Select a product configuration model, and then, on the Action Pane, in the **Run** group, click **Test**.</span></span>





