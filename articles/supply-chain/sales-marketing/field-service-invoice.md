---
title: Synkronisera avtalsfakturor i Field Service till fritextfakturor i Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Dynamics 365 Field Service till fritextfakturor i Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 21a77a0289055285f47323803a484c012e662e3a
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102744"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="212e3-103">Synkronisera avtalsfakturor i Field Service till fritextfakturor i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="212e3-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="212e3-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Dynamics 365 Field Service till fritextfakturor i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="212e3-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="212e3-105">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="212e3-105">Templates and tasks</span></span>

<span data-ttu-id="212e3-106">Följande mall och underliggande uppgifter används för att köra synkronisering av avtalsfakturor från Field Service till fritextfakturor i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="212e3-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="212e3-107">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="212e3-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="212e3-108">Avtalsfakturor (Field Service till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="212e3-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="212e3-109">**Namnen på uppgifterna i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="212e3-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="212e3-110">Fakturarubriker</span><span class="sxs-lookup"><span data-stu-id="212e3-110">Invoice headers</span></span>
- <span data-ttu-id="212e3-111">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="212e3-111">Invoice lines</span></span>

<span data-ttu-id="212e3-112">Följande synkroniseringsuppgifter krävs före synkronisering av avtalsfakturor kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="212e3-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="212e3-113">Konton (Sales till Supply Chain Management) – Direkt</span><span class="sxs-lookup"><span data-stu-id="212e3-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="212e3-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="212e3-114">Entity set</span></span>

| <span data-ttu-id="212e3-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="212e3-115">Field Service</span></span>  | <span data-ttu-id="212e3-116">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="212e3-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="212e3-117">fakturor</span><span class="sxs-lookup"><span data-stu-id="212e3-117">invoices</span></span>       | <span data-ttu-id="212e3-118">Dataverse fakturahuvuden i fritext för kund</span><span class="sxs-lookup"><span data-stu-id="212e3-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="212e3-119">fakturainformation</span><span class="sxs-lookup"><span data-stu-id="212e3-119">invoicedetails</span></span> | <span data-ttu-id="212e3-120">Dataverse fakturarader i fritext för kund</span><span class="sxs-lookup"><span data-stu-id="212e3-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="212e3-121">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="212e3-121">Entity flow</span></span>

<span data-ttu-id="212e3-122">Fakturor som har skapats från ett avtal i Field Service kan synkroniseras till Supply Chain Management via ett Microsoft Dataverse dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="212e3-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="212e3-123">Uppdateringar till dessa fakturor synkroniseras till fritextfakturor i Supply Chain Management om redovisningsstatus för fritextfakturor är **pågående**.</span><span class="sxs-lookup"><span data-stu-id="212e3-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="212e3-124">Efter fritextfakturorna bokförs i Supply Chain Management och redovisningsstatus uppdateras till **slutförd**, kan du inte längre synkronisera uppdateringar från Field Service.</span><span class="sxs-lookup"><span data-stu-id="212e3-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="212e3-125">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="212e3-125">Field Service CRM solution</span></span>

<span data-ttu-id="212e3-126">Kolumnen **Har rader med avtalsursprung** har lagts till i tabellen **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="212e3-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="212e3-127">Den här kolumnen hjälper till att garantera att endast de fakturor som skapas från ett avtal är synkroniserade.</span><span class="sxs-lookup"><span data-stu-id="212e3-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="212e3-128">Värdet är **sant** om fakturan innehåller minst en fakturarad som härrör från ett avtal.</span><span class="sxs-lookup"><span data-stu-id="212e3-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="212e3-129">Kolumnen **Har avtalsursprung** har lagts till i tabellen **Fakturarad**.</span><span class="sxs-lookup"><span data-stu-id="212e3-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="212e3-130">Den här kolumnen hjälper till att garantera att endast de fakturarader som skapas från ett avtal är synkroniserade.</span><span class="sxs-lookup"><span data-stu-id="212e3-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="212e3-131">Värdet är **sant** om fakturaraden kommer från ett avtal.</span><span class="sxs-lookup"><span data-stu-id="212e3-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="212e3-132">**Fakturadatum** är ett obligatoriskt fält i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="212e3-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="212e3-133">Därför måste kolumnen ha ett värde i Field Service innan synkroniseringen sker.</span><span class="sxs-lookup"><span data-stu-id="212e3-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="212e3-134">Följande logik måste läggas till för att uppfylla detta krav:</span><span class="sxs-lookup"><span data-stu-id="212e3-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="212e3-135">Om kolumnen **Fakturadatum** är tomt på tabellen **Faktura** (om den inte har något värde), anges det aktuella datumet när en fakturarad som härrör från en överenskommelse läggs till.</span><span class="sxs-lookup"><span data-stu-id="212e3-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="212e3-136">Användaren kan ändra kolumnen **Fakturadatum**.</span><span class="sxs-lookup"><span data-stu-id="212e3-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="212e3-137">Men när användaren försöker spara en faktura som härrör från ett avtal får han eller hon ett affärsprocessfel om kolumnen **Fakturadatum** är tomt på fakturan.</span><span class="sxs-lookup"><span data-stu-id="212e3-137">However, when the user tries to save an invoice that originates from an agreement, they receive a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="212e3-138">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="212e3-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="212e3-139">I Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="212e3-139">In Supply Chain Management</span></span>

<span data-ttu-id="212e3-140">Ett fakturafakturaursprung måste ställas in för integrationen för att särskilja fritextfakturor i Supply Chain Management som skapas från avtalsfakturor i Field Service.</span><span class="sxs-lookup"><span data-stu-id="212e3-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="212e3-141">När en faktura har ett fakturaursprung i typen **Integration avtal/faktura** visas fältet **Externt fakturanummer** på rubriken för **Försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="212e3-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="212e3-142">Förutom att visas på fakturarubriken, kan information **Externt fakturanummer** användas för att garantera att fakturor som skapas från avtalsfakturor för Field Service filtreras bort under synkroniseringen av fakturan från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="212e3-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="212e3-143">Gå till **Kundreskontra** \> **Inställningar** \> **Ursprungskoder för faktura**.</span><span class="sxs-lookup"><span data-stu-id="212e3-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="212e3-144">Välj **Ny** för att skapa ett nytt fakturaursprung.</span><span class="sxs-lookup"><span data-stu-id="212e3-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="212e3-145">I fältet **Fakturaursprung** anger du ett namn för fakturaursprung som t.ex. **FS**.</span><span class="sxs-lookup"><span data-stu-id="212e3-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="212e3-146">I fältet **Beskrivning** anger du en beskrivning såsom **Avtalsfakturor för Field Service**.</span><span class="sxs-lookup"><span data-stu-id="212e3-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="212e3-147">Markera kryssrutan **Tilldelning av ursprungstyp**.</span><span class="sxs-lookup"><span data-stu-id="212e3-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="212e3-148">Ange fältet **Typ av fakturaursprung** till **Integration avtal/faktura**.</span><span class="sxs-lookup"><span data-stu-id="212e3-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="212e3-149">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="212e3-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="212e3-150">I dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="212e3-150">In the Data Integration project</span></span>

<span data-ttu-id="212e3-151">Uppgift: **Fakturarader**</span><span class="sxs-lookup"><span data-stu-id="212e3-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="212e3-152">Se till att standardvärdet för Supply Chain Management-fältet **Visningsvärde för huvudkonto** uppdateras så att det matchar det önskade värdet.</span><span class="sxs-lookup"><span data-stu-id="212e3-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="212e3-153">Standardmallvärdet är **401100**.</span><span class="sxs-lookup"><span data-stu-id="212e3-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="212e3-154">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="212e3-154">Template mapping in Data integration</span></span>

<span data-ttu-id="212e3-155">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="212e3-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="212e3-156">Avtalsfakturor (Field Service till Supply Chain Management): Fakturarubriker</span><span class="sxs-lookup"><span data-stu-id="212e3-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="212e3-157">[![Mallmappning i Dataintegration för fakturahuvuden](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="212e3-157">[![Template mapping in Data integration for invoice headers](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="212e3-158">Avtalsfakturor (Field Service till Supply Chain Management): Fakturarader</span><span class="sxs-lookup"><span data-stu-id="212e3-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="212e3-159">[![Mallmappning i Dataintegration för fakturarader](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="212e3-159">[![Template mapping in Data integration for invoice lines](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]