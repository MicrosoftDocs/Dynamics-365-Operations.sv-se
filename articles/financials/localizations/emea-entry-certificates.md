---
title: EU-mottagningskvitton
description: "Det här avsnittet innehåller information om mottagningskvitton för Europeiska unionen (EU)."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 6856a52ce85d31c4ef8225e56159e8a7ec698fd7
ms.contentlocale: sv-se
ms.lasthandoff: 06/29/2017


---

# <a name="eu-entry-certificates"></a><span data-ttu-id="5c9be-103">Mottagningskvitton för EU</span><span class="sxs-lookup"><span data-stu-id="5c9be-103">EU entry certificates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5c9be-104">Det här avsnittet innehåller information om mottagningskvitton för Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="5c9be-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="5c9be-105">Du kan utföra följande uppgifter för ett EU-mottagningskvitto:</span><span class="sxs-lookup"><span data-stu-id="5c9be-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="5c9be-106">Skapa och skicka ett EU-mottagningskvitto tillsammans med en följesedel eller kundfaktura för leverans av artiklar och tjänster till EU-länder/områden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="5c9be-107">Ta emot det EU-mottagningskvitto som har signerats av en EU-kund.</span><span class="sxs-lookup"><span data-stu-id="5c9be-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="5c9be-108">Överför det signerade EU-mottagningskvittot som tas emot antingen från kunden eller från en tredje part, som ansvarar för att leverera artiklar till kunden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="5c9be-109">Associera det överförda EU-mottagningskvittot med en kundfaktura.</span><span class="sxs-lookup"><span data-stu-id="5c9be-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="5c9be-110">Uppdatera statusen för det överförda EU-mottagningskvittot.</span><span class="sxs-lookup"><span data-stu-id="5c9be-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c9be-111">Krav</span><span class="sxs-lookup"><span data-stu-id="5c9be-111">Prerequisites</span></span>
<span data-ttu-id="5c9be-112">Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar</span><span class="sxs-lookup"><span data-stu-id="5c9be-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c9be-113">Kategori</span><span class="sxs-lookup"><span data-stu-id="5c9be-113">Category</span></span></th>
<th><span data-ttu-id="5c9be-114">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="5c9be-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5c9be-115">Land/region</span><span class="sxs-lookup"><span data-stu-id="5c9be-115">Country/region</span></span></td>
<td><span data-ttu-id="5c9be-116">Den primära adressen för den juridiska personen måste ligga i ett EU-land.</span><span class="sxs-lookup"><span data-stu-id="5c9be-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5c9be-117">Relaterade inställningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="5c9be-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="5c9be-118">Välj alternativen <strong>Aktivera hantering av mottagningskvitton</strong> och <strong>Aktivera utfärdande av mottagningskvitton</strong> på sidan <strong>Parametrar för kundreskontra</strong>.</span><span class="sxs-lookup"><span data-stu-id="5c9be-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="5c9be-119">Välj <strong>Mottagningskvitto krävs</strong> på snabbfliken <strong>Faktura och leverans</strong> på sidan <strong>Kunder</strong> för att ange om ett EU-mottagningskvitto är obligatoriskt för kunden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="5c9be-120">Markera kryssrutan <strong>Utfärda mottagningskvitto</strong> om du vill utfärda ett EU-mottagningskvitto för kundens juridiska person.</span><span class="sxs-lookup"><span data-stu-id="5c9be-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="5c9be-121">Välj en nummerseriekod för <strong>Postcertifikat</strong> på sidan <strong>Parametrar för kundreskontra</strong>.</span><span class="sxs-lookup"><span data-stu-id="5c9be-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5c9be-122">Relaterade transaktioner</span><span class="sxs-lookup"><span data-stu-id="5c9be-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="5c9be-123">Skapa ett kundkonto.</span><span class="sxs-lookup"><span data-stu-id="5c9be-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="5c9be-124">Skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="5c9be-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="5c9be-125">Skapa och registrera och överföra ett EU-mottagningskvitto</span><span class="sxs-lookup"><span data-stu-id="5c9be-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="5c9be-126">Du kan skapa ett EU-postcertifikat automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="5c9be-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="5c9be-127">Ett EU-mottagningskvitto skapas och skrivs ut automatiskt när du bokför en följesedel eller en faktura för en kund via sidan **Bokför med följesedel** eller sidan **Bokför med faktura**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="5c9be-128">Skapa ett EU-mottagningskvitto manuellt eller skriv ut det på nytt för en kundfaktura via sidan **Fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="5c9be-129">Du kan även ange information om ett EU-mottagningskvitto som utfärdats av en tredje part på sidan **Mottagningskvittojournal**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="5c9be-130">Skapa ett EU-mottagningskvitto automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="5c9be-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="5c9be-131">Du kan skapa ett EU-mottagningskvitto automatiskt, med hjälp av en följesedel på sidan **Alla försäljningsorder** eller genom att använda en faktura på sidan **Försäljningsorder** sidan.</span><span class="sxs-lookup"><span data-stu-id="5c9be-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="5c9be-132">Skapa ett EU-mottagningskvitto manuellt med en faktura på sidan **Fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="5c9be-133">Du måste dock ändra kvittostatusen för en faktura innan du skapar ett EU-mottagningskvitto manuellt.</span><span class="sxs-lookup"><span data-stu-id="5c9be-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="5c9be-134">Registrera ett EU-mottagningskvitto</span><span class="sxs-lookup"><span data-stu-id="5c9be-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="5c9be-135">Om registrering krävs kan även registrera ett EU-mottagningskvitto som utfärdats av tredje part på sidan **Mottagningskvittojournal**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="5c9be-136">Överföra ett mottaget EU-mottagningskvitto</span><span class="sxs-lookup"><span data-stu-id="5c9be-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="5c9be-137">Använd sidan **Bilagor** för att överföra ett mottaget EU-mottagningskvitto som har signerats av en EU-kund.</span><span class="sxs-lookup"><span data-stu-id="5c9be-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="5c9be-138">När kvittot har överförts kan du associera det med en faktura som bevis på att artiklarna har levererats.</span><span class="sxs-lookup"><span data-stu-id="5c9be-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="5c9be-139">Det här beviset krävs om du måste utfärda en faktura som inte inkluderar mervärdesskatt (moms) och den även används vid granskning.</span><span class="sxs-lookup"><span data-stu-id="5c9be-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="5c9be-140">Valfritt: Uppdatera mottagningskvittots status och skriv ut status för en faktura</span><span class="sxs-lookup"><span data-stu-id="5c9be-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="5c9be-141">Du kan uppdatera mottagningskvittostatusen och skriva ut status för en kundfaktura på sidan **Fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="5c9be-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="5c9be-142">Teknisk information för systemadministratörer</span><span class="sxs-lookup"><span data-stu-id="5c9be-142">Technical information for system administrators</span></span>
<span data-ttu-id="5c9be-143">Om du inte har åtkomst till de sidor som används för att slutföra den här uppgiften, kontakta systemadministratören och ange information som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5c9be-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c9be-144">Kategori</span><span class="sxs-lookup"><span data-stu-id="5c9be-144">Category</span></span></th>
<th><span data-ttu-id="5c9be-145">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="5c9be-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5c9be-146">Säkerhetsroller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="5c9be-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="5c9be-147">Om du vill ställa in och skapa ut EU-mottagningskvitton för artiklar eller tjänster måste du vara medlem i en säkerhetsroll som innehåller följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="5c9be-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="5c9be-148"><strong>Kundreskontraansvarig</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="5c9be-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="5c9be-149"><strong>Kundtjänstrepresentant</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="5c9be-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="5c9be-150"><strong>Försäljningsansvarig</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="5c9be-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="5c9be-151"><strong>Leveransansvarig</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="5c9be-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






