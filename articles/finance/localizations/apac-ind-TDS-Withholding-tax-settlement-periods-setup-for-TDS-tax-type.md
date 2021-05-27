---
title: Ställ in kvittningsperioder för källskatt för TDS-skattetyp
description: I det här avsnittet beskrivs hur du ställer in kvittningsperioder för kvittningsperioder för funktionen Skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023585"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="e0b4c-103">Ställ in kvittningsperioder för källskatt för TDS-skattetyp</span><span class="sxs-lookup"><span data-stu-id="e0b4c-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0b4c-104">I det här avsnittet beskrivs hur du ställer in kvittningsperioder för kvittningsperioder för funktionen Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="e0b4c-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="e0b4c-105">Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekvittningsperioder**.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="e0b4c-106">[![Sidan Källskattekvittningsperioder](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="e0b4c-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="e0b4c-107">I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattekvittningsperioder för skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="e0b4c-108">Klicka på **Nytt** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="e0b4c-109">I fältet **Kvittningsperiod** anger du ett namn på TDS-kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="e0b4c-110">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="e0b4c-111">I fältet **Källskattemyndighet** väljer du TDS-myndighet som du definierar TDS-kvittningsperioden för.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="e0b4c-112">Under snabbfliken **Allmänt**, i fältet **Periodintervall**, väljer du typen av periodintervall för TDS-kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="e0b4c-113">I fältet **Antal enheter** anger du antalet enheter för periodintervalltypen.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="e0b4c-114">Under snabbfliken **Perioder**, i fältet **Från-datum**, väljer du startdatum för TDS-kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="e0b4c-115">I fältet **Till-datum** anger du slutdatum.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="e0b4c-116">Om du vill skapa en efterföljande TDS-kvittningsperiod för en befintlig period, baserat på periodintervallet och periodenheterna, väljer du **Ny period**.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="e0b4c-117">Om du vill visa information om den periodiska TDS-kvittning som körs för en viss kvittningsperiod väljer du **Källskattebetalningar** för att öppna sidan **Källskattebetalning**.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0b4c-118">Om du vill köra den periodiska TDS-kvittningsprocessen går du till **Redovisning \> Periodisk \> Källskatt \> Betalning av källskatt**.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="e0b4c-119">[![Sidan Betalning av källskatt](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="e0b4c-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="e0b4c-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-120">Close the page.</span></span>
