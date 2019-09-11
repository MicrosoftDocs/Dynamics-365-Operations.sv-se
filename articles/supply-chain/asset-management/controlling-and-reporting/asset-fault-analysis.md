---
title: Felanalys för tillgång
description: I det här avsnittet beskrivs felanalys för tillgång i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918451"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="f04b7-103">Felanalys för tillgång</span><span class="sxs-lookup"><span data-stu-id="f04b7-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="f04b7-104">I Tillgångshantering kan du analysera tillgångsfelregistrerings för att få en översikt över det totala antalet fel som registrerats under en viss period.</span><span class="sxs-lookup"><span data-stu-id="f04b7-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="f04b7-105">Felregistreringar kan analyseras från olika perspektiv, till exempel med fokus på tillgångar, tillgångstyper, funktionsplatser, felsymptom eller feltyper.</span><span class="sxs-lookup"><span data-stu-id="f04b7-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="f04b7-106">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Felanalys för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="f04b7-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="f04b7-107">I dialogrutan **Beräkning av tillgångsfelanalys** kan du använda fältet **Nivå** för att indikera hur detaljerad du vill att tillgångsfelraderna ska vara avseende funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="f04b7-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> <span data-ttu-id="f04b7-108">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångsfelrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="f04b7-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="f04b7-109">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla tillgångsfelrader på alla den funktionsplatsnivå som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="f04b7-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="f04b7-110">Om du vill begränsa sökningen kan du välja specifika tillgångar, feldatum, felorsaker och felåtgärder på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="f04b7-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="f04b7-111">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="f04b7-112">På fliken **Tillgångsfelanalys**, klicka på en eller flera knappar på åtgärdsfönstergrupperna **Gruppera efter...** för att visa detaljnivån som du vill se.</span><span class="sxs-lookup"><span data-stu-id="f04b7-112">On the **Asset fault analysis** tab, click one or more buttons in the **Group by...** action pane groups to display the detail level you want to see.</span></span> <span data-ttu-id="f04b7-113">Aktiverade knappar är markerade.</span><span class="sxs-lookup"><span data-stu-id="f04b7-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="f04b7-114">Aktivera eller inaktivera knappar genom att klicka på dem.</span><span class="sxs-lookup"><span data-stu-id="f04b7-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="f04b7-115">Klicka på **Uppdatera beräkningar** om du vill visa dina val på skärmen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="f04b7-116">Varje gång du aktiverar eller inaktiverar knappar i åtgärdsfönstergrupperna **Gruppera efter...**, kom ihåg att klicka på knappen **Uppdatera beräkningar** när du har ändrat valen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-116">Every time you activate or deactivate buttons in the **Group by...** action pane groups, remember to click the **Update calculations** button after you changed the selections.</span></span> <span data-ttu-id="f04b7-117">Detta är nödvändigt eftersom en stor mängd data bearbetas när du räknar om en felsannolikhet.</span><span class="sxs-lookup"><span data-stu-id="f04b7-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

<span data-ttu-id="f04b7-118">Det finns många sätt att analysera felregistreringar.</span><span class="sxs-lookup"><span data-stu-id="f04b7-118">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="f04b7-119">Nedan visas exempel på fem skärmbilder av hur olika dataval ger olika typer av information.</span><span class="sxs-lookup"><span data-stu-id="f04b7-119">Below you see examples in five screenshots of how different data selections provide different pieces of information.</span></span> <span data-ttu-id="f04b7-120">Du kommer att se hur olika val ger bättre insikt och detaljrikedom när du analyserar felregistreringar på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="f04b7-120">You will see how different selections provide more insight and detail when analyzing asset fault registrations.</span></span>

<span data-ttu-id="f04b7-121">I skärmbilden nedan är bara knappen **Symptom** markerad.</span><span class="sxs-lookup"><span data-stu-id="f04b7-121">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="f04b7-122">Felregistreringar har utförts på tre felsymtom: "luftläcka", "utlöst säkring" och "utrustning har fastnat".</span><span class="sxs-lookup"><span data-stu-id="f04b7-122">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="f04b7-123">I kolumnen **Sannolikhet %** blir procentsatserna totalt 100 %.</span><span class="sxs-lookup"><span data-stu-id="f04b7-123">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="f04b7-124">Sannolikheten baseras på alla **symptom**registreringar i den här felanalysen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-124">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figur 1](media/06-controlling-and-reporting.png)


<span data-ttu-id="f04b7-126">I bilden nedan läggs **år** och **månad** till för att visa hur du kan visa felregistreringar under en vald period.</span><span class="sxs-lookup"><span data-stu-id="f04b7-126">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="f04b7-127">Felsymptomen visas nu som registreringar per år/månad.</span><span class="sxs-lookup"><span data-stu-id="f04b7-127">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="f04b7-128">Om du lägger till alla procentsatser för varje månad i kolumnen **Sannolikhet %** blir procentsatserna totalt 100 %.</span><span class="sxs-lookup"><span data-stu-id="f04b7-128">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="f04b7-129">Sannolikheten baseras på **symptom**registreringarna i den här felanalysen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-129">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="f04b7-130">Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felsymptom som du ska undersöka närmare för att begränsa antalet registreringar för det felsymptomet.</span><span class="sxs-lookup"><span data-stu-id="f04b7-130">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figur 2](media/07-controlling-and-reporting.png)


- <span data-ttu-id="f04b7-132">Kombinationen av till gångar och en tillgångstyp används som grund för beräkningarna som visas i på de tre bilderna nedan, vilket ökar detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="f04b7-132">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  
- <span data-ttu-id="f04b7-133">I allmänhet innehåller knapparna i grupperna **Gruppera efter datum**, **Gruppera efter tillgång**, **Gruppera efter funktionsplats** samt knappen **Fel** (fel-ID) perioder eller tillgångsrelationer.</span><span class="sxs-lookup"><span data-stu-id="f04b7-133">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** action pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="f04b7-134">Knapparna **Symptom**, **Område**, **Typ**, **Orsak** och **Åtgärd** är kategoriseringar som används vid felhantering för att analysera registreringar av tillgångsfel och hitta problemområden.</span><span class="sxs-lookup"><span data-stu-id="f04b7-134">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="f04b7-135">På skärmbilden nedan har **Tillgång** och **Tillgångstyp** lagts till för att ge mer detaljerad information om felregistreringar.</span><span class="sxs-lookup"><span data-stu-id="f04b7-135">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="f04b7-136">Felsymptomen delas nu upp i kombinationer av **Tillgång** / **Tillgångstyp** / **Symptom**.</span><span class="sxs-lookup"><span data-stu-id="f04b7-136">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="f04b7-137">I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** uppgår var och en till 100 %.</span><span class="sxs-lookup"><span data-stu-id="f04b7-137">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="f04b7-138">Sannolikheten baseras på **symptom**registreringarna i den här felanalysen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-138">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="f04b7-139">Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felsymptom som du ska undersöka närmare för att begränsa antalet registreringar för det felsymptomet.</span><span class="sxs-lookup"><span data-stu-id="f04b7-139">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figur 3](media/08-controlling-and-reporting.png)


<span data-ttu-id="f04b7-141">På skärmbilden nedan har **Område** lagts till i **Symptom**, **Tillgång** och **Tillgångstyp** för att ge fler detaljer om felregistreringar.</span><span class="sxs-lookup"><span data-stu-id="f04b7-141">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="f04b7-142">I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** på en tillgång uppgår var och en till 100 %.</span><span class="sxs-lookup"><span data-stu-id="f04b7-142">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="f04b7-143">Sannolikheten baseras på kombinationen av **Symptom** och **Område** i den här felanalysen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-143">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="f04b7-144">Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felområde som du ska undersöka närmare för att begränsa antalet registreringar för det felområdet.</span><span class="sxs-lookup"><span data-stu-id="f04b7-144">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figur 4](media/09-controlling-and-reporting.png)


<span data-ttu-id="f04b7-146">I skärmbilden nedan läggs **Typ** till, och den mest detaljerade beräkningen i det här exemplet visas.</span><span class="sxs-lookup"><span data-stu-id="f04b7-146">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="f04b7-147">I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** på en tillgång uppgår var och en till 100 %.</span><span class="sxs-lookup"><span data-stu-id="f04b7-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="f04b7-148">Sannolikheten baseras på kombinationen av **Symptom**, **Område** och **Typ** i den här felanalysen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-148">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="f04b7-149">Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på en feltyp som du ska undersöka närmare för att begränsa antalet registreringar för den feltypen.</span><span class="sxs-lookup"><span data-stu-id="f04b7-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figur 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="f04b7-151">Om du vill ha en översikt över alla felregistreringar som har skapats på arbetsorder och underhållsbegäranden, klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="f04b7-151">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="f04b7-152">På sidan **Tillgångsfel** väljer du en tillgångsfelregistrering och expanderar fönstret **Relaterad information** för att visa information om den relaterade arbetsordern eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="f04b7-152">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

