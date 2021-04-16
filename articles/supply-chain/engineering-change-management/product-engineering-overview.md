---
title: Konstruktionsändringshantering – översikt
description: Det här ämnet innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 964db71efc9dc81d60199e37de8668de9d667496
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842091"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="75b02-103">Konstruktionsändringshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="75b02-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="75b02-104">Funktionssammanfattning</span><span class="sxs-lookup"><span data-stu-id="75b02-104">Feature summary</span></span>

<span data-ttu-id="75b02-105">Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="75b02-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="75b02-106">Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="75b02-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="75b02-107">Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa tekniska förändringar under hela livscykeln för en produkt.</span><span class="sxs-lookup"><span data-stu-id="75b02-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="75b02-108">Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik.</span><span class="sxs-lookup"><span data-stu-id="75b02-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="75b02-109">Nedan följer en lista över de viktigaste funktionerna:</span><span class="sxs-lookup"><span data-stu-id="75b02-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="75b02-110">Produktversionering</span><span class="sxs-lookup"><span data-stu-id="75b02-110">Product versioning</span></span>
- <span data-ttu-id="75b02-111">Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (det tekniska företaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer</span><span class="sxs-lookup"><span data-stu-id="75b02-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="75b02-112">Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)</span><span class="sxs-lookup"><span data-stu-id="75b02-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="75b02-113">Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="75b02-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="75b02-114">Begäran om teknisk ändring som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="75b02-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="75b02-115">Teknisk ändringsändringsorder som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="75b02-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="75b02-116">Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.</span><span class="sxs-lookup"><span data-stu-id="75b02-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="75b02-117">Aktivera funktionerna för hantering av tekniska ändringar och versionsdimensioner för ditt system</span><span class="sxs-lookup"><span data-stu-id="75b02-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="75b02-118">Innan du kan använda hantering av tekniska ändringar måste du aktivera både funktionen *konstruktionsändringshantering* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="75b02-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="75b02-119">Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera funktionen för *produktversionsdimension* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="75b02-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="75b02-120">Sätt först på funktionerna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="75b02-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="75b02-121">Gå till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75b02-121">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="75b02-122">Sök efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="75b02-122">Check for updates.</span></span>
1. <span data-ttu-id="75b02-123">Aktivera funktionen med namnet **konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="75b02-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="75b02-124">Om du vill använda den, ska du även aktivera funktionen med namnet **Produktdimensionsversion**.</span><span class="sxs-lookup"><span data-stu-id="75b02-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="75b02-125">Sätt sedan på konfigurationstangenterna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="75b02-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="75b02-126">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="75b02-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="75b02-127">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="75b02-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="75b02-128">Expandera noden **Handel**</span><span class="sxs-lookup"><span data-stu-id="75b02-128">Expand the **Trade** node</span></span>
1. <span data-ttu-id="75b02-129">Markera kryssrutan **konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="75b02-129">Select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="75b02-130">Om du vill använda den ska du också markera kryssrutan **Produktdimension - Version**.</span><span class="sxs-lookup"><span data-stu-id="75b02-130">If you want to use it, then also select the **Product dimension - Version** check box.</span></span>
1. <span data-ttu-id="75b02-131">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="75b02-131">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
