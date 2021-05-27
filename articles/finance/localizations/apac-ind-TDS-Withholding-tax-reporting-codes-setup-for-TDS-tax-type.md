---
title: Ställ in källskatterapporteringskoder för TDS-skattetypen
description: Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS). I det här avsnittet beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.
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
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023608"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="fb50a-104">Ställ in källskatterapporteringskoder för TDS-skattetypen</span><span class="sxs-lookup"><span data-stu-id="fb50a-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb50a-105">Källskatterapporteringskoder används för att generera utdrag från formulär 26Q och formulär 27Q för Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="fb50a-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="fb50a-106">I det här avsnittet beskrivs hur du ställer in steg för källskatterapporteringskoder så att du kan ställa in TDS-rapporteringskoder.</span><span class="sxs-lookup"><span data-stu-id="fb50a-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="fb50a-107">Gå till **Skatt \> Konfiguration \> Källskatt \> Källskatterapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="fb50a-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="fb50a-108">[![Sidan Källskatterapporteringskoder](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="fb50a-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="fb50a-109">I fältet **Skattetyp** väljer du **TDS** för att definiera källskatterapporteringskoder för skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="fb50a-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="fb50a-110">I fältet **Källskattekomponent** väljer du TDS-komponent som du definierar källskatterapporteringskoden för.</span><span class="sxs-lookup"><span data-stu-id="fb50a-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="fb50a-111">I fältet **Källskattekomponentgrupp** visas TDS-komponentgruppen som definierades för TDS-komponenten som du definierar.</span><span class="sxs-lookup"><span data-stu-id="fb50a-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="fb50a-112">I fältet **Avsnittskod** under snabbfliken **Allmänt** visas avsnittskoden som är kopplad till TDS-komponentgruppen.</span><span class="sxs-lookup"><span data-stu-id="fb50a-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="fb50a-113">Under snabbfliken **Allmänt**, i fältet **Raporteringskod**, väljer du TDS-rapporteringskod:</span><span class="sxs-lookup"><span data-stu-id="fb50a-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="fb50a-114">TDS</span><span class="sxs-lookup"><span data-stu-id="fb50a-114">TDS</span></span>
    - <span data-ttu-id="fb50a-115">TCS</span><span class="sxs-lookup"><span data-stu-id="fb50a-115">TCS</span></span>
    - <span data-ttu-id="fb50a-116">Tillägg</span><span class="sxs-lookup"><span data-stu-id="fb50a-116">Surcharge</span></span>
    - <span data-ttu-id="fb50a-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="fb50a-117">PE\_Cess</span></span>
    - <span data-ttu-id="fb50a-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="fb50a-118">SHE\_Cess</span></span>

5. <span data-ttu-id="fb50a-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb50a-119">Close the page.</span></span>
