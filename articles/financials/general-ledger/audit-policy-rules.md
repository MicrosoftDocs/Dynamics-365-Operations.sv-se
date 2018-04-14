---
title: "Regler för granskningspolicy"
description: "Du kan använda granskningsprinciper för att utvärdera utgiftsrapporter, leverantörsfakturor och inköpsorder för att säkerställa att de överensstämmer med policyregler som du skapar. Alla regler som är associerade med en granskningspolicy körs i batchläge enligt en tidsplan som du anger.  Varje policyregel är en instans av en policyregeltyp. Endast en policyregel i taget kan gälla för en policyregeltyp."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 273beb0acef51059b40f9842062ed4dbba770160
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="audit-policy-rules"></a><span data-ttu-id="31588-106">Regler för granskningspolicy</span><span class="sxs-lookup"><span data-stu-id="31588-106">Audit policy rules</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="31588-107">Du kan använda granskningsprinciper för att utvärdera utgiftsrapporter, leverantörsfakturor och inköpsorder för att säkerställa att de överensstämmer med policyregler som du skapar.</span><span class="sxs-lookup"><span data-stu-id="31588-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="31588-108">Alla regler som är associerade med en granskningspolicy körs i batchläge enligt en tidsplan som du anger.</span><span class="sxs-lookup"><span data-stu-id="31588-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="31588-109">Varje policyregel är en instans av en policyregeltyp.</span><span class="sxs-lookup"><span data-stu-id="31588-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="31588-110">Endast en policyregel i taget kan gälla för en policyregeltyp.</span><span class="sxs-lookup"><span data-stu-id="31588-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="31588-111">Frågor och frågetyper</span><span class="sxs-lookup"><span data-stu-id="31588-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="31588-112">När du skapar en granskningspolicyregel, väljer du först en policyregeltyp.</span><span class="sxs-lookup"><span data-stu-id="31588-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="31588-113">Policyregeltypen anger vilken programobjektträdfråga som ska användas som utgångspunkt för att skapa policyregeln.</span><span class="sxs-lookup"><span data-stu-id="31588-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="31588-114">Den kan också ange den frågetyp som ska användas för policyregeln.</span><span class="sxs-lookup"><span data-stu-id="31588-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="31588-115">Frågan bestämmer vilket källdokument som policyregeln utvärderar.</span><span class="sxs-lookup"><span data-stu-id="31588-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="31588-116">Den visar även fälten i källdokumentet som identifierar både den juridiska personen och det datum som ska användas när dokument har valts för granskning.</span><span class="sxs-lookup"><span data-stu-id="31588-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="31588-117">Frågetypen styr standardfälten på frågesidan och sidan för granskningspolicyregler.</span><span class="sxs-lookup"><span data-stu-id="31588-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="31588-118">Följande tabell visar de frågetyper som finns tillgängliga för granskningspolicyregler.</span><span class="sxs-lookup"><span data-stu-id="31588-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31588-119">Frågetyp</span><span class="sxs-lookup"><span data-stu-id="31588-119">Query type</span></span></th>
<th><span data-ttu-id="31588-120">Syfte</span><span class="sxs-lookup"><span data-stu-id="31588-120">Purpose</span></span></th>
<th><span data-ttu-id="31588-121">Mer information</span><span class="sxs-lookup"><span data-stu-id="31588-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="31588-122">Villkor</span><span class="sxs-lookup"><span data-stu-id="31588-122">Conditional</span></span></td>
<td><span data-ttu-id="31588-123">Utvärdera källdokumentattribut mot angivna värden.</span><span class="sxs-lookup"><span data-stu-id="31588-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31588-124">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31588-124">Aggregate</span></span></td>
<td><span data-ttu-id="31588-125">Utvärdera flera källdokument eller källdokumentrader mot en policyregel genom summering av numeriska värden.</span><span class="sxs-lookup"><span data-stu-id="31588-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31588-126">Sampling</span><span class="sxs-lookup"><span data-stu-id="31588-126">Sampling</span></span></td>
<td><span data-ttu-id="31588-127">Välj slumpmässigt en viss procent av källdokumenten som ska utvärderas för policykränkningar.</span><span class="sxs-lookup"><span data-stu-id="31588-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="31588-128">När du väljer det här alternativet använder du sidan för regler för granskningspolicy för att ange procenten av dokument som ska väljas slumpmässigt för granskning.</span><span class="sxs-lookup"><span data-stu-id="31588-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31588-129">Duplicera</span><span class="sxs-lookup"><span data-stu-id="31588-129">Duplicate</span></span></td>
<td><span data-ttu-id="31588-130">Utvärdera källdokument för att bestämma om de innehåller dubblettposter i angivna fält.</span><span class="sxs-lookup"><span data-stu-id="31588-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="31588-131">När du väljer det här alternativet använder du sidan för granskningspolicyregler för att ange antal dagar du vill lägga till början av dokumentvalsdatumintervallet när dokument utvärderas om det finns dubblettposter.</span><span class="sxs-lookup"><span data-stu-id="31588-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="31588-132">Listsökning</span><span class="sxs-lookup"><span data-stu-id="31588-132">List search</span></span></td>
<td><span data-ttu-id="31588-133">Utvärdera källdokument för specifika enheter.</span><span class="sxs-lookup"><span data-stu-id="31588-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="31588-134">Rotdokumentet för frågan definierar dokumentet som revideras.</span><span class="sxs-lookup"><span data-stu-id="31588-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="31588-135">Frågan måste vara en listfråga som innehåller en referens till det registret dirpartytable.</span><span class="sxs-lookup"><span data-stu-id="31588-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="31588-136">Detta alternativ kan användas endast med följande AOT-frågor:</span><span class="sxs-lookup"><span data-stu-id="31588-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="31588-137"><span class="ui">AuditPolicyExpenseList</span> (Utgiftsrapport som övervakas av medarbetare)</span><span class="sxs-lookup"><span data-stu-id="31588-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="31588-138"><span class="ui">AuditPolicyPurchList</span> (Inköpsorder som övervakas av leverantörer)</span><span class="sxs-lookup"><span data-stu-id="31588-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="31588-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Leverantörsfaktura som övervakas av leverantörer)</span><span class="sxs-lookup"><span data-stu-id="31588-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="31588-140">Ange övervakade enheter på sidan för regler för granskningspolicyn när du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="31588-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="31588-141">Nyckelordssökning</span><span class="sxs-lookup"><span data-stu-id="31588-141">Keyword search</span></span></td>
<td><span data-ttu-id="31588-142">Utvärdera källdokument för att bestämma om de innehåller vissa word.</span><span class="sxs-lookup"><span data-stu-id="31588-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="31588-143">Ange de ord som ska sökas på sidan för regler för granskningspolicyn när du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="31588-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="31588-144">Sidan för regler för granskningspolicyn innehåller även alternativ som låter dig ange de register och fält som ska utvärderas för de ord som du har angett.</span><span class="sxs-lookup"><span data-stu-id="31588-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="31588-145">Gemensamma parametrar</span><span class="sxs-lookup"><span data-stu-id="31588-145">Common parameters</span></span>
<span data-ttu-id="31588-146">Alla policyregler för en viss granskningspolicy delar samma batchparametrar och samma datumintervallet för dokumenturval.</span><span class="sxs-lookup"><span data-stu-id="31588-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="31588-147">Parametrarna för policyn anges på sidan Ytterligare alternativ.</span><span class="sxs-lookup"><span data-stu-id="31588-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="see-also"></a><span data-ttu-id="31588-148">Se även</span><span class="sxs-lookup"><span data-stu-id="31588-148">See also</span></span>
--------

<span data-ttu-id="31588-149">[Överträdelser av granskningspolicyn och ärenden](audit-policy-violations-cases.md)
[Definiera granskningspolicyer för källdokument](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="31588-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



