---
title: Konfigurara skattekomponenter för skattetypen TDS
description: I det här avsnittet beskrivs hur du ställer in källskattekomponenter för skattetypen Skatteavdrag vid källa (TDS). Här förklaras också hur du definierar den tröskelgräns som används för att beräkna TDS för varje TDS-komponent.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023593"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="61659-104">Konfigurara skattekomponenter för skattetypen TDS</span><span class="sxs-lookup"><span data-stu-id="61659-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61659-105">I det här avsnittet beskrivs hur du ställer in källskattekomponenter för skattetypen Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="61659-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="61659-106">TDS-komponenterna är TDS, tilläggsavgift, PE-Cess och SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="61659-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="61659-107">I det här avsnittet förklaras också hur du definierar den tröskel som används för att beräkna TDS för varje TDS-komponent.</span><span class="sxs-lookup"><span data-stu-id="61659-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="61659-108">Du kan dessutom definiera ett undantagströskelvärde som används för att beräkna TDS för varje TDS-komponent.</span><span class="sxs-lookup"><span data-stu-id="61659-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="61659-109">Följ dessa steg för att ställa in TDS-komponenter.</span><span class="sxs-lookup"><span data-stu-id="61659-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="61659-110">Gå till **Skatt \> Konfiguration \> Källskatt \> Källskattekomponenter**.</span><span class="sxs-lookup"><span data-stu-id="61659-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="61659-111">[![Sidan Källskattekomponenter](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="61659-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="61659-112">I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattekomponenter för skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="61659-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="61659-113">I åtgärdsfönstret, välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="61659-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="61659-114">I fältet **Källskattekomponenter** anger du ett namn på TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="61659-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="61659-115">I fältet **Källskattekomponentgrupp** väljer du källskattekomponentgruppen TDS som TDS-komponenten ska kopplas till.</span><span class="sxs-lookup"><span data-stu-id="61659-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="61659-116">På snabbfliken **Allmänt** i fältet **Beskrivning** anger du en beskrivning för TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="61659-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="61659-117">I åtgärdsfönstret väljer du **Tröskel** för att öppna sidan **Tröskel**, så att du kan definiera den tröskel som används för att beräkna TDS för TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="61659-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="61659-118">Använd fälten **Från-datum** och **Till-datum** för att definiera perioden som tröskeln gäller.</span><span class="sxs-lookup"><span data-stu-id="61659-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="61659-119">Under snabbfliken **Allmänt**, i fältet **Tröskel**, anger du tröskelvärdet som används för att beräkna TDS för TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="61659-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="61659-120">Skatten dras av vid källan bara när det ackumulerade fakturabeloppet går över tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="61659-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="61659-121">Om t.ex. tröskelbeloppet är 10 000 beräknas TDS efter att det ackumulerade fakturabeloppet överstiger 10 000 (d.v.s. när det är 10 001 eller mer).</span><span class="sxs-lookup"><span data-stu-id="61659-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="61659-122">I fältet **Undantagströskel** anger du undantagströskelvärdet som används för att beräkna TDS för TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="61659-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="61659-123">Skatten på en fakturarad dras av vid källan bara när beloppet går över undantagströskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="61659-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="61659-124">Om undantagströskelbeloppet till exempel är 5 000, beräknas TDS på en specifik fakturarad om fakturaradsbeloppet överstiger 5 000 (med andra ord om det är 5 001 eller mer).</span><span class="sxs-lookup"><span data-stu-id="61659-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="61659-125">[![Sidan Tröskel](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="61659-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="61659-126">Undantagströskeln måste vara mindre än eller lika med tröskelbeloppet.</span><span class="sxs-lookup"><span data-stu-id="61659-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="61659-127">Skatten dras av för en transaktion om transaktionsbeloppet går över undantagströskeln, även om det ackumulerade fakturabeloppet inte går över tröskelvärdet som har angetts i fältet **Tröskel**.</span><span class="sxs-lookup"><span data-stu-id="61659-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="61659-128">Stäng sidan **Tröskel** för att återgå till sidan **Källskattekomponenter**.</span><span class="sxs-lookup"><span data-stu-id="61659-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="61659-129">I åtgärdsfönstret väljer du **Kopiera** för att öppna dialogrutan **Kopiera källskattekomponenter**, så att du kan kopiera TDS-komponenter som konfigurerades för en TDS-komponentgrupp till en annan TDS-komponentgrupp.</span><span class="sxs-lookup"><span data-stu-id="61659-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="61659-130">I fältet **Från** väljer du den TDS-komponentgrupp som TDS-komponenterna ska kopieras från.</span><span class="sxs-lookup"><span data-stu-id="61659-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="61659-131">I fältet **Till** väljer du den källskattekomponentgrupp som TDS-komponenterna ska kopieras till.</span><span class="sxs-lookup"><span data-stu-id="61659-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61659-132">Vanliga TDS-komponenter som är kopplade till båda TDS-komponentgrupperna kopieras inte.</span><span class="sxs-lookup"><span data-stu-id="61659-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="61659-133">Välj **OK** för att kopiera och skapa TDS-komponenter för den andra TDS-komponentgruppen på sidan **Källskattekomponenter**.</span><span class="sxs-lookup"><span data-stu-id="61659-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="61659-134">[![Dialogrutan Kopiera källskattekomponenter](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="61659-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="61659-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="61659-135">Close the page.</span></span>
