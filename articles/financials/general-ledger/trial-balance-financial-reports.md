---
title: Ekonomiska råbalansrapporter
description: Den här artikeln beskriver standardrapporter för råbalanser. Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9e8c16724364df4dd62150056299e818470aa63
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553701"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="cd258-104">Ekonomiska råbalansrapporter</span><span class="sxs-lookup"><span data-stu-id="cd258-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd258-105">Den här artikeln beskriver standardrapporter för råbalanser.</span><span class="sxs-lookup"><span data-stu-id="cd258-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="cd258-106">Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov.</span><span class="sxs-lookup"><span data-stu-id="cd258-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="cd258-107">Standardrapporter för råbalans</span><span class="sxs-lookup"><span data-stu-id="cd258-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="cd258-108">Tre råbalansrapporter är tillgängliga i ekonomisk rapportering i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cd258-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations.</span></span>

| <span data-ttu-id="cd258-109">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="cd258-109">Default report</span></span>                                 | <span data-ttu-id="cd258-110">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="cd258-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cd258-111">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="cd258-112">Visar saldoinformation för alla konton med och inkluderar debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="cd258-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="cd258-113">Råbalanssammanfattning - standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="cd258-114">Visar information om saldo för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.</span><span class="sxs-lookup"><span data-stu-id="cd258-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="cd258-115">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="cd258-116">Visar saldoinformation för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år.</span><span class="sxs-lookup"><span data-stu-id="cd258-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="cd258-117">Byggstenar</span><span class="sxs-lookup"><span data-stu-id="cd258-117">Building blocks</span></span>
<span data-ttu-id="cd258-118">Råbalansrapporterna använder följande byggstenar.</span><span class="sxs-lookup"><span data-stu-id="cd258-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="cd258-119">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="cd258-119">Default report</span></span>                                 | <span data-ttu-id="cd258-120">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="cd258-120">Row definition</span></span>          | <span data-ttu-id="cd258-121">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="cd258-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="cd258-122">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="cd258-123">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-123">Trial Balance - Default</span></span> | <span data-ttu-id="cd258-124">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="cd258-125">Råbalanssammanfattning - standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="cd258-126">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-126">Trial Balance - Default</span></span> | <span data-ttu-id="cd258-127">Råbalanssammanfattning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="cd258-128">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="cd258-129">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-129">Trial Balance - Default</span></span> | <span data-ttu-id="cd258-130">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="cd258-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="cd258-131">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="cd258-131">Row definition</span></span>

<span data-ttu-id="cd258-132">Raddefinitionen Råbalans – standard innehåller en rad som tar emot alla huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="cd258-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="cd258-133">Därför kan alla generera rapporten, utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="cd258-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="cd258-134">När du visar rapporten borrar du till enskild rad om du vill se information om varje konto.</span><span class="sxs-lookup"><span data-stu-id="cd258-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="cd258-135">Du kan ändra raddefinitionen så att den innehåller mer information.</span><span class="sxs-lookup"><span data-stu-id="cd258-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="cd258-136">Om du vill ändra Råbalans – standardinställning så att den innehåller rader för alla konton, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cd258-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="cd258-137">Klicka på **Redigera** och sedan på **Infoga rader från dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="cd258-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="cd258-138">Kommandot **Infoga rader från dimensioner** gör att du kan välja dimensionerna du vill ha i raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cd258-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="cd258-139">För den här raddefinitionen ska du använda **Huvudkonto**.</span><span class="sxs-lookup"><span data-stu-id="cd258-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="cd258-140">Se till att **Huvudkonto** bara innehåller et-tecken och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd258-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="cd258-141">Raddefinitionen innehåller nu alla huvudkonton för din juridiska standardperson.</span><span class="sxs-lookup"><span data-stu-id="cd258-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="cd258-142">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="cd258-142">Column definition</span></span>

<span data-ttu-id="cd258-143">Alla råbalansrapporter använder olika kolumndefinitioner.</span><span class="sxs-lookup"><span data-stu-id="cd258-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="cd258-144">Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="cd258-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="cd258-145">**Detaljerad råbalans – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="cd258-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="cd258-146">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cd258-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="cd258-147">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="cd258-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="cd258-148">**ATTR (3)** – attribut:</span><span class="sxs-lookup"><span data-stu-id="cd258-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="cd258-149">Transaktionsdatum</span><span class="sxs-lookup"><span data-stu-id="cd258-149">Transaction Date</span></span>
        -   <span data-ttu-id="cd258-150">Verifikation</span><span class="sxs-lookup"><span data-stu-id="cd258-150">Voucher</span></span>
        -   <span data-ttu-id="cd258-151">Journalbeskrivning</span><span class="sxs-lookup"><span data-stu-id="cd258-151">Journal Description</span></span>
    -   <span data-ttu-id="cd258-152">**FD** – ekonomisk data som bara innehåller debet</span><span class="sxs-lookup"><span data-stu-id="cd258-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="cd258-153">**FD** – ekonomisk data som bara innehåller kredit</span><span class="sxs-lookup"><span data-stu-id="cd258-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="cd258-154">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="cd258-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="cd258-155">**Råbalanssammanfattning – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="cd258-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="cd258-156">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="cd258-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="cd258-157">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cd258-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="cd258-158">**ATTR** – ett attribut:</span><span class="sxs-lookup"><span data-stu-id="cd258-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="cd258-159">Verifikation</span><span class="sxs-lookup"><span data-stu-id="cd258-159">Voucher</span></span>
    -   <span data-ttu-id="cd258-160">**FD** – den ingående balansen</span><span class="sxs-lookup"><span data-stu-id="cd258-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="cd258-161">**FD** – ekonomisk data som bara innehåller debet</span><span class="sxs-lookup"><span data-stu-id="cd258-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="cd258-162">**FD** – ekonomisk data som bara innehåller kredit</span><span class="sxs-lookup"><span data-stu-id="cd258-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="cd258-163">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="cd258-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="cd258-164">**CALC** – den utgående balansen</span><span class="sxs-lookup"><span data-stu-id="cd258-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="cd258-165">**Summerad råbalans på årsbasis – standardinställning:**</span><span class="sxs-lookup"><span data-stu-id="cd258-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="cd258-166">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="cd258-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="cd258-167">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cd258-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="cd258-168">**ATTR** – ett attribut</span><span class="sxs-lookup"><span data-stu-id="cd258-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="cd258-169">Verifikation</span><span class="sxs-lookup"><span data-stu-id="cd258-169">Voucher</span></span>
    -   <span data-ttu-id="cd258-170">**FD** – den ingående balansen för det innevarande året</span><span class="sxs-lookup"><span data-stu-id="cd258-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="cd258-171">**FD** – ekonomisk data som bara innehåller debet för innevarande året</span><span class="sxs-lookup"><span data-stu-id="cd258-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="cd258-172">**FD** – ekonomisk data som bara innehåller kredit för innevarande året</span><span class="sxs-lookup"><span data-stu-id="cd258-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="cd258-173">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="cd258-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="cd258-174">**CALC** – den utgående balansen</span><span class="sxs-lookup"><span data-stu-id="cd258-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="cd258-175">**FD** – ekonomisk data som bara innehåller debet för det senaste året</span><span class="sxs-lookup"><span data-stu-id="cd258-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="cd258-176">**FD** – ekonomisk data som bara innehåller kredit för det senaste året</span><span class="sxs-lookup"><span data-stu-id="cd258-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="cd258-177">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cd258-177">Additional resources</span></span>
--------

[<span data-ttu-id="cd258-178">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="cd258-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="cd258-179">Visa ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="cd258-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="cd258-180">Dynamics-ekonomirapporteringsblogg</span><span class="sxs-lookup"><span data-stu-id="cd258-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)



