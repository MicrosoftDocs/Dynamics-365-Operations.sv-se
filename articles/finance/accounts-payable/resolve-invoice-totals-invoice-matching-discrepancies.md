---
title: Åtgärda avvikelser under matchning av fakturasummor – översikt
description: Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4a20368385ec43547ee3d29770bd83cdec47e4a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189509"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a><span data-ttu-id="84ffc-103">Åtgärda avvikelser under matchning av fakturasummor – översikt</span><span class="sxs-lookup"><span data-stu-id="84ffc-103">Resolve discrepancies during invoice totals matching overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84ffc-104">En typ av fakturakontroll validering är fakturasummor matchning.</span><span class="sxs-lookup"><span data-stu-id="84ffc-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="84ffc-105">Ange att systemet ska utföra fakturasummor matchning på **leverantörsskulder parametrar sidan** , på **fakturan fliken validering** , **matchar fakturasummor** alternativet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="84ffc-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="84ffc-106">Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.</span><span class="sxs-lookup"><span data-stu-id="84ffc-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="84ffc-107">Sex summorna kan jämföras på **fakturasummor matchande detaljer** .</span><span class="sxs-lookup"><span data-stu-id="84ffc-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="84ffc-108">Om någon av summorna avviker från den förväntade motsvarande inköpsorder totalt, en matchande avvikelse flaggas.</span><span class="sxs-lookup"><span data-stu-id="84ffc-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="84ffc-109">För att granska faktura som har summorna matchande avvikelser i **säljarens faktura** arbetsytan klickar du på den **väntande fakturor** panel.</span><span class="sxs-lookup"><span data-stu-id="84ffc-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="84ffc-110">Sedan, på rutan åtgärd, på **fliken granskning** klickar du **matchande detaljer**.</span><span class="sxs-lookup"><span data-stu-id="84ffc-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="84ffc-111">Om matchning skillnader har upptäckts, varningsikoner visas intill beloppet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="84ffc-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="84ffc-112">Du kan visa fler detaljer om summor på fakturasummor matchande detaljer.</span><span class="sxs-lookup"><span data-stu-id="84ffc-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="84ffc-113">När du identifierar en avvikelse, kan du behöva kontakta säljaren om du tycker att informationen på fakturan är felaktig.</span><span class="sxs-lookup"><span data-stu-id="84ffc-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="84ffc-114">Beroende på vilket avtal med säljaren kan du sedan ta någon av dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="84ffc-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="84ffc-115">Acceptera prisskillnaden och Bokför faktura som har matchande avvikelser.</span><span class="sxs-lookup"><span data-stu-id="84ffc-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="84ffc-116">Ditt system kan vara konfigurerat att kräva godkännande innan den kan posta om det finns motsvarande skillnader.</span><span class="sxs-lookup"><span data-stu-id="84ffc-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="84ffc-117">I detta fall måste du godkänna matchningen avvikelse och kan även ange ett godkännande kommentar.</span><span class="sxs-lookup"><span data-stu-id="84ffc-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="84ffc-118">Du kan sedan välja att kontera faktura.</span><span class="sxs-lookup"><span data-stu-id="84ffc-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="84ffc-119">Ändra fakturans belopp till det förväntade värdet och Bokför faktura.</span><span class="sxs-lookup"><span data-stu-id="84ffc-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="84ffc-120">Begära ett fullständigt erkännande och en ny korrigerad faktura från leverantören.</span><span class="sxs-lookup"><span data-stu-id="84ffc-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="84ffc-121">Mer information finns i [Undersöka eller lösa undantag](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="84ffc-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


