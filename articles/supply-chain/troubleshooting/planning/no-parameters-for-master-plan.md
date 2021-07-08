---
title: Parametrar för huvudplanen finns inte
description: När du försöker bekräfta planerade order visas ett felmeddelande som anger att inga parametrar finns för huvudplanen.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294184"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a><span data-ttu-id="9c00d-103">Parametrar för huvudplanen finns inte</span><span class="sxs-lookup"><span data-stu-id="9c00d-103">Parameters for the master plan don't exist</span></span>

<span data-ttu-id="9c00d-104">Felkod: SYS25368</span><span class="sxs-lookup"><span data-stu-id="9c00d-104">Error code: SYS25368</span></span>

## <a name="symptoms"></a><span data-ttu-id="9c00d-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="9c00d-105">Symptoms</span></span>

<span data-ttu-id="9c00d-106">När du har bekräftat planerade order visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="9c00d-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="9c00d-107">Parametrar för huvudplan %1 finns inte.</span><span class="sxs-lookup"><span data-stu-id="9c00d-107">Parameters for master plan %1 do not exist.</span></span>

## <a name="cause"></a><span data-ttu-id="9c00d-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="9c00d-108">Cause</span></span>

<span data-ttu-id="9c00d-109">På grund av konfigurationsproblem hittar systemet inte inställningarna för den angivna planen.</span><span class="sxs-lookup"><span data-stu-id="9c00d-109">Because of configuration issues, the system can't find the settings for the specified plan.</span></span>

## <a name="resolution"></a><span data-ttu-id="9c00d-110">Lösning</span><span class="sxs-lookup"><span data-stu-id="9c00d-110">Resolution</span></span>

- <span data-ttu-id="9c00d-111">Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner** och se till att det finns en plan med det angivna namnet.</span><span class="sxs-lookup"><span data-stu-id="9c00d-111">Go to **Master planning \> Setup \> Plans \> Master plans**, and make sure that a plan that has the specified name exists.</span></span>
