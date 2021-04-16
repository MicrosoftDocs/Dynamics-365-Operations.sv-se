---
title: Enhetlig nummerserie för jobb-ID:n
description: Den här funktionen innehåller en enda, enhetlig nummerserie som genererar jobb-ID för modulerna Produktionskontroll, Tillverkningskörning och Tid och närvaro.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824952"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="b6eb1-103">Enhetlig nummerserie för jobb-ID:n</span><span class="sxs-lookup"><span data-stu-id="b6eb1-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6eb1-104">Den här funktionen innehåller en enda, enhetlig nummerserie som genererar jobb-ID för modulerna Produktionskontroll, Tillverkningskörning och Tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="b6eb1-105">Tidigare kunde du välja en annan nummerserie för var och en av dessa moduler, vilket skulle kunna resultera i motstridiga jobb-ID om två eller flera av dessa sekvenser använde identiskt format.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="b6eb1-106">En sådan konflikt kan leda till skadade data.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="b6eb1-107">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="b6eb1-107">Turn on this feature for your system</span></span>

<span data-ttu-id="b6eb1-108">Om ditt system inte redan innehåller de funktioner som beskrivs i det här avsnittet, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera funktionen *Enhetlig nummerserie för jobb-ID*.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="b6eb1-109">Ställ in enhetlig nummerserie för jobb-ID</span><span class="sxs-lookup"><span data-stu-id="b6eb1-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="b6eb1-110">När den här funktionen har aktiverats kommer de befintliga nummerserieinställningarna för **Jobbidentifiering** som finns på parametersidorna för produktionskontroll, tillverkningskörning samt tids- och närvaromoduler att inaktiveras och ett nytt fält för **Enhetligt jobb-ID** läggs till.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="b6eb1-111">Värdet **Enhetligt jobb-ID** delas av alla tre modulerna, vilket säkerställer att alla moduler refererar till samma nummersekvens.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="b6eb1-112">Jobb-ID kommer därför att vara unika i alla tre moduler och en konflikt kommer aldrig att inträffa.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="b6eb1-113">Ställ in enhetlig nummerserie för jobb-ID.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="b6eb1-114">Aktivera funktionen enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="b6eb1-115">Du kan antingen identifiera nummerserien du vill använda för dina enhetliga jobb-ID-nummer eller skapa ett nytt.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="b6eb1-116">Mer information finns i [Nummerserier (översikt)](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b6eb1-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="b6eb1-117">Gå till sidan **Parametrarna för produktionskontroll**, **Parametrar för tillverkningskörning** eller **Tid- och närvaroparametrar**.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="b6eb1-118">Det spelar ingen roll vilken du väljer eftersom när du gör den här inställningen på någon av dessa sidor uppdateras alla andra sidor automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="b6eb1-119">Öppna fliken **Nummerserier** på den valda parametersidan.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="b6eb1-120">Tilldela den **nummerseriekod** som du tidigare identifierade till raden med enhetliga **enhetliga jobb-ID**.</span><span class="sxs-lookup"><span data-stu-id="b6eb1-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
