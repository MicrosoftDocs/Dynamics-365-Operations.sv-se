---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av skattedata mellan Finance and Operations och Common Data Service.
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
ms.openlocfilehash: 0d32a5f7859f0200da823a73d94b9a6b2a9c8e7d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020016"
---
# <a name="integrated-tax"></a><span data-ttu-id="e316c-103">Integrerad moms</span><span class="sxs-lookup"><span data-stu-id="e316c-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="e316c-104">Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt.</span><span class="sxs-lookup"><span data-stu-id="e316c-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="e316c-105">Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.</span><span class="sxs-lookup"><span data-stu-id="e316c-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="e316c-106">Mallar</span><span class="sxs-lookup"><span data-stu-id="e316c-106">Templates</span></span>

<span data-ttu-id="e316c-107">Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e316c-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="e316c-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e316c-108">Finance and Operations</span></span>   | <span data-ttu-id="e316c-109">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="e316c-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="e316c-110">Skattekoder</span><span class="sxs-lookup"><span data-stu-id="e316c-110">Tax codes</span></span>                  | <span data-ttu-id="e316c-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="e316c-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="e316c-112">Skattegrupper</span><span class="sxs-lookup"><span data-stu-id="e316c-112">Tax groups</span></span>               | <span data-ttu-id="e316c-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="e316c-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="e316c-114">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="e316c-114">Tax item groups</span></span>          | <span data-ttu-id="e316c-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="e316c-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="e316c-116">Undantag från skatteplikt</span><span class="sxs-lookup"><span data-stu-id="e316c-116">Tax Exemptions</span></span>           | <span data-ttu-id="e316c-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="e316c-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="e316c-118">Skattemyndighet</span><span class="sxs-lookup"><span data-stu-id="e316c-118">Tax Authorities</span></span>          | <span data-ttu-id="e316c-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="e316c-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="e316c-120">Källskattekoder</span><span class="sxs-lookup"><span data-stu-id="e316c-120">Withholding tax codes</span></span>      | <span data-ttu-id="e316c-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="e316c-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="e316c-122">Källskattegrupper</span><span class="sxs-lookup"><span data-stu-id="e316c-122">Withholding tax groups</span></span>   | <span data-ttu-id="e316c-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="e316c-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="e316c-124">Momsgrupp för huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="e316c-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="e316c-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="e316c-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

