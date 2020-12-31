---
title: Customer payment insights (förhandsversion)
description: I det här ämnet beskrivs funktioner för betalningsinsikter som hjälper dig att bättre förstå en enskild kunds typiska betalningspraxis. Funktionen kan också hjälpa dig att identifiera omständigheter gör att du bör starta inkassoprocesser tidigare än vad du annars skulle ha gjort.
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
ms.openlocfilehash: f151942555ac503338f0fd44aa8779e3c2970fb1
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644643"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="eb9c2-104">Customer payment insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="eb9c2-104">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="eb9c2-105">I det här ämnet beskrivs funktioner för betalningsinsikter som hjälper dig att bättre förstå en enskild kunds typiska betalningspraxis.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-105">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices.</span></span> <span data-ttu-id="eb9c2-106">Funktionen kan också hjälpa dig att identifiera omständigheter gör att du bör starta inkassoprocesser tidigare än vad du annars skulle ha gjort.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-106">The feature can help you identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="eb9c2-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="eb9c2-107">Overview</span></span>

<span data-ttu-id="eb9c2-108">Det kan vara svårt att förutsäga när en kund kommer att betala sina fakturor.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-108">It can be hard to predict when customers will pay their invoices.</span></span> <span data-ttu-id="eb9c2-109">Den här bristen på insyn leder till mindre korrekta kassaflödesprognoser, inkassoprocesser som startar för sent och order som kan levereras som standard till kunder.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-109">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="eb9c2-110">Kundbetalningsinsikter (förhandsversion) hjälper organisationer att förutsäga när en kundfaktura kommer att betalas.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-110">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid.</span></span> <span data-ttu-id="eb9c2-111">Denna information kan hjälpa organisationer att skapa inkassostrategier som förbättrar sannolikheten för att bli betald i tid.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-111">This information can help organizations create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="eb9c2-112">Förutsägelser</span><span class="sxs-lookup"><span data-stu-id="eb9c2-112">Predictions</span></span>

<span data-ttu-id="eb9c2-113">Med hjälp av betalningsförutsägelserna kan organisationerna förbättra sina affärsprocesser genom att hjälpa dem att enkelt identifiera fakturor som sannolikt kommer att betalas sent och vidta lämpliga åtgärder som förbättrar deras chans att bli betalda i tid.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-113">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="eb9c2-114">Genom att använda en modell för maskininlärning som används för historiska fakturor, betalningar och kunddata, Customer Payment Insights (förhandsversion), förutsägs mer noggrant när en kund betalar en utestående faktura.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-114">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="eb9c2-115">Kundbetalningsinsikter (förhandsversion) kan förutsäga tre sannolikheter för betalning för varje öppen faktura:</span><span class="sxs-lookup"><span data-stu-id="eb9c2-115">For each open invoice, Customer payment insights (Preview) can predict three payment probabilities:</span></span>

-   <span data-ttu-id="eb9c2-116">Sannolikhet för att betalningen görs i tid</span><span class="sxs-lookup"><span data-stu-id="eb9c2-116">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="eb9c2-117">Sannolikhet för att betalningen görs sent</span><span class="sxs-lookup"><span data-stu-id="eb9c2-117">Probability of payment being made late</span></span>
-   <span data-ttu-id="eb9c2-118">Sannolikhet för att betalningen görs mycket sent</span><span class="sxs-lookup"><span data-stu-id="eb9c2-118">Probability of payment being made very late</span></span>

<span data-ttu-id="eb9c2-119">Kundbetalningsinsikter (förhandsversion) tillhandahåller en aggregerad vy över förväntade betalningar, vilket kan hjälpa organisationer att första det totala betalningsbelopp de kan förvänta sig från en kund i en av tre buckets, I tid, Sent och Mycket sent.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-119">Customer payment insights (Preview) also provides an aggregated view of expected payments, which can help organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late.</span></span>

<span data-ttu-id="eb9c2-120">[![Aggregerad vy över betalningsförutsägelser](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="eb9c2-120">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="eb9c2-121">Dessutom tilldelas varje faktura en sannolikhet för betalning i tid.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-121">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="eb9c2-122">Om sannolikheten för betalning i tid är mindre än 50 %, är fakturorna taggade med en röd cirkel för att indikera att dessa fakturor kräver inkassouppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-122">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="eb9c2-123">[![Lista över sannolikhet för betalning](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="eb9c2-123">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="eb9c2-124">Customer Payment Insights (förhandsversion) innehåller också sammanhangsbaserad information för att förklara förutsägelsen, t.ex. de främsta faktorer som påverkar förutsägelser, aktuell status för affärsverksamhet med kunden och detaljer om historiska kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-124">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="eb9c2-125">I många företag har inkassoprocessen varit en reaktiv aktivitet. Inkassoprocessen startar inte förrän fakturorna förfaller.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-125">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="eb9c2-126">Med Customer Payment Insights (förhandsversion) kan organisationer vara mer proaktiva om inkasso.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-126">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="eb9c2-127">De behöver inte längre vänta på att transaktionerna ska bli klara för att inleda inkassoprocessen.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-127">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="eb9c2-128">I stället kan de använda funktionen betalningsförutsägelse för att avgöra om proaktiv inkasso förbättrar sannolikheten för att få betalt i tid.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-128">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="eb9c2-129">Med betalningsförutsägelse får företag också den information som behövs för att motivera inledningen av inkassoprocessen tidigt.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-129">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="eb9c2-130">Metod</span><span class="sxs-lookup"><span data-stu-id="eb9c2-130">Methodology</span></span>

<span data-ttu-id="eb9c2-131">Det är svårt att utveckla och distribuera en AI-lösning.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-131">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="eb9c2-132">Det krävs ett team med dataforskare, ämnesexperter och tekniker som arbetar under en längre tid för att formulera, utveckla, distribuera och underhålla en användbar AI-lösning.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-132">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy, and maintain a usable AI solution.</span></span> <span data-ttu-id="eb9c2-133">Vi gör det enkelt att driftsätta och använda AI-lösningar i Finance.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-133">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="eb9c2-134">Vi har förpackade AI-lösningar i Finance som byggts ovanpå Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-134">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="eb9c2-135">En slutanvändare kan med knappen bara klicka på och distribuera AI-lösningen och börja använda fördelarna med intelligenta förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-135">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="eb9c2-136">Om en organisation inte är nöjd med noggrannheten i förutsägelser kan en priviligierad användare, med hjälp av ett enda klick, gå in i tillägget AI Builder och sedan markera eller avmarkera fälten som används för att generera förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-136">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="eb9c2-137">När de är klara kan de utbilda och publicera ändringarna och den nyutbildade modellen hämtas automatiskt för förutsägelser i Finance.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-137">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="eb9c2-138">Hur du skaffar Customer Payment Insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="eb9c2-138">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="eb9c2-139">Skicka e-post till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du vill testa Kundbetalningsinsikter (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="eb9c2-139">Send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="eb9c2-140">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="eb9c2-140">Privacy Notice</span></span>

<span data-ttu-id="eb9c2-141">Förhandsversioner (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations de (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="eb9c2-141">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


