---
title: Garantiavtal
description: I det här avsnittet beskrivs garantiavtal i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 71905d5b362c80d48b78210b59cacfb1e7899757
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874703"
---
# <a name="warranty-agreements"></a><span data-ttu-id="cf59c-103">Garantiavtal</span><span class="sxs-lookup"><span data-stu-id="cf59c-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="cf59c-104">I Tillgångshantering kan du ställa in garantivillkor som kan kopplas till en tillgång eller till en tillgångstyp.</span><span class="sxs-lookup"><span data-stu-id="cf59c-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="cf59c-105">Garantivillkor skapas för en viss period.</span><span class="sxs-lookup"><span data-stu-id="cf59c-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="cf59c-106">Garantin kan ställas in för att ge fullständig täckning eller deltäckning, och du kan ställa in villkor som är relaterade till timmar, utgifter och artiklar.</span><span class="sxs-lookup"><span data-stu-id="cf59c-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="cf59c-107">Det första steget är att skapa alla leverantörsgarantiavtal som du har för din utrustning.</span><span class="sxs-lookup"><span data-stu-id="cf59c-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="cf59c-108">Du kopplar sedan garantiavtal till tillgångar eller tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="cf59c-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="cf59c-109">Leverantörsgarantiavtal används endast i informationssyfte.</span><span class="sxs-lookup"><span data-stu-id="cf59c-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="cf59c-110">Om leverantörsgaranti har ställts in för en tillgång kan du se garantiperioden för tillgången.</span><span class="sxs-lookup"><span data-stu-id="cf59c-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="cf59c-111">Skapa ett garantiavtal</span><span class="sxs-lookup"><span data-stu-id="cf59c-111">Create a warranty agreement</span></span>

<span data-ttu-id="cf59c-112">Ett garantiavtal kan innehålla flera avtalsrader för att täcka garantin för arbetstid, utgifter och artiklar.</span><span class="sxs-lookup"><span data-stu-id="cf59c-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="cf59c-113">Välj **Tillgångshantering** \> **Inställningar** \> **Tillgångar** \> **Garanti**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="cf59c-114">Välj **Ny** för att skapa en produkt.</span><span class="sxs-lookup"><span data-stu-id="cf59c-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="cf59c-115">Ange ett garanti-ID i fältet **Garanti**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-115">In the **Warranty** field, enter a warranty ID.</span></span>
4. <span data-ttu-id="cf59c-116">Ange en beskrivning i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="cf59c-117">På snabbfliken **Detaljer** visar fältet **Tillgångar** antalet aktiva tillgångar som använder garantiavtalet.</span><span class="sxs-lookup"><span data-stu-id="cf59c-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="cf59c-118">På snabbflikarna **Timgaranti** och **Artikelgaranti** följer du dessa steg för att lägga till rader som ska ingå i ett garantiavtal som gäller för timmar eller artiklar:</span><span class="sxs-lookup"><span data-stu-id="cf59c-118">On the **Hour warranty** and **Item warranty** FastTabs, follow these steps to add lines that should be included in a warranty agreement that pertains to hours or items:</span></span>

    1. <span data-ttu-id="cf59c-119">Välj **Lägg till rad** om du vill lägga till ett nytt villkor i garantin.</span><span class="sxs-lookup"><span data-stu-id="cf59c-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="cf59c-120">Ett sekventiellt nummer anges automatiskt i fältet **Rad**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="cf59c-121">Välj typen av garantiperiod i fältet **Period**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="cf59c-122">Ange ett värde i fältet **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="cf59c-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="cf59c-123">Det här fältet definierar antalet perioder som garantin ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="cf59c-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="cf59c-124">I fältet **Procent** anger du täckningsgraden för garantiraden.</span><span class="sxs-lookup"><span data-stu-id="cf59c-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="cf59c-125">Procentsatsen anger hur mycket som företaget täcker.</span><span class="sxs-lookup"><span data-stu-id="cf59c-125">The percentage indicates how much is covered by your company.</span></span>

![Figur 1](media/01-warranty.png)
