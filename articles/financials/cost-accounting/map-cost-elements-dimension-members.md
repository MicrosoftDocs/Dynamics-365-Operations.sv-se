---
title: Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar
description: Genom att mappa olika dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar för kostnadselement slår du samman data till ett gemensamt format för analysändamål.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e5c9387d74443ec6ca5dc70ad923b67f962181dc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "318153"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="a2716-103">Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="a2716-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2716-104">Genom att mappa olika dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar för kostnadselement slår du samman data till ett gemensamt format för analysändamål.</span><span class="sxs-lookup"><span data-stu-id="a2716-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="a2716-105">Om du är ett globalt företag och följer lagstadgade redovisningsbestämmelser, kan du använda flera kontoplaner.</span><span class="sxs-lookup"><span data-stu-id="a2716-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="a2716-106">När du importerar dimensionsmedlemmar för kostnadselement från olika kontoplaner, kan du sluta med en blandning av konton.</span><span class="sxs-lookup"><span data-stu-id="a2716-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="a2716-107">Dessa konton är kanske emellertid av samma slag och du vill kanske analysera och fördela kostnader för dem, genom att använda ett gemensamt format.</span><span class="sxs-lookup"><span data-stu-id="a2716-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="a2716-108">Mappa dimensionsmedlemmar för kostnadselement till en gemensamt format</span><span class="sxs-lookup"><span data-stu-id="a2716-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="a2716-109">Följande exempel visar hur du som en kostnadscontroller kan skapa en ny dimension för kostnadselement i som mappar dimensionsmedlemmar för kostnadselement för den amerikanska kontoplanstrukturen och den franska kontoplanstrukturen till en gemensam uppsättning med dimensionsmedlemmar för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a2716-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="a2716-110">Du kan sedan använda den gemensam uppsättningen med dimensionsmedlemmar för kostnadselement om du vill analysera kostnadsdata från de två juridiska personerna i en kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="a2716-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="a2716-111">Källa: amerikanska kontoplanen</span><span class="sxs-lookup"><span data-stu-id="a2716-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="a2716-112">Källa: franska kontoplanen</span><span class="sxs-lookup"><span data-stu-id="a2716-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="a2716-113">Ny gemensam uppsättning med dimensionsmedlemmar för kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a2716-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="a2716-114">Importerade dimensionsmedlemmar för kostnadselement från den amerikanska kontoplanen</span><span class="sxs-lookup"><span data-stu-id="a2716-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="a2716-115">Importerade dimensionsmedlemmar för kostnadselement från den franska kontoplanen</span><span class="sxs-lookup"><span data-stu-id="a2716-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="a2716-116">Mappning av franska och amerikanska dimensionsmedlemmar för kostnadselement till en gemensam uppsättning</span><span class="sxs-lookup"><span data-stu-id="a2716-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="a2716-117">5001: Försäljning</span><span class="sxs-lookup"><span data-stu-id="a2716-117">5001: Sales</span></span>                                                           | <span data-ttu-id="a2716-118">5001: Försäljning och reklam</span><span class="sxs-lookup"><span data-stu-id="a2716-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="a2716-119">5000: Försäljning och reklam</span><span class="sxs-lookup"><span data-stu-id="a2716-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="a2716-120">5030: Reklam</span><span class="sxs-lookup"><span data-stu-id="a2716-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="a2716-121">6390: Lagerinköp\*</span><span class="sxs-lookup"><span data-stu-id="a2716-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="a2716-122">7000: Rengöringskostnader</span><span class="sxs-lookup"><span data-stu-id="a2716-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="a2716-123">7001: Rengöringskostnader</span><span class="sxs-lookup"><span data-stu-id="a2716-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="a2716-124">7001: Reseutgifter</span><span class="sxs-lookup"><span data-stu-id="a2716-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="a2716-125">7001: Reseutgifter</span><span class="sxs-lookup"><span data-stu-id="a2716-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="a2716-126">\*Lagerinköp för franska dimensionsmedlemmar för kostnadselement är inte mappade.</span><span class="sxs-lookup"><span data-stu-id="a2716-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="a2716-127">Valutakonvertering</span><span class="sxs-lookup"><span data-stu-id="a2716-127">Currency conversion</span></span>
<span data-ttu-id="a2716-128">De olika kontoplanerna som du använder, kan kanske ställas in för att använda olika valutor.</span><span class="sxs-lookup"><span data-stu-id="a2716-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="a2716-129">Kontrollera att du anger en valutakonvertering så att kostnadsdata bearbetas, genom att använda korrekt valuta, enligt definitionen i kostnadsredovisningen där dimensionsmedlemmar för kostnadselement används.</span><span class="sxs-lookup"><span data-stu-id="a2716-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="a2716-130">I föregående exempel om amerikanska dollar (USD) används i kostnadsredovisningen, måste du skapa en valutakonvertering från USD till euro (EUR) för att bearbeta transaktioner för de mappade dimensionsmedlemmarna för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a2716-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="a2716-131">Uppdatera mappningar när som helst</span><span class="sxs-lookup"><span data-stu-id="a2716-131">Update mappings at any time</span></span>
<span data-ttu-id="a2716-132">Du kan uppdatera mappningdefinitioner för en dimension för kostnadselement när som helst.</span><span class="sxs-lookup"><span data-stu-id="a2716-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="a2716-133">Eftersom mappningar inte har giltighetsdatum, tillämpas ändringar nästa gång du bearbetar kostnadstransaktioner eller kör kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="a2716-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>



