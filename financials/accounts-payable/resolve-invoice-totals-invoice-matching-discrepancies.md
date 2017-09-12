---
title: "Åtgärda avvikelser under fakturasummor matchning"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3f7e1261838866688c97529b0edfa1354034247b
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="aaea7-102">Åtgärda avvikelser under fakturasummor matchning</span><span class="sxs-lookup"><span data-stu-id="aaea7-102">Resolve discrepancies during invoice totals matching</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="aaea7-103">En typ av fakturakontroll validering är fakturasummor matchning.</span><span class="sxs-lookup"><span data-stu-id="aaea7-103">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="aaea7-104">Ange att systemet ska utföra fakturasummor matchning på **leverantörsskulder parametrar sidan** , på **fakturan fliken validering** , **matchar fakturasummor** alternativet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aaea7-104">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="aaea7-105">Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.</span><span class="sxs-lookup"><span data-stu-id="aaea7-105">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="aaea7-106">Sex summorna kan jämföras på **fakturasummor matchande detaljer** .</span><span class="sxs-lookup"><span data-stu-id="aaea7-106">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="aaea7-107">Om någon av summorna avviker från den förväntade motsvarande inköpsorder totalt, en matchande avvikelse flaggas.</span><span class="sxs-lookup"><span data-stu-id="aaea7-107">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="aaea7-108">För att granska faktura som har summorna matchande avvikelser i **säljarens faktura** arbetsytan klickar du på den **väntande fakturor** panel.</span><span class="sxs-lookup"><span data-stu-id="aaea7-108">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="aaea7-109">Sedan, på rutan åtgärd, på **fliken granskning** klickar du **matchande detaljer**.</span><span class="sxs-lookup"><span data-stu-id="aaea7-109">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="aaea7-110">Om matchning skillnader har upptäckts, varningsikoner visas intill beloppet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="aaea7-110">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="aaea7-111">Du kan visa fler detaljer om summor på fakturasummor matchande detaljer.</span><span class="sxs-lookup"><span data-stu-id="aaea7-111">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="aaea7-112">När du identifierar en avvikelse, kan du behöva kontakta säljaren om du tycker att informationen på fakturan är felaktig.</span><span class="sxs-lookup"><span data-stu-id="aaea7-112">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="aaea7-113">Beroende på vilket avtal med säljaren kan du sedan ta någon av dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="aaea7-113">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="aaea7-114">Acceptera prisskillnaden och Bokför faktura som har matchande avvikelser.</span><span class="sxs-lookup"><span data-stu-id="aaea7-114">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="aaea7-115">Ditt system kan vara konfigurerat att kräva godkännande innan den kan posta om det finns motsvarande skillnader.</span><span class="sxs-lookup"><span data-stu-id="aaea7-115">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="aaea7-116">I detta fall måste du godkänna matchningen avvikelse och kan även ange ett godkännande kommentar.</span><span class="sxs-lookup"><span data-stu-id="aaea7-116">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="aaea7-117">Du kan sedan välja att kontera faktura.</span><span class="sxs-lookup"><span data-stu-id="aaea7-117">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="aaea7-118">Ändra fakturans belopp till det förväntade värdet och Bokför faktura.</span><span class="sxs-lookup"><span data-stu-id="aaea7-118">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="aaea7-119">Begära ett fullständigt erkännande och en ny korrigerad faktura från leverantören.</span><span class="sxs-lookup"><span data-stu-id="aaea7-119">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="aaea7-120">Mer information finns i [Undersöka eller lösa undantag](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="aaea7-120">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



