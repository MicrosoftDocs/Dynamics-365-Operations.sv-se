---
title: Skriva ut rapporten för momsbetalning per kod
description: Det här avsnittet innehåller information om de inställningar och åtgärder som krävs för att skriva ut rapporten momsbetalning per kod i redovisnings- eller skattekodsvalutan.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eb3ee4a12d2d29c2769f1ae22e11dc05608b47c1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815462"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="1d4d0-103">Skriva ut rapporten för momsbetalning per kod</span><span class="sxs-lookup"><span data-stu-id="1d4d0-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d4d0-104">Om du vill skriva ut rapporten **momsbetalning per kod** gå till **moms** \> **förfrågningar och rapporter** \> **momsrapporter** \> **momsbetalning per kod**.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="1d4d0-105">Som standard genereras rapportbelopp i den juridiska personens redovisningsvaluta för alla rapportkoder som har ställts in på sidan **momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="1d4d0-106">Du kan också generera rapporten så att den visar momsbetalningsbeloppen i valutorna för momskoderna för alla rapportkoder som har tilldelats momskoderna på sidan **momskoder**.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="1d4d0-107">Aktivera en funktion</span><span class="sxs-lookup"><span data-stu-id="1d4d0-107">Turn on the feature</span></span>

<span data-ttu-id="1d4d0-108">I arbetsytan **funktionshantering** aktivera följande funktion: **Generera momsbetalningen per kodrapport i valutan för momsbetalningskod**.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="1d4d0-109">Köra rapporten</span><span class="sxs-lookup"><span data-stu-id="1d4d0-109">Run the report</span></span>

1. <span data-ttu-id="1d4d0-110">Gå till **Skatt** \> **Förfrågningar och rapporter** \> **Momsrapporter** \> **Momsbetalning per kod**.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="1d4d0-111">I fältet **rapportvaluta**, välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="1d4d0-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="1d4d0-112">**Redovisningsvaluta** – Skriv ut rapportbeloppen i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="1d4d0-113">**Momskodvaluta** – Skriv ut rapportbeloppen i momskodernas valutor.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Dialogrutan momsbetalning per kod](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="1d4d0-115">Den följande bilden visar ett exempel på den rapport som genereras.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="1d4d0-116">Rapporten visar att rapporteringskoden **101** har valutan **EUR** om fältet **momsvaluta** anges till **EUR** för den momskod som rapportkoden är tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="1d4d0-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Exempel på rapporten för momsbetalning per kod](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]