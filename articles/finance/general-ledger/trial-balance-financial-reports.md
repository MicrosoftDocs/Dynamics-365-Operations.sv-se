---
title: Ekonomiska råbalansrapporter
description: Den här artikeln beskriver standardrapporter för råbalanser. Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103668"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="2903c-104">Ekonomiska råbalansrapporter</span><span class="sxs-lookup"><span data-stu-id="2903c-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2903c-105">Den här artikeln beskriver standardrapporter för råbalanser.</span><span class="sxs-lookup"><span data-stu-id="2903c-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="2903c-106">Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov.</span><span class="sxs-lookup"><span data-stu-id="2903c-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="2903c-107">Standardrapporter för råbalans</span><span class="sxs-lookup"><span data-stu-id="2903c-107">Default trial balance reports</span></span>

<span data-ttu-id="2903c-108">Tre råbalansrapporter är tillgängliga i ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="2903c-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="2903c-109">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="2903c-109">Default report</span></span>                                 | <span data-ttu-id="2903c-110">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="2903c-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2903c-111">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="2903c-112">Visar saldoinformation för alla konton med och inkluderar debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="2903c-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="2903c-113">Råbalanssammanfattning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="2903c-114">Visar information om saldo för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.</span><span class="sxs-lookup"><span data-stu-id="2903c-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="2903c-115">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="2903c-116">Visar saldoinformation för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år.</span><span class="sxs-lookup"><span data-stu-id="2903c-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="2903c-117">Byggstenar</span><span class="sxs-lookup"><span data-stu-id="2903c-117">Building blocks</span></span>
<span data-ttu-id="2903c-118">Råbalansrapporterna använder följande byggstenar.</span><span class="sxs-lookup"><span data-stu-id="2903c-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="2903c-119">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="2903c-119">Default report</span></span>                                 | <span data-ttu-id="2903c-120">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="2903c-120">Row definition</span></span>          | <span data-ttu-id="2903c-121">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="2903c-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="2903c-122">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="2903c-123">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-123">Trial Balance - Default</span></span> | <span data-ttu-id="2903c-124">Detaljerad råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="2903c-125">Råbalanssammanfattning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="2903c-126">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-126">Trial Balance - Default</span></span> | <span data-ttu-id="2903c-127">Råbalanssammanfattning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="2903c-128">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="2903c-129">Råbalans – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-129">Trial Balance - Default</span></span> | <span data-ttu-id="2903c-130">Summerad råbalans på årsbasis – standardinställning</span><span class="sxs-lookup"><span data-stu-id="2903c-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="2903c-131">När du kör rapporten **Råbalans** i Financial Reporting ska du markera kryssrutorna för **Visa rader utan belopp** och **Visa rapporter utan aktiva rader** på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2903c-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="2903c-132">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="2903c-132">Row definition</span></span>

<span data-ttu-id="2903c-133">Raddefinitionen Råbalans – standard innehåller en rad som tar emot alla huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="2903c-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="2903c-134">Därför kan alla generera rapporten, utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="2903c-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="2903c-135">När du visar rapporten borrar du till enskild rad om du vill se information om varje konto.</span><span class="sxs-lookup"><span data-stu-id="2903c-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="2903c-136">Du kan ändra raddefinitionen så att den innehåller mer information.</span><span class="sxs-lookup"><span data-stu-id="2903c-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="2903c-137">Om du vill ändra Råbalans – standardinställning så att den innehåller rader för alla konton, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2903c-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="2903c-138">Klicka på **Redigera** och sedan på **Infoga rader från dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="2903c-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="2903c-139">Kommandot **Infoga rader från dimensioner** gör att du kan välja dimensionerna du vill ha i raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="2903c-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="2903c-140">För den här raddefinitionen ska du använda **Huvudkonto**.</span><span class="sxs-lookup"><span data-stu-id="2903c-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="2903c-141">Se till att **Huvudkonto** bara innehåller et-tecken och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2903c-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="2903c-142">Raddefinitionen innehåller nu alla huvudkonton för din juridiska standardperson.</span><span class="sxs-lookup"><span data-stu-id="2903c-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="2903c-143">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="2903c-143">Column definition</span></span>

<span data-ttu-id="2903c-144">Alla råbalansrapporter använder olika kolumndefinitioner.</span><span class="sxs-lookup"><span data-stu-id="2903c-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="2903c-145">Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="2903c-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="2903c-146">**Detaljerad råbalans – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="2903c-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="2903c-147">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="2903c-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="2903c-148">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="2903c-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="2903c-149">**ATTR (3)** – attribut:</span><span class="sxs-lookup"><span data-stu-id="2903c-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="2903c-150">Transaktionsdatum</span><span class="sxs-lookup"><span data-stu-id="2903c-150">Transaction Date</span></span>
        -   <span data-ttu-id="2903c-151">Verifikation</span><span class="sxs-lookup"><span data-stu-id="2903c-151">Voucher</span></span>
        -   <span data-ttu-id="2903c-152">Journalbeskrivning</span><span class="sxs-lookup"><span data-stu-id="2903c-152">Journal Description</span></span>
    -   <span data-ttu-id="2903c-153">**FD** – ekonomisk data som bara innehåller debet</span><span class="sxs-lookup"><span data-stu-id="2903c-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="2903c-154">**FD** – ekonomisk data som bara innehåller kredit</span><span class="sxs-lookup"><span data-stu-id="2903c-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="2903c-155">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="2903c-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="2903c-156">**Råbalanssammanfattning – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="2903c-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="2903c-157">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="2903c-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="2903c-158">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="2903c-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="2903c-159">**ATTR** – ett attribut:</span><span class="sxs-lookup"><span data-stu-id="2903c-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="2903c-160">Verifikation</span><span class="sxs-lookup"><span data-stu-id="2903c-160">Voucher</span></span>
    -   <span data-ttu-id="2903c-161">**FD** – den ingående balansen</span><span class="sxs-lookup"><span data-stu-id="2903c-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="2903c-162">**FD** – ekonomisk data som bara innehåller debet</span><span class="sxs-lookup"><span data-stu-id="2903c-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="2903c-163">**FD** – ekonomisk data som bara innehåller kredit</span><span class="sxs-lookup"><span data-stu-id="2903c-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="2903c-164">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="2903c-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="2903c-165">**CALC** – den utgående balansen</span><span class="sxs-lookup"><span data-stu-id="2903c-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="2903c-166">**Summerad råbalans på årsbasis – standardinställning:**</span><span class="sxs-lookup"><span data-stu-id="2903c-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="2903c-167">**ACCT** – kontokoder</span><span class="sxs-lookup"><span data-stu-id="2903c-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="2903c-168">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="2903c-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="2903c-169">**ATTR** – ett attribut</span><span class="sxs-lookup"><span data-stu-id="2903c-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="2903c-170">Verifikation</span><span class="sxs-lookup"><span data-stu-id="2903c-170">Voucher</span></span>
    -   <span data-ttu-id="2903c-171">**FD** – den ingående balansen för det innevarande året</span><span class="sxs-lookup"><span data-stu-id="2903c-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="2903c-172">**FD** – ekonomisk data som bara innehåller debet för innevarande året</span><span class="sxs-lookup"><span data-stu-id="2903c-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="2903c-173">**FD** – ekonomisk data som bara innehåller kredit för innevarande året</span><span class="sxs-lookup"><span data-stu-id="2903c-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="2903c-174">**CALC** – nettoskillnaden</span><span class="sxs-lookup"><span data-stu-id="2903c-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="2903c-175">**CALC** – den utgående balansen</span><span class="sxs-lookup"><span data-stu-id="2903c-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="2903c-176">**FD** – ekonomisk data som bara innehåller debet för det senaste året</span><span class="sxs-lookup"><span data-stu-id="2903c-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="2903c-177">**FD** – ekonomisk data som bara innehåller kredit för det senaste året</span><span class="sxs-lookup"><span data-stu-id="2903c-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2903c-178">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2903c-178">Additional resources</span></span>

[<span data-ttu-id="2903c-179">Översikt över ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="2903c-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="2903c-180">Visa ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="2903c-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="2903c-181">Dynamics-ekonomirapporteringsblogg</span><span class="sxs-lookup"><span data-stu-id="2903c-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
