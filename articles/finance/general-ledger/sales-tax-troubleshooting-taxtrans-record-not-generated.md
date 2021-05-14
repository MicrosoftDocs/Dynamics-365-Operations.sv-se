---
title: TaxTrans-post genereras inte
description: Detta ämne tillhandahåller felsökningsinformation som kan vara till hjälp när en TaxTrans-post inte genereras.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0c7414cc39198ff4d5be9b4c41ca62f9c78c9250
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947709"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="bdfea-103">TaxTrans-post genereras inte</span><span class="sxs-lookup"><span data-stu-id="bdfea-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdfea-104">Om du väljer **Bokförd moms** för en transaktion men sidan **Bokförd moms** antingen inte anger några momsrader eller saknar en momsrad, kanske posten **TaxTrans** inte har genererats.</span><span class="sxs-lookup"><span data-stu-id="bdfea-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="bdfea-105">[![Bokförd momssida som inte innehåller några radartiklar](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="bdfea-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="bdfea-106">Felsök det här problemet genom att följa stegen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="bdfea-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="bdfea-107">Kontrollera momsen innan du bokför transaktionen</span><span class="sxs-lookup"><span data-stu-id="bdfea-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="bdfea-108">Innan du bokför transaktionen väljer du, på sidan **Bokföring av faktura**, **Moms** för att kontrollera beräkningen.</span><span class="sxs-lookup"><span data-stu-id="bdfea-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="bdfea-109">[![Knappen Moms på sidan Bokföring av faktura](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="bdfea-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="bdfea-110">På sidan **Tillfälliga momstransaktioner** kan du granska resultatet av beräkningen.</span><span class="sxs-lookup"><span data-stu-id="bdfea-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="bdfea-111">Om ingen moms beräknas, gå till [Moms beräknas inte, eller också är momsbeloppet noll](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="bdfea-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="bdfea-112">Hitta TaxTrans-posten i all bokförd moms</span><span class="sxs-lookup"><span data-stu-id="bdfea-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="bdfea-113">Gå till **Moms** \> **Förfrågningar och rapporter** \> **Momsförfrågningar** > **Bokförd moms**.</span><span class="sxs-lookup"><span data-stu-id="bdfea-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="bdfea-114">I kolumnrubriken för **Verifikation** väljer du filtersymbolen för att hitta posten **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="bdfea-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="bdfea-115">Kontrollera datumet om det finns momsposter du letar efter.</span><span class="sxs-lookup"><span data-stu-id="bdfea-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="bdfea-116">Om datumet inte är det samma som datumet för journalrubriken skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="bdfea-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="bdfea-117">[![Sidan Bokförd moms](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="bdfea-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="bdfea-118">Felsöka om du vill kontrollera detaljer</span><span class="sxs-lookup"><span data-stu-id="bdfea-118">Debug to check details</span></span>

1. <span data-ttu-id="bdfea-119">Mer information om hur du felsöker och fastställer huruvida **TmpTaxWorkTrans** och **TaxUncommitted** har genererats korrekt, se [Fältvärdet i TaxTrans är felaktigt](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="bdfea-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="bdfea-120">Om **TaxTmpWorkTrans** eller **TaxUncommitted** har genererats korrekt lägger du till en brytpunkt för **TaxPost::SaveAndPost()** och **Tax::SaveAndPost** i syfte att felsöka orsaken till att **TaxTrans** inte förts in.</span><span class="sxs-lookup"><span data-stu-id="bdfea-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="bdfea-121">[![Brytpunkter tillagda i kod](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="bdfea-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="bdfea-122">[![Resultat av tillagda brytpunkter](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="bdfea-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="bdfea-123">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="bdfea-123">Determine whether customization exists</span></span>

<span data-ttu-id="bdfea-124">Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="bdfea-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="bdfea-125">Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="bdfea-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
