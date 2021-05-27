---
title: Testvariabler för kvalitetshantering
description: I detta ämne beskrivs hur du skapar testvariabler som kan användas för kvalitativa tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b5102d09f5762a390d6fd3aadafcb2ed23820982
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021718"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="28e13-103">Testvariabler för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="28e13-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28e13-104">I detta ämne beskrivs hur du skapar testvariabler som kan användas för kvalitativa tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28e13-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="28e13-105">Du måste definiera en testvariabel och dess möjliga resultat för varje kvalitativt test som definieras på sidan **Tester**.</span><span class="sxs-lookup"><span data-stu-id="28e13-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="28e13-106">(För kvalitativa tester är fältet **Typ** på sidan **Tester** inställt på *Alternativ*.)</span><span class="sxs-lookup"><span data-stu-id="28e13-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="28e13-107">Du använder sidan **Testvariabler** för att skapa, redigera och visa möjliga resultat för en testvariabel som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="28e13-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="28e13-108">För varje resultat tilldelar du ett statusvärde som är antingen *Godkänd* eller *Misslyckades* för att ange huruvida testet har godkänts eller misslyckats när det resultatet har valts som ett testresultat.</span><span class="sxs-lookup"><span data-stu-id="28e13-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="28e13-109">Du använder sidan **Testgrupper** om du vill tilldela en testvariabel och ett standardresultat för den till ett enskilt kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="28e13-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="28e13-110">För varje testvariabel rekommenderar vi att du definierar minst två resultat: ett som har statusvärdet *Godkänt* och ett som har resultatstatusen *Misslyckades*.</span><span class="sxs-lookup"><span data-stu-id="28e13-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="28e13-111">Det finns ingen gräns för det totala antalet variabler eller resultat som kan definieras.</span><span class="sxs-lookup"><span data-stu-id="28e13-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="28e13-112">Flera tester kan dessutom använda samma testvariabler för att registrera resultat.</span><span class="sxs-lookup"><span data-stu-id="28e13-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="28e13-113">Exempel på testvariabler</span><span class="sxs-lookup"><span data-stu-id="28e13-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="28e13-114">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="28e13-114">Example 1</span></span>

<span data-ttu-id="28e13-115">Ett tillverkningsföretag utför två tester av tillverkade material.</span><span class="sxs-lookup"><span data-stu-id="28e13-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="28e13-116">I ett test associeras pH-nivån med en färgremsa.</span><span class="sxs-lookup"><span data-stu-id="28e13-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="28e13-117">Acceptabla pH-nivåer uppträder i ljusare färger, och oacceptabla pH-nivåer i mörkare färger.</span><span class="sxs-lookup"><span data-stu-id="28e13-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="28e13-118">I ett annat test utförs flera visuella granskningar, och kvalitetsmedarbetare använder sitt omdöme för att fastställa huruvida artikeln klarar den visuella inspektionen eller inte.</span><span class="sxs-lookup"><span data-stu-id="28e13-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="28e13-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="28e13-119">Example 2</span></span>

<span data-ttu-id="28e13-120">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="28e13-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="28e13-121">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="28e13-121">This inspection test has several variables.</span></span> <span data-ttu-id="28e13-122">En variabel är smak, och de möjliga resultaten för denna är "god" eller "dålig".</span><span class="sxs-lookup"><span data-stu-id="28e13-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="28e13-123">En andra variabel är färg, och de möjliga resultaten för denna är "alltför mörk", "alltför ljus" och "korrekt".</span><span class="sxs-lookup"><span data-stu-id="28e13-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="28e13-124">Skapa en testvariabel</span><span class="sxs-lookup"><span data-stu-id="28e13-124">Create a test variable</span></span>

<span data-ttu-id="28e13-125">Gör så här om du vill skapa en testvariabel.</span><span class="sxs-lookup"><span data-stu-id="28e13-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="28e13-126">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testvariabler**.</span><span class="sxs-lookup"><span data-stu-id="28e13-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="28e13-127">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="28e13-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="28e13-128">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="28e13-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="28e13-129">**Variabel** – Ange ett unikt ID eller namn för variabeln.</span><span class="sxs-lookup"><span data-stu-id="28e13-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="28e13-130">**Beskrivning** – Ange en detaljerad beskrivning av variabeln.</span><span class="sxs-lookup"><span data-stu-id="28e13-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="28e13-131">Med den nya raden fortsatt vald väljer du **Resultat** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="28e13-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="28e13-132">På sidan **Testvariabelresultat** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="28e13-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="28e13-133">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="28e13-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="28e13-134">**Resultat** – Ange ett unikt ID eller namn för resultatet.</span><span class="sxs-lookup"><span data-stu-id="28e13-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="28e13-135">**Beskrivning** – Ange en detaljerad beskrivning av resultatet.</span><span class="sxs-lookup"><span data-stu-id="28e13-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="28e13-136">**Resultatstatus** – Välj antingen *Godkänn* eller *Misslyckades* för att ange huruvida testet godkänts eller misslyckats när resultatet valts som testresultat.</span><span class="sxs-lookup"><span data-stu-id="28e13-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="28e13-137">Upprepa föregående steg för varje ytterligare resultat.</span><span class="sxs-lookup"><span data-stu-id="28e13-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="28e13-138">Kontrollera att minst ett resultat har statusvärdet *Godkänt* och att minst ett har statusvärdet *Misslyckades*.</span><span class="sxs-lookup"><span data-stu-id="28e13-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="28e13-139">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="28e13-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28e13-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="28e13-140">Additional resources</span></span>

- [<span data-ttu-id="28e13-141">Testinstrument för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="28e13-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="28e13-142">Kvalitetshanteringstester</span><span class="sxs-lookup"><span data-stu-id="28e13-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="28e13-143">Testgrupper för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="28e13-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
