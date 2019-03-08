---
title: Avrundningsbelopp för avskrivningsberäkningar.
description: Den här artikeln diskuterar fältet Avrundning av avskrivning som finns på inställningssidorna för räkenskapsbok.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7721e46a72e0f8133ed67c597a066a97ffd61669
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "308424"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="1581e-103">Avrundningsbelopp för avskrivningsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="1581e-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1581e-104">Den här artikeln diskuterar fältet Avrundning av avskrivning som finns på inställningssidorna för räkenskapsbok.</span><span class="sxs-lookup"><span data-stu-id="1581e-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="1581e-105">Avrundningsbeloppet för avskrivning anges för varje bok.</span><span class="sxs-lookup"><span data-stu-id="1581e-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="1581e-106">Avrundningsbeloppet för avskrivning används i avskrivningsprofilen för anläggningstillgångar som visar den framtida avskrivningen, värdet på anläggningstillgången och även i avskrivningsförslag.</span><span class="sxs-lookup"><span data-stu-id="1581e-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="1581e-107">Ange lägsta tillåtna avskrivningsbelopp för räkenskapsboken.</span><span class="sxs-lookup"><span data-stu-id="1581e-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="1581e-108">Oavsett avrundningen som har ställts in avrundas inte avskrivningsbeloppet i den sista avskrivningsperioden.</span><span class="sxs-lookup"><span data-stu-id="1581e-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="1581e-109">I slutet av den sista avskrivningsperioden måste värdet på anläggningstillgången måste vara 0 (noll) eller kassationsvärdet, om kassationsvärde används.</span><span class="sxs-lookup"><span data-stu-id="1581e-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="1581e-110">Exempel</span><span class="sxs-lookup"><span data-stu-id="1581e-110">Example</span></span>

<span data-ttu-id="1581e-111">Avskrivning utan avrundning beräknas som 2 444,44.</span><span class="sxs-lookup"><span data-stu-id="1581e-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="1581e-112">Som följande tabell visar varierar beloppen som föreslås beroende på hur avrundningen är inställd.</span><span class="sxs-lookup"><span data-stu-id="1581e-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="1581e-113">Avrundningsmetod</span><span class="sxs-lookup"><span data-stu-id="1581e-113">Rounding method</span></span> | <span data-ttu-id="1581e-114">Avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="1581e-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="1581e-115">Avrundning 0,1</span><span class="sxs-lookup"><span data-stu-id="1581e-115">Rounding 0.1</span></span>    | <span data-ttu-id="1581e-116">2 444,40</span><span class="sxs-lookup"><span data-stu-id="1581e-116">2,444.40</span></span>            |
| <span data-ttu-id="1581e-117">Avrundning 1,00</span><span class="sxs-lookup"><span data-stu-id="1581e-117">Rounding 1.00</span></span>   | <span data-ttu-id="1581e-118">2 444,00</span><span class="sxs-lookup"><span data-stu-id="1581e-118">2,444.00</span></span>            |
| <span data-ttu-id="1581e-119">Avrundning 10,00</span><span class="sxs-lookup"><span data-stu-id="1581e-119">Rounding 10.00</span></span>  | <span data-ttu-id="1581e-120">2 440,00</span><span class="sxs-lookup"><span data-stu-id="1581e-120">2,440.00</span></span>            |
| <span data-ttu-id="1581e-121">Avrundning 100,00</span><span class="sxs-lookup"><span data-stu-id="1581e-121">Rounding 100.00</span></span> | <span data-ttu-id="1581e-122">2 400,00</span><span class="sxs-lookup"><span data-stu-id="1581e-122">2,400.00</span></span>            |





