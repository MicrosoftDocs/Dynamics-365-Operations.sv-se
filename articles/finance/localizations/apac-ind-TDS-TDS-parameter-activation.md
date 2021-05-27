---
title: Ställ in TDS-parametrar
description: I det här avsnittet beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner. Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023596"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="b9c5d-104">Ställ in TDS-parametrar</span><span class="sxs-lookup"><span data-stu-id="b9c5d-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9c5d-105">I det här avsnittet beskrivs hur du ställer in parametrar för att aktivera funktionen Skatteavdrag vid källa (TDS) i angivna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="b9c5d-106">Detta är ett nödvändigt steg för att använda funktionen Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="b9c5d-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="b9c5d-107">Gå till **Redovisning \> Redovisningsinställning \> Allmänna redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="b9c5d-108">Under fliken **Direkta skatter**, i avsnittet **Skatteavdrag vid källa**, ställer du in alternativet **Aktivera TDS** på **Ja** för att aktivera TDS-funktionaliteten och sidorna och fälten som används för den.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="b9c5d-109">Ställ in alternativet **Faktura** på **Ja** för att aktivera fälten som används för att beräkna och dra av TDS på fakturanivå.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="b9c5d-110">Ställ in alternativet **Betalning** på **Ja** för att aktivera fälten som används för att beräkna och dra av TDS på betalningsnivå.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="b9c5d-111">[![Fliken Direkt skatt](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="b9c5d-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="b9c5d-112">Under fliken **Nummersekvenser** letar du upp raden där fältet **Referens** är inställt på **Betalning av källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="b9c5d-113">I fältet **Nummersekvenskod** för raden väljer du nummersekvenskoden.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="b9c5d-114">Nummersekvenskoden används för att generera verifikationsnummer för den periodiska TDS-kvittningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9c5d-115">Om du vill köra den periodiska TDS-kvittningsprocessen går du till **Skatt \> Deklarationer \> Källskatt \> Betalning av källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="b9c5d-116">[![Fliken Nummerserie](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="b9c5d-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="b9c5d-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b9c5d-117">Close the page.</span></span>
