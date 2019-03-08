---
title: Synkronisera avtalsfakturor i Field Service till fristextfakturor i Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Microsoft Dynamics 365 for Field Service till fritextfakturor i Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 55301ba39dd28fbae5b6c21b1da3c3d9cf6afd8a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "333264"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a><span data-ttu-id="e50a9-103">Synkronisera avtalsfakturor i Field Service till fritextfakturor i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e50a9-103">Synchronize agreement invoices in Field Service to free text invoices in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e50a9-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Microsoft Dynamics 365 for Field Service till fritextfakturor i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e50a9-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Microsoft Dynamics 365 for Field Service to free text invoices in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e50a9-105">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="e50a9-105">Templates and tasks</span></span>

<span data-ttu-id="e50a9-106">Följande mall och underliggande uppgifter används för att köra synkronisering av avtalsfakturor från Field Service till fritextfakturor i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e50a9-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Finance and Operations.</span></span>

<span data-ttu-id="e50a9-107">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="e50a9-107">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="e50a9-108">Avtalsfakturor (Field Service till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e50a9-108">Agreement invoices (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="e50a9-109">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="e50a9-109">**Names of the tasks in the Data integration project:**</span></span>

- <span data-ttu-id="e50a9-110">Fakturarubriker</span><span class="sxs-lookup"><span data-stu-id="e50a9-110">Invoice headers</span></span>
- <span data-ttu-id="e50a9-111">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="e50a9-111">Invoice lines</span></span>

<span data-ttu-id="e50a9-112">Följande synkroniseringsuppgifter krävs före synkronisering av avtalsfakturor kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="e50a9-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="e50a9-113">Konton (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="e50a9-113">Accounts (Sales to Fin and Ops) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="e50a9-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="e50a9-114">Entity set</span></span>

| <span data-ttu-id="e50a9-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="e50a9-115">Field Service</span></span>  | <span data-ttu-id="e50a9-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e50a9-116">Finance and Operations</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="e50a9-117">fakturor</span><span class="sxs-lookup"><span data-stu-id="e50a9-117">invoices</span></span>       | <span data-ttu-id="e50a9-118">Fakturahuvuden i fritext för CDS-kund</span><span class="sxs-lookup"><span data-stu-id="e50a9-118">CDS customer free text invoice headers</span></span> |
| <span data-ttu-id="e50a9-119">fakturainformation</span><span class="sxs-lookup"><span data-stu-id="e50a9-119">invoicedetails</span></span> | <span data-ttu-id="e50a9-120">Fakturarader i fritext för CDS-kund</span><span class="sxs-lookup"><span data-stu-id="e50a9-120">CDS customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="e50a9-121">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="e50a9-121">Entity flow</span></span>

<span data-ttu-id="e50a9-122">Fakturor som har skapats från ett avtal i Field Service kan synkroniseras till Finance and Operations via ett Common Data Service (CDS) dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="e50a9-122">Invoices that are created from an agreement in Field Service can be synchronized to Finance and Operations via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="e50a9-123">Uppdateringar till dessa fakturor synkroniseras till fritextfakturor i Finance and Operations om redovisningsstatus för fritextfakturor är **pågående**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-123">Updates to these invoices will be synchronized to the free text invoices in Finance and Operations if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="e50a9-124">Efter fritextfakturorna bokförs i Finance and Operations och redovisningsstatus uppdateras till **slutförd**, kan du inte längre synkronisera uppdateringar från Field Service.</span><span class="sxs-lookup"><span data-stu-id="e50a9-124">After the free text invoices are posted in Finance and Operations, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="e50a9-125">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="e50a9-125">Field Service CRM solution</span></span>

<span data-ttu-id="e50a9-126">Fältet **Har rader med avtalsursprung** har lagts till i entiteten **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-126">The **Has Lines With Agreement Origin** field has been added to the **Invoice** entity.</span></span> <span data-ttu-id="e50a9-127">Det här fältet hjälper till att garantera att endast de fakturor som skapas från ett avtal är synkroniserade.</span><span class="sxs-lookup"><span data-stu-id="e50a9-127">This field helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e50a9-128">Värdet är **sant** om fakturan innehåller minst en fakturarad som härrör från ett avtal.</span><span class="sxs-lookup"><span data-stu-id="e50a9-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="e50a9-129">Fältet **Har rader med avtalsursprung** har lagts till i entiteten **Fakturarad**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-129">The **Has Agreement Origin** field has been added to the **Invoice Line** entity.</span></span> <span data-ttu-id="e50a9-130">Det här fältet hjälper till att garantera att endast de fakturarader som skapas från ett avtal är synkroniserade.</span><span class="sxs-lookup"><span data-stu-id="e50a9-130">This field helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e50a9-131">Värdet är **sant** om fakturaraden kommer från ett avtal.</span><span class="sxs-lookup"><span data-stu-id="e50a9-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="e50a9-132">**Fakturadatum** är ett obligatoriskt fält i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e50a9-132">**Invoice date** is a mandatory field in Finance and Operations.</span></span> <span data-ttu-id="e50a9-133">Därför måste fältet ha ett värde i Field Service innan synkroniseringen sker.</span><span class="sxs-lookup"><span data-stu-id="e50a9-133">Therefore, the field must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="e50a9-134">Följande logik måste läggas till för att uppfylla detta krav:</span><span class="sxs-lookup"><span data-stu-id="e50a9-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="e50a9-135">Om fältet **Fakturadatum** är tomt på entiteten **Faktura** (om den inte har något värde), anges det aktuella datumet när en fakturarad som härrör från en överenskommelse läggs till.</span><span class="sxs-lookup"><span data-stu-id="e50a9-135">If the **Invoice Date** field is blank on the **Invoice** entity (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="e50a9-136">Användaren kan ändra fältet **Fakturadatum**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-136">The user can change the **Invoice Date** field.</span></span> <span data-ttu-id="e50a9-137">Men när användaren försöker spara en faktura som härrör från ett avtal får han eller hon ett affärsprocessfel om fältet **Fakturadatum** är tomt på fakturan.</span><span class="sxs-lookup"><span data-stu-id="e50a9-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** field is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="e50a9-138">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e50a9-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="e50a9-139">I Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e50a9-139">In Finance and Operations</span></span>

<span data-ttu-id="e50a9-140">Ett fakturafakturaursprung måste ställas in för integrationen för att särskilja fritextfakturor i Finance and Operations som skapas från avtalsfakturor i Field Service.</span><span class="sxs-lookup"><span data-stu-id="e50a9-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Finance and Operations that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="e50a9-141">När en faktura har ett fakturaursprung i typen **Integration avtal/faktura** visas fältet **Externt fakturanummer** på rubriken för **Försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="e50a9-142">Förutom att visas på fakturarubriken, kan information **Externt fakturanummer** användas för att garantera att fakturor som skapas från avtalsfakturor för Field Service filtreras bort under synkroniseringen av fakturan från Finance and Operations till Field Service.</span><span class="sxs-lookup"><span data-stu-id="e50a9-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Finance and Operations to Field Service.</span></span>

1. <span data-ttu-id="e50a9-143">Gå till **Kundreskontra** \> **Inställningar** \> **Ursprungskoder för faktura**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="e50a9-144">Välj **Ny** för att skapa ett nytt fakturaursprung.</span><span class="sxs-lookup"><span data-stu-id="e50a9-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="e50a9-145">I fältet **Fakturaursprung** anger du ett namn för fakturaursprung som t.ex. **FS**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="e50a9-146">I fältet **Beskrivning** anger du en beskrivning såsom **Avtalsfakturor för Field Service**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="e50a9-147">Markera kryssrutan **Tilldelning av ursprungstyp**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="e50a9-148">Ange fältet **Typ av fakturaursprung** till **Integration avtal/faktura**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="e50a9-149">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="e50a9-150">I dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="e50a9-150">In the Data Integration project</span></span>

<span data-ttu-id="e50a9-151">Uppgift: **Fakturarader**</span><span class="sxs-lookup"><span data-stu-id="e50a9-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="e50a9-152">Se till att standardvärdet för Finance and Operations-fältet **Visningsvärde för huvudkonto** uppdateras så att det matchar det önskade värdet.</span><span class="sxs-lookup"><span data-stu-id="e50a9-152">Make sure that the default value for the Finance and Operations field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="e50a9-153">Standardmallvärdet är **401100**.</span><span class="sxs-lookup"><span data-stu-id="e50a9-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e50a9-154">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="e50a9-154">Template mapping in Data integration</span></span>

<span data-ttu-id="e50a9-155">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="e50a9-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a><span data-ttu-id="e50a9-156">Avtalsfakturor (Field Service till Fin and Ops): Fakturarubriker</span><span class="sxs-lookup"><span data-stu-id="e50a9-156">Agreement invoices (Field Service to Fin and Ops): Invoice headers</span></span>

<span data-ttu-id="e50a9-157">[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="e50a9-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a><span data-ttu-id="e50a9-158">Avtalsfakturor (Field Service till Fin and Ops): Fakturarubrikrader</span><span class="sxs-lookup"><span data-stu-id="e50a9-158">Agreement invoices (Field Service to Fin and Ops): Invoice lines</span></span>

<span data-ttu-id="e50a9-159">[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="e50a9-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>
