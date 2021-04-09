---
title: Redigera och granska onlineorder och asynkrona kundordertransaktioner
description: Det här ämnet beskriver hur du redigerar och granskar transaktioner för onlineorder och asynkrona kundorder i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5113f7ac0d308076ebaa9daeca0929eb537e94ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792691"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="235fb-103">Redigera och granska onlineorder och asynkrona kundordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="235fb-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="235fb-104">Det här ämnet beskriver hur du redigerar och granskar transaktioner för onlineorder och asynkrona kundorder i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="235fb-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="235fb-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="235fb-105">Overview</span></span>

<span data-ttu-id="235fb-106">Mellan Commerce-versionerna 10.0.5 och 10.0.6 har stöd lagts till för redigering av hämtköpstransaktioner (till exempel försäljning och returer) och transaktioner för kontanthantering (till exempel borttagning av växelpost och betalningsmedel).</span><span class="sxs-lookup"><span data-stu-id="235fb-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="235fb-107">I Commerce version 10.0.7 har stöd för redigering av onlineordertransaktioner och asynkrona kundordertransaktioner lagts till.</span><span class="sxs-lookup"><span data-stu-id="235fb-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="235fb-108">Redigera och granska ordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="235fb-108">Edit and audit order transactions</span></span>

<span data-ttu-id="235fb-109">Följ de här stegen om du vill redigera och granska ordertransaktioner i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="235fb-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="235fb-110">Installera [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="235fb-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="235fb-111">Gå till sidan **Butiksparametrar**, fliken **Kundorder** på snabbfliken **Order** och ange en spärrkod för **Spärrkod för ordersynkroniseringsfel**.</span><span class="sxs-lookup"><span data-stu-id="235fb-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="235fb-112">Öppna arbetsytan **Butiksekonomi**.</span><span class="sxs-lookup"><span data-stu-id="235fb-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="235fb-113">På panelerna **Synkroniseringsfel för onlineorder** och **Synkroniseringsfel för kundorder** finns en förfiltrerad vy av sidan med butikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="235fb-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="235fb-114">På var och en visas de transaktionsposter som inte kunnat synkroniseras för motsvarande ordertyp.</span><span class="sxs-lookup"><span data-stu-id="235fb-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="235fb-115">Öppna sidan **Synkroniseringsfel för onlineorder** eller sidan **Synkroniseringsfel för kundorder**.</span><span class="sxs-lookup"><span data-stu-id="235fb-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="235fb-116">Välj en post för att visa information om synkroniseringsfelet.</span><span class="sxs-lookup"><span data-stu-id="235fb-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="235fb-117">På snabbfliken **Synkroniseringsstatus** finns följande felinformation:</span><span class="sxs-lookup"><span data-stu-id="235fb-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="235fb-118">Status för väntande order</span><span class="sxs-lookup"><span data-stu-id="235fb-118">Pending order status</span></span>
    - <span data-ttu-id="235fb-119">Information om orderfel</span><span class="sxs-lookup"><span data-stu-id="235fb-119">Order error details</span></span>
    - <span data-ttu-id="235fb-120">Datum och tid för ändring</span><span class="sxs-lookup"><span data-stu-id="235fb-120">Modified date and time</span></span>
    - <span data-ttu-id="235fb-121">Antal nya försök</span><span class="sxs-lookup"><span data-stu-id="235fb-121">Retry count</span></span>

1. <span data-ttu-id="235fb-122">Om felinformationen anger att posten måste åtgärdas väljer du **Office Add in** och välj sedan **Redigera vald transaktion**.</span><span class="sxs-lookup"><span data-stu-id="235fb-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="235fb-123">En Excel-fil som visar detaljerna för den valda transaktionen öppnas.</span><span class="sxs-lookup"><span data-stu-id="235fb-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="235fb-124">Om transaktionen som redigeras är en onlineordertransaktion innehåller Excel-filen följande kalkylblad:</span><span class="sxs-lookup"><span data-stu-id="235fb-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="235fb-125">**Transaktion** – I det här kalkylbladet finns huvudinformation för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="235fb-126">**Försäljningstransaktion** – I det här kalkylbladet finns radinformation för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="235fb-127">**Betalningstransaktioner** – I det här kalkyl bladet finns detaljinformation om betalningsraderna för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="235fb-128">**Rabattransaktioner** – I det här kalkylbladet finns rabattrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="235fb-129">**Momstransaktioner** – I det här kalkylbladet finns momsrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="235fb-130">**Avgiftstransaktioner** – I det här kalkylbladet finns avgiftsrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="235fb-131">Om transaktionen som redigeras är en asynkron kundordertransaktion innehåller Excel-filen följande kalkylblad:</span><span class="sxs-lookup"><span data-stu-id="235fb-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="235fb-132">**Rader** – I det här kalkylbladet finns huvud- och radinformation för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="235fb-133">**Betalningar** – I det här kalkyl bladet finns detaljinformation om betalningsraderna för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="235fb-134">**Rabatter** – I det här kalkylbladet finns rabattrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="235fb-135">**Moms** – I det här kalkylbladet finns momsrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="235fb-136">**Avgifter** – I det här kalkylbladet finns avgiftsrelaterad information för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="235fb-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="235fb-137">Ange **Redigering** i fältet **Status för väntande order** i Excel-filen och publicera sedan ändringen.</span><span class="sxs-lookup"><span data-stu-id="235fb-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="235fb-138">På det här sättet förhindrar du jobbet **Synkronisera order** som körs i batchläge hoppar över den här posten under bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="235fb-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="235fb-139">I Excel-filen ändrar du lämpliga fält och skickar tillbaka informationen till Commerce-administration med hjälp av publiceringsfunktionen i Dynamics Excel Add-in.</span><span class="sxs-lookup"><span data-stu-id="235fb-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="235fb-140">När du har publicerat data visas ändringarna i systemet.</span><span class="sxs-lookup"><span data-stu-id="235fb-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="235fb-141">Under publiceringen görs ingen validering av ändringar som användarna gör.</span><span class="sxs-lookup"><span data-stu-id="235fb-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="235fb-142">Du kan visa en fullständig granskningsspårning av ändringarna genom att välja **Visa redovisningsspårning** i rubriken för **Butikstransaktion** för ändringarna på rubriknivå och i det relevanta avsnittet och den relevanta posten på den aktuella transaktionssidan.</span><span class="sxs-lookup"><span data-stu-id="235fb-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="235fb-143">Till exempel kommer alla ändringar som är relaterade till försäljningsrader att visas på sidan **Försäljningstransaktioner** och alla ändringar som är relaterade till betalningar kommer att visas på sidan **Betalningstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="235fb-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="235fb-144">Följande granskningsinformation underhålls för ändringarna:</span><span class="sxs-lookup"><span data-stu-id="235fb-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="235fb-145">Datum och tid för ändring</span><span class="sxs-lookup"><span data-stu-id="235fb-145">Modified date and time</span></span>
    - <span data-ttu-id="235fb-146">Fält</span><span class="sxs-lookup"><span data-stu-id="235fb-146">Field</span></span>
    - <span data-ttu-id="235fb-147">Gammalt värde</span><span class="sxs-lookup"><span data-stu-id="235fb-147">Old value</span></span>
    - <span data-ttu-id="235fb-148">Nytt värde</span><span class="sxs-lookup"><span data-stu-id="235fb-148">New value</span></span>
    - <span data-ttu-id="235fb-149">Ändrades av</span><span class="sxs-lookup"><span data-stu-id="235fb-149">Modified by</span></span>

1. <span data-ttu-id="235fb-150">När du har gjort och publicerat ändringarna väljer du **Synkronisera order** om du vill att synkroniseringsprocessen ska starta direkt.</span><span class="sxs-lookup"><span data-stu-id="235fb-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="235fb-151">Du kan också vänta och bearbeta transaktionen genom att köra synkroniseringsprocessen batchläge.</span><span class="sxs-lookup"><span data-stu-id="235fb-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="235fb-152">När order har synkroniserats får de som standard en spärrstatus, baserat på spärrkoden som definierats i Commerce-parametrarna.</span><span class="sxs-lookup"><span data-stu-id="235fb-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="235fb-153">Orderspärren måste tas bort innan dessa order kan bearbetas ytterligare för uppfyllelse eller andra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="235fb-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="235fb-154">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="235fb-154">Additional resources</span></span>

[<span data-ttu-id="235fb-155">Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering</span><span class="sxs-lookup"><span data-stu-id="235fb-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="235fb-156">Redigera ekonomiska dimensioner för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="235fb-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="235fb-157">Skapa en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="235fb-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="235fb-158">Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="235fb-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]