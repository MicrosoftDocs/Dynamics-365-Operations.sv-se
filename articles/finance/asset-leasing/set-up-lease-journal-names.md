---
title: Konfigurera namn för leasingjournal
description: I det här ämnet beskrivs hur du definierar namn på leasingjournaler. Namn på leasingjournaler anger de journaler som poster som kommer från Leasing av tillgångar bokförs på.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c139df124b249ec9dc5d16096e6f45f22d435456
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880896"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="cc2c0-104">Konfigurera namn för leasingjournal</span><span class="sxs-lookup"><span data-stu-id="cc2c0-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc2c0-105">Namn på leasingjournaler anger de journaler som transaktioner i Leasing av tillgångar bokförs till.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="cc2c0-106">Endast journalnamn som tilldelas journaltypen **Leasing av tillgångar** visas i fälten **Första redovisningstillfälle** och **Namn på månatlig journal** på sidan **Parametrar för tillgångsleasing**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="cc2c0-107">Endast journaltypen **Registrering av leverantörsfaktura** kan tilldelas fältet **Namn på fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="cc2c0-108">Konfigurera namn på leasingjournaler genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="cc2c0-109">Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="cc2c0-110">Välj en journal på fliken **Allmänt** i fältet **Journalnamn för första redovisningstillfälle**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="cc2c0-111">Alla journalposter för första redovisningstillfälle bokförs med det här journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="cc2c0-112">Välj en journal i fältet **Namn på fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="cc2c0-113">Om alternativet **Betala till leverantör** är inställt på **Ja** för leasingboken bokförs fakturor för leasing och utgiftsbetalning till det här journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="cc2c0-114">Välj en journal i fältet **Namn för leasingjournal**.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="cc2c0-115">Alla avskrivnings-, ränte-och omklassificeringstransaktioner för kortfristiga poster bokförs till det här journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="cc2c0-116">Om alternativet **Betala till leverantör** är inställt på **Nej** för leasingboken bokförs poster för leasingbetalningar och utgiftsbetalning också till det här journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="cc2c0-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
