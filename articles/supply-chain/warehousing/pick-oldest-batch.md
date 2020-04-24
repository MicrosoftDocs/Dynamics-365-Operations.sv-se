---
title: Plocka den äldsta batchen på en mobil enhet
description: Det här avsnittet beskriver hur du ställer in och använder alternativen att plocka den äldsta batchen från en mobil enhet.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f235c34d6369c6f0584a7bac1c1be75f3d84c9c0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215641"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="0de32-103">Plocka den äldsta batchen på en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="0de32-103">Pick oldest batch on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0de32-104">Du kan komma åt konfigurationen **Plocka äldsta batchen** via menyn för en mobil enhet och du kan tvinga eller varna lagerarbetare att plocka den äldsta batchen på deras nuvarande plats.</span><span class="sxs-lookup"><span data-stu-id="0de32-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="0de32-105">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="0de32-105">Where it applies</span></span>
<span data-ttu-id="0de32-106">Plocka den äldsta batchen konfigureras på en mobil enhets menyalternativ och påverkar plockningen av batchen under artiklar.</span><span class="sxs-lookup"><span data-stu-id="0de32-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="0de32-107">Hur du ställer in konfigurationen för Plocka äldsta batchen</span><span class="sxs-lookup"><span data-stu-id="0de32-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="0de32-108">För artiklar som är inställda på att använda befintligt arbete kan **Plocka äldsta batchen** ställas in på **Ingen**, **Varna** eller **Tvinga** från menyn i en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="0de32-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="0de32-109">**Ingen**: arbetare får inga meddelanden och tillåts plocka valfri batch på sin plats.</span><span class="sxs-lookup"><span data-stu-id="0de32-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="0de32-110">**Varning** och **Tvinga**: en lista över batchen/batcherna med det äldsta utgångsdatumet visas ovanför batchkontrollen när arbetaren väljer en batch.</span><span class="sxs-lookup"><span data-stu-id="0de32-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="0de32-111">Om platsen är registreringsskyltskontrollerad visas en lista över registreringsskyltar med den äldsta batchen ovanför registreringsskyltskontrollen.</span><span class="sxs-lookup"><span data-stu-id="0de32-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="0de32-112">**Varning**: om en arbetare väljer en registreringsskylt eller en batch som inte finns i listan kommer att kontrollen att nollas och en varning indikerar att det finns en äldre batch att välja.</span><span class="sxs-lookup"><span data-stu-id="0de32-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="0de32-113">För att kunna fortsätta arbetet kan arbetaren välja samma registreringsskylt eller batch igen.</span><span class="sxs-lookup"><span data-stu-id="0de32-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="0de32-114">**Tvinga**: arbetare fortsätter att få meddelanden om att det inte finns en äldre batch att plocka.</span><span class="sxs-lookup"><span data-stu-id="0de32-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>
