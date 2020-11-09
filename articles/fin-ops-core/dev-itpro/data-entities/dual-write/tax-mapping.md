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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 26818ceace7d2b7e7c3ed4d0bb0bd9ab2e884aba
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997610"
---
# <a name="integrated-tax"></a><span data-ttu-id="7958a-103">Integrerad moms</span><span class="sxs-lookup"><span data-stu-id="7958a-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="7958a-104">Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt.</span><span class="sxs-lookup"><span data-stu-id="7958a-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="7958a-105">Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.</span><span class="sxs-lookup"><span data-stu-id="7958a-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="7958a-106">Mallar</span><span class="sxs-lookup"><span data-stu-id="7958a-106">Templates</span></span>

<span data-ttu-id="7958a-107">Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="7958a-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="7958a-108">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="7958a-108">Finance and Operations apps</span></span> | <span data-ttu-id="7958a-109">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7958a-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="7958a-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7958a-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="7958a-111">Artikelmomsgrupp</span><span class="sxs-lookup"><span data-stu-id="7958a-111">Item sales tax group</span></span> | <span data-ttu-id="7958a-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="7958a-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="7958a-113">Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="7958a-113">Sales tax authorities</span></span> | <span data-ttu-id="7958a-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="7958a-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="7958a-115">Momsbefrielsekod CDS</span><span class="sxs-lookup"><span data-stu-id="7958a-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="7958a-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="7958a-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="7958a-117">Momsgrupper</span><span class="sxs-lookup"><span data-stu-id="7958a-117">Sales tax groups</span></span> | <span data-ttu-id="7958a-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="7958a-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="7958a-119">Bokföringsgrupper V2 för momsredovisning</span><span class="sxs-lookup"><span data-stu-id="7958a-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="7958a-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="7958a-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="7958a-121">Källskattekoder</span><span class="sxs-lookup"><span data-stu-id="7958a-121">Withholding tax codes</span></span> | <span data-ttu-id="7958a-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="7958a-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="7958a-123">Källskattegrupper</span><span class="sxs-lookup"><span data-stu-id="7958a-123">Withholding tax groups</span></span> | <span data-ttu-id="7958a-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="7958a-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

