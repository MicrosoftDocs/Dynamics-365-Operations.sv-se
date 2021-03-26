---
title: Översikt över intäktsredovisning
description: Det här ämnet innehåller information om intäktsredovisningsfunktionen. Funktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för redovisning av både intäktspris och intäktsplan för order med flera element.
author: kweekley
manager: aolson
ms.date: 11/11/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b21cf04674d01df31dc3304886e7cda035bdcce2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238266"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="5e488-104">Översikt över intäktsredovisning</span><span class="sxs-lookup"><span data-stu-id="5e488-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e488-105">Företag i branscher som säljer flera element, som produkter, tjänster, prenumerationer och liknande, måste kunna bryta ut order med flera element så att intäkten kan identifieras utifrån en uppsättning företagsspecifika och branschspecifika riktlinjer.</span><span class="sxs-lookup"><span data-stu-id="5e488-105">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

> [!NOTE]
> <span data-ttu-id="5e488-106">Intäktsredovisningsfunktionen kan inte aktiveras via funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="5e488-106">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="5e488-107">För närvarande måste du använda konfigurationsnycklar för att aktivera den.</span><span class="sxs-lookup"><span data-stu-id="5e488-107">Currently, you must use configuration keys to turn it on.</span></span>

> <span data-ttu-id="5e488-108">Intäktsredovisning, inklusive buntfunktionen, stöds inte för användning i Commerce-kanaler (e-handel, kassa, callcenter).</span><span class="sxs-lookup"><span data-stu-id="5e488-108">Revenue recognition, including bundle functionality, isn't supported for use in Commerce channels (e-commerce, POS, call center).</span></span> <span data-ttu-id="5e488-109">Artiklar som konfigurerats med intäktsredovisning ska inte läggas till på order eller transaktioner som skapas i Commerce-kanaler.</span><span class="sxs-lookup"><span data-stu-id="5e488-109">Items configured with revenue recognition should not be added to orders or transactions created in Commerce channels.</span></span>

<span data-ttu-id="5e488-110">I allmänhet kan intäktsredovisningsprocessen användas för att utföra dess uppgifter:</span><span class="sxs-lookup"><span data-stu-id="5e488-110">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="5e488-111">Allokera intäkter som hjälp för att säkerställa att lämpligt intäktspris identifieras baserat på värdet av komponenterna i order med flera element.</span><span class="sxs-lookup"><span data-stu-id="5e488-111">Allocate revenue, to help ensure that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="5e488-112">Periodisera intäkter, baserat på intäktsplaner som motsvarar avtalad tidsram och procentandel för identifiering av intäkter över tid.</span><span class="sxs-lookup"><span data-stu-id="5e488-112">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="5e488-113">Videon om [hur du redovisar intäkter i Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (visas ovan) ingår i [spellistan för Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.</span><span class="sxs-lookup"><span data-stu-id="5e488-113">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="5e488-114">Intäktsredovisningsfunktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för redovisning av både intäktspris och intäktsplan.</span><span class="sxs-lookup"><span data-stu-id="5e488-114">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="5e488-115">Frisläppta produkter används för att stödja intäktsredovisning på försäljningsorderdokument.</span><span class="sxs-lookup"><span data-stu-id="5e488-115">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="5e488-116">De frisläppta produkterna innehåller den inställning som behövs för att fastställa intäktspris och intäktsplan.</span><span class="sxs-lookup"><span data-stu-id="5e488-116">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="5e488-117">Försäljningsordern kan ursprungligen komma från ett Tid och material-projekt.</span><span class="sxs-lookup"><span data-stu-id="5e488-117">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="5e488-118">Företag kan använda intäktsplansfunktionen utan att använda intäktsprisfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5e488-118">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="5e488-119">Därför används priset på försäljningsorderrader som antingen intäkt eller periodiserad intäkt.</span><span class="sxs-lookup"><span data-stu-id="5e488-119">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="5e488-120">Om det finns en intäktsplan finns på försäljningsorderraden kommer priset på försäljningsorderraden att periodiseras.</span><span class="sxs-lookup"><span data-stu-id="5e488-120">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="5e488-121">Om det inte finns någon intäktsplan på försäljningsorderraden kommer priset på försäljningsorderraden att bokföras på ett intäktskonto när det faktureras.</span><span class="sxs-lookup"><span data-stu-id="5e488-121">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="5e488-122">Intäktspriset beräknas antingen när försäljningsordern bekräftas eller när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="5e488-122">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="5e488-123">För att förhandsgranska intäktspriset innan fakturan bokförs måste försäljningsordern bekräftas.</span><span class="sxs-lookup"><span data-stu-id="5e488-123">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="5e488-124">När försäljningsordern har bekräftats skapas även en förväntad intäktsplan om någon försäljningsorderrad har en intäktsplan.</span><span class="sxs-lookup"><span data-stu-id="5e488-124">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="5e488-125">När försäljningsordern faktureras raderas den förväntade intäktsplanen och den förväntade intäktsplanen ersätts av den faktiska intäktsredovisningsplanen.</span><span class="sxs-lookup"><span data-stu-id="5e488-125">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="5e488-126">Uppgifterna för intäktsredovisningsplanen bevaras för respektive försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="5e488-126">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="5e488-127">Därför kan intäktsredovisningsansvarig visa uppgifterna och frisläppa rader till intäkt när avtalad skyldighet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5e488-127">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="5e488-128">I slutet av varje period kan intäktsredovisningsansvariga skapa en intäktsjournal för att frisläppa planerade rader som förfallit eller före ett datum som de definierar.</span><span class="sxs-lookup"><span data-stu-id="5e488-128">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date they define.</span></span> <span data-ttu-id="5e488-129">Denna intäktsjournal bokförs inte omgående.</span><span class="sxs-lookup"><span data-stu-id="5e488-129">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="5e488-130">Därför kan intäktsredovisningsansvarig verifiera att korrekta belopp frisläpps från periodiserad intäkt till faktisk intäkt.</span><span class="sxs-lookup"><span data-stu-id="5e488-130">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="5e488-131">Om en avtalsförändring gör att en ny försäljningsorderrad måste läggas till antingen till den befintliga försäljningsordern eller till en ny försäljningsorder kan en omallokeringsprocess köras för att korrigera intäktspriset på alla försäljningsorderrader.</span><span class="sxs-lookup"><span data-stu-id="5e488-131">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]