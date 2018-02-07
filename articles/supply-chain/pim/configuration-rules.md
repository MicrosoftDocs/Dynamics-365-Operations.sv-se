---
title: Konfigurationsregler
description: "Den här artikeln innehåller allmän information om konfigurationsregler. Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bc8e606cdc0bc5a45321c67ce9b089059f226df2
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="configuration-rules"></a><span data-ttu-id="bf5d2-104">Konfigurationsregler</span><span class="sxs-lookup"><span data-stu-id="bf5d2-104">Configuration rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bf5d2-105">Den här artikeln innehåller allmän information om konfigurationsregler.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="bf5d2-106">Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="bf5d2-107">Konfigurationsregler är tillgängliga när du definierar dimensionsbaserade konfigurationmodeller.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="bf5d2-108">Konfigurationsregler används för att antingen framtvinga eller förbjuda specifika artikelkombinationer i en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="bf5d2-109">När en strukturlista har skapats, och de relevanta artiklarna har tilldelats till respektive konfigurationsgrupper, kan en eller flera konfigurationsregler definieras.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="bf5d2-110">Om två artiklar hör ihop, används operatorn **Välj** för att säkerställa inkludering.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="bf5d2-111">Om två artiklar är ömsesidigt uteslutande används operatorn **Avmarkera** för att säkerställa uteslutande.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="bf5d2-112">**Obs!** Den här informationen gäller endast för produktmallar som använder dimensionsbaserad konfigurationteknik.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="bf5d2-113">Befintliga konfigurationer påverkas inte av senare ändringar av konfigurationsreglerna.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="bf5d2-114">Det är dock viktigt att du ställer in reglerna innan du definierar en ny konfiguration eller att du kontrollerar reglerna om du tror att de har ändrats.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="bf5d2-115">**Obs!** För metoden **Markera** väljs den härledda konfigurationsgruppen, artikelnumret eller konfigurationen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="bf5d2-116">För metoden **Avmarkera** kan den härledda konfigurationsgruppen, artikelnumret eller konfigurationen inte kan väljas.</span><span class="sxs-lookup"><span data-stu-id="bf5d2-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="see-also"></a><span data-ttu-id="bf5d2-117">Se även</span><span class="sxs-lookup"><span data-stu-id="bf5d2-117">See also</span></span>
--------

[<span data-ttu-id="bf5d2-118">Dimensionsbaserad produktkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bf5d2-118">Dimension-based product configuration</span></span>](dimension-based-product-configuration.md)




