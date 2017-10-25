---
title: "Översikt över produktkonfigurationsmodeller"
description: "I den här artikeln definieras termer och begrepp som avser produktkonfigurationsmodeller. Med produktkonfigurationsmodeller kan du bygga en allmän produktstruktur som kan användas för att konfigurera många produktvarianter för en och samma produkt."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c222f0d17be6eea0f776f5460c793b82d8b3e0ab
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="product-configuration-models-overview"></a><span data-ttu-id="a8e41-104">Översikt över produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="a8e41-104">Product configuration models overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a8e41-105">I den här artikeln definieras termer och begrepp som avser produktkonfigurationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="a8e41-105">This article defines terms and concepts that are relevant to product configuration models.</span></span> <span data-ttu-id="a8e41-106">Med produktkonfigurationsmodeller kan du bygga en allmän produktstruktur som kan användas för att konfigurera många produktvarianter för en och samma produkt.</span><span class="sxs-lookup"><span data-stu-id="a8e41-106">Product configuration models let you build a generic product structure that can be used to configure many product variants for a single product.</span></span>

<span data-ttu-id="a8e41-107">Modeller för produktkonfiguration skapas för att representera en struktur för den allmänna produkt.</span><span class="sxs-lookup"><span data-stu-id="a8e41-107">Product configuration models are created to represent a generic product structure.</span></span> <span data-ttu-id="a8e41-108">När du har ställt in en modell för produktkonfiguration kan du konfigurera en viss produktvariant som har en unik strukturlista (BOM) och ett unikt flöde.</span><span class="sxs-lookup"><span data-stu-id="a8e41-108">After you've set up a product configuration model, you can configure a distinct product variant that has a unique bill of materials (BOM) and a unique route.</span></span> <span data-ttu-id="a8e41-109">Modeller för produktkonfiguration använder både deklarativa begränsningar och absolut nödvändiga beräkningar för att hantera relationerna och begränsningarna mellan olika produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="a8e41-109">Product configuration models use both declarative constraints and imperative calculations to handle the relations and limitations between different product variants.</span></span> <span data-ttu-id="a8e41-110">Du kan konfigurera artiklar på försäljningsorder, försäljningsofferter, inköpsorder och tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="a8e41-110">You can configure items on sales orders, sales quotations, purchase orders, and production orders.</span></span> <span data-ttu-id="a8e41-111">I tabellen nedan beskrivs de registerbegränsningsbaserade villkoren och koncepten.</span><span class="sxs-lookup"><span data-stu-id="a8e41-111">The following table describes the table constraint–based terms and concepts.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8e41-112">Komponenter</span><span class="sxs-lookup"><span data-stu-id="a8e41-112">Components</span></span></td>
<td><span data-ttu-id="a8e41-113">Komponenterna är huvudbyggnadblocken av en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-113">Components are the main building blocks of a product configuration model.</span></span> <span data-ttu-id="a8e41-114">Komponenter visas i en trädstruktur på sidan <strong>Detaljer för begränsningsbaserad produktkonfigurationsmodell</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-114">Components are displayed in a tree structure on the <strong>Constraint-based product configuration model details</strong> page.</span></span> <span data-ttu-id="a8e41-115">Komponenter kan innehålla följande element:</span><span class="sxs-lookup"><span data-stu-id="a8e41-115">Components can contain the following elements:</span></span>
<ul>
<li><span data-ttu-id="a8e41-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="a8e41-116">Attributes</span></span></li>
<li><span data-ttu-id="a8e41-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="a8e41-117">Constraints</span></span></li>
<li><span data-ttu-id="a8e41-118">Beräkningar</span><span class="sxs-lookup"><span data-stu-id="a8e41-118">Calculations</span></span></li>
<li><span data-ttu-id="a8e41-119">Delkomponenter</span><span class="sxs-lookup"><span data-stu-id="a8e41-119">Subcomponents</span></span></li>
<li><span data-ttu-id="a8e41-120">Användarbehov</span><span class="sxs-lookup"><span data-stu-id="a8e41-120">User requirements</span></span></li>
<li><span data-ttu-id="a8e41-121">Strukturlisterader</span><span class="sxs-lookup"><span data-stu-id="a8e41-121">BOM lines</span></span></li>
<li><span data-ttu-id="a8e41-122">Flödesoperationer</span><span class="sxs-lookup"><span data-stu-id="a8e41-122">Route operations</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-123">Attribut</span><span class="sxs-lookup"><span data-stu-id="a8e41-123">Attributes</span></span></td>
<td><span data-ttu-id="a8e41-124">Attribut beskriver alla funktioner för modellen för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-124">Attributes describe all the features of the product configuration model.</span></span> <span data-ttu-id="a8e41-125">Du kan använda attribut om du vill ange de funktioner som kan väljas, när en specifik produkt som konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a8e41-125">You can use attributes to specify the features that can be selected when a distinct product is configured.</span></span> <span data-ttu-id="a8e41-126">Attribut används i begränsningar och villkor.</span><span class="sxs-lookup"><span data-stu-id="a8e41-126">Attributes are used in constraints and conditions.</span></span> <span data-ttu-id="a8e41-127">När attribut skapas och läggs till en modell för produktkonfiguration, refereras till de relaterade attributtyperna.</span><span class="sxs-lookup"><span data-stu-id="a8e41-127">When attributes are created and added to a product configuration model, the related attribute types are referenced.</span></span> <span data-ttu-id="a8e41-128">Ett standardvärde kan anges för ett attribut.</span><span class="sxs-lookup"><span data-stu-id="a8e41-128">A default value can be set for an attribute.</span></span> <span data-ttu-id="a8e41-129">Standardvärdet används i konfigurationanvändargränssnittet (UI), när modellen för produktkonfiguration konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a8e41-129">The default value is used in the configuration user interface (UI) when the product configuration model is configured.</span></span> <span data-ttu-id="a8e41-130">Du kan ange att ett attribut är obligatoriskt, skrivskyddat, eller dolt.</span><span class="sxs-lookup"><span data-stu-id="a8e41-130">You can specify that an attribute is mandatory, read-only, or hidden.</span></span>
<ul>
<li><span data-ttu-id="a8e41-131"><strong>Obligatorisk</strong> – Ett värde måste anges för attribut, när produkten konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a8e41-131"><strong>Mandatory</strong> – A value must be set for the attribute when the product is configured.</span></span></li>
<li><span data-ttu-id="a8e41-132"><strong>Skrivskyddad</strong> – Attributvärdet visas under en konfigurationssession, men kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="a8e41-132"><strong>Read-only</strong> – The attribute value is displayed during a configuration session, but it can't be changed.</span></span></li>
<li><span data-ttu-id="a8e41-133"><strong>Gömt</strong> – Attributvärdet ingår i begränsningar och kriterier, men visas inte under en konfigurationssession.</span><span class="sxs-lookup"><span data-stu-id="a8e41-133"><strong>Hidden</strong> – The attribute value is included in constraints and conditions, but isn't displayed during a configuration session.</span></span></li>
</ul>
<span data-ttu-id="a8e41-134">Du kan även ange ett villkor för attribut.</span><span class="sxs-lookup"><span data-stu-id="a8e41-134">You can also specify a condition for attributes.</span></span> <span data-ttu-id="a8e41-135">Om villkoret uppfylls, måste ett värde angetts för obligatoriska attribut.</span><span class="sxs-lookup"><span data-stu-id="a8e41-135">If the condition is met, a value must be entered for the mandatory attribute.</span></span> <span data-ttu-id="a8e41-136">Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-136">Conditions are expressions that must be met for attributes, BOM lines, and route operations to be included in a product configuration model.</span></span> <span data-ttu-id="a8e41-137">Alla attribut som refereras i ett villkor, blir obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="a8e41-137">Any attribute that is referenced in a condition becomes mandatory.</span></span> <span data-ttu-id="a8e41-138">Vi rekommenderar att du väljer attribut som är obligatoriska i fliken <strong>Attribut</strong>. Detta kan göra det enklare att identifiera obligatoriska attribut.</span><span class="sxs-lookup"><span data-stu-id="a8e41-138">We recommend that you select attributes as mandatory on the <strong>Attributes</strong> tab. This can make it easier to identify mandatory attributes.</span></span> <span data-ttu-id="a8e41-139">Attributvärden är en viktig del av du vill återanvända konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="a8e41-139">Attribute values are an important part of reusing configurations.</span></span> <span data-ttu-id="a8e41-140">Attributvärden används för att fastställer om en konfiguration finns, som matchar val som en användare har gjort under en konfigurationssession.</span><span class="sxs-lookup"><span data-stu-id="a8e41-140">The system uses attribute values to determine whether a configuration exists that matches the selections that a user made during a configuration session.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-141">Attributtyper</span><span class="sxs-lookup"><span data-stu-id="a8e41-141">Attribute types</span></span></td>
<td><span data-ttu-id="a8e41-142">Attributtyper anger de uppsättning datatyper för attribut som används i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-142">Attribute types specify the set of data types for attributes that are used in a product configuration model.</span></span> <span data-ttu-id="a8e41-143">Följande attributtyper används:</span><span class="sxs-lookup"><span data-stu-id="a8e41-143">The following attribute types are used:</span></span>
<ul>
<li><span data-ttu-id="a8e41-144"><strong>Heltal</strong> med eller utan ett intervall</span><span class="sxs-lookup"><span data-stu-id="a8e41-144"><strong>Integer</strong> with or without a range</span></span></li>
<li><span data-ttu-id="a8e41-145"><strong>Decimal</strong></span><span class="sxs-lookup"><span data-stu-id="a8e41-145"><strong>Decimal</strong></span></span></li>
<li><span data-ttu-id="a8e41-146"><strong>Text</strong> med eller utan en fast lista</span><span class="sxs-lookup"><span data-stu-id="a8e41-146"><strong>Text</strong> with or without a fixed list</span></span></li>
<li><span data-ttu-id="a8e41-147"><strong>Boolesk</strong></span><span class="sxs-lookup"><span data-stu-id="a8e41-147"><strong>Boolean</strong></span></span></li>
</ul>
<span data-ttu-id="a8e41-148">Om attributtypen är <strong>Booleskt</strong>, <strong>Heltal</strong> med ett intervall, eller <strong>Text</strong> med en fast lista är uppsättning värden tillgänglig när en modell för produktkonfiguration ställs in.</span><span class="sxs-lookup"><span data-stu-id="a8e41-148">If the attribute type is <strong>Boolean</strong>, <strong>Integer</strong> with a range, or <strong>Text</strong> with a fixed list, the set of values is available when a product configuration model is set up.</span></span> <span data-ttu-id="a8e41-149"><strong>Obs!</strong> Produktkonfigurationslösaren känner bara igen följande attributtyper: <strong>Booelskt</strong>, <strong>Text</strong> med en fast lista och <strong>Heltal</strong> med ett intervall.</span><span class="sxs-lookup"><span data-stu-id="a8e41-149"><strong>Note:</strong> The Product configuration solver recognizes only the following attribute types: <strong>Boolean</strong>, <strong>Text</strong> with a fixed list, and <strong>Integer</strong> with a range.</span></span> <span data-ttu-id="a8e41-150">Därför kan endast dessa attributtyper användas i uttryckbegränsningar och villkor.</span><span class="sxs-lookup"><span data-stu-id="a8e41-150">Therefore, only these attribute types can be used in expression constraints and conditions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-151">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="a8e41-151">Constraints</span></span></td>
<td><span data-ttu-id="a8e41-152">Begränsningar beskriver begränsningarna i produktmodellkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="a8e41-152">Constraints describe the restrictions of the product model configuration.</span></span> <span data-ttu-id="a8e41-153">Begränsningar används för att garantera att endast giltiga värden väljs när en produkt konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a8e41-153">Constraints are used to guarantee that only valid values are selected when a product is being configured.</span></span> <span data-ttu-id="a8e41-154">Det kan antingen vara uttryckbegränsningar eller registret begränsningar:</span><span class="sxs-lookup"><span data-stu-id="a8e41-154">Constraints can be either expression constraints or table constraints:</span></span>
<ul>
<li><span data-ttu-id="a8e41-155">Uttryckbegränsningar kan bara användas för komponenten att de är kopplat till.</span><span class="sxs-lookup"><span data-stu-id="a8e41-155">Expression constraints can be used only for the component that they are tied to.</span></span> <span data-ttu-id="a8e41-156">Uttryckbegränsningarna för en komponent kan referera till attribut i komponentens delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="a8e41-156">The expression constraints for a component can reference attributes of the component's subcomponents.</span></span> <span data-ttu-id="a8e41-157">Produktkonfigurationslösaren används för att lösa begränsningar, och du måste använda lösarens syntax när du skriver begränsningarna.</span><span class="sxs-lookup"><span data-stu-id="a8e41-157">The Product configuration solver is used to solve the constraints, and you must use the solver syntax when you write the constraints.</span></span> <span data-ttu-id="a8e41-158">Mer information finns på avsnittslänken om uttrycksbegränsningar och registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="a8e41-158">For more information, see the topic link about expression constraints and table constraints.</span></span></li>
<li><span data-ttu-id="a8e41-159">Registerbegränsningar måste definieras innan de kan användas på en komponent i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="a8e41-159">Table constraints must be defined before they can be applied to a component in a product configuration model.</span></span> <span data-ttu-id="a8e41-160">Registerbegränsningar kan vara antingen användardefinierade eller systemdefinierade.</span><span class="sxs-lookup"><span data-stu-id="a8e41-160">Table constraints can be either user-defined or system-defined.</span></span> <span data-ttu-id="a8e41-161">En användardefinierad registerbegränsning är en sorts matris som kan användas för att beskriva uppsättningen kombinationer vilka definieras av attributtyper.</span><span class="sxs-lookup"><span data-stu-id="a8e41-161">A user-defined table constraint is a type of matrix that can be used to describe the set of combinations for the attribute values that are defined by attribute types.</span></span> <span data-ttu-id="a8e41-162">Om till exempel högtalare tillverkas kan matrisen för en användardefinierad registerbegränsning ha kolumner för högtalarens finish och högtalargallret.</span><span class="sxs-lookup"><span data-stu-id="a8e41-162">For example, if speakers are produced, the matrix for a user-defined table constraint might have columns for the speaker finish and grill.</span></span></li>
</ul><span data-ttu-id="a8e41-163">
<strong>Exempel</strong> Högtalarna är tillgängliga i fyra varianter: Svart, Ek, och Rosenträ och Vitt.</span><span class="sxs-lookup"><span data-stu-id="a8e41-163">
<strong>Example</strong> Speakers are available in four finishes: Black, Oak, Rosewood, and White.</span></span> <span data-ttu-id="a8e41-164">Högtalarna kan ha ett av tre främre galler: svart, metall eller vitt.</span><span class="sxs-lookup"><span data-stu-id="a8e41-164">The speakers can have one of three front grills: Black, Metal, or White.</span></span> <span data-ttu-id="a8e41-165">Svart finish är tillgänglig för alla galler och andra ytbehandlingar begränsas till vissa galler.</span><span class="sxs-lookup"><span data-stu-id="a8e41-165">The Black finish is available for all grills, but the other finishes are limited to specific grills.</span></span> <span data-ttu-id="a8e41-166">Följande tabell visar ett exempel på informationen som visas på fliken <strong>Tillåtna kombinationer</strong> på sidan <strong>Redigera registerbegränsning</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-166">The following table shows an example of the information that is displayed on the <strong>Allowed combinations</strong> tab on the <strong>Edit table constraint</strong> page.</span></span>
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a8e41-167">Kabinettfinish</span><span class="sxs-lookup"><span data-stu-id="a8e41-167">Cabinet finish</span></span></th>
<th><span data-ttu-id="a8e41-168">Frontgaller</span><span class="sxs-lookup"><span data-stu-id="a8e41-168">Front grill</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8e41-169">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-169">Black</span></span></td>
<td><span data-ttu-id="a8e41-170">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-170">Black</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-171">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-171">Black</span></span></td>
<td><span data-ttu-id="a8e41-172">Metall</span><span class="sxs-lookup"><span data-stu-id="a8e41-172">Metal</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-173">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-173">Black</span></span></td>
<td><span data-ttu-id="a8e41-174">Vit</span><span class="sxs-lookup"><span data-stu-id="a8e41-174">White</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-175">Ek</span><span class="sxs-lookup"><span data-stu-id="a8e41-175">Oak</span></span></td>
<td><span data-ttu-id="a8e41-176">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-176">Black</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-177">Rosenträ</span><span class="sxs-lookup"><span data-stu-id="a8e41-177">Rosewood</span></span></td>
<td><span data-ttu-id="a8e41-178">Vit</span><span class="sxs-lookup"><span data-stu-id="a8e41-178">White</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-179">Vit</span><span class="sxs-lookup"><span data-stu-id="a8e41-179">White</span></span></td>
<td><span data-ttu-id="a8e41-180">Svart</span><span class="sxs-lookup"><span data-stu-id="a8e41-180">Black</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-181">Vit</span><span class="sxs-lookup"><span data-stu-id="a8e41-181">White</span></span></td>
<td><span data-ttu-id="a8e41-182">Vit</span><span class="sxs-lookup"><span data-stu-id="a8e41-182">White</span></span></td>
</tr>
</tbody>
</table>
<span data-ttu-id="a8e41-183">En systemdefinierad registerbegränsning representerar en koppling mellan en attributtyp och ett fält i ett Finance and Operations-register.</span><span class="sxs-lookup"><span data-stu-id="a8e41-183">A system-defined table constraint represents a mapping between an attribute type and a field in a Finance and Operations table.</span></span> <span data-ttu-id="a8e41-184">Systemdefinierade registerbegränsningar kopplar dynamiskt attributtypen till fältet.</span><span class="sxs-lookup"><span data-stu-id="a8e41-184">A system-defined table constraint dynamically links the attribute type to the field.</span></span> <span data-ttu-id="a8e41-185">Länken gör att attributet i en produktkonfigurationsmodell återspeglar data i fältet i Finance and Operations-registret.</span><span class="sxs-lookup"><span data-stu-id="a8e41-185">The link enables the attribute in a product configuration model to reflect the data of the field in the Finance and Operations table.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-186">Beräkningar</span><span class="sxs-lookup"><span data-stu-id="a8e41-186">Calculations</span></span></td>
<td><span data-ttu-id="a8e41-187">Beräkningar representerar ett tillägg till begränsningar.</span><span class="sxs-lookup"><span data-stu-id="a8e41-187">Calculations represent a supplement to constraints.</span></span> <span data-ttu-id="a8e41-188">Du kan använda en beräkning för att utföra aritmetiska operationer på attribut av typen <strong>Decimal</strong> och <strong>Heltal</strong>, eller logiska operationer som gäller attribut av typen <strong>Text</strong> med en fast lista eller <strong>Booleskt</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-188">You can use a calculation to perform arithmetic operations on attributes of the <strong>Decimal</strong> and <strong>Integer</strong> types, or logical operations that involve attributes of the <strong>Text</strong> with a fixed list and <strong>Boolean</strong> types.</span></span> <span data-ttu-id="a8e41-189">En beräkning har ett målattribut som ska innehålla resultatet av beräkningsuttrycket.</span><span class="sxs-lookup"><span data-stu-id="a8e41-189">A calculation has a target attribute that will hold the result of the calculation expression.</span></span> <span data-ttu-id="a8e41-190">Du bygger beräkningsuttrycket med hjälp av uttrycksredigeraren.</span><span class="sxs-lookup"><span data-stu-id="a8e41-190">The calculation expression is built by using the expression editor.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-191">Delkomponenter</span><span class="sxs-lookup"><span data-stu-id="a8e41-191">Subcomponents</span></span></td>
<td><span data-ttu-id="a8e41-192">Delkomponenter återspeglar trädstrukturen för den modell som produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-192">Subcomponents reflect the tree structure of the product configuration model.</span></span> <span data-ttu-id="a8e41-193">Du kan använda delkomponenter för att skapa strukturen för modellen för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-193">You can use subcomponents to build the structure of the product configuration model.</span></span> <span data-ttu-id="a8e41-194">Delkomponenter refererar till befintliga komponenter.</span><span class="sxs-lookup"><span data-stu-id="a8e41-194">Subcomponents reference existing components.</span></span> <span data-ttu-id="a8e41-195">Därför främjar delkomponenter återanvändningen av komponenter i flera modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-195">Therefore, subcomponents encourage the reuse of components in multiple product configuration models.</span></span> <span data-ttu-id="a8e41-196">På sidan <strong>Information för strukturlisterad</strong> för en delkomponent kan du välja ett annat värde för delkomponenten.</span><span class="sxs-lookup"><span data-stu-id="a8e41-196">On the <strong>BOM line details</strong> page for a subcomponent, you can select a distinct value for the subcomponent.</span></span> <span data-ttu-id="a8e41-197">Alternativt kan du välja ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in.</span><span class="sxs-lookup"><span data-stu-id="a8e41-197">Alternatively, you can select an attribute that the value is selected for when the product configuration model is set up.</span></span> <span data-ttu-id="a8e41-198">Om du vill ta med en produkt som en komponent eller delkomponent måste du ange följande på sidan <strong>Skapa produkt</strong> när du skapar produkten:</span><span class="sxs-lookup"><span data-stu-id="a8e41-198">To include a product as a component or subcomponent, you must specify the following information on the <strong>Create product</strong> page when you create the product:</span></span>
<ul>
<li><span data-ttu-id="a8e41-199">Välj <strong>Artikel</strong> i fältet <strong>Produkttyp</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-199">In the <strong>Product type</strong> field, select <strong>Item</strong>.</span></span></li>
<li><span data-ttu-id="a8e41-200">I fältet <strong>Delprodukttyp</strong> väljer du <strong>Produkthuvud</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-200">In the <strong>Product subtype</strong> field, select <strong>Product master</strong>.</span></span></li>
<li><span data-ttu-id="a8e41-201">I fältet <strong>Konfigurationsteknik</strong> väljer du <strong>Begränsningsbaserad konfiguration</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-201">In the <strong>Configuration technology</strong> field, select <strong>Constraint-based configuration</strong>.</span></span></li>
</ul>
<span data-ttu-id="a8e41-202">Du kan visa om en frisläppt produkt kan användas som en komponent eller delkomponent på fliken <strong>Allmänt</strong> på sidan <strong>Information om frisläppt produkt</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8e41-202">You can view whether a released product can be used as a component or subcomponent on the <strong>General</strong> tab of the <strong>Released product details</strong> page.</span></span> <span data-ttu-id="a8e41-203">Om <strong>Begränsningsbaserad konfiguration</strong> valts i fältet <strong>Konfigurationsteknik</strong> kan produkten användas som en komponent eller delkomponent.</span><span class="sxs-lookup"><span data-stu-id="a8e41-203">If <strong>Constraint-based configuration</strong> is selected in the <strong>Configuration technology</strong> field, the product can be used as a component or subcomponent.</span></span> <span data-ttu-id="a8e41-204">Du kan dölja delkomponenter så att de inte visas för användaren under en konfigurationssession.</span><span class="sxs-lookup"><span data-stu-id="a8e41-204">You can hide subcomponents so that they aren't displayed to the user during a configuration session.</span></span> <span data-ttu-id="a8e41-205">Attribut, delkomponenter och användarkrav, som gäller delkomponenten, döljs också.</span><span class="sxs-lookup"><span data-stu-id="a8e41-205">Attributes, subcomponents, and user requirements that are related to the subcomponent are also hidden.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-206">Användarbehov</span><span class="sxs-lookup"><span data-stu-id="a8e41-206">User requirements</span></span></td>
<td><span data-ttu-id="a8e41-207">Användarkrav representerar en abstraktion mellan användarkrav och specifika komponenter och attribut.</span><span class="sxs-lookup"><span data-stu-id="a8e41-207">User requirements represent an abstraction between user requirements and specific components and attributes.</span></span> <span data-ttu-id="a8e41-208">Du kan inte koppla ett användarkrav till en artikel.</span><span class="sxs-lookup"><span data-stu-id="a8e41-208">You can't map a user requirement to an item.</span></span> <span data-ttu-id="a8e41-209">Till exempel en kund shoppar för ett hemmabiosystem.</span><span class="sxs-lookup"><span data-stu-id="a8e41-209">For example, a customer is shopping for a home theater system.</span></span> <span data-ttu-id="a8e41-210">Försäljaren kanske ber om storleken på platsen där kund planerar att installera systemet, som bestämmer hur många watt krävs.</span><span class="sxs-lookup"><span data-stu-id="a8e41-210">The sales representative might ask about the size of the room where the customer plans to install the system, to determine how many watts are required.</span></span> <span data-ttu-id="a8e41-211">I det här exemplet kan platsstorleken vara ett användarkrav som hjälper dig att bestämma lämpligt attributvärde för en viss komponent. Du kan dölja användarkrav så att de inte visas för användaren under en konfigurationssession.</span><span class="sxs-lookup"><span data-stu-id="a8e41-211">In this example, the room size can be a user requirement that helps determine the appropriate attribute value for a specific component.You can hide user requirements so that they aren't displayed to the user during a configuration session.</span></span> <span data-ttu-id="a8e41-212">Attribut, delkomponenter och användarkrav, som gäller användarkrav, döljs också.</span><span class="sxs-lookup"><span data-stu-id="a8e41-212">Attributes, subcomponents, and user requirements that are related to the user requirement are also hidden.</span></span> <span data-ttu-id="a8e41-213">Du kan ange ett villkor för att kontrollera om en användarkrav kan döljas.</span><span class="sxs-lookup"><span data-stu-id="a8e41-213">You can write a condition to control whether a user requirement can be hidden.</span></span> <span data-ttu-id="a8e41-214">Du måste ange villkoret med hjälp av OML-syntaxen (Optimization Modeling Language).</span><span class="sxs-lookup"><span data-stu-id="a8e41-214">You must write the condition by using Optimization Modeling Language (OML) syntax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8e41-215">Strukturlisterader</span><span class="sxs-lookup"><span data-stu-id="a8e41-215">BOM lines</span></span></td>
<td><span data-ttu-id="a8e41-216">Strukturlisterader representerar de enskilda materialen av komponenterna i modellen för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-216">BOM lines represent the individual materials of the components in the product configuration model.</span></span> <span data-ttu-id="a8e41-217">På sidan <strong>Information för strukturlisterad</strong> är alla artiklar tillgängliga för val.</span><span class="sxs-lookup"><span data-stu-id="a8e41-217">On the <strong>BOM line details</strong> page, all items are available for selection.</span></span> <span data-ttu-id="a8e41-218">Ett villkor kan läggas till på strukturlisteraden, så att strukturlisteraderna som väljs för en viss produktvariant kan variera, baserat på användarens val när modellen för produktkonfiguration ställs in.</span><span class="sxs-lookup"><span data-stu-id="a8e41-218">A condition can be added to the BOM line, so that the BOM lines that are selected for a distinct product variant can vary, based on the user's selection when the product configuration model is set up.</span></span> <span data-ttu-id="a8e41-219">Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-219">Conditions are expressions that must be met for attributes, BOM lines, and route operations to be included in a product configuration model.</span></span> <span data-ttu-id="a8e41-220">På sidan <strong>Information för strukturlisterad</strong> kan du välja ett annat värde.</span><span class="sxs-lookup"><span data-stu-id="a8e41-220">On the <strong>BOM line details</strong> page, you can select a distinct value.</span></span> <span data-ttu-id="a8e41-221">Alternativt kan du koppla ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in.</span><span class="sxs-lookup"><span data-stu-id="a8e41-221">Alternatively, you can map to an attribute that the value is selected for when the product configuration model is set up.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8e41-222">Flödesoperationer</span><span class="sxs-lookup"><span data-stu-id="a8e41-222">Route operations</span></span></td>
<td><span data-ttu-id="a8e41-223">På sidan <strong>Flödesoperationsinformation</strong> kan du välja ett annat värde.</span><span class="sxs-lookup"><span data-stu-id="a8e41-223">On the <strong>Route operation details</strong> page, you can select a distinct value.</span></span> <span data-ttu-id="a8e41-224">Alternativt kan du koppla ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in.</span><span class="sxs-lookup"><span data-stu-id="a8e41-224">Alternatively, you can map to an attribute that the value is selected for when the product configuration model is set up.</span></span> <span data-ttu-id="a8e41-225">Villkor skrivs som uttryckbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="a8e41-225">Conditions are written like expression constraints.</span></span> <span data-ttu-id="a8e41-226">Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8e41-226">Conditions are expressions that must be met for attributes, BOM lines, and route operations to be included in a product configuration model.</span></span></td>
</tr>
</tbody>
</table>





