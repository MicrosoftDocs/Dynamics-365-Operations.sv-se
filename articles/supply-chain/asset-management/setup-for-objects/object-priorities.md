---
title: Tillgångs tjänstenivå
description: I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216586"
---
# <a name="asset-service-levels"></a><span data-ttu-id="fe74a-103">Tillgångs tjänstenivå</span><span class="sxs-lookup"><span data-stu-id="fe74a-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="fe74a-104">I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="fe74a-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="fe74a-105">Tillgångs tjänstenivåer är relaterade till tillgångar och överförs till underhållsbegäran och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="fe74a-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="fe74a-106">De används för att beräkna prioriteten för arbetsorder under arbetsorderplaneringen.</span><span class="sxs-lookup"><span data-stu-id="fe74a-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="fe74a-107">Tillgångs tjänstenivåer kan ändras om ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="fe74a-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="fe74a-108">Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fe74a-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="fe74a-109">Du måste ställa in minst en standardpost för tillgångs tjänstenivån.</span><span class="sxs-lookup"><span data-stu-id="fe74a-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="fe74a-110">Den här standardposten används om ingen annan matchning hittas under arbetsorderplaneringen.</span><span class="sxs-lookup"><span data-stu-id="fe74a-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="fe74a-111">**Exempel 1:** Standardtjänstenivå som används om ingen annan matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="fe74a-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="fe74a-112">I den här posten väljer du bara en tjänstenivå.</span><span class="sxs-lookup"><span data-stu-id="fe74a-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="fe74a-113">**Exempel 2:** en hög tjänstenivå som används för att tidsplanera jobb för en Volvo lastbilsmotor.</span><span class="sxs-lookup"><span data-stu-id="fe74a-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="fe74a-114">I den här posten väljer du en relevant tillgångstyp (t.ex. **lastbilsmotor**), en tillverkare (**Volvo**) och en tjänstenivå.</span><span class="sxs-lookup"><span data-stu-id="fe74a-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="fe74a-115">Ställ in tillgångs tjänstenivåer</span><span class="sxs-lookup"><span data-stu-id="fe74a-115">Set up asset service levels</span></span>

1. <span data-ttu-id="fe74a-116">Välj **tillgångshantering** \> **inställningar** \> **tillgångs tjänstenivåer**.</span><span class="sxs-lookup"><span data-stu-id="fe74a-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="fe74a-117">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="fe74a-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fe74a-118">Beroende på den detaljnivå som krävs för tillgången tjänstenivå, göra relevanta val i fälten **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **arbetsordertyp** och **tjänstenivå**.</span><span class="sxs-lookup"><span data-stu-id="fe74a-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe74a-119">När tillgångs tjänstenivå används för underhållsbegäran arbetsorder går tillgångshantering igenom alla tillgångs tillgångs tjänstenivåposter för att kontrollera om det finns en möjlig matchning.</span><span class="sxs-lookup"><span data-stu-id="fe74a-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="fe74a-120">Den kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="fe74a-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="fe74a-121">Med andra ord söker tillgångshantering först efter en matchning för fältet **arbetsordertyp**.</span><span class="sxs-lookup"><span data-stu-id="fe74a-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="fe74a-122">Om ingen matchning hittas söker den efter en matchning för fältet **tillgång** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="fe74a-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="fe74a-123">Som du kan se i layouten på sidan **tillgångs tjänstenivåer** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning.</span><span class="sxs-lookup"><span data-stu-id="fe74a-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="fe74a-124">Om ingen matchning hittas används den standardpost som inte har några val i dessa fält.</span><span class="sxs-lookup"><span data-stu-id="fe74a-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="fe74a-125">I fältet **tjänstnivå** väljer du en siffra som anger tjänstnivån (prioritet).</span><span class="sxs-lookup"><span data-stu-id="fe74a-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="fe74a-126">Om du ändrar en tillgångs tjänstenivåpost på sidan **tillgångs tjänstenivåer** när du redan har använt den på en arbetsorder, uppdateras tjänstenivån på underhållsbegäran och arbetsorder inte i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="fe74a-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
