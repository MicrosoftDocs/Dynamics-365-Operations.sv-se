---
title: Konstruktionsändringshantering – översikt
description: Det här ämnet innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion.
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
ms.openlocfilehash: d9430fe02abe58f37d2bfd1431b4da61527d0834
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115059"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="ff6ac-103">Konstruktionsändringshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="ff6ac-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="ff6ac-104">Funktionssammanfattning</span><span class="sxs-lookup"><span data-stu-id="ff6ac-104">Feature summary</span></span>

<span data-ttu-id="ff6ac-105">Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="ff6ac-106">Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="ff6ac-107">Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa konstruktionsändringar under hela livscykeln för en produkt.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="ff6ac-108">Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="ff6ac-109">Nedan följer en lista över de viktigaste funktionerna:</span><span class="sxs-lookup"><span data-stu-id="ff6ac-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="ff6ac-110">Produktversionering</span><span class="sxs-lookup"><span data-stu-id="ff6ac-110">Product versioning</span></span>
- <span data-ttu-id="ff6ac-111">Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (konstruktionsföretaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer</span><span class="sxs-lookup"><span data-stu-id="ff6ac-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="ff6ac-112">Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)</span><span class="sxs-lookup"><span data-stu-id="ff6ac-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="ff6ac-113">Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="ff6ac-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="ff6ac-114">Begäran om konstruktionsändring som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="ff6ac-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="ff6ac-115">Konstruktionsändringsorder som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="ff6ac-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="ff6ac-116">Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="ff6ac-117">Aktivera funktionerna för konstruktionsändringshantering och versionsdimensioner för ditt system</span><span class="sxs-lookup"><span data-stu-id="ff6ac-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="ff6ac-118">Innan du kan använda hantering av konstruktionsändringar måste du aktivera både funktionen *Konstruktionsändringshantering* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="ff6ac-119">Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera funktionen för *produktversionsdimension* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="ff6ac-120">Sätt först på funktionerna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="ff6ac-121">Gå till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ac-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="ff6ac-122">Sök efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-122">Check for updates.</span></span>
1. <span data-ttu-id="ff6ac-123">Aktivera funktionen med namnet *Konstruktionsändringshantering*.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-123">Turn on the feature that is named *Engineering Change Management*.</span></span>
1. <span data-ttu-id="ff6ac-124">Om du vill använda den, ska du även aktivera funktionen med namnet *Produktdimensionsversion*.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-124">If you want to use it, also turn on the feature that is named *Product dimension version*.</span></span>

<span data-ttu-id="ff6ac-125">Sätt sedan på konfigurationstangenterna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="ff6ac-126">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ac-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="ff6ac-127">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="ff6ac-128">Expandera noden **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="ff6ac-129">Aktivera konfigurationsnyckeln för huvudfunktionen genom att markera kryssrutan **Konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** checkbox.</span></span>
1. <span data-ttu-id="ff6ac-130">Expandera noden **Tillägg för teknik för ändringshantering** och markera eller avmarkera följande kryssrutor efter behov (beroende på vilka funktioner du vill använda):</span><span class="sxs-lookup"><span data-stu-id="ff6ac-130">Expand the **Engineering Change Management** node, and select or clear the following checkboxes as required (depending on the features that you want to use):</span></span>

    - <span data-ttu-id="ff6ac-131">**Attributsökning** – Markera den här kryssrutan om du vill aktivera [attributsökningsfunktionen](engineering-attributes-and-search.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ac-131">**Attribute search** – Select this checkbox to enable the [attribute search feature](engineering-attributes-and-search.md).</span></span> <span data-ttu-id="ff6ac-132">Vi rekommenderar att du aktiverar funktionen, men du kan avmarkera kryssrutan om du inte vill använda den.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-132">We recommend enabling this feature, but you can clear this checkbox if you won't use it.</span></span>
    - <span data-ttu-id="ff6ac-133">**Ändringshantering för processtillverkning** – Markera den här kryssrutan om du vill använda funktioner för teknikändringshantering för att hantera ändringar i formler för processtillverkning.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-133">**Change management for process manufacturing** – Select this checkbox if you want to use Engineering change management features to manage changes in formulas for process manufacturing.</span></span> <span data-ttu-id="ff6ac-134">Om du inte behöver hantera recept kan du avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-134">If you don't have to manage formulas, you can clear this checkbox.</span></span> <span data-ttu-id="ff6ac-135">Mer information finns i [Hantera ändringar i formler och deras ingredienser](manage-formula-changes.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ac-135">For more information, see [Manage changes in formulas and their ingredients](manage-formula-changes.md).</span></span>

1. <span data-ttu-id="ff6ac-136">Om du även vill använda versionsdimensionen ska du välja kryssrutan **Produktdimension – Version**.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-136">If you also want to use the version dimension, then select the **Product dimension - Version** checkbox.</span></span> <span data-ttu-id="ff6ac-137">(Denna kryssruta finns längre ned i listan, inte inkapslad under noden **Konstruktionsändringshantering**.)</span><span class="sxs-lookup"><span data-stu-id="ff6ac-137">(This checkbox is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="ff6ac-138">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ac-138">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff6ac-139">Från och med april 2022 aktiveras licensnycklarna för både **Konstruktionsändringshantering** och **Produktdimension – Version** som standard för alla nya installationer, men de kan fortfarande inaktiveras vid behov.</span><span class="sxs-lookup"><span data-stu-id="ff6ac-139">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
