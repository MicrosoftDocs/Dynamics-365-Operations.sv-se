---
title: Ställ in källskattekoder för TDS-skattetypen
description: I det här avsnittet beskrivs hur du konfigurerar skattekoder för skatteavdrag vid källan (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023610"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="3a52a-103">Ställ in källskattekoder för TDS-skattetypen</span><span class="sxs-lookup"><span data-stu-id="3a52a-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a52a-104">I det här avsnittet beskrivs hur du konfigurerar skattekoder för skatteavdrag vid källan (TDS).</span><span class="sxs-lookup"><span data-stu-id="3a52a-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="3a52a-105">Gå till **Skatt \> Indirekt skatt \> Källskatt \> Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="3a52a-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="3a52a-106">[![Sidan Källskattekoder](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="3a52a-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="3a52a-107">I åtgärdsfönstret väljer du **Ny** för att skapa en källskattekod för TDS och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="3a52a-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="3a52a-108">Under snabbfliken **Allmänt**, i fältet **Skattetyp**, väljer du **TDS** för att kategorisera skattekoder som en TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="3a52a-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="3a52a-109">I fältet **Kvittningsperiod** väljer du TDS-kvittningsperioden för TDS-skattekoden.</span><span class="sxs-lookup"><span data-stu-id="3a52a-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="3a52a-110">I fältet **Huvudkonto** väljer du redovisningskontot som TDS-beloppet ska bokföras i.</span><span class="sxs-lookup"><span data-stu-id="3a52a-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="3a52a-111">I fältet **Kundreskontrakonto** väljer du det kundreskontrakonto som TDS-beloppet som dras av i försäljningstransaktioner ska bokföras i.</span><span class="sxs-lookup"><span data-stu-id="3a52a-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="3a52a-112">Fältet **Ursprung** ställs automatiskt in på **Procentandel av bruttobelopp**, och värdet kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="3a52a-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a52a-113">Du kan inte ställa in ursprunget på **Procentandel av nettobelopp** för skattekoder av skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="3a52a-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="3a52a-114">I fältet **Källskattekomponent** väljer du TDS-skattekomponenten för TDS-skattekoden.</span><span class="sxs-lookup"><span data-stu-id="3a52a-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="3a52a-115">I åtgärdsfönstret väljer du **Värden** för att öppna sidan **Källskattevärden**.</span><span class="sxs-lookup"><span data-stu-id="3a52a-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="3a52a-116">I fältet **Från-datum** anger du startdatum för TDS-värdet.</span><span class="sxs-lookup"><span data-stu-id="3a52a-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="3a52a-117">I fältet **Till-datum** anger du slutdatum.</span><span class="sxs-lookup"><span data-stu-id="3a52a-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a52a-118">Fälten **Nedre gräns**, **Övre gräns** och **Exkludera %** är inte tillgängliga för skattekoder av skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="3a52a-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="3a52a-119">I fältet **Värde** anger du procentandelen av TDS för TDS-skattekoden.</span><span class="sxs-lookup"><span data-stu-id="3a52a-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="3a52a-120">Stäng sidan **Källskattevärden** för att återgå till sidan **Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="3a52a-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a52a-121">Knappen **Gränser** på sidan **Källskattekoder** är inte tillgänglig för skattekoder av skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="3a52a-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="3a52a-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3a52a-122">Close the page.</span></span>
