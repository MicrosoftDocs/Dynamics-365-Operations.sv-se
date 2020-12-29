---
title: Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer
description: I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dc52284473f3e3275675b608386641c8570218b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437531"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="e6162-103">Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="e6162-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e6162-104">I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.</span><span class="sxs-lookup"><span data-stu-id="e6162-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="e6162-105">Detta gör det möjligt för lagerarbetare att konsolidera artiklar på en enda registreringsskylt med artiklar på en annan registreringsskylt på samma plats.</span><span class="sxs-lookup"><span data-stu-id="e6162-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="e6162-106">Exempelvis kan de använda detta om efterföljande mellanlagring var desamma på båda arbetsordrar, så att arbetsuppgiften endast måste utföras en enda gång för de sammanslagna artiklarna.</span><span class="sxs-lookup"><span data-stu-id="e6162-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="e6162-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e6162-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="e6162-108">Denna uppgift utförs vanligtvis av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="e6162-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="e6162-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="e6162-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="e6162-110">Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="e6162-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="e6162-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e6162-111">Click New.</span></span>
3. <span data-ttu-id="e6162-112">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="e6162-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="e6162-113">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="e6162-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="e6162-114">Välj "Indirect" i fältet Model.</span><span class="sxs-lookup"><span data-stu-id="e6162-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="e6162-115">Välj "Consolidate license plates" i fältet Activity code.</span><span class="sxs-lookup"><span data-stu-id="e6162-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

