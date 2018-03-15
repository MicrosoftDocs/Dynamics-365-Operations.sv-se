---
title: "Automation av leverantörsfaktura"
description: "Det här avsnittet beskriver de funktioner som är tillgängliga för slutpunkt till slutpunkt-automatisering av leverantörsfakturor, även fakturor som innehåller bilagor."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 92a52646063c145d733b9d2960253004e8eab80a
ms.openlocfilehash: 34dc8d762db4a4802e52188ebda298db234ee376
ms.contentlocale: sv-se
ms.lasthandoff: 03/05/2018

---
# <a name="vendor-invoice-automation"></a><span data-ttu-id="a946d-103">Automation av leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="a946d-103">Vendor invoice automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a946d-104">Det här avsnittet beskriver de funktioner som är tillgängliga för slutpunkt till slutpunkt-automatisering av leverantörsfakturor, även fakturor som innehåller bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-104">This topic explains the features that are available for end-to-end automation of vendor invoices, even invoices that include attachments.</span></span>

<span data-ttu-id="a946d-105">Organisationer som vill förenkla sina processer för leverantörsreskontra (AP) identifierar ofta behandlingen av fakturan som ett av det viktigaste behandlingsområdet att effektivisera.</span><span class="sxs-lookup"><span data-stu-id="a946d-105">Organizations that want to streamline their Accounts payable (AP) processes often identify invoice processing as one of the top process areas that should be more efficient.</span></span> <span data-ttu-id="a946d-106">I många fall kan dessa organisationer avlasta behandlingen av pappersfakturor till en tredjeparts tjänstleverantör av optisk teckenläsning (OCR).</span><span class="sxs-lookup"><span data-stu-id="a946d-106">In many cases, these organizations offload the processing of paper invoices to a third-party optical character recognition (OCR) service provider.</span></span> <span data-ttu-id="a946d-107">De får sedan metadata för en maskinläsbar faktura tillsammans med en skannad bild av varje faktura.</span><span class="sxs-lookup"><span data-stu-id="a946d-107">They then receive machine-readable invoice metadata together with a scanned image of each invoice.</span></span> <span data-ttu-id="a946d-108">Som en hjälp för automatiseringen byggs sedan en ”slut”-lösning för att möjliggöra förbrukning av dessa artefakter i faktureringssystemet.</span><span class="sxs-lookup"><span data-stu-id="a946d-108">To help with automation, a “last mile” solution is then built to enable consumption of these artifacts in the invoicing system.</span></span> <span data-ttu-id="a946d-109">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition möjliggör nu ”slut”-automatisering via en färdig lösning för automatisering av fakturan.</span><span class="sxs-lookup"><span data-stu-id="a946d-109">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition now enables this “last mile” automation out of the box, through an invoice automation solution.</span></span>

## <a name="solution-context"></a><span data-ttu-id="a946d-110">Kontexten för lösningen</span><span class="sxs-lookup"><span data-stu-id="a946d-110">Solution context</span></span>

<span data-ttu-id="a946d-111">Lösningen för automatiseringen av fakturor innebär ett standardgränssnitt som kan acceptera fakturametadata för fakturahuvudet och fakturaraderna och även bifogade filer som är kopplade till fakturan.</span><span class="sxs-lookup"><span data-stu-id="a946d-111">The invoice automation solution enables a standard interface that can accept invoice metadata for the invoice header and invoice lines, and also attachments that are applicable to the invoice.</span></span> <span data-ttu-id="a946d-112">Alla externa system som genererar artefakter som överensstämmer med det här gränssnittet kan skicka flödet till Finance and Operations för automatisk bearbetning av fakturor och bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="a946d-112">Any external system that can generate artifacts that comply with this interface will be able to send the feed into Finance and Operations for automatic processing of invoices and attachments.</span></span>

<span data-ttu-id="a946d-113">Följande bild visar ett exempelscenario på integrering där Contoso samarbetar med en OCR-tjänstleverantör för behandling av leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="a946d-113">The following illustration shows a sample integration scenario where Contoso has partnered with an OCR service provider for vendor invoice processing.</span></span> <span data-ttu-id="a946d-114">Contosos leverantörer skickar fakturor till tjänstleverantören via e-post.</span><span class="sxs-lookup"><span data-stu-id="a946d-114">Contoso’s vendors send invoices to the service provider by email.</span></span> <span data-ttu-id="a946d-115">Via OCR-bearbetningen genererar tjänstleverantören fakturans metadata (rubrik och/eller rader) och en skannad bild av fakturan.</span><span class="sxs-lookup"><span data-stu-id="a946d-115">Through OCR processing, the service provider generates invoice metadata (header and/or lines) and a scanned image of the invoice.</span></span> <span data-ttu-id="a946d-116">Ett integreringsskikt omvandlar sedan dessa artefakter så att Finance and Operations kan förbruka dem.</span><span class="sxs-lookup"><span data-stu-id="a946d-116">An integration layer then transforms these artifacts so that Finance and Operations can consume them.</span></span>

![Exempel på integreringsscenario](media/vendor_invoice_automation_01.png)

<span data-ttu-id="a946d-118">Det finns flera variationer av föregående scenario som är möjliga om fakturintegrering krävs.</span><span class="sxs-lookup"><span data-stu-id="a946d-118">Several variations of the preceding scenario are possible if invoice integration is required.</span></span> <span data-ttu-id="a946d-119">Migrering av data är ett annat användningsfall där detta gränssnitt kan användas för att skapa fakturor och bilagor i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a946d-119">Data migration is another use case where this interface can be used to create invoices and attachments in Finance and Operations.</span></span>

### <a name="solution-components"></a><span data-ttu-id="a946d-120">Lösningens komponenter</span><span class="sxs-lookup"><span data-stu-id="a946d-120">Solution components</span></span>

<span data-ttu-id="a946d-121">Lösningens fotspår består av följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="a946d-121">The solution footprint consists of the following components:</span></span>

+ <span data-ttu-id="a946d-122">Dataenheter för fakturahuvudet, fakturarader och fakturera bilagor</span><span class="sxs-lookup"><span data-stu-id="a946d-122">Data entities for the invoice header, invoice lines, and invoice attachments</span></span>
+ <span data-ttu-id="a946d-123">Undantagsbehandling av fakturor</span><span class="sxs-lookup"><span data-stu-id="a946d-123">Exception processing for invoices</span></span>
+ <span data-ttu-id="a946d-124">En sida-vid-sida-bilagevisning på fakturor</span><span class="sxs-lookup"><span data-stu-id="a946d-124">A side-by-side attachment viewer in invoices</span></span>

<span data-ttu-id="a946d-125">Resten av det här avsnittet innehåller detaljerade beskrivningar av dessa komponenter.</span><span class="sxs-lookup"><span data-stu-id="a946d-125">The rest of this topic provides detailed descriptions of these solution components.</span></span>

## <a name="data-entities"></a><span data-ttu-id="a946d-126">Datatabeller</span><span class="sxs-lookup"><span data-stu-id="a946d-126">Data entities</span></span>

<span data-ttu-id="a946d-127">Ett datapaket är den arbetsenhet som måste skickas till Finance and Operations, så att fakturahuvuden, fakturarader och fakturans bilagor kan skapas.</span><span class="sxs-lookup"><span data-stu-id="a946d-127">A data package is the unit of work that must be sent to Finance and Operations, so that invoice headers, invoice lines, and invoice attachments can be created.</span></span> <span data-ttu-id="a946d-128">Följande dataenheter används för artefakter som ingår i datapaketet:</span><span class="sxs-lookup"><span data-stu-id="a946d-128">The following data entities are used for the artifacts that make up the data package:</span></span>

+ <span data-ttu-id="a946d-129">Leverantörsfakturahuvud</span><span class="sxs-lookup"><span data-stu-id="a946d-129">Vendor invoice header</span></span>
+ <span data-ttu-id="a946d-130">Leverantörsfakturarad</span><span class="sxs-lookup"><span data-stu-id="a946d-130">Vendor invoice line</span></span>
+ <span data-ttu-id="a946d-131">Dokumentbilaga till leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="a946d-131">Vendor invoice document attachment</span></span>

<span data-ttu-id="a946d-132">Dokumentbilagor till leverantörsfakturan är en ny dataenhet som introduceras som en del av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a946d-132">Vendor invoice document attachment is a new data entity that is introduced as part of this feature.</span></span> <span data-ttu-id="a946d-133">Rubrikenheten för leverantörsfakturan har ändrats så att den stöder bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-133">The Vendor invoice header entity has been modified so that it supports attachments.</span></span> <span data-ttu-id="a946d-134">Radenheten för leverantörsfakturan har inte ändrats för den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a946d-134">The Vendor invoice line entity hasn’t been modified for this feature.</span></span>

<span data-ttu-id="a946d-135">Det här avsnittet ger inte en detaljerad definition av ett datapaket.</span><span class="sxs-lookup"><span data-stu-id="a946d-135">This topic doesn’t give a detailed definition of a data package.</span></span> <span data-ttu-id="a946d-136">Det ges inte heller någon beskrivning av hur du skapar datapaket.</span><span class="sxs-lookup"><span data-stu-id="a946d-136">It also doesn’t explain how to create data packages.</span></span> <span data-ttu-id="a946d-137">Den här informationen finns i [Ramverk för dataenheter och -paket](../../dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a946d-137">For this information, see [Data entities and packages framework](../../dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

<span data-ttu-id="a946d-138">Om du snabbt vill generera testdata som inkluderar fakturor och bilagor ska du följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="a946d-138">To quickly generate test data that includes invoices and attachments, follow these steps.</span></span>

1. <span data-ttu-id="a946d-139">Logga in på din instans av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a946d-139">Sign in to your Finance and Operations instance.</span></span>
1. <span data-ttu-id="a946d-140">Gå till **Leverantörsreskontra** > **Fakturor** > **Väntande leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="a946d-140">Go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.</span></span>
1. <span data-ttu-id="a946d-141">Skapa fakturor som har rader och bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-141">Create invoices that have lines and attachments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a946d-142">Bilagorna måste vara rubrikbilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-142">The attachments must be header attachments.</span></span> <span data-ttu-id="a946d-143">För närvarande stöder inte dokumentbilageenheten för leverantörsfakturan radbilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-143">Currently, the Vendor invoice document attachment entity doesn’t support line attachments.</span></span>

1. <span data-ttu-id="a946d-144">Öppna arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="a946d-144">Open the **Data management** workspace.</span></span>
1. <span data-ttu-id="a946d-145">Skapa ett exportjobb som innehåller leverantörsfakturans rubrik, leverantörsfakturaraden och leverantörsfakturans dokumentbilageenhet.</span><span class="sxs-lookup"><span data-stu-id="a946d-145">Create an export job that includes the Vendor invoice header, Vendor invoice line, and Vendor invoice document attachment entities.</span></span>
1. <span data-ttu-id="a946d-146">Exportera data.</span><span class="sxs-lookup"><span data-stu-id="a946d-146">Export the data.</span></span>
1. <span data-ttu-id="a946d-147">Hämta exporterade data som ett paket.</span><span class="sxs-lookup"><span data-stu-id="a946d-147">Download the exported data as a package.</span></span> <span data-ttu-id="a946d-148">Du kan nu använda paketet för att importera data till målinstanser för testningsändamål.</span><span class="sxs-lookup"><span data-stu-id="a946d-148">You can now use the package to import data into target instances for testing purposes.</span></span>

### <a name="determining-the-legal-entity-for-an-invoice"></a><span data-ttu-id="a946d-149">Fastställa juridisk person för en faktura</span><span class="sxs-lookup"><span data-stu-id="a946d-149">Determining the legal entity for an invoice</span></span>

<span data-ttu-id="a946d-150">Fakturor som importeras med datapaket kan associeras med den juridiska person de tillhör på två sätt:</span><span class="sxs-lookup"><span data-stu-id="a946d-150">Invoices that are imported via data packages can be associated with the legal entity that they belong to in two ways:</span></span>

+ <span data-ttu-id="a946d-151">Importjobbet som bearbetar fakturan importerar den till samma företag som jobbet planerades för i arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="a946d-151">The import job that processes the invoice imports it into the same company in which the job was scheduled in the **Data management** workspace.</span></span> <span data-ttu-id="a946d-152">Med andra ord fastställer företaget som utför jobbet vilket företag fakturan tillhör.</span><span class="sxs-lookup"><span data-stu-id="a946d-152">In other words, the company of the job determines the company that the invoice belongs to.</span></span>
+ <span data-ttu-id="a946d-153">När datapaket som innehåller fakturor skickas till Finance and Operations kan anroparen (det vill säga integreringsprogrammet som körs utanför Finance and Operations) explicit ange företagets ID i HTTP-förfrågan.</span><span class="sxs-lookup"><span data-stu-id="a946d-153">When the data package that contains invoices is sent to Finance and Operations, the caller (that is, the integration application that runs outside of Finance and Operations) can explicitly mention the company ID in the HTTP request.</span></span> <span data-ttu-id="a946d-154">I det här fallet åsidosätts företagssammanhanget i Finance and Operations som jobbet körs i och fakturorna importeras till det företag som skickades via en HTTP-begäran.</span><span class="sxs-lookup"><span data-stu-id="a946d-154">In this case, the company context in which the processing job runs in Finance and Operations is overridden, and the invoices are imported into the company that was passed via the HTTP request.</span></span>

> [!NOTE]
> <span data-ttu-id="a946d-155">Detta beteende är standard för datahantering.</span><span class="sxs-lookup"><span data-stu-id="a946d-155">This behavior is standard data management behavior.</span></span> <span data-ttu-id="a946d-156">Det förklaras här, i samband med fakturor, för fullständighet.</span><span class="sxs-lookup"><span data-stu-id="a946d-156">It’s explained here, in the context of invoices, just for the sake of completeness.</span></span>

## <a name="exception-processing"></a><span data-ttu-id="a946d-157">Behandling av undantag</span><span class="sxs-lookup"><span data-stu-id="a946d-157">Exception processing</span></span>

<span data-ttu-id="a946d-158">I fall där leverantörsfakturor kommer till Finance and Operations via integrering måste det finnas ett enkelt sätt för ansvariga för leverantörsreskontra att behandla undantag och felaktiga fakturor och att skapa väntande fakturor med utgångspunkt från felaktiga fakturor.</span><span class="sxs-lookup"><span data-stu-id="a946d-158">In scenarios where vendor invoices come into Finance and Operations via integration, there must be an easy way for an Accounts payable team member to process exceptions or failed invoices, and to create pending invoices out of failed invoices.</span></span> <span data-ttu-id="a946d-159">Behandlingen av detta undantag för leverantörsfakturor ingår nu i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a946d-159">This exception processing for vendor invoices is now part of Finance and Operations.</span></span>

### <a name="exceptions-list-page"></a><span data-ttu-id="a946d-160">Sida med lista över undantag</span><span class="sxs-lookup"><span data-stu-id="a946d-160">Exceptions list page</span></span>

<span data-ttu-id="a946d-161">Den nya sidan med lista över undantag finns på **Leverantörsreskontra** > **Fakturor** > **Importfel** > **Leverantörsfakturor som inte importerades**.</span><span class="sxs-lookup"><span data-stu-id="a946d-161">The new list page for invoice exceptions is available at **Accounts payable** > **Invoices** > **Import failures** > **Vendor invoices that failed to import**.</span></span> <span data-ttu-id="a946d-162">Den här sidan visar alla rubrikposter för leverantörsfakturan från mellanlagringsregistret för leverantörsfakturans rubrikdatapost.</span><span class="sxs-lookup"><span data-stu-id="a946d-162">This page shows all the vendor invoice header records from the staging table of the Vendor invoice header data entity.</span></span> <span data-ttu-id="a946d-163">Observera att du kan visa samma poster från arbetsytan **Datahantering**, där du även kan utföra samma åtgärder som ingår i funktionen för hantering av undantag.</span><span class="sxs-lookup"><span data-stu-id="a946d-163">Note that you can view the same records from the **Data management** workspace, where you can also perform the same actions that are provided in the exception handling feature.</span></span> <span data-ttu-id="a946d-164">Användargränssnittet för funktionen för hantering av undantag är dock optimerad för en funktionell användare.</span><span class="sxs-lookup"><span data-stu-id="a946d-164">However, the UI that the exception handling feature provides is optimized for a functional user.</span></span>

![Sida med lista över undantag](media/vendor_invoice_automation_02.png)

<span data-ttu-id="a946d-166">Den här sidan innehåller följande fält som kommer in via flödet:</span><span class="sxs-lookup"><span data-stu-id="a946d-166">This list page includes the following fields that come in via the feed:</span></span>

+ <span data-ttu-id="a946d-167">**Företag** – företaget som fakturan tillhör</span><span class="sxs-lookup"><span data-stu-id="a946d-167">**Company** – The company that the invoice belongs to</span></span>
+ <span data-ttu-id="a946d-168">**Felmeddelande** – felmeddelandet som ramverket för datahantering utfärdar för att förklara varför fakturan inte kunde skapas</span><span class="sxs-lookup"><span data-stu-id="a946d-168">**Error message** – The error message that the data management framework issues to explain why the invoice could not be created</span></span>
+ <span data-ttu-id="a946d-169">**Nummer** – fakturanumret</span><span class="sxs-lookup"><span data-stu-id="a946d-169">**Number** – The invoice number</span></span>
+ <span data-ttu-id="a946d-170">**Fakturakonto**</span><span class="sxs-lookup"><span data-stu-id="a946d-170">**Invoice account**</span></span>
+ <span data-ttu-id="a946d-171">**Namn** – leverantörens namn</span><span class="sxs-lookup"><span data-stu-id="a946d-171">**Name** – The vendor’s name</span></span>
+ <span data-ttu-id="a946d-172">**Leverantörskonto**</span><span class="sxs-lookup"><span data-stu-id="a946d-172">**Vendor account**</span></span>
+ <span data-ttu-id="a946d-173">**Inköpsorder** – numret på inköpsordern (IO) för fakturan</span><span class="sxs-lookup"><span data-stu-id="a946d-173">**Purchase order** – The purchase order (PO) number for the invoice</span></span>
+ <span data-ttu-id="a946d-174">**Bokföringsdatum**</span><span class="sxs-lookup"><span data-stu-id="a946d-174">**Posting date**</span></span>
+ <span data-ttu-id="a946d-175">**Fakturadatum**</span><span class="sxs-lookup"><span data-stu-id="a946d-175">**Invoice date**</span></span>
+ <span data-ttu-id="a946d-176">**Fakturabeskrivning**</span><span class="sxs-lookup"><span data-stu-id="a946d-176">**Invoice description**</span></span>
+ <span data-ttu-id="a946d-177">**Valuta**</span><span class="sxs-lookup"><span data-stu-id="a946d-177">**Currency**</span></span>
+ <span data-ttu-id="a946d-178">**Logg**</span><span class="sxs-lookup"><span data-stu-id="a946d-178">**Log**</span></span>
+ <span data-ttu-id="a946d-179">**Radreferens** – identifierare som kommer från det externa systemet</span><span class="sxs-lookup"><span data-stu-id="a946d-179">**Line reference** – The identifier that comes from the external system</span></span>

    > [!NOTE]
    > <span data-ttu-id="a946d-180">Radreferensen är inte fakturans ID.</span><span class="sxs-lookup"><span data-stu-id="a946d-180">The line reference isn’t the invoice ID.</span></span>

<span data-ttu-id="a946d-181">Den här listsidan har även ett förhandsgranskningsfönster som kan användas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a946d-181">This list page also has a preview pane that you can used in the following ways:</span></span>

+ <span data-ttu-id="a946d-182">Visa hela felmeddelandet så att du inte behöver utöka kolumnen **Felmeddelande** i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a946d-182">View the whole error message, so that you don’t have to expand the **Error message** column in the grid.</span></span>
+ <span data-ttu-id="a946d-183">Visa hela listan över bifogade filer för fakturan, om bilagor medföljde fakturan.</span><span class="sxs-lookup"><span data-stu-id="a946d-183">View the whole list of attachments for the invoice, if any attachments came with the invoice.</span></span>

<span data-ttu-id="a946d-184">Listsidan stöder följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-184">The list page supports the following actions:</span></span>

+ <span data-ttu-id="a946d-185">**Redigera** – öppna undantagsposten i redigeringsläge, så att du kan lösa problemen.</span><span class="sxs-lookup"><span data-stu-id="a946d-185">**Edit** – Open the exception record in edit mode, so that you can fix the issues.</span></span>
+ <span data-ttu-id="a946d-186">**Alternativ** – åtkomst till standardalternativ som är tillgängliga på listsidor.</span><span class="sxs-lookup"><span data-stu-id="a946d-186">**Options** – Access the standard options that are available on list pages.</span></span> <span data-ttu-id="a946d-187">Du kan använda alternativet **Lägg till arbetsyta** för att fästa listsidan med undantag på din arbetsyta som en lista eller panel.</span><span class="sxs-lookup"><span data-stu-id="a946d-187">You can use the **Add to workspace** option to pin the exceptions list page to your workspace as a list or tile.</span></span>

### <a name="exception-details-page"></a><span data-ttu-id="a946d-188">Informationssida för undantag</span><span class="sxs-lookup"><span data-stu-id="a946d-188">Exception details page</span></span>

<span data-ttu-id="a946d-189">När du startar redigeringsläget visas informationssidan för undantag för fakturan med fel.</span><span class="sxs-lookup"><span data-stu-id="a946d-189">When you start edit mode, the exception details page for the invoice that has issues appears.</span></span> <span data-ttu-id="a946d-190">Om det inte finns bilagor visas fakturan och standardbilagan sida vid sida på informationssidan för undantag.</span><span class="sxs-lookup"><span data-stu-id="a946d-190">If there are any attachments, the invoice and the default attachment appear side by side on the exception details page.</span></span>

![Informationssida för undantag](media/vendor_invoice_automation_03.png)

<span data-ttu-id="a946d-192">I föregående illustration fanns det inga rader för leverantörsfakturarubrik som kom in.</span><span class="sxs-lookup"><span data-stu-id="a946d-192">In the preceding illustration, there weren’t any lines for the vendor invoice header that came in.</span></span> <span data-ttu-id="a946d-193">Radavsnittet är därför tomt.</span><span class="sxs-lookup"><span data-stu-id="a946d-193">Therefore, the lines section is empty.</span></span>

<span data-ttu-id="a946d-194">Informationssidan för undantag stöder följande åtgärd:</span><span class="sxs-lookup"><span data-stu-id="a946d-194">The exception details page supports the following operation:</span></span>

+ <span data-ttu-id="a946d-195">**Skapa väntande faktura** – när du har åtgärdat felen på fakturan som en del av behandlingen av ett undantag kan du klicka på den här knappen om du vill skapa en väntande faktura.</span><span class="sxs-lookup"><span data-stu-id="a946d-195">**Create pending invoice** – After you’ve fixed the issues on the invoice as part of exception processing, you can click this button to create the pending invoice.</span></span> <span data-ttu-id="a946d-196">Väntande fakturor skapas i bakgrunden (som en asynkron åtgärd).</span><span class="sxs-lookup"><span data-stu-id="a946d-196">The creation of pending invoices occurs in the background (as an asynchronous operation).</span></span>

### <a name="shared-service-vs-organization-based-exception-processing"></a><span data-ttu-id="a946d-197">Delad tjänst i förhållande till organisationsbaserad hantering av undantag</span><span class="sxs-lookup"><span data-stu-id="a946d-197">Shared service vs. organization-based exception processing</span></span>

<span data-ttu-id="a946d-198">Sidan med en lista över undantag stöder standardsäkerhetskonstruktioner som arbetsytan **Datahantering** stöder för behandling av mellanlagringsposter.</span><span class="sxs-lookup"><span data-stu-id="a946d-198">The exceptions list page supports the standard security constructs that the **Data management** workspace supports for the processing of staging records.</span></span> <span data-ttu-id="a946d-199">Importen av fakturan kan skyddas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a946d-199">The invoice import job can be secured in the following ways:</span></span>

+ <span data-ttu-id="a946d-200">Efter användarroll</span><span class="sxs-lookup"><span data-stu-id="a946d-200">By user role</span></span>
+ <span data-ttu-id="a946d-201">Efter användare</span><span class="sxs-lookup"><span data-stu-id="a946d-201">By user</span></span>
+ <span data-ttu-id="a946d-202">Efter juridisk person</span><span class="sxs-lookup"><span data-stu-id="a946d-202">By legal entity</span></span>

![Importjobb som skyddas av användarroll och juridisk person](media/vendor_invoice_automation_04.png)

<span data-ttu-id="a946d-204">Om skydd konfigureras för importen av fakturan, godkänner sidan med listan över undantag dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="a946d-204">If security is configured for the invoice import job, the exceptions list page honors those settings.</span></span> <span data-ttu-id="a946d-205">Användarna kommer enbart att kunna visa de undantagsposter för fakturan som den här inställningen tillåter.</span><span class="sxs-lookup"><span data-stu-id="a946d-205">Users will be able to see only the invoice exception records that this setup allows them to see.</span></span>

<span data-ttu-id="a946d-206">Exempelvis har Contoso beslutat att bearbeta fakturaundantag efter juridisk person.</span><span class="sxs-lookup"><span data-stu-id="a946d-206">For example, Contoso has decided to process invoice exceptions by legal entity.</span></span> <span data-ttu-id="a946d-207">Därför konfigureras skyddet för importen av fakturan så att en användare som är en juridisk person A ser undantag för fakturan i juridisk person A, medan en användare som är juridisk person B enbart ser fakturaundantag i den juridiska personen B. Denna inställning möjliggör ansvarsfördelning för hantering av undantag för fakturan.</span><span class="sxs-lookup"><span data-stu-id="a946d-207">Therefore, security is configured on the invoice import job in such a way that a user in legal entity A can see only invoice exceptions in legal entity A, whereas a user in legal entity B can see only invoice exceptions in legal entity B. This setup enables segregation of duties for the management of invoice exceptions.</span></span>

<span data-ttu-id="a946d-208">Contoso kan även bestämma sig för att inte tillämpa något skydd, så att samma användare kan bearbeta fakturaundantag för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="a946d-208">Contoso could also decide not to enforce any security, so that the same users can process invoice exceptions for all legal entities.</span></span> <span data-ttu-id="a946d-209">Denna inställning möjliggör ett scenario med delade tjänster för hantering av fakturaundantag.</span><span class="sxs-lookup"><span data-stu-id="a946d-209">This setup enables a shared services scenario for the management of invoice exceptions.</span></span>

## <a name="side-by-side-attachment-viewer"></a><span data-ttu-id="a946d-210">Visningsprogram för sida-vid-sida-bilaga</span><span class="sxs-lookup"><span data-stu-id="a946d-210">Side-by-side attachment viewer</span></span>

<span data-ttu-id="a946d-211">För att du snabbt ska kunna visa bilagor till leverantörsfakturor innehåller följande sidor, som används i faktureringsprocessen, nu ett visningsprogram för bilagor:</span><span class="sxs-lookup"><span data-stu-id="a946d-211">To help you easily view the attachments for vendor invoices, the following pages that are used in the invoicing process now provide an attachment viewer:</span></span>

+ <span data-ttu-id="a946d-212">**Hantering av undantag**</span><span class="sxs-lookup"><span data-stu-id="a946d-212">**Exception handling**</span></span>
+ <span data-ttu-id="a946d-213">**Väntande leverantörsfakturor** sida (även tillgänglig i processen för granskning av fakturan)</span><span class="sxs-lookup"><span data-stu-id="a946d-213">**Pending vendor invoices** page (also available in the invoice review process)</span></span>
+ <span data-ttu-id="a946d-214">**Fakturajournal** sida för förfrågan (för bokförda fakturor)</span><span class="sxs-lookup"><span data-stu-id="a946d-214">**Invoice journal** inquiry page (for posted invoices)</span></span>

<span data-ttu-id="a946d-215">Här är huvudfunktionerna i visningsprogrammet för bilagor:</span><span class="sxs-lookup"><span data-stu-id="a946d-215">Here is the main functionality that the attachment viewer provides:</span></span>

+ <span data-ttu-id="a946d-216">Visa alla bilagstyper som stöds av Dokumenthantering (filer, bilder, URL-adresser och anteckningar).</span><span class="sxs-lookup"><span data-stu-id="a946d-216">View all attachment types that Document management supports (files, images, URLs, and notes).</span></span>
+ <span data-ttu-id="a946d-217">Visa flersidiga TIFF-filer.</span><span class="sxs-lookup"><span data-stu-id="a946d-217">View multi-page TIFF files.</span></span>
+ <span data-ttu-id="a946d-218">Utföra följande åtgärder på bildfiler:</span><span class="sxs-lookup"><span data-stu-id="a946d-218">Perform the following actions on image files:</span></span>
  + <span data-ttu-id="a946d-219">Markera delar av bilden.</span><span class="sxs-lookup"><span data-stu-id="a946d-219">Highlight parts of the image.</span></span>
  + <span data-ttu-id="a946d-220">Blockera delar av bilden.</span><span class="sxs-lookup"><span data-stu-id="a946d-220">Block parts of the image.</span></span>
  + <span data-ttu-id="a946d-221">Lägga till anteckningar till bilden.</span><span class="sxs-lookup"><span data-stu-id="a946d-221">Add annotations to the image.</span></span>
  + <span data-ttu-id="a946d-222">Zooma in eller ut i bilden.</span><span class="sxs-lookup"><span data-stu-id="a946d-222">Zoom in and out on the image.</span></span>
  + <span data-ttu-id="a946d-223">Panorera bilden.</span><span class="sxs-lookup"><span data-stu-id="a946d-223">Pan the image.</span></span>
  + <span data-ttu-id="a946d-224">Ångra och göra om åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a946d-224">Undo and redo actions.</span></span>
  + <span data-ttu-id="a946d-225">Anpassa bilden till storlek.</span><span class="sxs-lookup"><span data-stu-id="a946d-225">Fit the image to size.</span></span>

> [!NOTE]
> <span data-ttu-id="a946d-226">Dessa åtgärder är bara tillgängliga för bildfiler (JPEG, TIFF, PNG och så vidare).</span><span class="sxs-lookup"><span data-stu-id="a946d-226">These actions are available only for image files (JPEG, TIFF, PNG, and so on).</span></span> <span data-ttu-id="a946d-227">Alla ändringar som du gör i en bild med hjälp av dessa åtgärder sparas i bildfilen.</span><span class="sxs-lookup"><span data-stu-id="a946d-227">Any changes that you make to an image by using these actions are saved to the image file.</span></span> <span data-ttu-id="a946d-228">För närvarande inkluderar visningsprogrammet för bilagor inte versionshantering eller granskning av funktioner.</span><span class="sxs-lookup"><span data-stu-id="a946d-228">Currently, the attachment viewer doesn’t include versioning or auditing capabilities.</span></span>

### <a name="default-attachment"></a><span data-ttu-id="a946d-229">Standardbilaga</span><span class="sxs-lookup"><span data-stu-id="a946d-229">Default attachment</span></span>

<span data-ttu-id="a946d-230">Om en leverantörsfaktura har fler än en bilaga kan du ställa in ett av dokumenten som standardbilaga på sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="a946d-230">If a vendor invoice has more than one attachment, you can set one of the documents as the default attachment on the **Attachments** page.</span></span> <span data-ttu-id="a946d-231">Alternativet **Standardbilaga** är ett nytt alternativ som har lagts till som en del av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a946d-231">The **Is default attachment** option is a new option that was added as part of this feature.</span></span> <span data-ttu-id="a946d-232">Det här alternativet visas också i dataenheten för leverantörsfakturans dokumentbilaga.</span><span class="sxs-lookup"><span data-stu-id="a946d-232">This option is also exposed in the Vendor invoice document attachment data entity.</span></span> <span data-ttu-id="a946d-233">Standardbilagan kan därför ställas in via integrering.</span><span class="sxs-lookup"><span data-stu-id="a946d-233">Therefore, the default attachment can be set through integrations.</span></span>

<span data-ttu-id="a946d-234">Endast ett dokument kan anges som standardbilaga.</span><span class="sxs-lookup"><span data-stu-id="a946d-234">Only one document can be set as the default attachment.</span></span> <span data-ttu-id="a946d-235">När du har angett ett dokument som standardbilaga visas det automatiskt i visningsprogrammet för bilagor när fakturan öppnas.</span><span class="sxs-lookup"><span data-stu-id="a946d-235">After you set a document as the default attachment, it’s automatically shown in the attachment viewer when the invoice is opened.</span></span> <span data-ttu-id="a946d-236">Om du inte anger ett dokument som standardbilaga visar visningsprogrammet för bilagor automatiskt vilken bilaga som helst när fakturan öppnas.</span><span class="sxs-lookup"><span data-stu-id="a946d-236">If you don’t set any document as the default attachment, the viewer doesn’t automatically show any attachment when the invoice is opened.</span></span>

### <a name="showhide-invoice-attachments"></a><span data-ttu-id="a946d-237">Visa/dölj fakturabilagor</span><span class="sxs-lookup"><span data-stu-id="a946d-237">Show/hide invoice attachments</span></span>

<span data-ttu-id="a946d-238">Med hjälp av en ny knapp på förfrågningssidan **Bearbetning av undantag**, **Väntande faktura** och **Fakturajournal** kan du visa eller dölja visningsprogrammet för bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-238">A new button that is available on the **Exception processing**, **Pending invoice**, and **Invoice journal** inquiry pages lets you show or hide the attachment viewer.</span></span>

### <a name="security"></a><span data-ttu-id="a946d-239">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="a946d-239">Security</span></span>

<span data-ttu-id="a946d-240">Följande åtgärder i visningsprogrammet för bilagor styrs via rollbaserad säkerhet:</span><span class="sxs-lookup"><span data-stu-id="a946d-240">The following actions in the attachment viewer are controlled via role-based security:</span></span>

+ <span data-ttu-id="a946d-241">Markera</span><span class="sxs-lookup"><span data-stu-id="a946d-241">Highlighting</span></span>
+ <span data-ttu-id="a946d-242">Spärra</span><span class="sxs-lookup"><span data-stu-id="a946d-242">Block</span></span>
+ <span data-ttu-id="a946d-243">Anteckning</span><span class="sxs-lookup"><span data-stu-id="a946d-243">Annotation</span></span>

### <a name="pending-vendor-invoices-page"></a><span data-ttu-id="a946d-244">Sida för väntande leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="a946d-244">Pending vendor invoices page</span></span>

<span data-ttu-id="a946d-245">Följande behörigheter tillåter skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-245">The following privileges provide ready-only access or read/write access to the attachment viewer for the highlighting, block, and annotation actions:</span></span>

+ <span data-ttu-id="a946d-246">**Underhålla bilden på leverantörsfakturan** – denna behörighet ger läs/skriv-behörighet.</span><span class="sxs-lookup"><span data-stu-id="a946d-246">**Maintain vendor invoice image** – This privilege provides read/write access.</span></span>
+ <span data-ttu-id="a946d-247">**Visa bilden på leverantörsfakturan** – denna behörighet ger enbart läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="a946d-247">**View vendor invoice image** – This privilege provides read-only access.</span></span>

<span data-ttu-id="a946d-248">Följande arbetsuppgifter ger skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-248">The following duties provide read-only access or read/write access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a946d-249">**Underhålla leverantörsfakturor** – behörighet för bilden på leverantörsfakturan tilldelas denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="a946d-249">**Maintain vendor invoices** – The Maintain vendor invoice image privilege is assigned to this duty.</span></span>
+ <span data-ttu-id="a946d-250">**Fråga om status på leverantörsfaktura** – behörighet för att visa bilden på leverantörsfakturan tilldelas denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="a946d-250">**Inquire into vendor invoice status** – The View vendor invoice image privilege is assigned to this duty.</span></span>

<span data-ttu-id="a946d-251">Följande roller ger skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-251">The following roles provide read-only access or read/write access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a946d-252">**Ansvarig för leverantörsreskontra** och **Chef för leverantörsreskontra** – underhålla leverantörsfakturor har tilldelats dessa roller.</span><span class="sxs-lookup"><span data-stu-id="a946d-252">**Accounts payable clerk** and **Accounts payable manager** – The Maintain vendor invoices duty is assigned to these roles.</span></span>
+ <span data-ttu-id="a946d-253">**Ansvarig för leverantörsreskontra**, **Chef för leverantörsreskontra**, **Ansvarig för centraliserade leverantörsreskontrabetalningar** och **Ansvarig för leverantörsreskontrabetalningar** – uppgiften Fråga om status på leverantörsfaktura har tilldelats dessa roller.</span><span class="sxs-lookup"><span data-stu-id="a946d-253">**Accounts payable clerk**, **Accounts payable manager**, **Accounts payable centralized payments clerk**, and **Accounts payable payments clerk** – The Inquire into vendor invoice status duty is assigned to these roles.</span></span>

### <a name="invoice-exception-details-page"></a><span data-ttu-id="a946d-254">Informationssida för fakturaundantag</span><span class="sxs-lookup"><span data-stu-id="a946d-254">Invoice exception details page</span></span>

<span data-ttu-id="a946d-255">Följande behörigheter tillåter skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a946d-255">The following privileges provide ready-only access or read/write access to the attachment viewer for the highlighting, block, and annotation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="a946d-256">Rollerna som nämns i det här avsnittet tillåter skrivskyddad åtkomst till bilderna på fakturan i visningsprogrammet för bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-256">Out of the box, the roles that are mentioned in this section provide read-only access to the invoice images in the attachment viewer.</span></span> <span data-ttu-id="a946d-257">Om en roll även måste ha skrivbehörighet för bilderna kan du bevilja skrivåtkomst till rollen med hjälp av den behörighet och den uppgift som beskrivs här.</span><span class="sxs-lookup"><span data-stu-id="a946d-257">If a role must also have write access to the images, you can grant write access to that role by using the privilege and duty that are described here.</span></span>

+ <span data-ttu-id="a946d-258">**Underhålla bild av enhet för leverantörsfakturarubrik** – denna behörighet ger full åtkomst till fakturabilderna i visningsprogrammet för bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-258">**Maintain vendor invoice header entity image** – This privilege provides read/write access to the invoice images in the attachment viewer.</span></span>
+ <span data-ttu-id="a946d-259">**Visa bild av enhet för leverantörsfakturarubrik** – denna behörighet ger skrivskyddad åtkomst till fakturabilderna i visningsprogrammet för bilagor.</span><span class="sxs-lookup"><span data-stu-id="a946d-259">**View vendor invoice header entity image** – This privilege provides read-only view to the invoice image in the attachment viewer.</span></span>

<span data-ttu-id="a946d-260">Följande arbetsuppgifter ger skrivskyddad åtkomst till visningsprogrammet för bilagor för dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-260">The following duties provide read-only access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a946d-261">**Underhålla leverantörsfakturor** – behörighet för att underhålla bilden på leverantörsfakturan är tilldelad denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="a946d-261">**Maintain vendor invoices** – The Maintain vendor invoice header entity image privilege is assigned to this duty.</span></span>

<span data-ttu-id="a946d-262">Följande roller ger skrivskyddad åtkomst till visningsprogrammet för bilagor för dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a946d-262">The following roles provide read-only access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a946d-263">**Ansvarig för leverantörsreskontra** och **Chef för leverantörsreskontra** – underhålla leverantörsfakturor har tilldelats dessa roller.</span><span class="sxs-lookup"><span data-stu-id="a946d-263">**Accounts payable clerk** and **Accounts payable manager** – The Maintain vendor invoices duty is assigned to these roles.</span></span>

<span data-ttu-id="a946d-264">Som standard, om användarrollen ger redigeringsrättigheter på valfri sida, har användaren även redigeringsrättigheter i visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a946d-264">By default, if the user role provides edit rights on any page, the user will also have edit rights on the attachments viewer for the highlighting, block, and annotation actions.</span></span> <span data-ttu-id="a946d-265">Om scenarier där en viss roll bör ha redigeringsrättigheter på sidan men inte i visningsprogrammet för bilagor kan behörighet i ovanstående lista användas i detta användningsfall.</span><span class="sxs-lookup"><span data-stu-id="a946d-265">However, if there are scenarios where a specific role should have edit rights on the page but not on the attachment viewer, the appropriate privileges from the preceding list can be used to satisfy the use case.</span></span>

