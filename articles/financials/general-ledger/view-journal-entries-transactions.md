---
title: Visa journalposter och transaktioner
description: "Det här avsnittet innehåller information om de olika sätten att visa journalposter och transaktioner."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fda51a8382cb7d8a9aa7392224486189c442550f
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="view-journal-entries-and-transactions"></a><span data-ttu-id="1f9a5-103">Visa journalposter och transaktioner</span><span class="sxs-lookup"><span data-stu-id="1f9a5-103">View journal entries and transactions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1f9a5-104">Det här avsnittet innehåller information om de olika sätten att visa journalposter och transaktioner.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-104">This article explains the various ways that you can view journal entries and transactions.</span></span> 

<span data-ttu-id="1f9a5-105">Användare som vill visa journaler och transaktioner kan göra det på flera sätt.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-105">Users who want to view journals and transactions have several ways to access the data.</span></span> <span data-ttu-id="1f9a5-106">De kan använda förfrågningssidor som innehåller vidaresökningsmöjligheter eller också kan de använda olika rapportalternativ i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-106">They can take advantage of inquiry pages that provide drill-down ability, or they can use various report options in the general ledger.</span></span>

## <a name="voucher-transactions"></a><span data-ttu-id="1f9a5-107">Verifikationstransaktioner</span><span class="sxs-lookup"><span data-stu-id="1f9a5-107">Voucher transactions</span></span>
<span data-ttu-id="1f9a5-108">**Verifikationstransaktioner** är en förfrågningssida där du kan välja bland olika register och fält för att ange villkor för saldot eller transaktionen som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-108">**Voucher transactions** is an inquiry page where you can select from various tables and fields to specify criteria for the balance or transaction that you're searching for.</span></span> <span data-ttu-id="1f9a5-109">Du kan till exempel visa alla transaktioner för ett visst datum eller konto eller alla transaktioner av typen **Pågående** som är i ett visst bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-109">For example, you can view all transactions for a specific date or account, or all transactions of the **Operating** type that are in a specific posting layer.</span></span> <span data-ttu-id="1f9a5-110">Som standard visar sidan journalnumret, verifikationen, datumet och huvudkontot, men du kan lägga till ytterligare register, fält och kriterier för att begränsa sökningen.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-110">By default, the page shows the journal number, voucher, date, and main account, but you can add additional tables, fields, and criteria to narrow down your search.</span></span>

## <a name="audit-trail"></a><span data-ttu-id="1f9a5-111">Redovisningsspårning</span><span class="sxs-lookup"><span data-stu-id="1f9a5-111">Audit trail</span></span>
<span data-ttu-id="1f9a5-112">**Redovisningsspårning** är en förfrågningssida som visar transaktionstyperna, beskrivningarna, vem som skapade transaktionerna och när de skapades.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-112">**Audit trail** is an inquiry page that shows the types of transactions, descriptions, who the transactions were created by, and when they were created.</span></span> <span data-ttu-id="1f9a5-113">Från sidan **Redovisningsspårning** kan du visa verifikationstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-113">From the **Audit trail** inquiry page, you can view the voucher transactions.</span></span>

## <a name="financial-reports"></a><span data-ttu-id="1f9a5-114">Ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="1f9a5-114">Financial reports</span></span>
<span data-ttu-id="1f9a5-115">Du kan även undersöka och analysera redovisningstransaktioner genom att köra ekonomiska rapporter.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-115">You can also explore and analyze general ledger transactions by running financial reports.</span></span> <span data-ttu-id="1f9a5-116">Eftersom designen av ekonomiska kan baseras på konton, dimensioner, kontokategorier eller en kombination av dessa tre, kan du visa transaktioner genom att söka vidare på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-116">Because the design of financial reports can be based on accounts, dimensions, account categories, or a combination of the three, you can view the transactions by drilling down in various ways.</span></span> <span data-ttu-id="1f9a5-117">Om du behöver mer information för redovisningstransaktioner, kan du också inkludera flera transaktionsegenskaper i rapportdesignen.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-117">If you require more information for general ledger transactions, you can also include multiple transaction properties as part of the report design.</span></span> <span data-ttu-id="1f9a5-118">Dessutom kan du om du vill visa transaktionerna som utgör ett redovisningssaldo kan du söka nedåt till kontotransaktioner, på samma sätt som du kan från sidan **Råbalans**.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-118">Additionally, if you want to see the transactions that make up a general ledger balance, you can drill down to account transactions, just as you can from the **Trial balance** list page.</span></span>

## <a name="ledger-reports"></a><span data-ttu-id="1f9a5-119">Redovisningsrapporter</span><span class="sxs-lookup"><span data-stu-id="1f9a5-119">Ledger reports</span></span>
<span data-ttu-id="1f9a5-120">Förutom ekonomiska rapporter kan du använda följande redovisningsrapporter om du vill visa redovisningstransaktioner:</span><span class="sxs-lookup"><span data-stu-id="1f9a5-120">In addition to the financial reports, you can use the following ledger reports to view general ledger transactions:</span></span>

-   <span data-ttu-id="1f9a5-121">**Dimensionsutdrag** – Den här rapporten visar transaktioner per dag och konto, och det finns också alternativ för att kunna visa transaktioner per dimension och period.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-121">**Dimension statement** – This report shows transactions by day and account, and there are also options to show transactions by dimension and period.</span></span>
-   <span data-ttu-id="1f9a5-122">**Redovisningstransaktionslista** – Den här rapporten visar transaktioner i transaktionsvalutan, redovisningsvalutan och rapporteringsvalutan på ett konto.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-122">**Ledger transaction list** – This report shows transactions in transaction, accounting, and reporting currencies for an account.</span></span>
-   <span data-ttu-id="1f9a5-123">**Skriv ut journalen** – den här rapporten visar resultatet av en bokförd journal.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-123">**Print journal** – This report shows the result of a posted journal.</span></span> <span data-ttu-id="1f9a5-124">Du kan köra rapporten efter journalbatchnummer eller journaltyp eller lägga till ytterligare fält.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-124">You can run the report by journal batch number or journal type, or add additional fields.</span></span>
-   <span data-ttu-id="1f9a5-125">**Bokförda transaktioner per journal** – I rapporten visas transaktionerna som har bokförts i en journal grupperade efter verifikation.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-125">**Posted transactions by journal** – This report shows the transactions that have been posted to a journal, grouped by voucher.</span></span>
-   <span data-ttu-id="1f9a5-126">**Transaktionslista efter datum** – Den här rapporten visar alla transaktioner per datum, tillsammans med journalnummer, verifikation och redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-126">**Transaction list by date** – This report shows all the transactions by date, together with the journal number, voucher, and ledger account.</span></span> <span data-ttu-id="1f9a5-127">Den visar också transaktionerna i transaktionsvalutan, kontovalutan och rapporteringsvalutan.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-127">It also shows the transactions in the transaction, accounting, and reporting currencies.</span></span>
-   <span data-ttu-id="1f9a5-128">**Transaktionsursprung** – Den här transaktionsrapporten visar konto efter journal och efter transaktionsvalutan, kontovalutan och rapporteringsvalutan.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-128">**Transaction origin** – This transaction report shows the account by journal, and by transaction, accounting, and reporting currency.</span></span> <span data-ttu-id="1f9a5-129">Den visar också varje rad i journalen som användes som avräkning.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-129">It also shows each line of the journal that was used as an offset.</span></span>


##<a name="see-also"></a><span data-ttu-id="1f9a5-130">Se även</span><span class="sxs-lookup"><span data-stu-id="1f9a5-130">See also</span></span>
- [<span data-ttu-id="1f9a5-131">Kontosaldon i redovisningskontot</span><span class="sxs-lookup"><span data-stu-id="1f9a5-131">General ledger account balances</span></span>](general-ledger-account-balances.md) 
- [<span data-ttu-id="1f9a5-132">Utforskare för redovisningskälla</span><span class="sxs-lookup"><span data-stu-id="1f9a5-132">Accounting source explorer</span></span>](..\accounts-payable\accounting-source-explorer.md)
- [<span data-ttu-id="1f9a5-133">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1f9a5-133">Financial reporting</span></span>](financial-reporting-getting-started.md)
- [<span data-ttu-id="1f9a5-134">Visa journalposter</span><span class="sxs-lookup"><span data-stu-id="1f9a5-134">View journal entries</span></span>](tasks/view-journal-entries-or-transactions.md)




