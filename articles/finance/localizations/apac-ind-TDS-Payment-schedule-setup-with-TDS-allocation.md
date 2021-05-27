---
title: Ställ in betalningsplaner med TDS-allokering
description: I det här avsnittet beskrivs hur du ställer in betalningsplaner med TDS-allokering (skatteavdrag vid källan).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023606"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="43b05-103">Ställ in betalningsplaner med TDS-allokering</span><span class="sxs-lookup"><span data-stu-id="43b05-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43b05-104">I det här avsnittet beskrivs hur du ställer in betalningsplaner med TDS-allokering (skatteavdrag vid källan).</span><span class="sxs-lookup"><span data-stu-id="43b05-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="43b05-105">Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsplaner**.</span><span class="sxs-lookup"><span data-stu-id="43b05-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="43b05-106">[![Sidan Betalningsplaner](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="43b05-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="43b05-107">I åtgärdsfönstret väljer du **Ny** för att skapa en betalningsplan och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="43b05-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="43b05-108">I fältet **Allokering** väljer du den metod som ska användas för att allokera betalningen för betalningsplanen:</span><span class="sxs-lookup"><span data-stu-id="43b05-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="43b05-109">Totalt</span><span class="sxs-lookup"><span data-stu-id="43b05-109">Total</span></span>
    - <span data-ttu-id="43b05-110">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="43b05-110">Fixed amount</span></span>
    - <span data-ttu-id="43b05-111">Fast kvantitet</span><span class="sxs-lookup"><span data-stu-id="43b05-111">Fixed quantity</span></span>
    - <span data-ttu-id="43b05-112">Angivet</span><span class="sxs-lookup"><span data-stu-id="43b05-112">Specified</span></span>

    <span data-ttu-id="43b05-113">I fältet **Källskatteallokering** visas TDS-allokeringsmetoden för betalningsplanen.</span><span class="sxs-lookup"><span data-stu-id="43b05-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="43b05-114">Om du väljer **Totalt** i fältet **Allokering** ställs fältet **Källskatteallokering** automatiskt in på **Totalt**.</span><span class="sxs-lookup"><span data-stu-id="43b05-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="43b05-115">Om du väljer **Fast belopp**, **Fast kvantitet** eller **Specificerat** i fältet **Allokering**, ställs fältet **Källskatteallokering** automatiskt in på **Proportionellt**.</span><span class="sxs-lookup"><span data-stu-id="43b05-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="43b05-116">Om fältet **Källskatteallokering** är inställt på **Totalt**, beräknas avbetalningarna baserat på bruttobeloppet, som inbegriper TDS-beloppet.</span><span class="sxs-lookup"><span data-stu-id="43b05-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="43b05-117">Om fältet **Källskatteallokering** är inställt på **Proportionellt**, beräknas avbetalningarna baserat på fakturans nettobelopp, efter avdrag av TDS-beloppet.</span><span class="sxs-lookup"><span data-stu-id="43b05-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="43b05-118">Ange andra uppgifter som behövs och stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="43b05-118">Enter the other required details, and then close the page.</span></span>
