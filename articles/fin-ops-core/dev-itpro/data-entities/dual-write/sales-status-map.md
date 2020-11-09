---
title: Ställ in mappningen för fälten för försäljningsorderstatus
description: I det här avsnittet beskrivs hur du ställer in fälten för försäljningsorderstatus för dubbelriktad skrivning.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997684"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="e8f71-103">Ställ in mappningen för fälten för försäljningsorderstatus</span><span class="sxs-lookup"><span data-stu-id="e8f71-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8f71-104">De fält som anger försäljningsorderstatus har olika uppräkningsvärden i Microsoft Dynamics 365 Supply Chain Management och Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e8f71-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="e8f71-105">Det krävs ytterligare inställningar för att mappa dessa fält i dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="e8f71-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="e8f71-106">Fält i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8f71-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="e8f71-107">I Supply Chain Management visar två fält status för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="e8f71-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="e8f71-108">De fält som du måste mappa är **status** och **dokumentstatus**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="e8f71-109">**Status** uppräkningen anger den övergripande statusen för ordern.</span><span class="sxs-lookup"><span data-stu-id="e8f71-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="e8f71-110">Denna status visas i orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="e8f71-110">This status is shown on the order header.</span></span>

<span data-ttu-id="e8f71-111">**Status** uppräkningen har följande värden:</span><span class="sxs-lookup"><span data-stu-id="e8f71-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="e8f71-112">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-112">Open Order</span></span>
- <span data-ttu-id="e8f71-113">Levererat</span><span class="sxs-lookup"><span data-stu-id="e8f71-113">Delivered</span></span>
- <span data-ttu-id="e8f71-114">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-114">Invoiced</span></span>
- <span data-ttu-id="e8f71-115">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-115">Cancelled</span></span>

<span data-ttu-id="e8f71-116">**Dokumentstatus** uppräkningen anger det senaste dokument som skapades för ordern.</span><span class="sxs-lookup"><span data-stu-id="e8f71-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="e8f71-117">Om t.ex. en order är bekräftad är dokumentet en bekräftelse på försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="e8f71-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="e8f71-118">Om en försäljningsorder är delvis fakturerad och den återstående raden bekräftas, kommer dokumentstatusen att ha kvar **faktura** , eftersom fakturan genereras senare i processen.</span><span class="sxs-lookup"><span data-stu-id="e8f71-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice** , because the invoice is generated later in the process.</span></span>

<span data-ttu-id="e8f71-119">**Dokumentstatus** uppräkningen har följande värden:</span><span class="sxs-lookup"><span data-stu-id="e8f71-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="e8f71-120">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="e8f71-120">Confirmation</span></span>
- <span data-ttu-id="e8f71-121">Plocklista</span><span class="sxs-lookup"><span data-stu-id="e8f71-121">Picking List</span></span>
- <span data-ttu-id="e8f71-122">Följesedel</span><span class="sxs-lookup"><span data-stu-id="e8f71-122">Packing Slip</span></span>
- <span data-ttu-id="e8f71-123">Faktura</span><span class="sxs-lookup"><span data-stu-id="e8f71-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="e8f71-124">Fält i Sales</span><span class="sxs-lookup"><span data-stu-id="e8f71-124">Fields in Sales</span></span>

<span data-ttu-id="e8f71-125">I Sales anger två fält status för ordern.</span><span class="sxs-lookup"><span data-stu-id="e8f71-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="e8f71-126">De fält som du måste mappa är **status** och **Bearbetningsstatus**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="e8f71-127">**Status** uppräkningen anger den övergripande statusen för ordern.</span><span class="sxs-lookup"><span data-stu-id="e8f71-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="e8f71-128">Det har följande värden:</span><span class="sxs-lookup"><span data-stu-id="e8f71-128">It has the following values:</span></span>

- <span data-ttu-id="e8f71-129">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-129">Active</span></span>
- <span data-ttu-id="e8f71-130">Skickade</span><span class="sxs-lookup"><span data-stu-id="e8f71-130">Submitted</span></span>
- <span data-ttu-id="e8f71-131">Uppfyllt</span><span class="sxs-lookup"><span data-stu-id="e8f71-131">Fulfilled</span></span>
- <span data-ttu-id="e8f71-132">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-132">Invoiced</span></span>
- <span data-ttu-id="e8f71-133">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-133">Cancelled</span></span>

<span data-ttu-id="e8f71-134">Uppräkningen av **bearbetningsstatus** introducerades så att statusen kan mappas mer exakt med Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8f71-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="e8f71-135">Följande tabell visar en mappning av **bearbetningsstatus** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8f71-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="e8f71-136">Bearbetningsstatus</span><span class="sxs-lookup"><span data-stu-id="e8f71-136">Processing Status</span></span>   | <span data-ttu-id="e8f71-137">Status i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8f71-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="e8f71-138">Dokumentstatus i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8f71-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="e8f71-139">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-139">Active</span></span>              | <span data-ttu-id="e8f71-140">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-140">Open Order</span></span>                        | <span data-ttu-id="e8f71-141">None</span><span class="sxs-lookup"><span data-stu-id="e8f71-141">None</span></span>                                       |
| <span data-ttu-id="e8f71-142">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="e8f71-142">Confirmed</span></span>           | <span data-ttu-id="e8f71-143">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-143">Open Order</span></span>                        | <span data-ttu-id="e8f71-144">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="e8f71-144">Confirmation</span></span>                               |
| <span data-ttu-id="e8f71-145">Plockad</span><span class="sxs-lookup"><span data-stu-id="e8f71-145">Picked</span></span>              | <span data-ttu-id="e8f71-146">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-146">Open Order</span></span>                        | <span data-ttu-id="e8f71-147">Plocklista</span><span class="sxs-lookup"><span data-stu-id="e8f71-147">Picking List</span></span>                               |
| <span data-ttu-id="e8f71-148">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="e8f71-148">Partially Delivered</span></span> | <span data-ttu-id="e8f71-149">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-149">Open Order</span></span>                        | <span data-ttu-id="e8f71-150">Följesedel</span><span class="sxs-lookup"><span data-stu-id="e8f71-150">Packing Slip</span></span>                               |
| <span data-ttu-id="e8f71-151">Levererat</span><span class="sxs-lookup"><span data-stu-id="e8f71-151">Delivered</span></span>           | <span data-ttu-id="e8f71-152">Levererat</span><span class="sxs-lookup"><span data-stu-id="e8f71-152">Delivered</span></span>                         | <span data-ttu-id="e8f71-153">Följesedel</span><span class="sxs-lookup"><span data-stu-id="e8f71-153">Packing Slip</span></span>                               |
| <span data-ttu-id="e8f71-154">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="e8f71-154">Partially Invoiced</span></span>  | <span data-ttu-id="e8f71-155">Levererat</span><span class="sxs-lookup"><span data-stu-id="e8f71-155">Delivered</span></span>                         | <span data-ttu-id="e8f71-156">Faktura</span><span class="sxs-lookup"><span data-stu-id="e8f71-156">Invoice</span></span>                                    |
| <span data-ttu-id="e8f71-157">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-157">Invoiced</span></span>            | <span data-ttu-id="e8f71-158">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-158">Invoiced</span></span>                          | <span data-ttu-id="e8f71-159">Faktura</span><span class="sxs-lookup"><span data-stu-id="e8f71-159">Invoice</span></span>                                    |
| <span data-ttu-id="e8f71-160">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-160">Cancelled</span></span>           | <span data-ttu-id="e8f71-161">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-161">Cancelled</span></span>                         | <span data-ttu-id="e8f71-162">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="e8f71-162">Not applicable</span></span>                             |

<span data-ttu-id="e8f71-163">Följande tabell visar en mappning av **bearbetningsstatus** mellan Sales och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8f71-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="e8f71-164">Bearbetningsstatus</span><span class="sxs-lookup"><span data-stu-id="e8f71-164">Processing Status</span></span>   | <span data-ttu-id="e8f71-165">Status i Sales</span><span class="sxs-lookup"><span data-stu-id="e8f71-165">Status in Sales</span></span> | <span data-ttu-id="e8f71-166">Status i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e8f71-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="e8f71-167">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-167">Active</span></span>              | <span data-ttu-id="e8f71-168">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-168">Active</span></span>          | <span data-ttu-id="e8f71-169">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-169">Open Order</span></span>                        |
| <span data-ttu-id="e8f71-170">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="e8f71-170">Confirmed</span></span>           | <span data-ttu-id="e8f71-171">Skickade</span><span class="sxs-lookup"><span data-stu-id="e8f71-171">Submitted</span></span>       | <span data-ttu-id="e8f71-172">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-172">Open Order</span></span>                        |
| <span data-ttu-id="e8f71-173">Plockad</span><span class="sxs-lookup"><span data-stu-id="e8f71-173">Picked</span></span>              | <span data-ttu-id="e8f71-174">Skickade</span><span class="sxs-lookup"><span data-stu-id="e8f71-174">Submitted</span></span>       | <span data-ttu-id="e8f71-175">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-175">Open Order</span></span>                        |
| <span data-ttu-id="e8f71-176">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="e8f71-176">Partially Delivered</span></span> | <span data-ttu-id="e8f71-177">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-177">Active</span></span>          | <span data-ttu-id="e8f71-178">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-178">Open Order</span></span>                        |
| <span data-ttu-id="e8f71-179">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="e8f71-179">Partially Invoiced</span></span>  | <span data-ttu-id="e8f71-180">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e8f71-180">Active</span></span>          | <span data-ttu-id="e8f71-181">Öppen order</span><span class="sxs-lookup"><span data-stu-id="e8f71-181">Open Order</span></span>                        |
| <span data-ttu-id="e8f71-182">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="e8f71-182">Partially Invoiced</span></span>  | <span data-ttu-id="e8f71-183">Uppfyllt</span><span class="sxs-lookup"><span data-stu-id="e8f71-183">Fulfilled</span></span>       | <span data-ttu-id="e8f71-184">Levererat</span><span class="sxs-lookup"><span data-stu-id="e8f71-184">Delivered</span></span>                         |
| <span data-ttu-id="e8f71-185">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-185">Invoiced</span></span>            | <span data-ttu-id="e8f71-186">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-186">Invoiced</span></span>        | <span data-ttu-id="e8f71-187">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="e8f71-187">Invoiced</span></span>                          |
| <span data-ttu-id="e8f71-188">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-188">Cancelled</span></span>           | <span data-ttu-id="e8f71-189">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-189">Cancelled</span></span>       | <span data-ttu-id="e8f71-190">Avbröts</span><span class="sxs-lookup"><span data-stu-id="e8f71-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="e8f71-191">Ställ in</span><span class="sxs-lookup"><span data-stu-id="e8f71-191">Setup</span></span>

<span data-ttu-id="e8f71-192">Om du vill ställa in mappningen för fälten för försäljningsorderstatus måste du aktivera attributen **IsSOPIntegrationEnabled** och **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="e8f71-193">Så här aktiverar du attribut **IsSOPIntegrationEnabled** följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e8f71-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="e8f71-194">I en webbläsare går du till `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="e8f71-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="e8f71-195">Ersätt **\<test-name\>** med företagets länk till Sales.</span><span class="sxs-lookup"><span data-stu-id="e8f71-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="e8f71-196">På den sida som är öppnad, sök efter **organizationid** och anteckna värdet.</span><span class="sxs-lookup"><span data-stu-id="e8f71-196">On the page that is opened, find **organizationid** , and make a note of the value.</span></span>

    ![Sök efter organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="e8f71-198">Öppna webbläsarkonsolen i Sales och kör följande skript.</span><span class="sxs-lookup"><span data-stu-id="e8f71-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="e8f71-199">Använd värdet **organizationid** från steg 2.</span><span class="sxs-lookup"><span data-stu-id="e8f71-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kod i webbläsarkonsol](media/sales-map-script.png)

4. <span data-ttu-id="e8f71-201">Kontrollera att **IsSOPIntegrationEnabled** är inställt på **true**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="e8f71-202">Använd URL från steg 1 för att kontrollera värdet.</span><span class="sxs-lookup"><span data-stu-id="e8f71-202">Use the URL from step 1 to check the value.</span></span>

    ![Ange IsSOPIntegrationEnabled till true](media/sales-map-integration-enabled.png)

<span data-ttu-id="e8f71-204">Så här aktiverar du attribut **isIntegrationUser** följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e8f71-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="e8f71-205">I Sales, gå till **Inställning \> Anpassning \> Anpassa systemet** , välj **Användarentitet** och öppna sedan **Formulär \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-205">In Sales, go to **Setting \> Customization \> Customize the System** , select **User entity** , and then open **Form \> User**.</span></span>

    ![Öppna användarformuläret](media/sales-map-user.png)

2. <span data-ttu-id="e8f71-207">I Tillgängliga fält, hitta **Användarläge för integration** och dubbelklicka på den för att lägga till den i formuläret.</span><span class="sxs-lookup"><span data-stu-id="e8f71-207">In Field Explorer, find **Integration user mode** , and double-click it to add it to the form.</span></span> <span data-ttu-id="e8f71-208">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e8f71-208">Save your change.</span></span>

    ![Lägga till fältet användarläge för integration i formuläret](media/sales-map-field-explorer.png)

3. <span data-ttu-id="e8f71-210">I Sales, gå till **inställning \> säkerhet \> användare** och ändra vyn från **aktiverade användare** till **programanvändare**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-210">In Sales, go to **Setting \> Security \> Users** , and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Ändra visningen av aktiverade användare till programanvändare](media/sales-map-enabled-users.png)

4. <span data-ttu-id="e8f71-212">Välj de två posterna för **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista över programanvändare](media/sales-map-user-mode.png)

5. <span data-ttu-id="e8f71-214">Ändra värdet för fältet **användarläge för integration** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e8f71-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Ändra värdet för fältet användarläge för integration](media/sales-map-user-mode-yes.png)

<span data-ttu-id="e8f71-216">Dina försäljningsorder är nu mappade.</span><span class="sxs-lookup"><span data-stu-id="e8f71-216">Your sales orders are now mapped.</span></span>
