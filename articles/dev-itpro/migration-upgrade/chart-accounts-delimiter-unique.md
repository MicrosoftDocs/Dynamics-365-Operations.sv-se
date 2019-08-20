---
title: Gör kontoplansavgränsare unika
description: I Dynamics 365 for Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden. Efter uppgraderingen måste du ändra avgränsarvärden.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8cc05772e7ee125a5ce8603c4d5f8719e8895c73
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851781"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="a28b3-104">Gör kontoplansavgränsare unika</span><span class="sxs-lookup"><span data-stu-id="a28b3-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a28b3-105">I Microsoft Dynamics AX 2012 kan använda samma avgränsare i diagrammet över konton och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="a28b3-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="a28b3-106">I Dynamics 365 for Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="a28b3-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="a28b3-107">Om det finns dubbla avgränsare kan du ändra den efter uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="a28b3-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="a28b3-108">Den här funktionen är inte tillgänglig i:</span><span class="sxs-lookup"><span data-stu-id="a28b3-108">This feature is available in:</span></span>
- <span data-ttu-id="a28b3-109">Dynamics 365 for Finance and Operations version 8.0</span><span class="sxs-lookup"><span data-stu-id="a28b3-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="a28b3-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 kan inte ange de ekonomiska dimensionerna när dimensionsvärdena innehåller avgränsare för kontoplan</span><span class="sxs-lookup"><span data-stu-id="a28b3-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="a28b3-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 kan inte välja delprojekt som dimension när delprojektformatet innehåller dimensionsavgränsaren</span><span class="sxs-lookup"><span data-stu-id="a28b3-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="a28b3-112">Uppdatera avgränsare</span><span class="sxs-lookup"><span data-stu-id="a28b3-112">Update delimiter</span></span>
<span data-ttu-id="a28b3-113">Om det finns en konflikt med kontoplanen, kan avgränsare för kontoplanen och projekt eller delprojekt-ID-formatet ändras.</span><span class="sxs-lookup"><span data-stu-id="a28b3-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="a28b3-114">Inga andra avgränsare för dimensionen kan ändras.</span><span class="sxs-lookup"><span data-stu-id="a28b3-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="a28b3-115">Du kan ändra avgränsare för kontoplan efter uppgradering till Finance and Operations i **Allmänna redovisningsparametrar** > **Kontoplan och dimensioner** > **Ändra avgränsare**.</span><span class="sxs-lookup"><span data-stu-id="a28b3-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="a28b3-116">Om den enda konflikten är projekt/delprojekt-ID-formatet kan du ändra det värdet i **Projekthantering och redovisningsparametrar** > **Allmänt** > **Ändra delprojektformat**.</span><span class="sxs-lookup"><span data-stu-id="a28b3-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="a28b3-117">Ta reda på om din miljö kräver uppdaterade avgränsare</span><span class="sxs-lookup"><span data-stu-id="a28b3-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="a28b3-118">Om avgränsare i din uppgraderade miljö står i konflikt, kan du uppleva instabilitet när du anger värden i en segmenterad postkontroll eller dimensionspostkontroll.</span><span class="sxs-lookup"><span data-stu-id="a28b3-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="a28b3-119">Detta innebär att du måste alltid använda sökningar eller en utfälld meny när du anger konto och dimensionskombinationer.</span><span class="sxs-lookup"><span data-stu-id="a28b3-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
