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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4457405"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="ab1d1-103">Ställ in mappningen för fälten för försäljningsorderstatus</span><span class="sxs-lookup"><span data-stu-id="ab1d1-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ab1d1-104">De fält som anger försäljningsorderstatus har olika uppräkningsvärden i Microsoft Dynamics 365 Supply Chain Management och Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="ab1d1-105">Det krävs ytterligare inställningar för att mappa dessa fält i dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="ab1d1-106">Fält i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ab1d1-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="ab1d1-107">I Supply Chain Management visar två fält status för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="ab1d1-108">De fält som du måste mappa är **status** och **dokumentstatus**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="ab1d1-109">**Status** uppräkningen anger den övergripande statusen för ordern.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="ab1d1-110">Denna status visas i orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-110">This status is shown on the order header.</span></span>

<span data-ttu-id="ab1d1-111">**Status** uppräkningen har följande värden:</span><span class="sxs-lookup"><span data-stu-id="ab1d1-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="ab1d1-112">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-112">Open Order</span></span>
- <span data-ttu-id="ab1d1-113">Levererat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-113">Delivered</span></span>
- <span data-ttu-id="ab1d1-114">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-114">Invoiced</span></span>
- <span data-ttu-id="ab1d1-115">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-115">Cancelled</span></span>

<span data-ttu-id="ab1d1-116">**Dokumentstatus** uppräkningen anger det senaste dokument som skapades för ordern.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="ab1d1-117">Om t.ex. en order är bekräftad är dokumentet en bekräftelse på försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="ab1d1-118">Om en försäljningsorder är delvis fakturerad och den återstående raden bekräftas, kommer dokumentstatusen att ha kvar **faktura**, eftersom fakturan genereras senare i processen.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="ab1d1-119">**Dokumentstatus** uppräkningen har följande värden:</span><span class="sxs-lookup"><span data-stu-id="ab1d1-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="ab1d1-120">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="ab1d1-120">Confirmation</span></span>
- <span data-ttu-id="ab1d1-121">Plocklista</span><span class="sxs-lookup"><span data-stu-id="ab1d1-121">Picking List</span></span>
- <span data-ttu-id="ab1d1-122">Följesedel</span><span class="sxs-lookup"><span data-stu-id="ab1d1-122">Packing Slip</span></span>
- <span data-ttu-id="ab1d1-123">Faktura</span><span class="sxs-lookup"><span data-stu-id="ab1d1-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="ab1d1-124">Fält i Sales</span><span class="sxs-lookup"><span data-stu-id="ab1d1-124">Fields in Sales</span></span>

<span data-ttu-id="ab1d1-125">I Sales anger två fält status för ordern.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="ab1d1-126">De fält som du måste mappa är **status** och **Bearbetningsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="ab1d1-127">**Status** uppräkningen anger den övergripande statusen för ordern.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="ab1d1-128">Det har följande värden:</span><span class="sxs-lookup"><span data-stu-id="ab1d1-128">It has the following values:</span></span>

- <span data-ttu-id="ab1d1-129">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-129">Active</span></span>
- <span data-ttu-id="ab1d1-130">Skickade</span><span class="sxs-lookup"><span data-stu-id="ab1d1-130">Submitted</span></span>
- <span data-ttu-id="ab1d1-131">Uppfyllt</span><span class="sxs-lookup"><span data-stu-id="ab1d1-131">Fulfilled</span></span>
- <span data-ttu-id="ab1d1-132">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-132">Invoiced</span></span>
- <span data-ttu-id="ab1d1-133">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-133">Cancelled</span></span>

<span data-ttu-id="ab1d1-134">Uppräkningen av **bearbetningsstatus** introducerades så att statusen kan mappas mer exakt med Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="ab1d1-135">Följande tabell visar en mappning av **bearbetningsstatus** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="ab1d1-136">Bearbetningsstatus</span><span class="sxs-lookup"><span data-stu-id="ab1d1-136">Processing Status</span></span>   | <span data-ttu-id="ab1d1-137">Status i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ab1d1-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="ab1d1-138">Dokumentstatus i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ab1d1-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="ab1d1-139">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-139">Active</span></span>              | <span data-ttu-id="ab1d1-140">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-140">Open Order</span></span>                        | <span data-ttu-id="ab1d1-141">None</span><span class="sxs-lookup"><span data-stu-id="ab1d1-141">None</span></span>                                       |
| <span data-ttu-id="ab1d1-142">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-142">Confirmed</span></span>           | <span data-ttu-id="ab1d1-143">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-143">Open Order</span></span>                        | <span data-ttu-id="ab1d1-144">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="ab1d1-144">Confirmation</span></span>                               |
| <span data-ttu-id="ab1d1-145">Plockad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-145">Picked</span></span>              | <span data-ttu-id="ab1d1-146">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-146">Open Order</span></span>                        | <span data-ttu-id="ab1d1-147">Plocklista</span><span class="sxs-lookup"><span data-stu-id="ab1d1-147">Picking List</span></span>                               |
| <span data-ttu-id="ab1d1-148">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-148">Partially Delivered</span></span> | <span data-ttu-id="ab1d1-149">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-149">Open Order</span></span>                        | <span data-ttu-id="ab1d1-150">Följesedel</span><span class="sxs-lookup"><span data-stu-id="ab1d1-150">Packing Slip</span></span>                               |
| <span data-ttu-id="ab1d1-151">Levererat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-151">Delivered</span></span>           | <span data-ttu-id="ab1d1-152">Levererat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-152">Delivered</span></span>                         | <span data-ttu-id="ab1d1-153">Följesedel</span><span class="sxs-lookup"><span data-stu-id="ab1d1-153">Packing Slip</span></span>                               |
| <span data-ttu-id="ab1d1-154">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-154">Partially Invoiced</span></span>  | <span data-ttu-id="ab1d1-155">Levererat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-155">Delivered</span></span>                         | <span data-ttu-id="ab1d1-156">Faktura</span><span class="sxs-lookup"><span data-stu-id="ab1d1-156">Invoice</span></span>                                    |
| <span data-ttu-id="ab1d1-157">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-157">Invoiced</span></span>            | <span data-ttu-id="ab1d1-158">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-158">Invoiced</span></span>                          | <span data-ttu-id="ab1d1-159">Faktura</span><span class="sxs-lookup"><span data-stu-id="ab1d1-159">Invoice</span></span>                                    |
| <span data-ttu-id="ab1d1-160">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-160">Cancelled</span></span>           | <span data-ttu-id="ab1d1-161">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-161">Cancelled</span></span>                         | <span data-ttu-id="ab1d1-162">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="ab1d1-162">Not applicable</span></span>                             |

<span data-ttu-id="ab1d1-163">Följande tabell visar en mappning av **bearbetningsstatus** mellan Sales och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="ab1d1-164">Bearbetningsstatus</span><span class="sxs-lookup"><span data-stu-id="ab1d1-164">Processing Status</span></span>   | <span data-ttu-id="ab1d1-165">Status i Sales</span><span class="sxs-lookup"><span data-stu-id="ab1d1-165">Status in Sales</span></span> | <span data-ttu-id="ab1d1-166">Status i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ab1d1-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="ab1d1-167">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-167">Active</span></span>              | <span data-ttu-id="ab1d1-168">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-168">Active</span></span>          | <span data-ttu-id="ab1d1-169">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-169">Open Order</span></span>                        |
| <span data-ttu-id="ab1d1-170">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-170">Confirmed</span></span>           | <span data-ttu-id="ab1d1-171">Skickade</span><span class="sxs-lookup"><span data-stu-id="ab1d1-171">Submitted</span></span>       | <span data-ttu-id="ab1d1-172">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-172">Open Order</span></span>                        |
| <span data-ttu-id="ab1d1-173">Plockad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-173">Picked</span></span>              | <span data-ttu-id="ab1d1-174">Skickade</span><span class="sxs-lookup"><span data-stu-id="ab1d1-174">Submitted</span></span>       | <span data-ttu-id="ab1d1-175">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-175">Open Order</span></span>                        |
| <span data-ttu-id="ab1d1-176">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-176">Partially Delivered</span></span> | <span data-ttu-id="ab1d1-177">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-177">Active</span></span>          | <span data-ttu-id="ab1d1-178">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-178">Open Order</span></span>                        |
| <span data-ttu-id="ab1d1-179">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-179">Partially Invoiced</span></span>  | <span data-ttu-id="ab1d1-180">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ab1d1-180">Active</span></span>          | <span data-ttu-id="ab1d1-181">Öppen order</span><span class="sxs-lookup"><span data-stu-id="ab1d1-181">Open Order</span></span>                        |
| <span data-ttu-id="ab1d1-182">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="ab1d1-182">Partially Invoiced</span></span>  | <span data-ttu-id="ab1d1-183">Uppfyllt</span><span class="sxs-lookup"><span data-stu-id="ab1d1-183">Fulfilled</span></span>       | <span data-ttu-id="ab1d1-184">Levererat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-184">Delivered</span></span>                         |
| <span data-ttu-id="ab1d1-185">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-185">Invoiced</span></span>            | <span data-ttu-id="ab1d1-186">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-186">Invoiced</span></span>        | <span data-ttu-id="ab1d1-187">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="ab1d1-187">Invoiced</span></span>                          |
| <span data-ttu-id="ab1d1-188">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-188">Cancelled</span></span>           | <span data-ttu-id="ab1d1-189">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-189">Cancelled</span></span>       | <span data-ttu-id="ab1d1-190">Avbröts</span><span class="sxs-lookup"><span data-stu-id="ab1d1-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="ab1d1-191">Ställ in</span><span class="sxs-lookup"><span data-stu-id="ab1d1-191">Setup</span></span>

<span data-ttu-id="ab1d1-192">Om du vill ställa in mappningen för fälten för försäljningsorderstatus måste du aktivera attributen **IsSOPIntegrationEnabled** och **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="ab1d1-193">Så här aktiverar du attribut **IsSOPIntegrationEnabled** följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="ab1d1-194">I en webbläsare går du till `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="ab1d1-195">Ersätt **\<test-name\>** med företagets länk till Sales.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="ab1d1-196">På den sida som är öppnad, sök efter **organizationid** och anteckna värdet.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Sök efter organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="ab1d1-198">Öppna webbläsarkonsolen i Sales och kör följande skript.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="ab1d1-199">Använd värdet **organizationid** från steg 2.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-199">Use the **organizationid** value from step 2.</span></span>

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

4. <span data-ttu-id="ab1d1-201">Kontrollera att **IsSOPIntegrationEnabled** är inställt på **true**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="ab1d1-202">Använd URL från steg 1 för att kontrollera värdet.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-202">Use the URL from step 1 to check the value.</span></span>

    ![Ange IsSOPIntegrationEnabled till true](media/sales-map-integration-enabled.png)

<span data-ttu-id="ab1d1-204">Så här aktiverar du attribut **isIntegrationUser** följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="ab1d1-205">I Sales, gå till **Inställning \> Anpassning \> Anpassa systemet**, välj **Användarentitet** och öppna sedan **Formulär \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![Öppna användarformuläret](media/sales-map-user.png)

2. <span data-ttu-id="ab1d1-207">I Tillgängliga fält, hitta **Användarläge för integration** och dubbelklicka på den för att lägga till den i formuläret.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="ab1d1-208">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-208">Save your change.</span></span>

    ![Lägga till fältet användarläge för integration i formuläret](media/sales-map-field-explorer.png)

3. <span data-ttu-id="ab1d1-210">I Sales, gå till **inställning \> säkerhet \> användare** och ändra vyn från **aktiverade användare** till **programanvändare**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Ändra visningen av aktiverade användare till programanvändare](media/sales-map-enabled-users.png)

4. <span data-ttu-id="ab1d1-212">Välj de två posterna för **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista över programanvändare](media/sales-map-user-mode.png)

5. <span data-ttu-id="ab1d1-214">Ändra värdet för fältet **användarläge för integration** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Ändra värdet för fältet användarläge för integration](media/sales-map-user-mode-yes.png)

<span data-ttu-id="ab1d1-216">Dina försäljningsorder är nu mappade.</span><span class="sxs-lookup"><span data-stu-id="ab1d1-216">Your sales orders are now mapped.</span></span>
