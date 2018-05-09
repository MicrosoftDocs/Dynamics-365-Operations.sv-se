--- 
title: "Ställ in leverantörer och leverantörsbankkonton för ISO20022-krediteringsöverföringar"
description: "I den här proceduren visas hur du ställer in den specifika information om leverantören och leverantörens specifika bankkonto som krävs för att generera ISO20022-kreditöverföringen eller någon annan fil för leverantörsbetalning."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7b489587097f2f10663a7cfb745ce1d17985b432
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="305d0-103">Ställ in leverantörer och leverantörsbankkonton för ISO20022-krediteringsöverföringar</span><span class="sxs-lookup"><span data-stu-id="305d0-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="305d0-104">I den här proceduren visas hur du ställer in den specifika information om leverantören och leverantörens specifika bankkonto som krävs för att generera ISO20022-kreditöverföringen eller någon annan fil för leverantörsbetalning.</span><span class="sxs-lookup"><span data-stu-id="305d0-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="305d0-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="305d0-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="305d0-106">Detta är den fjärde proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="305d0-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="305d0-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="305d0-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="305d0-108">Ställ in bankdetaljer</span><span class="sxs-lookup"><span data-stu-id="305d0-108">Set up bank details</span></span>
1. <span data-ttu-id="305d0-109">Gå till leverantörsreskontra > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="305d0-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="305d0-110">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="305d0-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="305d0-111">Filtrera till exempel efter fältet Leverantörskonto med värdet "DE-001".</span><span class="sxs-lookup"><span data-stu-id="305d0-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="305d0-112">Klicka på DE-001 om du vill öppna leverantörsinformationen.</span><span class="sxs-lookup"><span data-stu-id="305d0-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="305d0-113">Klicka på Leverantör i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="305d0-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="305d0-114">Klicka på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="305d0-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="305d0-115">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="305d0-115">Click Edit.</span></span>
    * <span data-ttu-id="305d0-116">Om det inte finns något tillgängligt bankkonto, måste du skapa ett nytt.</span><span class="sxs-lookup"><span data-stu-id="305d0-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="305d0-117">Skriv "COBADEFFXXX" i fältet SWIFT-kod.</span><span class="sxs-lookup"><span data-stu-id="305d0-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="305d0-118">Skriv "DE36200400000628808808" i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="305d0-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="305d0-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="305d0-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="305d0-120">Ställ in betalningsmetod för leverantören</span><span class="sxs-lookup"><span data-stu-id="305d0-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="305d0-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="305d0-121">Click Edit.</span></span>
2. <span data-ttu-id="305d0-122">Visa eller dölj avsnittet Betalning.</span><span class="sxs-lookup"><span data-stu-id="305d0-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="305d0-123">I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="305d0-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="305d0-124">I listan klickar du på länken på SEPA CT-raden.</span><span class="sxs-lookup"><span data-stu-id="305d0-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="305d0-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="305d0-125">Click Save.</span></span>


