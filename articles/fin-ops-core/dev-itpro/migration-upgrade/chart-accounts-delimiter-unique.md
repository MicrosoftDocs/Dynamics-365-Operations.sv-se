---
title: Gör planavgränsare unika
description: Det här ämnet förklarar hur du inte kan ha samma avgränsare för kontoplanen och dimensionsvärden. Efter uppgraderingen måste du ändra avgränsarvärden.
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
ms.openlocfilehash: 2622245c7ce7213665ab32f4020c282df28cb886
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248790"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="e3ea1-104">Gör kontoplansavgränsare unika</span><span class="sxs-lookup"><span data-stu-id="e3ea1-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3ea1-105">I Microsoft Dynamics AX 2012 kan använda samma avgränsare i diagrammet över konton och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="e3ea1-106">I aktuella versioner av Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-106">In current versions of Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="e3ea1-107">Om det finns dubbla avgränsare kan du ändra den efter uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="e3ea1-108">Den här funktionen finns inte i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="e3ea1-108">This feature is available in the following versions:</span></span>
- <span data-ttu-id="e3ea1-109">Finance and Operations version 8.0</span><span class="sxs-lookup"><span data-stu-id="e3ea1-109">Finance and Operations version 8.0</span></span>
- <span data-ttu-id="e3ea1-110">Finance and Operations version 7.1, KB 4094701 kan inte ange de ekonomiska dimensionerna när dimensionsvärdena innehåller avgränsare för kontoplan</span><span class="sxs-lookup"><span data-stu-id="e3ea1-110">Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="e3ea1-111">Finance and Operations version 7.2, KB 4092967 kan inte välja delprojekt som dimension när delprojektformatet innehåller dimensionsavgränsaren</span><span class="sxs-lookup"><span data-stu-id="e3ea1-111">Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="e3ea1-112">Uppdatera avgränsare</span><span class="sxs-lookup"><span data-stu-id="e3ea1-112">Update delimiter</span></span>
<span data-ttu-id="e3ea1-113">Om det finns en konflikt med kontoplanen, kan avgränsare för kontoplanen och projekt eller delprojekt-ID-formatet ändras.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-113">If there is a conflict with the chart of accounts, the chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="e3ea1-114">Inga andra avgränsare för dimensionen kan ändras.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="e3ea1-115">Du kan ändra avgränsare för kontoplan efter uppgradering i **Allmänna redovisningsparametrar** > **Kontoplan och dimensioner** > **Ändra avgränsare**.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-115">You can change the chart of accounts delimiter after upgrade in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="e3ea1-116">Om den enda konflikten är projekt/delprojekt-ID-formatet kan du ändra det värdet i **Projekthantering och redovisningsparametrar** > **Allmänt** > **Ändra delprojektformat**.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="e3ea1-117">Ta reda på om din miljö kräver uppdaterade avgränsare</span><span class="sxs-lookup"><span data-stu-id="e3ea1-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="e3ea1-118">Om avgränsare i din uppgraderade miljö står i konflikt, kan du uppleva instabilitet när du anger värden i en segmenterad postkontroll eller dimensionspostkontroll.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="e3ea1-119">Detta innebär att du måste alltid använda sökningar eller en utfälld meny när du anger konto och dimensionskombinationer.</span><span class="sxs-lookup"><span data-stu-id="e3ea1-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
