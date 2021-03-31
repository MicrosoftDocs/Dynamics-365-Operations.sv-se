---
title: Registrera en leverantörsfaktura i fakturajournalen
description: Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a60a5959046ca9e953bac80aaeb382d07a267643
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227146"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="094d9-103">Registrera en leverantörsfaktura i fakturajournalen</span><span class="sxs-lookup"><span data-stu-id="094d9-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="094d9-104">Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="094d9-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="094d9-105">Exempel på den här typen av faktura omfattar utgifter för förrådsartiklar och tjänster.</span><span class="sxs-lookup"><span data-stu-id="094d9-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="094d9-106">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="094d9-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="094d9-107">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Arbetsytor > Leverantörsfakturapost**.</span><span class="sxs-lookup"><span data-stu-id="094d9-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="094d9-108">Klicka på **Ny fakturajournal** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="094d9-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="094d9-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="094d9-109">Click **New**.</span></span>
4. <span data-ttu-id="094d9-110">Ange journalnamnet eller klicka på den nedrullningsbara knappen i fältet **Namn** för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="094d9-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="094d9-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="094d9-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="094d9-112">Klicka på **Rader** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="094d9-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="094d9-113">Ange bokföringsdatum som ska uppdatera redovisningen i fältet **Datum**.</span><span class="sxs-lookup"><span data-stu-id="094d9-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="094d9-114">Ange **leverantörskontot** i fältet **Konto**.</span><span class="sxs-lookup"><span data-stu-id="094d9-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="094d9-115">Ange fakturanumret i fältet **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="094d9-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="094d9-116">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="094d9-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="094d9-117">I fältet **Kredit** väljer du ett tal.</span><span class="sxs-lookup"><span data-stu-id="094d9-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="094d9-118">Ange kontonumret  eller klicka på den nedrullningsbara knappen i fältet **motkonto** för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="094d9-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="094d9-119">**Momsgruppen** får sin standard från leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="094d9-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="094d9-120">**Artikelmomsgruppen** får sin standard från huvudkontot som anges i fältet **motkonto**.</span><span class="sxs-lookup"><span data-stu-id="094d9-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="094d9-121">**Förfallodatumet** beräknas utifrån betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="094d9-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="094d9-122">**Kassarabatt** får sin standard från leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="094d9-122">The **Cash discount** will default from the Vendor account.</span></span>
12. <span data-ttu-id="094d9-123">Om du har aktiverat arbetsflöde för leverantörsfakturajournal klickar du på **Arbetsflöde > Skicka**.</span><span class="sxs-lookup"><span data-stu-id="094d9-123">If you have enabled Vendor invoice journal workflow, click **Workflow > Submit**.</span></span>
    * <span data-ttu-id="094d9-124">När det inskickade materialet godkänns kommer datumet att tidigareläggas till den första dagen i nästa öppna period om transaktionens bokföringsdatum infaller inom en period som har stoppats eller stängts för redovisningsbokföring.</span><span class="sxs-lookup"><span data-stu-id="094d9-124">When your submission is approved, the date will be advanced to the first day of the next open period, if the transaction posting date falls within a period that is On hold or Closed for ledger posting.</span></span>
12. <span data-ttu-id="094d9-125">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="094d9-125">Click **Post**.</span></span>
13. <span data-ttu-id="094d9-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="094d9-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]