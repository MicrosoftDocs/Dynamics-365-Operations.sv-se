---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av momsdata mellan Finance and Operations och Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853869"
---
# <a name="integrated-tax"></a><span data-ttu-id="69d58-103">Integrerad moms</span><span class="sxs-lookup"><span data-stu-id="69d58-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69d58-104">Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt.</span><span class="sxs-lookup"><span data-stu-id="69d58-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="69d58-105">Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.</span><span class="sxs-lookup"><span data-stu-id="69d58-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="69d58-106">Mallar</span><span class="sxs-lookup"><span data-stu-id="69d58-106">Templates</span></span>

<span data-ttu-id="69d58-107">Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="69d58-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="69d58-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="69d58-108">Finance and Operations</span></span>   | <span data-ttu-id="69d58-109">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="69d58-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="69d58-110">Skattekoder</span><span class="sxs-lookup"><span data-stu-id="69d58-110">Tax codes</span></span>                  | <span data-ttu-id="69d58-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="69d58-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="69d58-112">Skattegrupper</span><span class="sxs-lookup"><span data-stu-id="69d58-112">Tax groups</span></span>               | <span data-ttu-id="69d58-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="69d58-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="69d58-114">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="69d58-114">Tax item groups</span></span>          | <span data-ttu-id="69d58-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="69d58-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="69d58-116">Undantag från skatteplikt</span><span class="sxs-lookup"><span data-stu-id="69d58-116">Tax Exemptions</span></span>           | <span data-ttu-id="69d58-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="69d58-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="69d58-118">Skattemyndighet</span><span class="sxs-lookup"><span data-stu-id="69d58-118">Tax Authorities</span></span>          | <span data-ttu-id="69d58-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="69d58-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="69d58-120">Källskattekoder</span><span class="sxs-lookup"><span data-stu-id="69d58-120">Withholding tax codes</span></span>      | <span data-ttu-id="69d58-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="69d58-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="69d58-122">Källskattegrupper</span><span class="sxs-lookup"><span data-stu-id="69d58-122">Withholding tax groups</span></span>   | <span data-ttu-id="69d58-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="69d58-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="69d58-124">Momsgrupp för huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="69d58-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="69d58-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="69d58-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

