---
title: Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer
description: I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfe07426e9ff11c60c5f703b810ba09d6c863399
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "343660"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="51f9c-103">Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="51f9c-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51f9c-104">I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.</span><span class="sxs-lookup"><span data-stu-id="51f9c-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="51f9c-105">Detta gör det möjligt för lagerarbetare att konsolidera artiklar på en enda registreringsskylt med artiklar på en annan registreringsskylt på samma plats.</span><span class="sxs-lookup"><span data-stu-id="51f9c-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="51f9c-106">Exempelvis kan de använda detta om efterföljande mellanlagring var desamma på båda arbetsordrar, så att arbetsuppgiften endast måste utföras en enda gång för de sammanslagna artiklarna.</span><span class="sxs-lookup"><span data-stu-id="51f9c-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="51f9c-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="51f9c-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="51f9c-108">Denna uppgift utförs vanligtvis av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="51f9c-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="51f9c-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="51f9c-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="51f9c-110">Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="51f9c-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="51f9c-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="51f9c-111">Click New.</span></span>
3. <span data-ttu-id="51f9c-112">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="51f9c-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="51f9c-113">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="51f9c-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="51f9c-114">Välj "Indirect" i fältet Model.</span><span class="sxs-lookup"><span data-stu-id="51f9c-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="51f9c-115">Välj "Consolidate license plates" i fältet Activity code.</span><span class="sxs-lookup"><span data-stu-id="51f9c-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

