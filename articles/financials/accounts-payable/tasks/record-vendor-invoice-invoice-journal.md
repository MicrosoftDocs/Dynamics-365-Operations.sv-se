---
title: Registrera en leverantörsfaktura i fakturajournalen
description: Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556371"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="23bc6-103">Registrera en leverantörsfaktura i fakturajournalen</span><span class="sxs-lookup"><span data-stu-id="23bc6-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23bc6-104">Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="23bc6-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="23bc6-105">Exempel på den här typen av faktura omfattar utgifter för förrådsartiklar och tjänster.</span><span class="sxs-lookup"><span data-stu-id="23bc6-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="23bc6-106">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="23bc6-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="23bc6-107">Gå till Leverantörsreskontra > Arbetsytor > Leverantörsfakturaregistrering.</span><span class="sxs-lookup"><span data-stu-id="23bc6-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="23bc6-108">Klicka på Ny fakturajournal.</span><span class="sxs-lookup"><span data-stu-id="23bc6-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="23bc6-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23bc6-109">Click New.</span></span>
4. <span data-ttu-id="23bc6-110">Ange journalnamnet eller klicka på den nedrullningsbara knappen i fältet Namn för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="23bc6-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="23bc6-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="23bc6-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="23bc6-112">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="23bc6-112">Click Lines.</span></span>
    * <span data-ttu-id="23bc6-113">Ange bokföringsdatum som ska uppdatera redovisningen i datumfältet.</span><span class="sxs-lookup"><span data-stu-id="23bc6-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="23bc6-114">Ange leverantörskontot i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="23bc6-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="23bc6-115">Ange fakturanumret i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="23bc6-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="23bc6-116">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="23bc6-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="23bc6-117">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="23bc6-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="23bc6-118">Ange kontnumret eller klicka på den nedrullningsbara knappen i motkontofältet för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="23bc6-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="23bc6-119">Momsgruppen får sin standard från leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="23bc6-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="23bc6-120">Artikelmomsgruppen får sin standard från huvudkontot som anges i motkontofältet.</span><span class="sxs-lookup"><span data-stu-id="23bc6-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="23bc6-121">Förfallodatumet beräknas utifrån betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="23bc6-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="23bc6-122">Kassarabatt får sin standard från leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="23bc6-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="23bc6-123">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="23bc6-123">Click Post.</span></span>
13. <span data-ttu-id="23bc6-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23bc6-124">Close the page.</span></span>

