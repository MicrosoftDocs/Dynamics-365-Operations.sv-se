---
title: Källskatt i försäljningstransaktioner
description: Detta ämne innehåller en lista med steg för att undvika beräkning av källskatt för valda kunder. För kunder som anger källskatt i sina betalningar till dig kan du tilldela standardkällskattegruppen.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: c50f6df1c63c91107da65f463934565f786d6ccd
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060796"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="869e7-104">Källskatt i försäljningstransaktioner</span><span class="sxs-lookup"><span data-stu-id="869e7-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="869e7-105">Detta ämne innehåller en lista med steg för att undvika beräkning av källskatt för valda kunder.</span><span class="sxs-lookup"><span data-stu-id="869e7-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="869e7-106">För kunder som anger källskatt i sina betalningar till dig kan du tilldela **Standardkällskattegruppen** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="869e7-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="869e7-107">Gå till **Navigeringsfönster > Moduler > Kundreskontra > Kunder > Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="869e7-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="869e7-108">Klicka på respektive kundkonto och sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="869e7-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="869e7-109">I fliken **Faktura och leverans** anger du fältet **Beräkna källskatt** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="869e7-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="869e7-110">Källskatt beräknas inte om **Beräkna källskatt** inte aktiveras för denna kund i huvuddatan.</span><span class="sxs-lookup"><span data-stu-id="869e7-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="869e7-111">Välj en källskattegrupp i **Källskattegrupp**.</span><span class="sxs-lookup"><span data-stu-id="869e7-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="869e7-112">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="869e7-112">Click **Save**.</span></span>

<span data-ttu-id="869e7-113">För artiklar/tjänster som är källskattepliktiga kan du tilldela **Standardkällskattegrupp för artiklar** under **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="869e7-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="869e7-114">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="869e7-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="869e7-115">Klicka på respektive artikelnummer och sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="869e7-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="869e7-116">I fliken **Sälj** klickar du på **Beräkna säljskatt**.</span><span class="sxs-lookup"><span data-stu-id="869e7-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="869e7-117">Källskatt beräknas inte om **Beräkna källskatt** inte anges som **Ja** för denna artikel i fliken **Sälj** på sidan **Frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="869e7-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="869e7-118">Välj en grupp för artikelkällskatt i listan **Källskattegrupp för artiklar**.</span><span class="sxs-lookup"><span data-stu-id="869e7-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="869e7-119">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="869e7-119">Click **Save**.</span></span>

<span data-ttu-id="869e7-120">Källskattegrupper och artikelkällskattegrupper kan tilldelas på sidan **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="869e7-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="869e7-121">Standardkällskattegruppen och artikelkällskattegruppen används som standardposter på försäljningsorderrader när du skapar en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="869e7-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="869e7-122">Källskatt beräknas och bokförs i **kundbetalningsjournalen**.</span><span class="sxs-lookup"><span data-stu-id="869e7-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="869e7-123">Du kan manuellt justera den tillämpliga källskattekoden och det faktiska källskattebeloppet på fliken **Källskatt** på sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="869e7-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="869e7-124">Det beräknade källskattebeloppet dras av från kundbetalningen och bokförs på **motkontot för källskatt** i en relaterad verifikation.</span><span class="sxs-lookup"><span data-stu-id="869e7-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>
