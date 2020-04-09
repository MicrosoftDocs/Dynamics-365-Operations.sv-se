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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173095"
---
# <a name="integrated-tax"></a><span data-ttu-id="ce379-103">Integrerad moms</span><span class="sxs-lookup"><span data-stu-id="ce379-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ce379-104">Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt.</span><span class="sxs-lookup"><span data-stu-id="ce379-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="ce379-105">Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.</span><span class="sxs-lookup"><span data-stu-id="ce379-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="ce379-106">Mallar</span><span class="sxs-lookup"><span data-stu-id="ce379-106">Templates</span></span>

<span data-ttu-id="ce379-107">Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ce379-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="ce379-108">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="ce379-108">Finance and Operations apps</span></span> | <span data-ttu-id="ce379-109">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ce379-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="ce379-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ce379-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="ce379-111">Momskoder</span><span class="sxs-lookup"><span data-stu-id="ce379-111">Tax codes</span></span>                   | <span data-ttu-id="ce379-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="ce379-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="ce379-113">Skattegrupper</span><span class="sxs-lookup"><span data-stu-id="ce379-113">Tax groups</span></span>                 | <span data-ttu-id="ce379-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="ce379-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="ce379-115">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="ce379-115">Tax item groups</span></span>             | <span data-ttu-id="ce379-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="ce379-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="ce379-117">Undantag från skatteplikt</span><span class="sxs-lookup"><span data-stu-id="ce379-117">Tax Exemptions</span></span>             | <span data-ttu-id="ce379-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="ce379-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="ce379-119">Skattemyndighet</span><span class="sxs-lookup"><span data-stu-id="ce379-119">Tax Authorities</span></span>             | <span data-ttu-id="ce379-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="ce379-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="ce379-121">Källskattekoder</span><span class="sxs-lookup"><span data-stu-id="ce379-121">Withholding tax codes</span></span>       | <span data-ttu-id="ce379-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="ce379-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="ce379-123">Källskattegrupper</span><span class="sxs-lookup"><span data-stu-id="ce379-123">Withholding tax groups</span></span>     | <span data-ttu-id="ce379-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="ce379-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="ce379-125">Momsgrupp för huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="ce379-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="ce379-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="ce379-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

