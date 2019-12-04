---
title: Customer payment insights (förhandsversion)
description: I det här avsnittet beskrivs de möjligheter till betalningsinsikter som hjälper till att förbättra förståelsen av enskilda kunders typiska betalningspraxis och kan identifiera omständigheter som motiverar inledande insamlingsprocesser tidigare än vad du har gjort.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774050"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="32e40-103">Customer payment insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="32e40-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="32e40-104">I det här avsnittet beskrivs de möjligheter till betalningsinsikter som hjälper till att förbättra förståelsen av enskilda kunders typiska betalningspraxis och kan identifiera omständigheter som motiverar inledande insamlingsprocesser tidigare än vad du har gjort.</span><span class="sxs-lookup"><span data-stu-id="32e40-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="32e40-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="32e40-105">Overview</span></span>

<span data-ttu-id="32e40-106">Organisationer finner det ofta svårt att förutsäga när en kund betalar sina fakturor.</span><span class="sxs-lookup"><span data-stu-id="32e40-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="32e40-107">Den här bristen på insyn leder till mindre korrekta kassaflödesprognoser, inkassoprocesser som startar för sent och order som kan levereras som standard till kunder.</span><span class="sxs-lookup"><span data-stu-id="32e40-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="32e40-108">Customer Payment Insights (förhandsversion) hjälper organisationer att förutse när en kundfaktura kommer att betalas, vilket hjälper organisationen att skapa insamlingsstrategier som förbättrar sannolikheten för att betalas i tid.</span><span class="sxs-lookup"><span data-stu-id="32e40-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="32e40-109">Förutsägelser</span><span class="sxs-lookup"><span data-stu-id="32e40-109">Predictions</span></span>

<span data-ttu-id="32e40-110">Med hjälp av betalningsförutsägelserna kan organisationerna förbättra sina affärsprocesser genom att hjälpa dem att enkelt identifiera fakturor som sannolikt kommer att betalas sent och vidta lämpliga åtgärder som förbättrar deras chans att bli betalda i tid.</span><span class="sxs-lookup"><span data-stu-id="32e40-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="32e40-111">Genom att använda en modell för maskininlärning som används för historiska fakturor, betalningar och kunddata, Customer Payment Insights (förhandsversion), förutsägs mer noggrant när en kund betalar en utestående faktura.</span><span class="sxs-lookup"><span data-stu-id="32e40-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="32e40-112">Customer Payment Insights (förhandsversion) förutsäger tre sannolikheter för betalning för respektive faktura:</span><span class="sxs-lookup"><span data-stu-id="32e40-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="32e40-113">Sannolikhet för att betalningen görs i tid</span><span class="sxs-lookup"><span data-stu-id="32e40-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="32e40-114">Sannolikhet för att betalningen görs sent</span><span class="sxs-lookup"><span data-stu-id="32e40-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="32e40-115">Sannolikhet för att betalningen görs mycket sent</span><span class="sxs-lookup"><span data-stu-id="32e40-115">Probability of payment being made very late</span></span>

<span data-ttu-id="32e40-116">För att hjälpa organisationer att förstå det totala betalningsbeloppet som de kan förvänta sig från en kund i en av de tre grupper, i tid, sent och mycket sent, innehåller Customer Payment Insights (förhandsversion) också en sammansatt vy med förväntade betalningar.</span><span class="sxs-lookup"><span data-stu-id="32e40-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="32e40-117">[![Aggregerad vy över betalningsförutsägelser](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="32e40-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="32e40-118">Dessutom tilldelas varje faktura en sannolikhet för betalning i tid.</span><span class="sxs-lookup"><span data-stu-id="32e40-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="32e40-119">Om sannolikheten för betalning i tid är mindre än 50 %, är fakturorna taggade med en röd cirkel för att indikera att dessa fakturor kräver inkassouppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="32e40-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="32e40-120">[![Lista över sannolikhet för betalning](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="32e40-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="32e40-121">Customer Payment Insights (förhandsversion) innehåller också sammanhangsbaserad information för att förklara förutsägelsen, t.ex. de främsta faktorer som påverkar förutsägelser, aktuell status för affärsverksamhet med kunden och detaljer om historiska kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="32e40-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="32e40-122">I många företag har inkassoprocessen varit en reaktiv aktivitet. Inkassoprocessen startar inte förrän fakturorna förfaller.</span><span class="sxs-lookup"><span data-stu-id="32e40-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="32e40-123">Med Customer Payment Insights (förhandsversion) kan organisationer vara mer proaktiva om inkasso.</span><span class="sxs-lookup"><span data-stu-id="32e40-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="32e40-124">De behöver inte längre vänta på att transaktionerna ska bli klara för att inleda inkassoprocessen.</span><span class="sxs-lookup"><span data-stu-id="32e40-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="32e40-125">I stället kan de använda funktionen betalningsförutsägelse för att avgöra om proaktiv inkasso förbättrar sannolikheten för att få betalt i tid.</span><span class="sxs-lookup"><span data-stu-id="32e40-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="32e40-126">Med betalningsförutsägelse får företag också den information som behövs för att motivera inledningen av inkassoprocessen tidigt.</span><span class="sxs-lookup"><span data-stu-id="32e40-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="32e40-127">Metod</span><span class="sxs-lookup"><span data-stu-id="32e40-127">Methodology</span></span>

<span data-ttu-id="32e40-128">Det är svårt att utveckla och distribuera en AI-lösning.</span><span class="sxs-lookup"><span data-stu-id="32e40-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="32e40-129">Det krävs ett team med dataforskare, ämnesexperter och tekniker som arbetar under en längre tid för att formulera, utveckla, distribuera och underhålla en användbar AI-lösning.</span><span class="sxs-lookup"><span data-stu-id="32e40-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="32e40-130">Vi gör det enkelt att driftsätta och använda AI-lösningar i Finance.</span><span class="sxs-lookup"><span data-stu-id="32e40-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="32e40-131">Vi har förpackade AI-lösningar i Finance som byggts ovanpå Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="32e40-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="32e40-132">En slutanvändare kan med knappen bara klicka på och distribuera AI-lösningen och börja använda fördelarna med intelligenta förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="32e40-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="32e40-133">Om en organisation inte är nöjd med noggrannheten i förutsägelser kan en priviligierad användare, med hjälp av ett enda klick, gå in i tillägget AI Builder och sedan markera eller avmarkera fälten som används för att generera förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="32e40-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="32e40-134">När de är klara kan de utbilda och publicera ändringarna och den nyutbildade modellen hämtas automatiskt för förutsägelser i Finance.</span><span class="sxs-lookup"><span data-stu-id="32e40-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="32e40-135">Hur du skaffar Customer Payment Insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="32e40-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="32e40-136">Skicka e-post till [Customer Payment Insights (förhandsversion)](mailto:fiap@microsoft.com) om du vill testa Customer Payment Insights (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="32e40-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="32e40-137">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="32e40-137">Privacy Notice</span></span>

<span data-ttu-id="32e40-138">Förhandsversioner (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations de (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="32e40-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


