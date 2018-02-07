---
title: "Systemdefinierade och användardefinierade registerbegränsningar"
description: "Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade. Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 4da560ca3cce5a28edd2a00506f825d5d88ef0f3
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="4d476-104">Systemdefinierade och användardefinierade registerbegränsningar</span><span class="sxs-lookup"><span data-stu-id="4d476-104">System-defined and user-defined table constraints</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4d476-105">Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade.</span><span class="sxs-lookup"><span data-stu-id="4d476-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="4d476-106">Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden.</span><span class="sxs-lookup"><span data-stu-id="4d476-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="4d476-107">Registerbegränsningar representerar matriser av kombinationer av attribut som tillåts för komponenter i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="4d476-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="4d476-108">Varje rad i registeren definierar en uppsättning möjliga attributvärden.</span><span class="sxs-lookup"><span data-stu-id="4d476-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="4d476-109">Du kan ange två typer av begränsningar i en produktkonfigurationsmodell:</span><span class="sxs-lookup"><span data-stu-id="4d476-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="4d476-110">**Uttryckbegränsning** – Skapa ett uttryck som definierar relationer mellan attribut som garanterar att endast kompatibla värden kan markeras under produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4d476-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="4d476-111">**registerbegränsning** – Skapa ett register som definierar alla kombinationer, som tillåts för en viss uppsättning attribut.</span><span class="sxs-lookup"><span data-stu-id="4d476-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="4d476-112">Två typer av registerbegränsningar finns: användardefinierade registerbegränsningar och systemdefinierade registerbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="4d476-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="4d476-113">Denna artikel beskriver användardefinierade och systemdefinierade registerbegränsningar för komponenter i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="4d476-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="4d476-114">Användardefinierad registerbegränsning</span><span class="sxs-lookup"><span data-stu-id="4d476-114">User-defined table constraints</span></span>
<span data-ttu-id="4d476-115">En användardefinierad registerbegränsning är en sorts matris som kan användas för att beskriva uppsättningen kombinationer vilka definieras av attributtyper.</span><span class="sxs-lookup"><span data-stu-id="4d476-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="4d476-116">Om du till exempel tillverkar högtalare, kan du inkludera kolumner för kabinettfinish och frontgaller i den användardefinierade registerbegränsningen.</span><span class="sxs-lookup"><span data-stu-id="4d476-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="4d476-117">Attributtypen för det kabinettfinish har fyra värden, och attributtypen för frontgaller har tre värden.</span><span class="sxs-lookup"><span data-stu-id="4d476-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="4d476-118">Därför om begränsningar inte används finns det 4 × 3 = 12 möjliga kombinationer.</span><span class="sxs-lookup"><span data-stu-id="4d476-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="4d476-119">Men i det här exemplet tillåts bara sex kombinationer, som visas i följande register.</span><span class="sxs-lookup"><span data-stu-id="4d476-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="4d476-120">Informationen visas på fliken **Tillåtna kombinationer** på sidan **Redigera registerbegränsning**.</span><span class="sxs-lookup"><span data-stu-id="4d476-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="4d476-121">Kabinettfinish</span><span class="sxs-lookup"><span data-stu-id="4d476-121">Cabinet finish</span></span> | <span data-ttu-id="4d476-122">Frontgaller</span><span class="sxs-lookup"><span data-stu-id="4d476-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="4d476-123">Svart</span><span class="sxs-lookup"><span data-stu-id="4d476-123">Black</span></span>          | <span data-ttu-id="4d476-124">Svart</span><span class="sxs-lookup"><span data-stu-id="4d476-124">Black</span></span>       |
| <span data-ttu-id="4d476-125">Svart</span><span class="sxs-lookup"><span data-stu-id="4d476-125">Black</span></span>          | <span data-ttu-id="4d476-126">Metall</span><span class="sxs-lookup"><span data-stu-id="4d476-126">Metal</span></span>       |
| <span data-ttu-id="4d476-127">Ek</span><span class="sxs-lookup"><span data-stu-id="4d476-127">Oak</span></span>            | <span data-ttu-id="4d476-128">Svart</span><span class="sxs-lookup"><span data-stu-id="4d476-128">Black</span></span>       |
| <span data-ttu-id="4d476-129">Rosenträ</span><span class="sxs-lookup"><span data-stu-id="4d476-129">Rosewood</span></span>       | <span data-ttu-id="4d476-130">Vit</span><span class="sxs-lookup"><span data-stu-id="4d476-130">White</span></span>       |
| <span data-ttu-id="4d476-131">Vit</span><span class="sxs-lookup"><span data-stu-id="4d476-131">White</span></span>          | <span data-ttu-id="4d476-132">Svart</span><span class="sxs-lookup"><span data-stu-id="4d476-132">Black</span></span>       |
| <span data-ttu-id="4d476-133">Vit</span><span class="sxs-lookup"><span data-stu-id="4d476-133">White</span></span>          | <span data-ttu-id="4d476-134">Vit</span><span class="sxs-lookup"><span data-stu-id="4d476-134">White</span></span>       |

<span data-ttu-id="4d476-135">Användardefinierade registerbegränsningar definieras av statisk streckkodsindata som fungerar på samma sätt som en uttrycksbegränsning.</span><span class="sxs-lookup"><span data-stu-id="4d476-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="4d476-136">När du använder en användardefinierad registerbegränsning, är fördelen att registerer är ofta enklare att skapa och underhåla än långa uttryckbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="4d476-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="4d476-137">Systemdefinierad registerbegränsning</span><span class="sxs-lookup"><span data-stu-id="4d476-137">System-defined table constraints</span></span>
<span data-ttu-id="4d476-138">En systemdefinierad registerbegränsning skapar en dynamisk mappning mellan en attributtyp och ett fält i ett register.</span><span class="sxs-lookup"><span data-stu-id="4d476-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="4d476-139">När en systemdefinierad registerbegränsning inkluderas i en produktkonfigurationsmodell garanterar mappningen att data i registret visas i stället för attributtypens värden.</span><span class="sxs-lookup"><span data-stu-id="4d476-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="4d476-140">Resultatet är en dynamisk begränsning, eftersom registerinnehållen kan ändras (exempelvis efter andra moduler.)</span><span class="sxs-lookup"><span data-stu-id="4d476-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="4d476-141">När du skapar en systemdefinierad registerbegränsning, väljer du ett register, definierar valfritt frågan som ska användas, och sedan associerar du attributtyper i fälten i det valda registret.</span><span class="sxs-lookup"><span data-stu-id="4d476-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="4d476-142">Dessa fälttyper måste matcha attributtyperna.</span><span class="sxs-lookup"><span data-stu-id="4d476-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="4d476-143">Innan ett register kan tillämpas på en modell för produktkonfiguration måste registerbegränsningen inkluderas i en begränsning av en av modellens komponenter.</span><span class="sxs-lookup"><span data-stu-id="4d476-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="4d476-144">Proceduren är att skapa en ny begränsning, markera typen av begränsning och välj den definition av registerbegränsning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="4d476-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="4d476-145">Så småningom måste alla fält i registerbegränsningen mappas till attribut i produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="4d476-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="see-also"></a><span data-ttu-id="4d476-146">Se även</span><span class="sxs-lookup"><span data-stu-id="4d476-146">See also</span></span>
--------

[<span data-ttu-id="4d476-147">Nyckelbegrepp i produktkonfigurationsmodeller</span><span class="sxs-lookup"><span data-stu-id="4d476-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)




