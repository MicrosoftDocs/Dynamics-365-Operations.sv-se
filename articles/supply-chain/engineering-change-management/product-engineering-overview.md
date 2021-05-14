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
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947530"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="932d7-103">Konstruktionsändringshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="932d7-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="932d7-104">Funktionssammanfattning</span><span class="sxs-lookup"><span data-stu-id="932d7-104">Feature summary</span></span>

<span data-ttu-id="932d7-105">Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="932d7-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="932d7-106">Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="932d7-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="932d7-107">Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa konstruktionsändringar under hela livscykeln för en produkt.</span><span class="sxs-lookup"><span data-stu-id="932d7-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="932d7-108">Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion.</span><span class="sxs-lookup"><span data-stu-id="932d7-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="932d7-109">Nedan följer en lista över de viktigaste funktionerna:</span><span class="sxs-lookup"><span data-stu-id="932d7-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="932d7-110">Produktversionering</span><span class="sxs-lookup"><span data-stu-id="932d7-110">Product versioning</span></span>
- <span data-ttu-id="932d7-111">Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (konstruktionsföretaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer</span><span class="sxs-lookup"><span data-stu-id="932d7-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="932d7-112">Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)</span><span class="sxs-lookup"><span data-stu-id="932d7-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="932d7-113">Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="932d7-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="932d7-114">Begäran om konstruktionsändring som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="932d7-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="932d7-115">Konstruktionsändringsorder som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="932d7-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="932d7-116">Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.</span><span class="sxs-lookup"><span data-stu-id="932d7-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="932d7-117">Aktivera funktionerna för konstruktionsändringshantering och versionsdimensioner för ditt system</span><span class="sxs-lookup"><span data-stu-id="932d7-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="932d7-118">Innan du kan använda hantering av konstruktionsändringar måste du aktivera både funktionen *Konstruktionsändringshantering* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="932d7-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="932d7-119">Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera funktionen för *produktversionsdimension* och dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="932d7-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="932d7-120">Sätt först på funktionerna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="932d7-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="932d7-121">Gå till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="932d7-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="932d7-122">Sök efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="932d7-122">Check for updates.</span></span>
1. <span data-ttu-id="932d7-123">Aktivera funktionen med namnet **Konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="932d7-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="932d7-124">Om du vill använda den, ska du även aktivera funktionen med namnet **Produktdimensionsversion**.</span><span class="sxs-lookup"><span data-stu-id="932d7-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="932d7-125">Sätt sedan på konfigurationstangenterna genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="932d7-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="932d7-126">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="932d7-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="932d7-127">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="932d7-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="932d7-128">Expandera noden **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="932d7-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="932d7-129">Aktivera konfigurationsnyckeln för huvudfunktionen genom att markera kryssrutan **Konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="932d7-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** check box.</span></span> <span data-ttu-id="932d7-130">(Det är inte nödvändigt att expandera noden om du inte även vill inaktivera en eller båda av dess delfunktioner.)</span><span class="sxs-lookup"><span data-stu-id="932d7-130">(It isn't necessary to expand the node unless you also want to disable one or both of its sub-features.)</span></span>
1. <span data-ttu-id="932d7-131">Om du även vill använda versionsdimensionen ska du välja kryssrutan **Produktdimension – Version**.</span><span class="sxs-lookup"><span data-stu-id="932d7-131">If you also want to use the version dimension, then select the **Product dimension - Version** check box.</span></span> <span data-ttu-id="932d7-132">(Denna kryssruta finns längre ned i listan, inte inkapslad under noden **Konstruktionsändringshantering**.)</span><span class="sxs-lookup"><span data-stu-id="932d7-132">(This check box is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="932d7-133">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="932d7-133">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="932d7-134">Från och med april 2022 aktiveras licensnycklarna för både **Konstruktionsändringshantering** och **Produktdimension – Version** som standard för alla nya installationer, men de kan fortfarande inaktiveras vid behov.</span><span class="sxs-lookup"><span data-stu-id="932d7-134">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
