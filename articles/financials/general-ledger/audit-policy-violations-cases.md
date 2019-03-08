---
title: Överträdelser av granskningspolicyn
description: Det här avsnittet innehåller en beskrivning av hur revisionsfall genereras från regelbrott för granskningspolicyregler. Här finns även information om hur olika granskningspolicyer använder datumintervallet för dokumenturval.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3ed72f829ca4060fe0a4c03b6d4a47a98cdebd6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "352538"
---
# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="733c6-104">Överträdelser av granskningspolicyn</span><span class="sxs-lookup"><span data-stu-id="733c6-104">Audit policy violations and cases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="733c6-105">Det här avsnittet innehåller en beskrivning av hur revisionsfall genereras från regelbrott för granskningspolicyregler.</span><span class="sxs-lookup"><span data-stu-id="733c6-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="733c6-106">Här finns även information om hur olika granskningspolicyer använder datumintervallet för dokumenturval.</span><span class="sxs-lookup"><span data-stu-id="733c6-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="733c6-107">Hur revisionsärenden genereras</span><span class="sxs-lookup"><span data-stu-id="733c6-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="733c6-108">Granskningspolicyn används för att identifiera utgiftsrapporter, inköpsorder och leverantörsfakturor som inte överensstämmer med affärsreglerna som du definierar och konfigurerar som granskningsregler.</span><span class="sxs-lookup"><span data-stu-id="733c6-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="733c6-109">Granskningspolicyn körs i batchläget.</span><span class="sxs-lookup"><span data-stu-id="733c6-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="733c6-110">När du kör en granskningspolicy, körs alla reglerna i policyn samtidigt.</span><span class="sxs-lookup"><span data-stu-id="733c6-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="733c6-111">Varje policyregel bedömer en uppsättning dokument.</span><span class="sxs-lookup"><span data-stu-id="733c6-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="733c6-112">Policyregeln väljer dokument som finns i datumperioden och som matchar kriteriet som ställts in.</span><span class="sxs-lookup"><span data-stu-id="733c6-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="733c6-113">Exempelvis kan en policyregel välja utgiftsrapporter med måltider som överstiger 500,00.</span><span class="sxs-lookup"><span data-stu-id="733c6-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="733c6-114">En annan policyregel kan välja leverantörsfakturor som ska betalas till en viss leverantör.</span><span class="sxs-lookup"><span data-stu-id="733c6-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="733c6-115">För varje dokument som väljs i uppsättningen, genereras en överträdelse.</span><span class="sxs-lookup"><span data-stu-id="733c6-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="733c6-116">Överträdelsen är en post där ett visst dokument, som faktura 12345, inte följer policyregeln.</span><span class="sxs-lookup"><span data-stu-id="733c6-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="733c6-117">Flera granskningsöverträdelseposter grupperas tillsammans och kopplas till revisionsfall.</span><span class="sxs-lookup"><span data-stu-id="733c6-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="733c6-118">Som standard grupperas fall för varje granskningspolicy efter granskningsregel.</span><span class="sxs-lookup"><span data-stu-id="733c6-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="733c6-119">Om du vill kan du välja andra grupperingsvillkor på sidan **Villkor för ärendegruppering**.</span><span class="sxs-lookup"><span data-stu-id="733c6-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="733c6-120">Exempelvis kan du gruppera sidhuvud för utgifter efter projekt-ID och leverantörsfakturor efter leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="733c6-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="733c6-121">I detta fall kommer alla överträdelser av utgiftsrubriker med samma projekt-ID att grupperas i samma ärende, och samtliga leverantörsfakturor som har samma leverantörskonto grupperas i samma ärende.</span><span class="sxs-lookup"><span data-stu-id="733c6-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="733c6-122">För granskningsregler som baseras på frågetypen **Duplicera** grupperas inte överträdelser efter policyregel eller efter villkor som har angetts på sidan **Villkor för ärendegruppering**.</span><span class="sxs-lookup"><span data-stu-id="733c6-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="733c6-123">I stället grupperas de efter de kriterier som är inbyggda i granskningsregeln.</span><span class="sxs-lookup"><span data-stu-id="733c6-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="733c6-124">Om till exempel en policyregel utvärderar utgiftsrapporter för dubblettutgifter med samma belopp, handlar-id och datum, blir alla utgifter som har samma värden i dessa fält ett enda ärende.</span><span class="sxs-lookup"><span data-stu-id="733c6-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="733c6-125">Alla utgifter som har andra värden, kommer att bli separata fall.</span><span class="sxs-lookup"><span data-stu-id="733c6-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="733c6-126">När revisionsfallen har skapats, hanteras de genom att använda de typiska processerna för ärendehantering.</span><span class="sxs-lookup"><span data-stu-id="733c6-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="733c6-127">Datumintervall för dokumenturval</span><span class="sxs-lookup"><span data-stu-id="733c6-127">Document selection date ranges</span></span>
<span data-ttu-id="733c6-128">När en granskningspolicy körs, väljer varje policyregel dokument med den angivna typen som har ett datum som finns i datumintervallet för dokument.</span><span class="sxs-lookup"><span data-stu-id="733c6-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="733c6-129">Datumintervallet anges på sidan **Ytterligare alternativ**.</span><span class="sxs-lookup"><span data-stu-id="733c6-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="733c6-130">Många dokument har mer än ett kopplat datum.</span><span class="sxs-lookup"><span data-stu-id="733c6-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="733c6-131">Datumfältet som granskningsregeln använder anges på sidan **Policyregeltyp**.</span><span class="sxs-lookup"><span data-stu-id="733c6-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="733c6-132">Nedan följer några andra sätt som en granskningspolicy använder datumintervallet på:</span><span class="sxs-lookup"><span data-stu-id="733c6-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="733c6-133">Policyn använder varje policyregelversion som gäller den sista dagen i dokumentdatumintervallet.</span><span class="sxs-lookup"><span data-stu-id="733c6-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="733c6-134">Du kan visa giltighetsdatumet för varje policyregel på sidan **Granskningspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="733c6-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="733c6-135">Policyn använder organisationsnoderna som är kopplade till policyn den sista dagen i datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="733c6-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="733c6-136">Endast organisationsnoderna som för närvarande är kopplade till policyn visas på listsidan **Granskningspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="733c6-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="733c6-137">För policyregler som är baserade på frågetypen **Listsökning** utvärderar policyn dokument för övervakade enheter som gäller den sista dagen i dokumentdatumintervallet.</span><span class="sxs-lookup"><span data-stu-id="733c6-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="733c6-138">Mer information finns i [Regler för granskningspolicy](audit-policy-rules.md)</span><span class="sxs-lookup"><span data-stu-id="733c6-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>



