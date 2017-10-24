---
title: "Installera komponenter för ett jobb"
description: "Det här avsnittet beskriver begreppsmässiga element som ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt inom din organisation."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: rschloma
ms.reviewer: rschloma
ms.search.scope: Core, Operations, UnifiedOperations, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c616637922e617661482875d78531ea79fda4407
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="setting-up-the-components-of-a-job"></a><span data-ttu-id="b9733-103">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="b9733-103">Setting up the components of a job</span></span>

[!include[banner](includes/banner.md)]

[!include[retail name](includes/retail-name.md)]


<span data-ttu-id="b9733-104">Det här avsnittet beskriver begreppsmässiga element som ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="b9733-104">This topic describes the conceptual elements that a job can include and provides examples of how you can use those elements in your organization.</span></span> 

<span data-ttu-id="b9733-105">Innan du kan skapa nya jobb måste du skapa viss referensinformation.</span><span class="sxs-lookup"><span data-stu-id="b9733-105">Before you can create jobs, you must set up some reference information.</span></span> <span data-ttu-id="b9733-106">Du kan skapa ett jobb som har bara ett namn.</span><span class="sxs-lookup"><span data-stu-id="b9733-106">You can create a job that has only a name.</span></span> <span data-ttu-id="b9733-107">Genom att lägga till ytterligare information, till exempel titel, anger du emellertid standardvärden för de befattningar som tilldelats till jobbet.</span><span class="sxs-lookup"><span data-stu-id="b9733-107">However, by including additional information, such as a job title, you provide default values for the positions that are assigned to the job.</span></span> <span data-ttu-id="b9733-108">Dessutom kan en del av informationen som du anger användas för att filtrera kompensationsplaner på specifika jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-108">Additionally, some of the information that you enter can be used to filter compensation plans to specific jobs.</span></span> <span data-ttu-id="b9733-109">Om du vill konfigurera berättiganden som du kan använda för att filtrera kompensationsplaner på ett specifikt jobb, bör du ställa in jobbfunktioner och jobbtyper innan du registrerar jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-109">If you want to set up eligibility that you can use to filter compensation plans to a specific job, you should set up job functions and job types before you set up jobs.</span></span> <span data-ttu-id="b9733-110">Genom att ha dessa standardvärden tillgängliga sparar du tid när du lägger till befattningar för jobbet.</span><span class="sxs-lookup"><span data-stu-id="b9733-110">By having these default values available, you will save time when you add positions to the job.</span></span> 

<span data-ttu-id="b9733-111">Viss jobbinformation, exempelvis befattning, typ och funktion, har giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="b9733-111">Some job details, such as the job title, type, and function, are date-effective.</span></span> <span data-ttu-id="b9733-112">Om du skapar ett jobb redan idag men inte lägger till denna information förrän senare och sedan tittar på jobbet från och med skapandedatum, så visas inte denna information.</span><span class="sxs-lookup"><span data-stu-id="b9733-112">If you create a job today but don't add these details until later, and you then look at the job as of the creation date, these details won't appear.</span></span> <span data-ttu-id="b9733-113">Därför bör du skapa en del av denna referensinformation innan du behöver den.</span><span class="sxs-lookup"><span data-stu-id="b9733-113">Therefore, you should create some of this reference information before you require it.</span></span> <span data-ttu-id="b9733-114">På så sätt kan du lägga till informationen till nya jobb när dessa skapas.</span><span class="sxs-lookup"><span data-stu-id="b9733-114">That way, you can add the information to new jobs when you create them.</span></span>

## <a name="job-titles"></a><span data-ttu-id="b9733-115">jobbtitlar</span><span class="sxs-lookup"><span data-stu-id="b9733-115">Job titles</span></span>
<span data-ttu-id="b9733-116">Innan du skapar jobb måste du ställa in titlar för jobben.</span><span class="sxs-lookup"><span data-stu-id="b9733-116">Before you create jobs, you must set up titles for those jobs.</span></span> <span data-ttu-id="b9733-117">Befattningar ärver jobbtitlar från jobben som befattningarna är kopplade till.</span><span class="sxs-lookup"><span data-stu-id="b9733-117">Positions inherit job titles from the jobs that the positions are associated with.</span></span> 

<span data-ttu-id="b9733-118">Underhåll jobbtitlar med hjälp av sidan **Titlar**, som du kan öppna genom att använda sökfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b9733-118">Maintain job titles using the **Titles** page, which you can open by using the Search function.</span></span> <span data-ttu-id="b9733-119">På sidan **Titlar ** anger du de rubriker som du vill använda för dina jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-119">On the **Titles **page, enter the titles that you plan to use for your jobs.</span></span>

## <a name="job-types"></a><span data-ttu-id="b9733-120">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="b9733-120">Job types</span></span>
<span data-ttu-id="b9733-121">Du använder jobbtyper för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="b9733-121">You use job types to group similar jobs into categories.</span></span> <span data-ttu-id="b9733-122">Jobbtyper krävs inte.</span><span class="sxs-lookup"><span data-stu-id="b9733-122">Job types aren't required.</span></span> <span data-ttu-id="b9733-123">Om du tänker använda jobbtyper när du ställer in berättiganderegler för kompensationshantering bör du ställa in jobbtyper innan du ställer in jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-123">However, if you plan to use job types when you set up eligibility rules for compensation management, you should set up job types before you set up jobs.</span></span> <span data-ttu-id="b9733-124">Några exempel på jobbtyper är heltid och deltid, eller lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="b9733-124">Some examples of job types are full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b9733-125">Du kan underhålla jobbtyper med hjälp av sidan **Jobbtyper**.</span><span class="sxs-lookup"><span data-stu-id="b9733-125">You maintain job types by using the **Job types** page.</span></span> <span data-ttu-id="b9733-126">På sidan **Jobbtyper** anger du ett namn och en kort beskrivning för jobbtypen.</span><span class="sxs-lookup"><span data-stu-id="b9733-126">On the **Job types** page, enter a name and a brief description for the job type.</span></span> <span data-ttu-id="b9733-127">I fältet **Befrielsestatus** väljer du ett av följande alternativ för att ange befrielsestatusen Fair Labor Standards Act (FLSA) befrielsestatus för jobb som har den här jobbtypen:</span><span class="sxs-lookup"><span data-stu-id="b9733-127">In the **Exempt status** field, select one of the following options to indicate the Fair Labor Standards Act (FLSA) exempt status of jobs that have this job type:</span></span>

-   <span data-ttu-id="b9733-128">**Undantag** – Jobb är befriade från övertid under FLSA.</span><span class="sxs-lookup"><span data-stu-id="b9733-128">**Exempt** – Jobs are exempt from overtime under the FLSA.</span></span>
-   <span data-ttu-id="b9733-129">**Icke-undantag** – Jobb är inte befriade från övertid under FLSA.</span><span class="sxs-lookup"><span data-stu-id="b9733-129">**Non-exempt** – Jobs aren't exempt from overtime under the FLSA.</span></span>
-   <span data-ttu-id="b9733-130">**Gäller inte** – FLSA-täckning gäller inte.</span><span class="sxs-lookup"><span data-stu-id="b9733-130">**Does not apply** – FLSA coverage isn't applicable.</span></span>

## <a name="job-functions"></a><span data-ttu-id="b9733-131">Jobbfunktioner</span><span class="sxs-lookup"><span data-stu-id="b9733-131">Job functions</span></span>
<span data-ttu-id="b9733-132">Jobbkopplingar beskriver funktionella kategorier på hög nivå och relaterar uppgifter på hög nivå.</span><span class="sxs-lookup"><span data-stu-id="b9733-132">Job junctions describe high-level functional categories and relate high-level duties.</span></span> <span data-ttu-id="b9733-133">Jobbfunktioner krävs inte.</span><span class="sxs-lookup"><span data-stu-id="b9733-133">Job functions aren't required.</span></span> <span data-ttu-id="b9733-134">Du kan använda jobbfunktioner tillsammans med jobbtyper för att filtrera kompensationsplaner till specifika jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-134">You can use job functions, together with job types, to filter compensation plans to specific jobs.</span></span> <span data-ttu-id="b9733-135">Du kopplar jobbfunktioner och jobbtyper till kompensationsplaner genom att ställa in berättiganderegler på sidan **Berättiganderegler**.</span><span class="sxs-lookup"><span data-stu-id="b9733-135">You associate job functions and job types with compensation plans by setting up eligibility rules on the **Eligibility rules** page.</span></span> <span data-ttu-id="b9733-136">Du kan sedan lägga till en nivåserie till en kompensationsplan som gäller den specifika kombinationen av en jobbtyp och en jobbfunktion som du har definierat med en berättiganderegel.</span><span class="sxs-lookup"><span data-stu-id="b9733-136">You can then attach a set of levels to a compensation plan that apply to the specific combination of a job type and job function that you've defined through an eligibility rule.</span></span> <span data-ttu-id="b9733-137">(Dessa funktioner gäller både planer för fast kompensation och planer för variabel kompensation.) Om du emellertid tänker använda jobbfunktioner när du skapar berättiganderegler för kompensationshantering, bör du skapa jobbfunktioner innan du skapar jobb.</span><span class="sxs-lookup"><span data-stu-id="b9733-137">(These features apply to both fixed compensation plans and variable compensation plans.) However, if you plan to use job functions when you set up eligibility rules for compensation management, you should set up job functions before you set up jobs.</span></span> <span data-ttu-id="b9733-138">Följande tabell anger några exempel på jobbfunktioner.</span><span class="sxs-lookup"><span data-stu-id="b9733-138">The following table shows some examples of job functions.</span></span>

| <span data-ttu-id="b9733-139">Jobb</span><span class="sxs-lookup"><span data-stu-id="b9733-139">Job</span></span>           | <span data-ttu-id="b9733-140">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="b9733-140">Job function</span></span>         |
|---------------|----------------------|
| <span data-ttu-id="b9733-141">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="b9733-141">Sales manager</span></span> | <span data-ttu-id="b9733-142">Chef på mellannivå</span><span class="sxs-lookup"><span data-stu-id="b9733-142">Mid-level Manager</span></span>    |
| <span data-ttu-id="b9733-143">Redovisare</span><span class="sxs-lookup"><span data-stu-id="b9733-143">Accountant</span></span>    | <span data-ttu-id="b9733-144">Yrkespersoner</span><span class="sxs-lookup"><span data-stu-id="b9733-144">Professionals</span></span>        |

<span data-ttu-id="b9733-145">Du underhåller jobbtyper med hjälp av sidan **Jobbfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="b9733-145">You maintain job functions by using the **Job functions** page.</span></span> <span data-ttu-id="b9733-146">På sidan **Jobbfunktioner** anger du en identifieringskod och en kort beskrivning för jobbfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b9733-146">On the **Job functions** page, enter an identification code and a brief description for the job function.</span></span>

## <a name="job-tasks"></a><span data-ttu-id="b9733-147">Jobbuppgifter</span><span class="sxs-lookup"><span data-stu-id="b9733-147">Job tasks</span></span>
<span data-ttu-id="b9733-148">Jobbuppgifter beskriver de grundläggande uppgifter som en anställd i en befattning måste utföra.</span><span class="sxs-lookup"><span data-stu-id="b9733-148">Job tasks describe the basic tasks that a worker who is in a position for a job must complete.</span></span> <span data-ttu-id="b9733-149">Samma jobbuppgift kan läggas till i flera jobb och i befattningar för de jobb som använder dessa jobbuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b9733-149">The same job task can be added to multiple jobs, and to positions for the jobs that use those job tasks.</span></span> <span data-ttu-id="b9733-150">Följande tabell anger några exempel på jobbuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b9733-150">The following table shows some examples of job tasks.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b9733-151">Jobb</span><span class="sxs-lookup"><span data-stu-id="b9733-151">Job</span></span></th>
<th><span data-ttu-id="b9733-152">Jobbuppgift</span><span class="sxs-lookup"><span data-stu-id="b9733-152">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b9733-153">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="b9733-153">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="b9733-154"><strong>Resultatgranskning</strong> – Granska varje säljares jobbprestation.</span><span class="sxs-lookup"><span data-stu-id="b9733-154"><strong>Perf-review</strong> – Review each salesperson's job performance.</span></span></li>
<li><span data-ttu-id="b9733-155"><strong>Frånvarogranskning</strong> – Godkänn eller avvisa varje säljares frånvaroförfrågningar eller -registreringar.</span><span class="sxs-lookup"><span data-stu-id="b9733-155"><strong>Abs-review</strong> – Approve or reject each salesperson's absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9733-156">Redovisare</span><span class="sxs-lookup"><span data-stu-id="b9733-156">Accountant</span></span></td>
<td><span data-ttu-id="b9733-157"><strong>FIN-rapport</strong> – Visa aktuella veckovisa ekonomiska rapporter för ekonomichefen.</span><span class="sxs-lookup"><span data-stu-id="b9733-157"><strong>FIN-Report</strong> – Present weekly financial reports to the chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b9733-158">Du kan underhålla jobbuppgifter med hjälp av sidan **Jobbuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="b9733-158">You maintain job tasks by using the **Job tasks** page.</span></span> <span data-ttu-id="b9733-159">På sidan **Jobbtyper** anger du ett namn och en kort beskrivning för jobbuppgiften.</span><span class="sxs-lookup"><span data-stu-id="b9733-159">On the **Job tasks** page, enter a name and description for the job task.</span></span> <span data-ttu-id="b9733-160">Om du vill kan du ange ytterligare information i fältet **Anteckningar**.</span><span class="sxs-lookup"><span data-stu-id="b9733-160">In the **Note** field, you can optionally enter additional information.</span></span> <span data-ttu-id="b9733-161">Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.</span><span class="sxs-lookup"><span data-stu-id="b9733-161">The notes can be updated for a specific job without changing the notes that you entered here.</span></span>

## <a name="areas-of-responsibility"></a><span data-ttu-id="b9733-162">Ansvarsområden</span><span class="sxs-lookup"><span data-stu-id="b9733-162">Areas of responsibility</span></span>
<span data-ttu-id="b9733-163">Använd ansvarsområden för att indikera arbetsroller, processer och produkter som en arbetare i en befattning bär ansvar för.</span><span class="sxs-lookup"><span data-stu-id="b9733-163">You use areas of responsibility to indicate the work roles, processes, and products that a worker who is in a position for a job is responsible for.</span></span> <span data-ttu-id="b9733-164">Till exempel: För ett jobb vid namn "Revisor" kan ett ansvarsområde vara "Ekonomisk rapporteringen för produkt A”.</span><span class="sxs-lookup"><span data-stu-id="b9733-164">For example, for a job that is named "Accountant," one area of responsibility might be "Financial reporting for product A."</span></span> <span data-ttu-id="b9733-165">Du underhåller ansvarsområden med hjälp av sidan **Ansvarsområden**, som du hittar genom att använda sökfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b9733-165">You maintain areas of responsibility by using the **Areas of responsibility** page, which you can find by using the Search function.</span></span> <span data-ttu-id="b9733-166">På sidan **Ansvarsområden** anger du ett namn och en beskrivning för ansvarsområdet.</span><span class="sxs-lookup"><span data-stu-id="b9733-166">On the **Areas of responsibility** page, enter a name and description for the responsibility.</span></span> <span data-ttu-id="b9733-167">Om du vill kan du ange ytterligare information i fältet **Anteckningar**.</span><span class="sxs-lookup"><span data-stu-id="b9733-167">In the **Note** field, you can optionally enter additional information.</span></span> <span data-ttu-id="b9733-168">Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.</span><span class="sxs-lookup"><span data-stu-id="b9733-168">The notes can be updated for a specific job without changing the notes that you entered here.</span></span>




