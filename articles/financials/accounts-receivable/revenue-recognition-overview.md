---
title: Översikt över intäktsredovisning
description: Det här ämnet innehåller information om intäktsredovisningsfunktionen. Funktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för igenkänning av både intäktspris och intäktsplanering för order med flera element.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863573"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="5b3bd-104">Översikt över intäktsredovisning</span><span class="sxs-lookup"><span data-stu-id="5b3bd-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="5b3bd-105">Intäktsredovisningsfunktionen kan ännu inte slås på via funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="5b3bd-106">För närvarande måste du använda konfigurationsnycklar för att slå på den.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="5b3bd-107">Företag i branscher som säljer flera element, som produkter, tjänster, prenumerationer och liknande, måste kunna bryta ut order med flera element så att intäkten kan identifieras utifrån en uppsättning företagsspecifika och branschspecifika riktlinjer.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="5b3bd-108">I allmänhet kan intäktsredovisningsprocessen användas för att utföra dess uppgifter:</span><span class="sxs-lookup"><span data-stu-id="5b3bd-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="5b3bd-109">Allokera intäkter som hjälp för att garantera att lämpligt intäktspris identifieras baserat på värdet av komponenterna i order med flera element.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized based on the value of the components on the multi-element orders.</span></span>
* <span data-ttu-id="5b3bd-110">Periodisera intäkter, baserat på intäktsplanering som motsvarar avtalad tidsram och procentandel för identifiering av intäkter över tid.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-110">Defer revenue, based on a revenue schedule that represents the contractual timeframe and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="5b3bd-111">Intäktsredovisningsfunktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för igenkänning av både intäktspris och intäktsplanering.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="5b3bd-112">Frisläppta produkter används för att stödja intäktsredovisning på försäljningsorderdokument.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="5b3bd-113">De frisläppta produkterna innehåller den inställning som behövs för att fastställa intäktspris och intäktsplanering.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="5b3bd-114">Försäljningsordern kan ursprungligen komma från ett Tid och material-projekt.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-114">The sales order can originate from a Time and material project.</span></span>

<span data-ttu-id="5b3bd-115">Företag kan använda intäktsplaneringsfunktionen utan att använda intäktsprisfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="5b3bd-116">Därför används priset på försäljningsorderrader som antingen intäkt eller periodiserad intäkt.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="5b3bd-117">Om intäktsplanering finns på försäljningsorderraden kommer priset på försäljningsorderraden att periodiseras.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="5b3bd-118">Om intäktsplanering inte finns på försäljningsorderraden kommer priset på försäljningsorderraden att bokföras på ett intäktskonto när det faktureras.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="5b3bd-119">Intäktspriset beräknas antingen när försäljningsordern bekräftas eller när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="5b3bd-120">För att förhandsgranska intäktspriset innan fakturan bokförs måste försäljningsordern bekräftas.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="5b3bd-121">När försäljningsordern har bekräftats skapas även en förväntad intäktsplanering om någon försäljningsorderrad innehåller en intäktsplanering.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line contains a revenue schedule.</span></span> <span data-ttu-id="5b3bd-122">När försäljningsordern faktureras raderas den förväntade intäktsplaneringen och den förväntade intäktsplaneringen ersätts av den faktiska intäktsredovisningsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="5b3bd-123">Uppgifterna för intäktsredovisningsplaneringen bevaras för respektive försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="5b3bd-124">Därför kan intäktsredovisningsansvarig visa uppgifterna och frisläppa rader till intäkt när avtalad skyldighet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="5b3bd-125">I slutet av varje period kan intäktsredovisningsansvarig skapa en intäktsjournal för att frisläppa planerade rader som förfallit eller före ett datum som hen definierar.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="5b3bd-126">Denna intäktsjournal bokförs inte omgående.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="5b3bd-127">Därför kan intäktsredovisningsansvarig verifiera att korrekta belopp frisläpps från periodiserad intäkt till faktisk intäkt.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="5b3bd-128">Om en avtalsförändring gör att en ny försäljningsorderrad måste läggas till antingen till den befintliga försäljningsordern eller till en ny försäljningsorder kan en omallokeringsprocess köras för att korrigera intäktspriset för alla försäljningsorderrader.</span><span class="sxs-lookup"><span data-stu-id="5b3bd-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines the sales orders.</span></span>
