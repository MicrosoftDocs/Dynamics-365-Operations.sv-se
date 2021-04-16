---
title: Tillgångs tjänstenivå
description: I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4163d059fda4ae0120d5c989e744c5a5fe0f5892
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808310"
---
# <a name="asset-service-levels"></a><span data-ttu-id="47250-103">Tillgångs tjänstenivå</span><span class="sxs-lookup"><span data-stu-id="47250-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="47250-104">I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="47250-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="47250-105">Tillgångs tjänstenivåer är relaterade till tillgångar och överförs till underhållsbegäran och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="47250-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="47250-106">De används för att beräkna prioriteten för arbetsorder under arbetsorderplaneringen.</span><span class="sxs-lookup"><span data-stu-id="47250-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="47250-107">Tillgångs tjänstenivåer kan ändras om ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="47250-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="47250-108">Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="47250-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="47250-109">Du måste ställa in minst en standardpost för tillgångs tjänstenivån.</span><span class="sxs-lookup"><span data-stu-id="47250-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="47250-110">Den här standardposten används om ingen annan matchning hittas under arbetsorderplaneringen.</span><span class="sxs-lookup"><span data-stu-id="47250-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="47250-111">**Exempel 1:** Standardtjänstenivå som används om ingen annan matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="47250-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="47250-112">I den här posten väljer du bara en tjänstenivå.</span><span class="sxs-lookup"><span data-stu-id="47250-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="47250-113">**Exempel 2:** en hög tjänstenivå som används för att tidsplanera jobb för en Volvo lastbilsmotor.</span><span class="sxs-lookup"><span data-stu-id="47250-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="47250-114">I den här posten väljer du en relevant tillgångstyp (t.ex. **lastbilsmotor**), en tillverkare (**Volvo**) och en tjänstenivå.</span><span class="sxs-lookup"><span data-stu-id="47250-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="47250-115">Ställ in tillgångs tjänstenivåer</span><span class="sxs-lookup"><span data-stu-id="47250-115">Set up asset service levels</span></span>

1. <span data-ttu-id="47250-116">Välj **tillgångshantering** \> **inställningar** \> **tillgångs tjänstenivåer**.</span><span class="sxs-lookup"><span data-stu-id="47250-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="47250-117">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="47250-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="47250-118">Beroende på den detaljnivå som krävs för tillgången tjänstenivå, göra relevanta val i fälten **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **arbetsordertyp** och **tjänstenivå**.</span><span class="sxs-lookup"><span data-stu-id="47250-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47250-119">När tillgångs tjänstenivå används för underhållsbegäran arbetsorder går tillgångshantering igenom alla tillgångs tillgångs tjänstenivåposter för att kontrollera om det finns en möjlig matchning.</span><span class="sxs-lookup"><span data-stu-id="47250-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="47250-120">Den kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="47250-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="47250-121">Med andra ord söker tillgångshantering först efter en matchning för fältet **arbetsordertyp**.</span><span class="sxs-lookup"><span data-stu-id="47250-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="47250-122">Om ingen matchning hittas söker den efter en matchning för fältet **tillgång** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="47250-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="47250-123">Som du kan se i layouten på sidan **tillgångs tjänstenivåer** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning.</span><span class="sxs-lookup"><span data-stu-id="47250-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="47250-124">Om ingen matchning hittas används den standardpost som inte har några val i dessa fält.</span><span class="sxs-lookup"><span data-stu-id="47250-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="47250-125">I fältet **tjänstnivå** väljer du en siffra som anger tjänstnivån (prioritet).</span><span class="sxs-lookup"><span data-stu-id="47250-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="47250-126">Om du ändrar en tillgångs tjänstenivåpost på sidan **tillgångs tjänstenivåer** när du redan har använt den på en arbetsorder, uppdateras tjänstenivån på underhållsbegäran och arbetsorder inte i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="47250-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]