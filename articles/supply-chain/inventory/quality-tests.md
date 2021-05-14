---
title: Kvalitetshanteringstester
description: I det här ämnet beskrivs hur du skapar tester som kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956833"
---
# <a name="quality-management-tests"></a><span data-ttu-id="67ac0-103">Kvalitetshanteringstester</span><span class="sxs-lookup"><span data-stu-id="67ac0-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67ac0-104">I det här ämnet beskrivs hur du skapar tester som kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="67ac0-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="67ac0-105">Du använder sidan **Tester** när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna.</span><span class="sxs-lookup"><span data-stu-id="67ac0-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="67ac0-106">Du kan tilldela en eller flera enskilda tester till en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="67ac0-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="67ac0-107">I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden.</span><span class="sxs-lookup"><span data-stu-id="67ac0-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="67ac0-108">Mätningsvärden används vid kvantitativa tester.</span><span class="sxs-lookup"><span data-stu-id="67ac0-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="67ac0-109">För kvalitativa tester används testvariabler.</span><span class="sxs-lookup"><span data-stu-id="67ac0-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="67ac0-110">För kvantitativa tester ställs fältet **Typ** in på *Heltal* eller *Del*.</span><span class="sxs-lookup"><span data-stu-id="67ac0-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="67ac0-111">En måttenhet anges också.</span><span class="sxs-lookup"><span data-stu-id="67ac0-111">A unit of measure is also specified.</span></span> <span data-ttu-id="67ac0-112">Kvalitetsspecifikationer och testresultat uttrycks som nummer.</span><span class="sxs-lookup"><span data-stu-id="67ac0-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="67ac0-113">För kvalitativa tester måste du ange fältet **Typ** som *Alternativ*.</span><span class="sxs-lookup"><span data-stu-id="67ac0-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="67ac0-114">Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ.</span><span class="sxs-lookup"><span data-stu-id="67ac0-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="67ac0-115">Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.</span><span class="sxs-lookup"><span data-stu-id="67ac0-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="67ac0-116">Du kan som tillval också tilldela ett testinstrument till ett test.</span><span class="sxs-lookup"><span data-stu-id="67ac0-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="67ac0-117">Testinstrumenten behövs emellertid inte för att skapa och använda tester med kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="67ac0-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="67ac0-118">Mer information finns i [Testinstrument för kvalitetshantering](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="67ac0-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="67ac0-119">Om du vill kan du även ange en enhet för ett test i syfte att ange måttenheten som testresultatet registreras i.</span><span class="sxs-lookup"><span data-stu-id="67ac0-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="67ac0-120">Ett test för temperatur kan till exempel innehålla en enhet med antingen grader i Fahrenheit eller Celsius.</span><span class="sxs-lookup"><span data-stu-id="67ac0-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="67ac0-121">Exempel på ett test</span><span class="sxs-lookup"><span data-stu-id="67ac0-121">Example of a test</span></span>

<span data-ttu-id="67ac0-122">Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test för förpackningsskador.</span><span class="sxs-lookup"><span data-stu-id="67ac0-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="67ac0-123">Företaget anger ytterligare information om det kvalitativa testet för att definiera testvariabeln (exempelvis skadad förpackning) och dess utfall.</span><span class="sxs-lookup"><span data-stu-id="67ac0-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="67ac0-124">Företaget använder sidan **Testgrupper** för att tilldela de två testerna till en testgrupp och ange testspecifik information.</span><span class="sxs-lookup"><span data-stu-id="67ac0-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="67ac0-125">Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.</span><span class="sxs-lookup"><span data-stu-id="67ac0-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="67ac0-126">Skapa test</span><span class="sxs-lookup"><span data-stu-id="67ac0-126">Create a test</span></span>

<span data-ttu-id="67ac0-127">Följ dessa steg om du vill skapa ett test.</span><span class="sxs-lookup"><span data-stu-id="67ac0-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="67ac0-128">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Tester**.</span><span class="sxs-lookup"><span data-stu-id="67ac0-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="67ac0-129">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="67ac0-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="67ac0-130">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="67ac0-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="67ac0-131">**Testgrupp** – Ange ett unikt ID eller namn för testgruppen.</span><span class="sxs-lookup"><span data-stu-id="67ac0-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="67ac0-132">**Beskrivning** – Ange en detaljerad beskrivning av testgruppen.</span><span class="sxs-lookup"><span data-stu-id="67ac0-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="67ac0-133">**Typ** – Välj den typ av resultat som testet resulterar i.</span><span class="sxs-lookup"><span data-stu-id="67ac0-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="67ac0-134">För kvantitativa tester väljer du *Del* eller *Heltal*.</span><span class="sxs-lookup"><span data-stu-id="67ac0-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="67ac0-135">Välj *Alternativ* för kvalitativa tester.</span><span class="sxs-lookup"><span data-stu-id="67ac0-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="67ac0-136">**Testinstrument** – Välj ett [testinstrument](quality-test-instruments.md) som ska användas för testet.</span><span class="sxs-lookup"><span data-stu-id="67ac0-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="67ac0-137">**Enhet** – Om du har valt *Del* eller *Heltal* i fältet **Typ** (det vill säga, om testet är ett kvantitativt) väljer du den måttenhet som testresultaten för registreras i.</span><span class="sxs-lookup"><span data-stu-id="67ac0-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="67ac0-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="67ac0-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="67ac0-139">När du har sparat ett test kan du inte längre redigera fältet **Typ** i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="67ac0-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="67ac0-140">Om du måste ändra den typ av testresultat som ska registreras för ett test väljer du **Ändra kvalitetstesttyp** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="67ac0-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="67ac0-141">I dialogrutan **Ändra kvalitetstesttyp** anger du dältet **Ny typ** till önskad typ och väljer sedan **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="67ac0-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67ac0-142">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="67ac0-142">Additional resources</span></span>

- [<span data-ttu-id="67ac0-143">Testinstrument för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="67ac0-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="67ac0-144">Testgrupper för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="67ac0-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="67ac0-145">Testvariabler för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="67ac0-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="67ac0-146">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="67ac0-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
