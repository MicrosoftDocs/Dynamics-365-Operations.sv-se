---
title: Platsprofilen tillåter inte negativt lager, men negativ lagerbehållning är tillåten
description: Alternativet Tillåt negativt lager för lagerställeprofilen är inställt på Nej, men systemet tillåter fortfarande negativ lagerbehållning.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026913"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="76931-103">Platsprofilen tillåter inte negativt lager, men negativ lagerbehållning är tillåten</span><span class="sxs-lookup"><span data-stu-id="76931-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="76931-104">KB-nummer: 4613622</span><span class="sxs-lookup"><span data-stu-id="76931-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="76931-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="76931-105">Symptoms</span></span>

<span data-ttu-id="76931-106">Alternativet **Tillåt negativt lager** för lagerställeprofilen är inställt på *Nej*, men systemet tillåter fortfarande negativ lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="76931-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="76931-107">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="76931-107">Example scenario</span></span>

<span data-ttu-id="76931-108">För statligt reglerade transaktioner måste systemet kunna registrera negativt lager för att bokföra förluster.</span><span class="sxs-lookup"><span data-stu-id="76931-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="76931-109">Du vill att en artikel ska kunna visa negativt lager, men bara på angivna platser, till exempel tankar.</span><span class="sxs-lookup"><span data-stu-id="76931-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="76931-110">Men om artikelmodellgruppen tillåter negativt lager upptäcker du att det inte spelar någon roll om lagerstället är inställt på att tillåta negativt lager.</span><span class="sxs-lookup"><span data-stu-id="76931-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="76931-111">Om artikeln har ställts in så att negativt lager inte tillåts spelar det ingen roll hur lagerställesprofilen ställs in.</span><span class="sxs-lookup"><span data-stu-id="76931-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="76931-112">Upplösning</span><span class="sxs-lookup"><span data-stu-id="76931-112">Resolution</span></span>

<span data-ttu-id="76931-113">Inställningen **Tillåt negativt lager** från lagerställeprofilen gäller endast lagerprocesser, till exempel plockning.</span><span class="sxs-lookup"><span data-stu-id="76931-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="76931-114">Artikelmodellgrupper som är inställda på att tillåta negativt lager påverkar dock alla processer från modulerna Lagerhantering och Lagerställeshantering, och lagerställesprofilen åsidosätter inte inställningen.</span><span class="sxs-lookup"><span data-stu-id="76931-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="76931-115">Du kan styra om ett lagerställe får ha negativt lager.</span><span class="sxs-lookup"><span data-stu-id="76931-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="76931-116">Ange att artikelmodellgrupperna inte ska tillåta negativt fysiskt lager och ange endast det relevanta lagerstället så att negativt lager tillåts.</span><span class="sxs-lookup"><span data-stu-id="76931-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
