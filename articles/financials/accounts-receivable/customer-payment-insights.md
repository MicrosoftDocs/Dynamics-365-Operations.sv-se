---
title: Kundbetalningsinsikter (förhandsgranskning)
description: Det här avsnittet beskriver hur insikter om kundbetalningar kan hjälpa till att förutsäga när en faktura ska betalas och hjälpa organisationer att optimera strategier som förbättrar sannolikheten att få betalt i tid.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566268"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="0b682-103">Kundbetalningsinsikter (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="0b682-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="0b682-104">Denna funktion ingår i en målinriktad uppdatering och är bara tillgänglig för användare som har valt privat förhandsvisning.</span><span class="sxs-lookup"><span data-stu-id="0b682-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="0b682-105">Denna funktion kommer att ingå i en kommande, allmänt tillgänglig version.</span><span class="sxs-lookup"><span data-stu-id="0b682-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="0b682-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="0b682-106">Overview</span></span>

<span data-ttu-id="0b682-107">Organisationer finner det ofta svårt att förutsäga när en kund betalar sina fakturor.</span><span class="sxs-lookup"><span data-stu-id="0b682-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="0b682-108">Denna brist på insyn kan leda till felaktiga kassaflödesprognoser, ineffektiva inkasseringsprocesser och risken att order levereras till kunder som kan utgöra en kreditrisk.</span><span class="sxs-lookup"><span data-stu-id="0b682-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="0b682-109">Insikter om kundbetalningar (förhandsgranskning) använder maskininlärning för att förutsäga när en faktura betalas.</span><span class="sxs-lookup"><span data-stu-id="0b682-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0b682-110">Den innehåller även optimeringsstrategier som kan skräddarsys för att maximera sannolikheten att kunderna betalar i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="0b682-111">Förutsägelser</span><span class="sxs-lookup"><span data-stu-id="0b682-111">Predictions</span></span>

<span data-ttu-id="0b682-112">Betalningsprognoser gör att organisationer kan förbättra sina affärsprocesser genom att:</span><span class="sxs-lookup"><span data-stu-id="0b682-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="0b682-113">Enkelt identifiera de fakturor som bedöms kan komma att betalas för sent.</span><span class="sxs-lookup"><span data-stu-id="0b682-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="0b682-114">Vidta lämpliga åtgärder för att öka sannolikheten för att få betalt i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="0b682-115">Insikter om kundbetalningar (förhandsgranskning) använder maskininlärning för att förutsäga när en faktura betalas.</span><span class="sxs-lookup"><span data-stu-id="0b682-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0b682-116">Här används historiska data om faktura, betalning och kund i syfte att skapa en modell för maskininlärning som används för att förutsäga när en faktura kommer att betalas.</span><span class="sxs-lookup"><span data-stu-id="0b682-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="0b682-117">Kundbetalningsinsikter (förhandsgranskning) förutsäger tre sannolikheter för betalning för respektive faktura:</span><span class="sxs-lookup"><span data-stu-id="0b682-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="0b682-118">Sannolikheten för betalning i tid (senast på fakturans förfallodatum).</span><span class="sxs-lookup"><span data-stu-id="0b682-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="0b682-119">Sannolikheten för betalning inom 30 dagar efter fakturans förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="0b682-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="0b682-120">Sannolikheten för betalning efter 30 dagar efter fakturans förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="0b682-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="0b682-121">Sannolikheten för betalningar kan visas i avsnittet om prognoser.</span><span class="sxs-lookup"><span data-stu-id="0b682-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="0b682-122">[![Betalningsprognoser](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="0b682-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="0b682-123">Varje faktura kopplas även till en primär betalningssannolikhet enligt någon av de tre beräknade sannolikheter för betalning enligt ovan.</span><span class="sxs-lookup"><span data-stu-id="0b682-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="0b682-124">Scenariot med bäst sannolikhet till betalning är vinnande scenario.</span><span class="sxs-lookup"><span data-stu-id="0b682-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="0b682-125">Låt oss till exempel anta att förutsägelsen för en faktura anger 71 procents sannolikhet att fakturan ska betalas i tid, 13 procents sannolikhet att fakturan ska betalas inom 30 dagar efter förfallodatum, och 16 procents sannolikhet att fakturan betalas efter 30 dagar efter förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="0b682-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="0b682-126">Den största sannolikheten visar att fakturan ska ingå i scenariot "i tid", varför fakturan kommer att märkas med sannolikheten att betalas i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="0b682-127">[![Betalningsförutsägelser](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="0b682-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="0b682-128">Optimeringsstrategier</span><span class="sxs-lookup"><span data-stu-id="0b682-128">Optimization strategies</span></span>

<span data-ttu-id="0b682-129">Utöver betalningsprognoser kan kundbetalningsinsikter (förhandsgranskning) optimera strategier för att öka risken för att få betalt i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="0b682-130">Detta gör det möjligt för organisationer att utföra "tänk om"-analyser genom att göra det möjligt för användare att justera faktura- kundparametrar och sedan jämföra motsvarande effekt baserat på möjligheten att få fakturainbetalningar i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="0b682-131">En organisation kanske exempelvis vill utvärdera effekten av att uppdatera kassarabatten på fakturor baserat på sannolikheten att erhålla betalningen i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="0b682-132">När fakturorna optimeras för att använda den nya rabatten kan användarna studera effekten av att tillämpa rabatten baserat på sannolikheten för att ta emot betalningar för dessa fakturor i tid.</span><span class="sxs-lookup"><span data-stu-id="0b682-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="0b682-133">Om kostnaden för att tillämpa rabatten är minimal i jämförelse med förmånen att få betalt i tid, kan organisationen välja att tillämpa vald rabatt på alla framtida, öppna order.</span><span class="sxs-lookup"><span data-stu-id="0b682-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="0b682-134">För närvarande finns endast rabatt som en optimeringsstrategi för insikter om kundbetalningar (förhandsgranskning).</span><span class="sxs-lookup"><span data-stu-id="0b682-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="0b682-135">[![Optimerade prognoser](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="0b682-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="0b682-136">Hur du får insikter om kundbetalningar (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="0b682-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="0b682-137">Om du är intresserad av att testa insikter om kundbetalningar (förhandsgranskning), e-posta då [Förhandsgranskningsteamet för finansiella insikter](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0b682-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="0b682-138">Sekretessmeddelande</span><span class="sxs-lookup"><span data-stu-id="0b682-138">Privacy Statement</span></span>

<span data-ttu-id="0b682-139">Förhandsgranskning lagrar kunddata i USA.</span><span class="sxs-lookup"><span data-stu-id="0b682-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="0b682-140">Förhandsgranskningar (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 for Finance and Operations de (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="0b682-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>
