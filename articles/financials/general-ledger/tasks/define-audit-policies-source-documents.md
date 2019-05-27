---
title: Definiera granskningspolicyer för källdokument
description: I den här proceduren visar vi hur du ställer in och kör granskningsprincipregler.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a82c3e8e8787beb309b75b73cda36f4ca8031d6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558893"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="13692-103">Definiera granskningspolicyer för källdokument</span><span class="sxs-lookup"><span data-stu-id="13692-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13692-104">I den här proceduren visar vi hur du ställer in och kör granskningsprincipregler.</span><span class="sxs-lookup"><span data-stu-id="13692-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="13692-105">I exemplet används utgiftsrapporter av typen hotellutgift.</span><span class="sxs-lookup"><span data-stu-id="13692-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="13692-106">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="13692-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="13692-107">Revisorrollen har rätt behörighet för att utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="13692-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="13692-108">Gå till Revision > Inställningar > Policyregeltyp.</span><span class="sxs-lookup"><span data-stu-id="13692-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="13692-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="13692-109">Click New.</span></span>
3. <span data-ttu-id="13692-110">I fältet Regelnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="13692-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="13692-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="13692-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="13692-112">I frågenamnfältet, välj raden Utgiftsrapport</span><span class="sxs-lookup"><span data-stu-id="13692-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="13692-113">Välj Sammansättning i frågetypsfältet</span><span class="sxs-lookup"><span data-stu-id="13692-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="13692-114">Välj Juridisk person i fältet Juridisk person</span><span class="sxs-lookup"><span data-stu-id="13692-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="13692-115">Välj Datum och tid för ändring i dokumentdatumreferensfältet</span><span class="sxs-lookup"><span data-stu-id="13692-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="13692-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="13692-116">Click Save.</span></span>
10. <span data-ttu-id="13692-117">Gå till revision workbench > Installation > Revision policy.</span><span class="sxs-lookup"><span data-stu-id="13692-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="13692-118">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="13692-118">Click New.</span></span>
12. <span data-ttu-id="13692-119">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="13692-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="13692-120">Expandera avsnittet Policyorganisationer.</span><span class="sxs-lookup"><span data-stu-id="13692-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="13692-121">Välj det ”Contoso Entertainment System USA" i trädet..</span><span class="sxs-lookup"><span data-stu-id="13692-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="13692-122">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-122">Click Add.</span></span>
16. <span data-ttu-id="13692-123">Välj ”Contoso Consulting USA" i trädet.</span><span class="sxs-lookup"><span data-stu-id="13692-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="13692-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-124">Click Add.</span></span>
18. <span data-ttu-id="13692-125">Välj ”Contoso Retail USA" i trädet.</span><span class="sxs-lookup"><span data-stu-id="13692-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="13692-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-126">Click Add.</span></span>
20. <span data-ttu-id="13692-127">Komprimera avsnittet Policyorganisationer.</span><span class="sxs-lookup"><span data-stu-id="13692-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="13692-128">Expandera avsnittet Policyregler.</span><span class="sxs-lookup"><span data-stu-id="13692-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="13692-129">I listan söker du efter och väljer den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="13692-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="13692-130">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="13692-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="13692-131">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="13692-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="13692-132">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="13692-132">Click Filter.</span></span>
26. <span data-ttu-id="13692-133">Markera raden för utgiftskategori i listan och ange Hotell</span><span class="sxs-lookup"><span data-stu-id="13692-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="13692-134">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="13692-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="13692-135">Klicka på fliken Sammansättning.</span><span class="sxs-lookup"><span data-stu-id="13692-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="13692-136">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-136">Click Add.</span></span>
30. <span data-ttu-id="13692-137">Välj ett fältvärde för transaktionsbelopp</span><span class="sxs-lookup"><span data-stu-id="13692-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="13692-138">Ange eller välj ett värde i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="13692-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="13692-139">Välj ”Summa” i fältet AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="13692-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="13692-140">Klicka på fliken Gruppera efter.</span><span class="sxs-lookup"><span data-stu-id="13692-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="13692-141">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-141">Click Add.</span></span>
35. <span data-ttu-id="13692-142">I listan väljer du ett värde av anställd </span><span class="sxs-lookup"><span data-stu-id="13692-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="13692-143">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-143">Click Add.</span></span>
37. <span data-ttu-id="13692-144">Välj ett värde för Utgiftskategori i listan</span><span class="sxs-lookup"><span data-stu-id="13692-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="13692-145">Ange eller välj ett värde i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="13692-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="13692-146">Klicka på fliken Har.</span><span class="sxs-lookup"><span data-stu-id="13692-146">Click the Having tab.</span></span>
40. <span data-ttu-id="13692-147">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="13692-147">Click Add.</span></span>
41. <span data-ttu-id="13692-148">Välj transaktionsbelopp</span><span class="sxs-lookup"><span data-stu-id="13692-148">Select Transaction amount</span></span>
42. <span data-ttu-id="13692-149">Ange eller välj ett värde i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="13692-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="13692-150">Välj ”Summa” i fältet AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="13692-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="13692-151">I fältet skriver du &quot;&gt;2000".</span><span class="sxs-lookup"><span data-stu-id="13692-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="13692-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="13692-152">Click OK.</span></span>
46. <span data-ttu-id="13692-153">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="13692-153">Click Test.</span></span>
47. <span data-ttu-id="13692-154">I fältet Startdatum för dokumenturval, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="13692-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="13692-155">I fältet Slutdatum för dokumenturval, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="13692-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="13692-156">Klicka på Kör test.</span><span class="sxs-lookup"><span data-stu-id="13692-156">Click Run test.</span></span>
50. <span data-ttu-id="13692-157">Klicka på Granskningspolicy i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="13692-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="13692-158">Klicka på ytterligare alternativ.</span><span class="sxs-lookup"><span data-stu-id="13692-158">Click Additional options.</span></span>
52. <span data-ttu-id="13692-159">Ange datum och tid i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="13692-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="13692-160">I fältet Slutdatum, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="13692-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="13692-161">Klicka på Batch.</span><span class="sxs-lookup"><span data-stu-id="13692-161">Click Batch.</span></span>
55. <span data-ttu-id="13692-162">Expandera avsnittet Kör i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="13692-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="13692-163">Välj Ja i fältet Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="13692-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="13692-164">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="13692-164">Click OK.</span></span>
58. <span data-ttu-id="13692-165">Gå till revision workbench > revision.</span><span class="sxs-lookup"><span data-stu-id="13692-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="13692-166">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="13692-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="13692-167">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="13692-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="13692-168">Expandera avsnittet Associationer.</span><span class="sxs-lookup"><span data-stu-id="13692-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="13692-169">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="13692-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="13692-170">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="13692-170">In the list, click the link in the selected row.</span></span>

