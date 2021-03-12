---
title: Kassaflödesprognos (förhandsversion)
description: I det här avsnittet beskrivs funktionen för kassaflödesprognos.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
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
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0df58d3571b124acbd1edbc6d6acdd49479c309e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990599"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="072bf-103">Kassaflödesprognos (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="072bf-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="072bf-104">Kassaflödet är kritiskt för alla företag.</span><span class="sxs-lookup"><span data-stu-id="072bf-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="072bf-105">Till och med lönsamma företag kan bli insolventa om de inte upprätthåller kassaflödet för att uppfylla omedelbara behov.</span><span class="sxs-lookup"><span data-stu-id="072bf-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="072bf-106">Prognosfunktionerna för kassaflöde i Finance-insikter gör det enklare för företag att övervaka och hantera sina kontantsaldon effektivt.</span><span class="sxs-lookup"><span data-stu-id="072bf-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="072bf-107">Funktionen använder maskininlärning för att hjälpa företag prognostisera kassaflöden mer noggrant än tidigare.</span><span class="sxs-lookup"><span data-stu-id="072bf-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="072bf-108">Den kan också hjälpa chefer att fatta beslut som optimerar affärsmöjligheter i samband med deras aktuella kassaposition.</span><span class="sxs-lookup"><span data-stu-id="072bf-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="072bf-109">För de flesta företag, är hantering av kassaflöde och körning av kassaflödesprognoser är en omständlig, repetitiv och manuell process.</span><span class="sxs-lookup"><span data-stu-id="072bf-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="072bf-110">De flesta företag använder Microsoft Excel-lösningar med varierande grad av komplexitet.</span><span class="sxs-lookup"><span data-stu-id="072bf-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="072bf-111">Utmaningarna med att korrekt prognostisera kassaflödet är bland andra:</span><span class="sxs-lookup"><span data-stu-id="072bf-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="072bf-112">Data är inte tillgängliga för beslutsfattarna eftersom de är spridda på flera ställen, bland annat:</span><span class="sxs-lookup"><span data-stu-id="072bf-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="072bf-113">Redovisnings- eller planeringssystem för företagsresurser</span><span class="sxs-lookup"><span data-stu-id="072bf-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="072bf-114">Programvara för ekonomisk planering</span><span class="sxs-lookup"><span data-stu-id="072bf-114">Financial planning software</span></span>
  - <span data-ttu-id="072bf-115">Excel</span><span class="sxs-lookup"><span data-stu-id="072bf-115">Excel</span></span>
  - <span data-ttu-id="072bf-116">Ytterligare programvarutillämpningar</span><span class="sxs-lookup"><span data-stu-id="072bf-116">Additional software applications</span></span> 
- <span data-ttu-id="072bf-117">Prognoser baseras på interna kunskaper som finns i "silor" inom varje domän eller avdelning.</span><span class="sxs-lookup"><span data-stu-id="072bf-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="072bf-118">Att mäta noggrannheten i kassaflödesprognoser när ekonomin har realiserats är osäkert och svårt.</span><span class="sxs-lookup"><span data-stu-id="072bf-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="072bf-119">Information om funktionen för kassaflödesprognoser</span><span class="sxs-lookup"><span data-stu-id="072bf-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="072bf-120">Funktionen Kassaflödesprognoser omfattar följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="072bf-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="072bf-121">Gör det enkelt att integrera kassaflödesdata från externa system till Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="072bf-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="072bf-122">Kassaflödesprognoser kan också använda ramverket för import-export av data.</span><span class="sxs-lookup"><span data-stu-id="072bf-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="072bf-123">Detta ramverk gör det enkelt att integrera med Excel OData.</span><span class="sxs-lookup"><span data-stu-id="072bf-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="072bf-124">Du kan också kombinera data från flera källor för att skapa en omfattande kassaflödeslösning.</span><span class="sxs-lookup"><span data-stu-id="072bf-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="072bf-125">Introducerar intelligent kassaposition.</span><span class="sxs-lookup"><span data-stu-id="072bf-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="072bf-126">Kassapositionen skapas utifrån kundens betalningsbeteende för att förutsäga när ett företag kan förvänta sig kontanter att anlända till sina konton.</span><span class="sxs-lookup"><span data-stu-id="072bf-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="072bf-127">Den analyserar också historiska mönster för att betala leverantörer, för att förutsäga när framtida fakturor och order sannolikt ska betalas.</span><span class="sxs-lookup"><span data-stu-id="072bf-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="072bf-128">Introducerar intelligenta kassaflödesprognoser för långsiktiga prognoser, med hjälp av tidsserieprognoser via automatisk integrering med AI Builder.</span><span class="sxs-lookup"><span data-stu-id="072bf-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="072bf-129">Ger möjlighet att spara specifika kassaflödespositioner och prognoser, redigera dem och sedan enkelt jämföra och mäta prognosresultatet med den faktiska ekonomin.</span><span class="sxs-lookup"><span data-stu-id="072bf-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="072bf-130">Möjliggör konsekvensanalys via jämförelser av ögonblicksbilder.</span><span class="sxs-lookup"><span data-stu-id="072bf-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="072bf-131">Du kan till exempel skapa flera ögonblicksbilder som representerar optimistiska, pessimistiska och mest realistiska vyer av ditt kassaflöde och sedan jämföra och visa skillnaderna.</span><span class="sxs-lookup"><span data-stu-id="072bf-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="072bf-132">Ger möjlighet att visa kassaflödesprognosen i flera valutor, för juridiska personer och filtrera och visa kassaflöden som hör till ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="072bf-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="072bf-133">Gör att du kan filtrera och visa bankkonton som hör till ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="072bf-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="072bf-134">Med funktionen för kassaflödesprognos i Dynamics 365 Finance kan din organisation omvandla omständliga, komplexa och repetitiva kassaflödesprognoser till en enkel, automatiserad process.</span><span class="sxs-lookup"><span data-stu-id="072bf-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="072bf-135">Genom att automatisera de mest omständliga aspekterna av kassaflödesprognoser kan du fokusera på de viktiga beslut som behövs för att driva fram önskade affärsresultat.</span><span class="sxs-lookup"><span data-stu-id="072bf-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="072bf-136">Konfigurera dimensioner för kassaflödesprognoser</span><span class="sxs-lookup"><span data-stu-id="072bf-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="072bf-137">Med en ny flik på sidan **Konfiguration av kassaflödesprognos** kan du kontrollera vilka ekonomiska dimensioner som ska användas för filtreringen i arbetsytan **Kassaflödesprognoser**.</span><span class="sxs-lookup"><span data-stu-id="072bf-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="072bf-138">Den här fliken visas endast om funktionen Kassaflödesprognoser är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="072bf-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="072bf-139">På fliken **Dimensioner** väljer du i listan med dimensioner som ska användas för filtrering och flyttar dem till den högra kolumnen med piltangenterna.</span><span class="sxs-lookup"><span data-stu-id="072bf-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="072bf-140">Endast två dimensioner kan väljas för filtrering av kassaflödesprognosdata.</span><span class="sxs-lookup"><span data-stu-id="072bf-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

#### <a name="privacy-notice"></a><span data-ttu-id="072bf-141">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="072bf-141">Privacy notice</span></span>
<span data-ttu-id="072bf-142">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="072bf-142">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
