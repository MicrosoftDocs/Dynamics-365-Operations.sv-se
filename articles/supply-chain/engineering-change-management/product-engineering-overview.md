---
title: Konstruktionsändringshantering – översikt
description: Det här ämnet innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b081cd8d56217b8cf76db824c29482d453fc9ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001958"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="1f653-103">Konstruktionsändringshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="1f653-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="1f653-104">Funktionssammanfattning</span><span class="sxs-lookup"><span data-stu-id="1f653-104">Feature summary</span></span>

<span data-ttu-id="1f653-105">Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="1f653-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="1f653-106">Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="1f653-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="1f653-107">Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa tekniska förändringar under hela livscykeln för en produkt.</span><span class="sxs-lookup"><span data-stu-id="1f653-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="1f653-108">Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik.</span><span class="sxs-lookup"><span data-stu-id="1f653-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="1f653-109">Nedan följer en lista över de viktigaste funktionerna:</span><span class="sxs-lookup"><span data-stu-id="1f653-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="1f653-110">Produktversionering</span><span class="sxs-lookup"><span data-stu-id="1f653-110">Product versioning</span></span>
- <span data-ttu-id="1f653-111">Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (det tekniska företaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer</span><span class="sxs-lookup"><span data-stu-id="1f653-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="1f653-112">Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)</span><span class="sxs-lookup"><span data-stu-id="1f653-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="1f653-113">Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="1f653-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="1f653-114">Begäran om teknisk ändring som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="1f653-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="1f653-115">Teknisk ändringsändringsorder som stöds av arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="1f653-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="1f653-116">Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.</span><span class="sxs-lookup"><span data-stu-id="1f653-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-engineering-change-management-for-your-system"></a><span data-ttu-id="1f653-117">Aktivera konstruktionsändringshantering för ditt system</span><span class="sxs-lookup"><span data-stu-id="1f653-117">Turn on engineering change management for your system</span></span>

<span data-ttu-id="1f653-118">Börja med att aktivera konstruktionsändringshantering genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="1f653-118">First, turn on engineering change management by following these steps.</span></span>

1. <span data-ttu-id="1f653-119">Gå till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f653-119">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="1f653-120">Sök efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="1f653-120">Check for updates.</span></span>
1. <span data-ttu-id="1f653-121">Aktivera funktionen med namnet **konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="1f653-121">Turn on the feature that is named **Engineering Change Management**.</span></span>

<span data-ttu-id="1f653-122">Aktivera sedan konfigurationsnyckeln för **konstruktionsändringshantering** genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="1f653-122">Next, turn on the **Engineering Change Management** configuration key by following these steps.</span></span>

1. <span data-ttu-id="1f653-123">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1f653-123">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="1f653-124">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1f653-124">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="1f653-125">Expandera noden **Handel** och markera kryssrutan **konstruktionsändringshantering**.</span><span class="sxs-lookup"><span data-stu-id="1f653-125">Expand the **Trade** node, and select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="1f653-126">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1f653-126">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
