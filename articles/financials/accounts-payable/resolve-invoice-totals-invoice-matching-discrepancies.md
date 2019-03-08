---
title: Åtgärda avvikelser under matchning av fakturasummor
description: Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67aa0b89eed1f82290659029dfcce92ca3710aea
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "331516"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="5a20c-103">Åtgärda avvikelser under matchning av fakturasummor</span><span class="sxs-lookup"><span data-stu-id="5a20c-103">Resolve discrepancies during invoice totals matching</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a20c-104">En typ av fakturakontroll validering är fakturasummor matchning.</span><span class="sxs-lookup"><span data-stu-id="5a20c-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="5a20c-105">Ange att systemet ska utföra fakturasummor matchning på **leverantörsskulder parametrar sidan** , på **fakturan fliken validering** , **matchar fakturasummor** alternativet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5a20c-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="5a20c-106">Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.</span><span class="sxs-lookup"><span data-stu-id="5a20c-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="5a20c-107">Sex summorna kan jämföras på **fakturasummor matchande detaljer** .</span><span class="sxs-lookup"><span data-stu-id="5a20c-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="5a20c-108">Om någon av summorna avviker från den förväntade motsvarande inköpsorder totalt, en matchande avvikelse flaggas.</span><span class="sxs-lookup"><span data-stu-id="5a20c-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="5a20c-109">För att granska faktura som har summorna matchande avvikelser i **säljarens faktura** arbetsytan klickar du på den **väntande fakturor** panel.</span><span class="sxs-lookup"><span data-stu-id="5a20c-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="5a20c-110">Sedan, på rutan åtgärd, på **fliken granskning** klickar du **matchande detaljer**.</span><span class="sxs-lookup"><span data-stu-id="5a20c-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="5a20c-111">Om matchning skillnader har upptäckts, varningsikoner visas intill beloppet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="5a20c-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="5a20c-112">Du kan visa fler detaljer om summor på fakturasummor matchande detaljer.</span><span class="sxs-lookup"><span data-stu-id="5a20c-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="5a20c-113">När du identifierar en avvikelse, kan du behöva kontakta säljaren om du tycker att informationen på fakturan är felaktig.</span><span class="sxs-lookup"><span data-stu-id="5a20c-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="5a20c-114">Beroende på vilket avtal med säljaren kan du sedan ta någon av dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="5a20c-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="5a20c-115">Acceptera prisskillnaden och Bokför faktura som har matchande avvikelser.</span><span class="sxs-lookup"><span data-stu-id="5a20c-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="5a20c-116">Ditt system kan vara konfigurerat att kräva godkännande innan den kan posta om det finns motsvarande skillnader.</span><span class="sxs-lookup"><span data-stu-id="5a20c-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="5a20c-117">I detta fall måste du godkänna matchningen avvikelse och kan även ange ett godkännande kommentar.</span><span class="sxs-lookup"><span data-stu-id="5a20c-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="5a20c-118">Du kan sedan välja att kontera faktura.</span><span class="sxs-lookup"><span data-stu-id="5a20c-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="5a20c-119">Ändra fakturans belopp till det förväntade värdet och Bokför faktura.</span><span class="sxs-lookup"><span data-stu-id="5a20c-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="5a20c-120">Begära ett fullständigt erkännande och en ny korrigerad faktura från leverantören.</span><span class="sxs-lookup"><span data-stu-id="5a20c-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="5a20c-121">Mer information finns i [Undersöka eller lösa undantag](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="5a20c-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


