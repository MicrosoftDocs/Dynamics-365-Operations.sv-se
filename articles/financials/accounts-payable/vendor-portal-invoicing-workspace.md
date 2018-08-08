---
title: "Faktureringsarbetsyta för leverantörssamarbeten"
description: "Det här avsnittet beskriver hur du kan visa leverantörsfakturor och skicka fakturor från arbetsytan för leverantörssamarbetesfakturering."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5520012a00e918e8748b974773eeaf2450f0c55e
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="9b9c9-103">Faktureringsarbetsyta för leverantörssamarbeten</span><span class="sxs-lookup"><span data-stu-id="9b9c9-103">Vendor collaboration invoicing workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b9c9-104">Det här avsnittet beskriver hur du kan visa leverantörsfakturor och skicka fakturor från arbetsytan för leverantörssamarbetesfakturering.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="9b9c9-105">**Faktureringsarbetsyta för leverantörssamarbeten** kan användas för att visa information om leverantörsfaktura och skicka in fakturor till Microsoft Dynamics 365 for Finance and Operations med hjälp av arbetsflödesfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to Microsoft Dynamics 365 for Finance and Operations using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="9b9c9-106">Arbetsyta för leverantörssamarbetesfakturering</span><span class="sxs-lookup"><span data-stu-id="9b9c9-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="9b9c9-107">Sammanfattningsrutor</span><span class="sxs-lookup"><span data-stu-id="9b9c9-107">Summary tiles</span></span>

<span data-ttu-id="9b9c9-108">**Sammanfattningsrutorna** ger en översikt över fakturorna för den valda leverantören.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="9b9c9-109">Du kan visa fakturor med hjälp av deras läge.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="9b9c9-110">Utkastfakturor har inte skickats in till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="9b9c9-111">Skickade, ej godkända fakturor är de fakturor som leverantören har skickat, men som inte har bokförts i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in Finance and Operations.</span></span>
-   <span data-ttu-id="9b9c9-112">Godkända, ej betalda fakturor är de fakturor som har bokförts i Finance and Operations, men som inte ännu har betalats till fullo.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-112">Approved, not paid invoices are those that have been posted in Finance and Operations, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="9b9c9-113">Betalda fakturor är de fakturor som har betalats till fullo i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-113">Paid invoices are those that have been fully paid in Finance and Operations.</span></span>

<span data-ttu-id="9b9c9-114">Om du klickar på en ruta öppnas en filtrerad vy av listsidan **Fakturor**.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>

### <a name="tabular-lists"></a><span data-ttu-id="9b9c9-115">Tabellistor</span><span class="sxs-lookup"><span data-stu-id="9b9c9-115">Tabular lists</span></span>

<span data-ttu-id="9b9c9-116">I avsnittet **Tabellistor** är status för faktureringen uppdelad på liknande sätt som sammanfattningsrutorna: Utkast och Skickad, ej godkända listor.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="9b9c9-117">En faktura kan skickas till arbetsflödet eller tas bort när den befinner sig läget Utkast.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="9b9c9-118">Den sista tabellistan är ett alternativ för att hitta fakturor.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="9b9c9-119">Du kan filtrera medan du söker för att tillåta snabbare sökningar.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-119">You can filter as you search, to allow for faster searches.</span></span>

### <a name="all-vendor-invoices-list-page"></a><span data-ttu-id="9b9c9-120">Alla listsidor med leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="9b9c9-120">All vendor invoices list page</span></span>

<span data-ttu-id="9b9c9-121">Du kan visa alla bokförda och ej bokförda leverantörsfakturor på listsidan **Leverantörssamarbetesfakturor**.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="9b9c9-122">Du kan använda den här listsidan för att visa betalningsstatus för fakturor.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="9b9c9-123">Betalningsstatus omfattar Ej bokförd, Obetald, Delvis betald och Helt betald.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="9b9c9-124">Skapa en ny leverantörsfaktura från en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="9b9c9-124">Creating a new invoice from a purchase order</span></span>

<span data-ttu-id="9b9c9-125">Du kan skapa en ny leverantörsfaktura, genom att välja åtgärden **Ny** på **Faktureringsarbetsyta för leverantörssamarbete**.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="9b9c9-126">Inköpsordernumret och fakturanumret måste anges av leverantören.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="9b9c9-127">Som standard visas alla rader från leverantörens inköpsorder på den nya fakturan.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="9b9c9-128">Informationen om kvantitet och kostnad kan redigeras innan leverantörsfakturan skickas till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="9b9c9-129">Du kan bifoga filer, anteckningar, bilder och URL-adresser till en faktura, innan du skickar in den.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>

<span data-ttu-id="9b9c9-130">Mer information finns i [Samarbeten med externa leverantörer](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span><span class="sxs-lookup"><span data-stu-id="9b9c9-130">For more information, see [Vendor collaboration with external vendors](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span></span>




