---
title: Allvarlighetsgradtyper för tillgång
description: Det här avsnittet beskriver allvarlighetsgradtyper för tillgång i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660038060826ade9301e50143e49b53ba3fcd3ab
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783605"
---
# <a name="asset-criticalities"></a><span data-ttu-id="3bb8a-103">Allvarlighetsgrad för tillgång</span><span class="sxs-lookup"><span data-stu-id="3bb8a-103">Asset criticalities</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3bb8a-104">Det här avsnittet beskriver allvarlighetsgradtyper för tillgång i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="3bb8a-105">Tillgångarnas allvarlighetsgrad är relaterad till tillgångar och överförs till arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="3bb8a-106">Det går inte att ändra på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-106">It can't be changed on a work order.</span></span> <span data-ttu-id="3bb8a-107">Tillgångens allvarlighetsgrad används för att beräkna allvarlighetsgrad för arbetsorder vid schemaläggning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="3bb8a-108">Med andra ord används den för att beräkna i vilken utsträckning ett underhållsjobb på en tillgång påverkar produktionsschemat och produktiviteten i företaget.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="3bb8a-109">Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="3bb8a-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="3bb8a-110">Om du vill ställa in allvarlighetsgrad kan du först skapa allvarlighetsgradtyper som ska användas i tillgångsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="3bb8a-111">Du ställer sedan in allvarlighetsgrad för tillgång.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="3bb8a-112">Ställ in allvarlighetsgradtyper</span><span class="sxs-lookup"><span data-stu-id="3bb8a-112">Set up criticality types</span></span>

1. <span data-ttu-id="3bb8a-113">Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **allvarlighetsgradtyper**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="3bb8a-114">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3bb8a-115">I fältet **allvarlighetsgrad** anger du ett nummer som indikerar allvarlighetsgraden.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="3bb8a-116">Ange ett namn för allvarlighetsgradtypen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="3bb8a-117">Ange en faktor i fältet **Faktor**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="3bb8a-118">Den här faktorn används under beräkningen av arbetsorderplanering för att fastställa den allvarlighetsgradpost som ska användas.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="3bb8a-119">(Den post som har den högsta faktorn används alltid.) Den här inställningen är relevant om, som visas i följande illustration, allvarlighetsgradrader skapas som har samma allvarlighetsgradvärde.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Figur 1](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="3bb8a-121">Ställ in allvarlighetsgrad för tillgång</span><span class="sxs-lookup"><span data-stu-id="3bb8a-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="3bb8a-122">Välj **tillgångshantering** \> **inställningar** \> **allvarlighetsgrad för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="3bb8a-123">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3bb8a-124">Beroende på hur önskad detaljnivå för allvarlighetsgrad för tillgång, gör relevanta val i **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **jobbtyp**, **jobbtypvariant**och **jobbkrav**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3bb8a-125">När en allvarlighetsgrad för tillgång har valts går tillgångshanteraren igenom alla poster för tillgångens allvarlighetsgrad för att kontrollera om det finns en möjlig matchning.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="3bb8a-126">Den kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="3bb8a-127">Med andra ord kontrollerar tillgångshantering först **jobbehov**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="3bb8a-128">Om ingen matchning hittas kontrollerar den **jobbtypvariant**.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="3bb8a-129">Om ingen matchning hittas kontrollerar den **jobbtyp**, osv.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="3bb8a-130">Som du kan se i layouten på sidan innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="3bb8a-131">Om ingen matchning hittas används den standardpost som inte har några val.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="3bb8a-132">I fältet **allvarlighetsgrad** väljer du en av de allvarlighetsgradvärden som du skapade i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="3bb8a-133">Anmärkningar om inställning av allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="3bb8a-133">Notes about criticality setup</span></span>

- <span data-ttu-id="3bb8a-134">Om du ändrar en tillgångs allvarlighetsgrad i den här inställningen när du redan har använt den på en arbetsorder, uppdateras inte allvarlighetsgraden på arbetsordern i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="3bb8a-135">Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderrad läggs till eller tas bort från arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="3bb8a-136">Om en arbetsorder innehåller flera arbetsorderjobb, används alltid den högsta allvarlighetsgraden enligt fältet **faktor** på sidan **allvarlighetsgradtyper** på arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="3bb8a-137">I allmänhet kan tillgångens allvarlighetsgrad ändras under en period.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="3bb8a-138">Allvarlighetsgrad kan påverkas av inköp av ny utrustning, renoveringar, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="3bb8a-139">Överväg att omvärdera din tillgångs allvarlighetsgrad med jämna mellanrum (till exempel en gång per år eller vartannat år) för att se till att dina allvarlighetsgraddefinitioner matchar din aktuella produktionsinställning.</span><span class="sxs-lookup"><span data-stu-id="3bb8a-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>
