---
title: Momsspecifikation per redovisningstransaktion (rapport)
description: I det här avsnittet beskrivs hur du använder rapporten Moms specifikation per redovisningstransaktion för att visa och skriva ut information om redovisningstransaktioner som moms beräknas för.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 75913edcbac0151d5d27d866ff5430b194c62738
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815270"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="a8b7f-103">Momsspecifikation per redovisningstransaktion (rapport)</span><span class="sxs-lookup"><span data-stu-id="a8b7f-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8b7f-104">I det här avsnittet beskrivs hur du använder rapporten **Moms specifikation per redovisningstransaktion** för att visa och skriva ut information om redovisningstransaktioner som moms beräknas för.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="a8b7f-105">Momskonton kontra icke-moms konton</span><span class="sxs-lookup"><span data-stu-id="a8b7f-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="a8b7f-106">Rapporten **Momsspecifikation per redovisningstransaktion** visas skattetransaktioner för både momskonton och icke-momskonton.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="a8b7f-107">Dessa konton kategoriseras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a8b7f-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="a8b7f-108">**Momskonto** – ett konto anses vara ett momskonto när en momstransaktion bokförs och huvudkontot på journalraden **moms** är ett momskonto, t.ex. ett konto för utgående moms eller ett konto för ingående moms.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="a8b7f-109">**Icke-momskonto** – ett konto anses vara ett icke-momskonto när en momstransaktion bokförs och huvudkontot på originaltransaktionen är ett journalraden icke-momskont, t.ex. ett intäktskonto eller ett utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="a8b7f-110">För skattekonton visar kolumnerna **Ursprung**, **Momsfordran** och **Momsskuld** på rapporten **0** (noll).</span><span class="sxs-lookup"><span data-stu-id="a8b7f-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="a8b7f-111">För icke-momskonton visas belopp i dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="a8b7f-112">Filtrera data i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-112">Filtering the data on the report</span></span>

<span data-ttu-id="a8b7f-113">När du genererar den här rapporten visas följande standardfält.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="a8b7f-114">Du kan använda dessa fält för att filtrera data som visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="a8b7f-115">Fält</span><span class="sxs-lookup"><span data-stu-id="a8b7f-115">Field</span></span>                      | <span data-ttu-id="a8b7f-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a8b7f-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="a8b7f-117">Datum</span><span class="sxs-lookup"><span data-stu-id="a8b7f-117">Date</span></span>                       | <span data-ttu-id="a8b7f-118">Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett datumintervall för momstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="a8b7f-119">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="a8b7f-119">Main account</span></span>               | <span data-ttu-id="a8b7f-120">Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett intervall för huvudkontona.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="a8b7f-121">Momskod</span><span class="sxs-lookup"><span data-stu-id="a8b7f-121">Sales tax code</span></span>             | <span data-ttu-id="a8b7f-122">Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett intervall för momskoder.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="a8b7f-123">Gruppering</span><span class="sxs-lookup"><span data-stu-id="a8b7f-123">Grouping</span></span>                   | <span data-ttu-id="a8b7f-124">Välj om rapporten ska grupperas efter redovisningskonto eller momskod.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="a8b7f-125">Delsumma efter momskod</span><span class="sxs-lookup"><span data-stu-id="a8b7f-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="a8b7f-126">Ställ in det här alternativet till **ja** om du vill visa delsummor efter momskod.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="a8b7f-127">Endast summor</span><span class="sxs-lookup"><span data-stu-id="a8b7f-127">Totals only</span></span>                | <span data-ttu-id="a8b7f-128">Ställ in det här alternativet till **ja** om du endast vill visa summor.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="a8b7f-129">Endast huvudkonton</span><span class="sxs-lookup"><span data-stu-id="a8b7f-129">Main accounts only</span></span>         | <span data-ttu-id="a8b7f-130">Ställ in det här alternativet till **ja** om du endast vill inkludera huvudkonton i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="a8b7f-131">Visa endast icke-momskonton i rapporten</span><span class="sxs-lookup"><span data-stu-id="a8b7f-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="a8b7f-132">Om du bara vill visa icke-momskonton i rapporten ställer du in ett filtervillkor, t.ex. en asterisk (\*), som visas på bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="a8b7f-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Rapporten visar icke-momskonton](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]