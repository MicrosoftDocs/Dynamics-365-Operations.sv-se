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
ms.openlocfilehash: b6be53e9a2065373ca37c2791568a8161823803f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772420"
---
## <a name="integrated-tax"></a><span data-ttu-id="dd994-103">Integrerad moms</span><span class="sxs-lookup"><span data-stu-id="dd994-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd994-104">Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt.</span><span class="sxs-lookup"><span data-stu-id="dd994-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="dd994-105">Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.</span><span class="sxs-lookup"><span data-stu-id="dd994-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="dd994-106">Mallar</span><span class="sxs-lookup"><span data-stu-id="dd994-106">Templates</span></span>

<span data-ttu-id="dd994-107">Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="dd994-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="dd994-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd994-108">Finance and Operations</span></span>   | <span data-ttu-id="dd994-109">Customer Engagement-program</span><span class="sxs-lookup"><span data-stu-id="dd994-109">Customer Engagement application</span></span>
-------------------------|---------------------------------
<span data-ttu-id="dd994-110">Skattekoder</span><span class="sxs-lookup"><span data-stu-id="dd994-110">Tax codes</span></span>                  | <span data-ttu-id="dd994-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd994-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="dd994-112">Skattegrupper</span><span class="sxs-lookup"><span data-stu-id="dd994-112">Tax groups</span></span>               | <span data-ttu-id="dd994-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd994-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="dd994-114">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="dd994-114">Tax item groups</span></span>          | <span data-ttu-id="dd994-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd994-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="dd994-116">Undantag från skatteplikt</span><span class="sxs-lookup"><span data-stu-id="dd994-116">Tax Exemptions</span></span>           | <span data-ttu-id="dd994-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd994-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="dd994-118">Skattemyndighet</span><span class="sxs-lookup"><span data-stu-id="dd994-118">Tax Authorities</span></span>          | <span data-ttu-id="dd994-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="dd994-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="dd994-120">Källskattekoder</span><span class="sxs-lookup"><span data-stu-id="dd994-120">Withholding tax codes</span></span>      | <span data-ttu-id="dd994-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd994-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="dd994-122">Källskattegrupper</span><span class="sxs-lookup"><span data-stu-id="dd994-122">Withholding tax groups</span></span>   | <span data-ttu-id="dd994-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd994-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="dd994-124">Momsgrupp för huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="dd994-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="dd994-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="dd994-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

