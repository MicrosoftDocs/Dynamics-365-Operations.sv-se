---
title: Förbättra prediktionsmodellen (förhandsversion)
description: I det här avsnittet beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 2bcdea4a2a8f4386b274077cd1e95398fb6fac37
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009382"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="5953b-103">Förbättra prediktionsmodellen (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="5953b-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5953b-104">I det här avsnittet beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller.</span><span class="sxs-lookup"><span data-stu-id="5953b-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="5953b-105">Du börjar förbättra din modell på arbetsytan **Prediktioner av kundbetalning** i Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="5953b-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="5953b-106">Förbättringsstegen slutförs sedan i AI Builder.</span><span class="sxs-lookup"><span data-stu-id="5953b-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="5953b-107">Välj historiska resultat</span><span class="sxs-lookup"><span data-stu-id="5953b-107">Select historical outcomes</span></span>

<span data-ttu-id="5953b-108">Du väljer först ett eller flera av de tre möjliga resultaten för fakturor: **i tid**, **sent** och **mycket sent**.</span><span class="sxs-lookup"><span data-stu-id="5953b-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="5953b-109">Alla tre resultat ska väljas.</span><span class="sxs-lookup"><span data-stu-id="5953b-109">All three outcomes should be selected.</span></span> <span data-ttu-id="5953b-110">Om du avmarkerar något av resultaten kommer fakturorna att filtreras bort från träningsprocessen och noggrannheten i förutsägelsen försämras.</span><span class="sxs-lookup"><span data-stu-id="5953b-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="5953b-111">[![Bekräfta resultat](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="5953b-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="5953b-112">Om din organisation bara behöver två resultat ändrar du tröskelvärdena **Sent** och **Mycket sent** till 0 (noll) dagar.</span><span class="sxs-lookup"><span data-stu-id="5953b-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="5953b-113">På så sätt komprimerar du på ett effektivt sätt förutsägelsen till en binär status av **I tid** eller **Sent**.</span><span class="sxs-lookup"><span data-stu-id="5953b-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="5953b-114">Välj fält</span><span class="sxs-lookup"><span data-stu-id="5953b-114">Select fields</span></span>

<span data-ttu-id="5953b-115">När du väljer fält som ska ingå i modellen måste du vara medveten om att listan innehåller alla tillgängliga fält i Microsoft Dataverse-registret som har mappats till datan i Azure-datasjön.</span><span class="sxs-lookup"><span data-stu-id="5953b-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="5953b-116">Vissa av dessa fält bör **inte** väljas.</span><span class="sxs-lookup"><span data-stu-id="5953b-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="5953b-117">De fält som inte ska väljas finns i en av tre kategorier:</span><span class="sxs-lookup"><span data-stu-id="5953b-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="5953b-118">Fältet är obligatoriskt för Dataverse-registret, men det finns inga säkerhetskopierade data för det i datasjön.</span><span class="sxs-lookup"><span data-stu-id="5953b-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="5953b-119">Fältet är ett ID och passar därför inte för maskininlärningsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5953b-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="5953b-120">Fältet visar information som inte är tillgänglig under förutsägelse.</span><span class="sxs-lookup"><span data-stu-id="5953b-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="5953b-121">I följande avsnitt visas de fält som är tillgängliga för entiteterna faktura och kund, och där listas de fält som **inte** ska väljas för träning.</span><span class="sxs-lookup"><span data-stu-id="5953b-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="5953b-122">Kategorin som anges för vart och ett av fälten refererar till kategorierna i föregående lista.</span><span class="sxs-lookup"><span data-stu-id="5953b-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="5953b-123">Fakturaregister för Dataverse</span><span class="sxs-lookup"><span data-stu-id="5953b-123">Invoice Dataverse table</span></span>

<span data-ttu-id="5953b-124">I följande illustrationer visar de fält som är tillgängliga för fakturaregistret.</span><span class="sxs-lookup"><span data-stu-id="5953b-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="5953b-125">[![Tillgängliga fält för fakturaregistret](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="5953b-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="5953b-126">Följande fält ska inte väljas för träning:</span><span class="sxs-lookup"><span data-stu-id="5953b-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="5953b-127">**Fakturakonto** (kategori 2)</span><span class="sxs-lookup"><span data-stu-id="5953b-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="5953b-128">**Är stängt** (kategori 3) – Det här fältet används för att filtrera fakturor för träning (stängt) och förutsägelse (ej stängt).</span><span class="sxs-lookup"><span data-stu-id="5953b-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="5953b-129">**Namn** (kategori 1)</span><span class="sxs-lookup"><span data-stu-id="5953b-129">**Name** (category 1)</span></span>
- <span data-ttu-id="5953b-130">**Käll-ID** (kategori 2)</span><span class="sxs-lookup"><span data-stu-id="5953b-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="5953b-131">**Källpost** (kategori 2)</span><span class="sxs-lookup"><span data-stu-id="5953b-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="5953b-132">**Källtabell** (kategori 2)</span><span class="sxs-lookup"><span data-stu-id="5953b-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="5953b-133">Kundregister för Dataverse</span><span class="sxs-lookup"><span data-stu-id="5953b-133">Customer Dataverse table</span></span>

<span data-ttu-id="5953b-134">I följande illustrationer visas de fält som är tillgängliga för kundregistret.</span><span class="sxs-lookup"><span data-stu-id="5953b-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="5953b-135">[![Tillgängliga fält för kundregistret](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="5953b-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="5953b-136">Följande fält ska inte väljas för träning:</span><span class="sxs-lookup"><span data-stu-id="5953b-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="5953b-137">**Radens unika nyckel** (kategori 2)</span><span class="sxs-lookup"><span data-stu-id="5953b-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="5953b-138">Filter</span><span class="sxs-lookup"><span data-stu-id="5953b-138">Filters</span></span>

<span data-ttu-id="5953b-139">Filtren stöder för närvarande inte scenariot för förutsägelser av kundbetalning.</span><span class="sxs-lookup"><span data-stu-id="5953b-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="5953b-140">Välj därför **Hoppa över detta steg** och fortsätt till sammanfattningssidan.</span><span class="sxs-lookup"><span data-stu-id="5953b-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="5953b-141">[![Fokusmodell med filter](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="5953b-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="5953b-142">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="5953b-142">Privacy notice</span></span>
<span data-ttu-id="5953b-143">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="5953b-143">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
