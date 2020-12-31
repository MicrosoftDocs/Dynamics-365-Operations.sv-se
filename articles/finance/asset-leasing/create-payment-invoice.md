---
title: Skapa betalningsfakturor
description: Det här avsnittet innehåller information om hur du skapar månatliga leasingfakturor. Du kan skapa fakturor för enskilda leasingar eller använda en batchprocess för att skapa dem för flera leasingar.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 32618814d00cb1e1f1082169a64b187cce1e76b4
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448195"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="1128b-104">Skapa betalningsfakturor</span><span class="sxs-lookup"><span data-stu-id="1128b-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1128b-105">Du kan skapa månatliga fakturor för enskilda leasingar eller använda en batchprocess för att skapa dem för flera leasingar.</span><span class="sxs-lookup"><span data-stu-id="1128b-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="1128b-106">Följande procedur visar hur du skapar en enskild leasingbetalningspost när parametern **Betala till leverantör** på sidan **Konfiguration av leasingbok** aktiveras.</span><span class="sxs-lookup"><span data-stu-id="1128b-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="1128b-107">På sidan **Sammanfattning av leasing** väljer du en leasing och väljer sedan **Böcker \> Betalningsplan**.</span><span class="sxs-lookup"><span data-stu-id="1128b-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="1128b-108">Välj den betalning som måste göras och välj sedan **Skapa journal**.</span><span class="sxs-lookup"><span data-stu-id="1128b-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="1128b-109">Ett meddelande visas om att en journal har skapats mot den valda betalningen.</span><span class="sxs-lookup"><span data-stu-id="1128b-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="1128b-110">Välj **Fakturajournaler** och välj sedan den faktura som måste betalas.</span><span class="sxs-lookup"><span data-stu-id="1128b-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="1128b-111">På fliken **Rader** granskar du journalposten innan du bokför den i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="1128b-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1128b-112">Som standard använder leverantörsfakturaraderna som skapas bokföringsprofilen från sidan **Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="1128b-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="1128b-113">Välj rätt journal och välj sedan den faktura som måste betalas.</span><span class="sxs-lookup"><span data-stu-id="1128b-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="1128b-114">I det här exemplet aktiveras parametern **Betala till leverantör** i leasingboken.</span><span class="sxs-lookup"><span data-stu-id="1128b-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="1128b-115">Därför kommer fakturan att finnas i fakturajournalen.</span><span class="sxs-lookup"><span data-stu-id="1128b-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="1128b-116">I avsnittet **Översikt** visas en sammanfattning av journalposten och i avsnittet **Rader** visas information om de faktiska journalraderna.</span><span class="sxs-lookup"><span data-stu-id="1128b-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1128b-117">Om parametern **Betala till leverantör** är inaktiverad kommer betalningsjournalposter att visas på sidan **Leasing av tillgångar** för leasingboken, och systemet skapar en post för leasingtillgångar i stället för en faktura.</span><span class="sxs-lookup"><span data-stu-id="1128b-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="1128b-118">Leasingbetalningsposten kommer att bokföras till det journalnamn som anges i fältet **Månatlig leasingjournal**.</span><span class="sxs-lookup"><span data-stu-id="1128b-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="1128b-119">När transaktionen har bokförts kan du visa transaktionsinformation och det bokförda värdet för leasingskulden genom att välja **Skuldtransaktioner** i leasingboken.</span><span class="sxs-lookup"><span data-stu-id="1128b-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="1128b-120">I betalningsplanen markeras kryssrutan **Journal bokförd** och raden visar fakturajournalnumret.</span><span class="sxs-lookup"><span data-stu-id="1128b-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="1128b-121">När en betalningsjournal och en post för journalen har skapats, måste du återföra posten innan den kan skapas på nytt.</span><span class="sxs-lookup"><span data-stu-id="1128b-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>
