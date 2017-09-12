---
title: "Systemdefinierade och användardefinierade registerbegränsningar"
description: "Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade. Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 9bce875b5688c3b2449262437091e28dbcb740f0
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="cdfcf-104">Systemdefinierade och användardefinierade registerbegränsningar</span><span class="sxs-lookup"><span data-stu-id="cdfcf-104">System-defined and user-defined table constraints</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cdfcf-105">Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="cdfcf-106">Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="cdfcf-107">Registerbegränsningar representerar matriser av kombinationer av attribut som tillåts för komponenter i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="cdfcf-108">Varje rad i registeren definierar en uppsättning möjliga attributvärden.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="cdfcf-109">Du kan ange två typer av begränsningar i en produktkonfigurationsmodell:</span><span class="sxs-lookup"><span data-stu-id="cdfcf-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="cdfcf-110">**Uttryckbegränsning** – Skapa ett uttryck som definierar relationer mellan attribut som garanterar att endast kompatibla värden kan markeras under produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="cdfcf-111">**registerbegränsning** – Skapa ett register som definierar alla kombinationer, som tillåts för en viss uppsättning attribut.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="cdfcf-112">Två typer av registerbegränsningar finns: användardefinierade registerbegränsningar och systemdefinierade registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="cdfcf-113">Denna artikel beskriver användardefinierade och systemdefinierade registerbegränsningar för komponenter i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="cdfcf-114">Användardefinierad registerbegränsning</span><span class="sxs-lookup"><span data-stu-id="cdfcf-114">User-defined table constraints</span></span>
<span data-ttu-id="cdfcf-115">En användardefinierad registerbegränsning är en sorts matris som kan användas för att beskriva uppsättningen kombinationer vilka definieras av attributtyper.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="cdfcf-116">Om du till exempel tillverkar högtalare, kan du inkludera kolumner för kabinettfinish och frontgaller i den användardefinierade registerbegränsningen.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="cdfcf-117">Attributtypen för det kabinettfinish har fyra värden, och attributtypen för frontgaller har tre värden.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="cdfcf-118">Därför om begränsningar inte används finns det 4 × 3 = 12 möjliga kombinationer.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="cdfcf-119">Men i det här exemplet tillåts bara sex kombinationer, som visas i följande register.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="cdfcf-120">Informationen visas på fliken **Tillåtna kombinationer** på sidan **Redigera registerbegränsning**.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="cdfcf-121">Kabinettfinish</span><span class="sxs-lookup"><span data-stu-id="cdfcf-121">Cabinet finish</span></span> | <span data-ttu-id="cdfcf-122">Frontgaller</span><span class="sxs-lookup"><span data-stu-id="cdfcf-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="cdfcf-123">Svart</span><span class="sxs-lookup"><span data-stu-id="cdfcf-123">Black</span></span>          | <span data-ttu-id="cdfcf-124">Svart</span><span class="sxs-lookup"><span data-stu-id="cdfcf-124">Black</span></span>       |
| <span data-ttu-id="cdfcf-125">Svart</span><span class="sxs-lookup"><span data-stu-id="cdfcf-125">Black</span></span>          | <span data-ttu-id="cdfcf-126">Metall</span><span class="sxs-lookup"><span data-stu-id="cdfcf-126">Metal</span></span>       |
| <span data-ttu-id="cdfcf-127">Ek</span><span class="sxs-lookup"><span data-stu-id="cdfcf-127">Oak</span></span>            | <span data-ttu-id="cdfcf-128">Svart</span><span class="sxs-lookup"><span data-stu-id="cdfcf-128">Black</span></span>       |
| <span data-ttu-id="cdfcf-129">Rosenträ</span><span class="sxs-lookup"><span data-stu-id="cdfcf-129">Rosewood</span></span>       | <span data-ttu-id="cdfcf-130">Vit</span><span class="sxs-lookup"><span data-stu-id="cdfcf-130">White</span></span>       |
| <span data-ttu-id="cdfcf-131">Vit</span><span class="sxs-lookup"><span data-stu-id="cdfcf-131">White</span></span>          | <span data-ttu-id="cdfcf-132">Svart</span><span class="sxs-lookup"><span data-stu-id="cdfcf-132">Black</span></span>       |
| <span data-ttu-id="cdfcf-133">Vit</span><span class="sxs-lookup"><span data-stu-id="cdfcf-133">White</span></span>          | <span data-ttu-id="cdfcf-134">Vit</span><span class="sxs-lookup"><span data-stu-id="cdfcf-134">White</span></span>       |

<span data-ttu-id="cdfcf-135">Användardefinierade registerbegränsningar definieras av statisk streckkodsindata som fungerar på samma sätt som en uttrycksbegränsning.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="cdfcf-136">När du använder en användardefinierad registerbegränsning, är fördelen att registerer är ofta enklare att skapa och underhåla än långa uttryckbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="cdfcf-137">Systemdefinierad registerbegränsning</span><span class="sxs-lookup"><span data-stu-id="cdfcf-137">System-defined table constraints</span></span>
<span data-ttu-id="cdfcf-138">En systemdefinierad registerbegränsning skapar en dynamisk mappning mellan en attributtyp och ett fält i ett register.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="cdfcf-139">När en systemdefinierad registerbegränsning inkluderas i en produktkonfigurationsmodell garanterar mappningen att data i registret visas i stället för attributtypens värden.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="cdfcf-140">Resultatet är en dynamisk begränsning, eftersom registerinnehållen kan ändras (exempelvis efter andra moduler.)</span><span class="sxs-lookup"><span data-stu-id="cdfcf-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="cdfcf-141">När du skapar en systemdefinierad registerbegränsning, väljer du ett register, definierar valfritt frågan som ska användas, och sedan associerar du attributtyper i fälten i det valda registret.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="cdfcf-142">Dessa fälttyper måste matcha attributtyperna.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="cdfcf-143">Innan ett register kan tillämpas på en modell för produktkonfiguration måste registerbegränsningen inkluderas i en begränsning av en av modellens komponenter.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="cdfcf-144">Proceduren är att skapa en ny begränsning, markera typen av begränsning och välj den definition av registerbegränsning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="cdfcf-145">Så småningom måste alla fält i registerbegränsningen mappas till attribut i produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="see-also"></a><span data-ttu-id="cdfcf-146">Se även</span><span class="sxs-lookup"><span data-stu-id="cdfcf-146">See also</span></span>
--------

[<span data-ttu-id="cdfcf-147">Nyckelbegrepp i produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="cdfcf-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)




