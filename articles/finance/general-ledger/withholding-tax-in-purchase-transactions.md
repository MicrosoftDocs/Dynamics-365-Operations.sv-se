---
title: Källskatt i inköpstransaktioner
description: För leverantörer som ska betala källskatt kan du tilldela **Standardkällskattegruppen** på sidan **Alla leverantörer**.
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
ms.openlocfilehash: 06c18e6b0779539a6da7ae7afbe000c4cfc78d9e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256677"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="dedc1-103">Källskatt i inköpstransaktioner</span><span class="sxs-lookup"><span data-stu-id="dedc1-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="dedc1-104">För leverantörer som ska betala källskatt kan du tilldela **Standardkällskattegruppen** på sidan **Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="dedc1-105">Gå till **Navigeringsfönter > Moduler > Leverantörsreskontra > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="dedc1-106">Klicka på respektive leverantörskonto och sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="dedc1-107">I fliken **Faktura och leverans** anger du fältet **Beräkna källskatt** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="dedc1-108">Källskatt beräknas inte om **Beräkna källskatt** inte aktiveras för denna leverantör i datan.</span><span class="sxs-lookup"><span data-stu-id="dedc1-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="dedc1-109">Välj en källskattegrupp i **Källskattegrupp**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="dedc1-110">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-110">Click **Save**.</span></span>

<span data-ttu-id="dedc1-111">För artiklar/tjänster som är källskattepliktiga kan du tilldela **Standardkällskattegrupp för artiklar** under **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="dedc1-112">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="dedc1-113">Klicka på respektive artikelnummer och sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="dedc1-114">I fliken **Inköp** klickar du på **Beräkna källskatt**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="dedc1-115">Källskatt beräknas inte om **Beräkna källskatt** inte anges som **Ja** för denna artikel i fliken **Inköp** på sidan **Frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="dedc1-116">Välj en grupp för artikelkällskatt i listan **Källskattegrupp för artiklar**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="dedc1-117">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-117">Click **Save**.</span></span>

<span data-ttu-id="dedc1-118">Källskattegrupper och artikelkällskattegrupper kan tilldelas på sidorna:</span><span class="sxs-lookup"><span data-stu-id="dedc1-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="dedc1-119">**Inköpsorder**</span><span class="sxs-lookup"><span data-stu-id="dedc1-119">**Purchase order**</span></span>
- <span data-ttu-id="dedc1-120">**Leverantörsfaktura**</span><span class="sxs-lookup"><span data-stu-id="dedc1-120">**Vendor invoice**</span></span>
- <span data-ttu-id="dedc1-121">**Fakturajournal**</span><span class="sxs-lookup"><span data-stu-id="dedc1-121">**Invoice journal**</span></span>

<span data-ttu-id="dedc1-122">Standardkällskattegruppen och artikelkällskattegruppen förs in på raderna när du skapar **inköpsorder** och/eller **Väntande leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="dedc1-123">För **Leverantörsfakturajournal** kan du aktivera **Beräkna källskatt** och sedan välja **Källskattegrupp för artiklar** i fliken **Allmänt** i journalen.</span><span class="sxs-lookup"><span data-stu-id="dedc1-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="dedc1-124">Det tillfälliga källskattebeloppet är tillgängligt i fältet **Justerad källskatt** i fliken **Summor** på sidan **Inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![Källskatt inkluderas i inköpsordern](media/withholding-tax-adjusted.png)

<span data-ttu-id="dedc1-126">Källskatt som beräknats i **leverantörsbetalningsjournalen**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="dedc1-127">Du kan manuellt justera tillämpliga källskattekoder och de faktiska källskattebeloppen på fliken **Källskatt** på sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="dedc1-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![Källskatt kan justeras manuellt på sidan Kvitta transaktioner](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="dedc1-129">Det härledda källskattebeloppet dras av från leverantörsbetalningen och bokförs på **Källskattekontot** i en relaterad verifikation.</span><span class="sxs-lookup"><span data-stu-id="dedc1-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Källskattekonto som visar en relaterad verifikation](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]