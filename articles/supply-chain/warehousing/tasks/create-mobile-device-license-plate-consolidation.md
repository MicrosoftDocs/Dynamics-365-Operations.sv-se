--- 
title: "Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer"
description: "I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar."
author: YuyuScheller
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 107f3dc015e0de49ea0e61cea9a0aa0c22d39b2b
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="941d0-103">Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="941d0-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="941d0-104">I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.</span><span class="sxs-lookup"><span data-stu-id="941d0-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="941d0-105">Detta gör det möjligt för lagerarbetare att konsolidera artiklar på en enda registreringsskylt med artiklar på en annan registreringsskylt på samma plats.</span><span class="sxs-lookup"><span data-stu-id="941d0-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="941d0-106">Exempelvis kan de använda detta om efterföljande mellanlagring var desamma på båda arbetsordrar, så att arbetsuppgiften endast måste utföras en enda gång för de sammanslagna artiklarna.</span><span class="sxs-lookup"><span data-stu-id="941d0-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="941d0-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="941d0-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="941d0-108">Denna uppgift utförs vanligtvis av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="941d0-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="941d0-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="941d0-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="941d0-110">Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="941d0-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="941d0-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="941d0-111">Click New.</span></span>
3. <span data-ttu-id="941d0-112">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="941d0-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="941d0-113">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="941d0-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="941d0-114">Välj "Indirect" i fältet Model.</span><span class="sxs-lookup"><span data-stu-id="941d0-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="941d0-115">Välj "Consolidate license plates" i fältet Activity code.</span><span class="sxs-lookup"><span data-stu-id="941d0-115">In the Activity code field, select 'Consolidate license plates'.</span></span>


