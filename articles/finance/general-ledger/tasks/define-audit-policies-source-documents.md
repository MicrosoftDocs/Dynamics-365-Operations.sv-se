---
title: Definiera granskningspolicyer för källdokument
description: I det här avsnittet visar vi hur du ställer in och kör granskningspolicyregler.
author: panolte
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e020a9e82ff18055e40e3e0ddc7bbed1068c886c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021439"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="d90c2-103">Definiera granskningspolicyer för källdokument</span><span class="sxs-lookup"><span data-stu-id="d90c2-103">Define audit policies for source documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d90c2-104">I det här avsnittet visar vi hur du ställer in och kör granskningspolicyregler.</span><span class="sxs-lookup"><span data-stu-id="d90c2-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="d90c2-105">I exemplet används utgiftsrapporter av typen hotellutgift.</span><span class="sxs-lookup"><span data-stu-id="d90c2-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="d90c2-106">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d90c2-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="d90c2-107">Revisorrollen har rätt behörighet för att utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="d90c2-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="d90c2-108">I navigeringsfönstret går du till **Moduler > Revision > Inställningar > Policyregeltyp**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="d90c2-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-109">Select **New**.</span></span>
3. <span data-ttu-id="d90c2-110">Skriv ett värde i fältet **Regelnamn**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="d90c2-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="d90c2-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="d90c2-112">I fältet **Frågenamn** väljer du **Utgiftsrapportrad**</span><span class="sxs-lookup"><span data-stu-id="d90c2-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="d90c2-113">I fältet **Frågetyp** väljer du **Sammansättning**</span><span class="sxs-lookup"><span data-stu-id="d90c2-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="d90c2-114">I fältet **Juridiskt person** väljer du **Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="d90c2-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="d90c2-115">I fältet **Dokumentdatumreferens** väljer du **Datum och tid för ändring**</span><span class="sxs-lookup"><span data-stu-id="d90c2-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="d90c2-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-116">Select **Save**.</span></span>
10. <span data-ttu-id="d90c2-117">I navigeringsfönstret går du till **Moduler > Revision > Inställningar > Granskningspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="d90c2-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-118">Select **New**.</span></span>
12. <span data-ttu-id="d90c2-119">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="d90c2-120">Expandera avsnittet **Policyorganisationer**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="d90c2-121">Välj **Contoso Entertainment System USA** i trädet och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="d90c2-122">Välj **Contoso Consulting USA** i trädet och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="d90c2-123">Välj **Contoso Retail USA** i trädet och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="d90c2-124">Komprimera avsnittet **Policyorganisationer**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="d90c2-125">Expandera avsnittet **Policyregler**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="d90c2-126">I listan söker du efter och väljer den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="d90c2-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="d90c2-127">Välj **Skapa policyregel**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="d90c2-128">I fältet **Gäller från** anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="d90c2-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="d90c2-129">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-129">Select **Filter**.</span></span>
23. <span data-ttu-id="d90c2-130">Välj raden för **Utgiftskategori** i listan och ställ in detaljerna till **Hotell**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="d90c2-131">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="d90c2-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="d90c2-132">Välj fliken **Sammansättning**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="d90c2-133">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-133">Select **Add**.</span></span>
27. <span data-ttu-id="d90c2-134">Välj fältvärdet **Transaktionsbelopp** i listan.</span><span class="sxs-lookup"><span data-stu-id="d90c2-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="d90c2-135">Ange eller välj ett värde i fältet **Fält**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="d90c2-136">I fältet **AggregateFunction** väljer du **Sum**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="d90c2-137">Välj fliken **Gruppera efter**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="d90c2-138">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-138">Select **Add**.</span></span>
32. <span data-ttu-id="d90c2-139">Välj värdet **Medarbetare** i listan.</span><span class="sxs-lookup"><span data-stu-id="d90c2-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="d90c2-140">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-140">Select **Add**.</span></span>
34. <span data-ttu-id="d90c2-141">Välj värdet **Utgiftskategori** i listan.</span><span class="sxs-lookup"><span data-stu-id="d90c2-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="d90c2-142">Ange eller välj ett värde i fältet **Fält**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="d90c2-143">Välj fliken **Har**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="d90c2-144">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-144">Select **Add**.</span></span>
38. <span data-ttu-id="d90c2-145">Välj **Transaktionsbelopp**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="d90c2-146">Ange eller välj ett värde i fältet **Fält**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="d90c2-147">I fältet **AggregateFunction** väljer du **Sum**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="d90c2-148">I fältet **Kriterier** skriver du `>2000`.</span><span class="sxs-lookup"><span data-stu-id="d90c2-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="d90c2-149">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-149">Select **OK**.</span></span>
43. <span data-ttu-id="d90c2-150">Välj **Test**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-150">Select **Test**.</span></span>
44. <span data-ttu-id="d90c2-151">I fältet **Startdatum för dokumenturval**, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="d90c2-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="d90c2-152">I fältet **Slutdatum för dokumenturval**, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="d90c2-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="d90c2-153">Välj **Kör test**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-153">Select **Run test**.</span></span>
47. <span data-ttu-id="d90c2-154">I åtgärdsfönstret, välj **Granskningspolicy**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="d90c2-155">Välj **Ytterligare alternativ**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="d90c2-156">I fältet **Startdatum**, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="d90c2-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="d90c2-157">I fältet **Slutdatum**, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="d90c2-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="d90c2-158">Välj **Batch**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-158">Select **Batch**.</span></span>
52. <span data-ttu-id="d90c2-159">Expandera avsnittet **Kör i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="d90c2-160">Välj **Ja** i fältet **Batchbearbetning**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="d90c2-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-161">Select **OK**.</span></span>
55. <span data-ttu-id="d90c2-162">I navigeringsfönstret går du till **Moduler > Revision > Granskningsärenden**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="d90c2-163">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d90c2-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="d90c2-164">Expandera avsnittet **Associationer**.</span><span class="sxs-lookup"><span data-stu-id="d90c2-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="d90c2-165">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d90c2-165">In the list, find and select the desired record.</span></span>

