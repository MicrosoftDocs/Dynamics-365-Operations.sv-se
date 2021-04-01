---
title: Statusar om transporthantering
description: I det här avsnittet beskrivs hur du skapar en transportstatus och kopplar statusen till ett transportföretagsstatus.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: fb0d98729046330037f96ab7e13a1bf897e35a1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233353"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="61e8c-103">Statusar om transporthantering</span><span class="sxs-lookup"><span data-stu-id="61e8c-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61e8c-104">Ställa in huvudkoder för att transportstatus ska tolka koder som tillhandahålls av transportföretag.</span><span class="sxs-lookup"><span data-stu-id="61e8c-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="61e8c-105">På så sätt kan du integrera med transportföretag som ger status.</span><span class="sxs-lookup"><span data-stu-id="61e8c-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="61e8c-106">Den transportstatus du anger som huvudkod för transportstatus kan hjälpa dig att följa statusen för en last, försändelse eller container.</span><span class="sxs-lookup"><span data-stu-id="61e8c-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="61e8c-107">Den specifika transportstatusen för en last, försändelse eller container kan bara uppdateras genom data integration och inte manuellt via användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="61e8c-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="61e8c-108">Skapa en transportstatus</span><span class="sxs-lookup"><span data-stu-id="61e8c-108">Create a transportation status</span></span>

<span data-ttu-id="61e8c-109">Följ dessa steg för att skapa en transportstatus:</span><span class="sxs-lookup"><span data-stu-id="61e8c-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="61e8c-110">Gå till **Transporthantering \> Inställningar \> Transportstatusmallar**.</span><span class="sxs-lookup"><span data-stu-id="61e8c-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="61e8c-111">Klicka på **Ny** om du vill skapa en transportstatusmall.</span><span class="sxs-lookup"><span data-stu-id="61e8c-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="61e8c-112">I fältet **Transportstatusmall** anger du en unik kod för transportstatus.</span><span class="sxs-lookup"><span data-stu-id="61e8c-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="61e8c-113">I fältet **Transporttyp** väljer du antingen *Transportföretag* eller *Nav* som typ av transport</span><span class="sxs-lookup"><span data-stu-id="61e8c-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="61e8c-114">Ange ett namn och en transportstatus.</span><span class="sxs-lookup"><span data-stu-id="61e8c-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="61e8c-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="61e8c-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="61e8c-116">Mappa en transportstatus till ett transportföretags status</span><span class="sxs-lookup"><span data-stu-id="61e8c-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="61e8c-117">För att mappa en transportstatus till ett transportföretags status följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="61e8c-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="61e8c-118">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretagets transportstatus**.</span><span class="sxs-lookup"><span data-stu-id="61e8c-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="61e8c-119">Klicka på **Ny** om du vill mappa en kod från ett transportföretag till en huvudkod för transportstatus.</span><span class="sxs-lookup"><span data-stu-id="61e8c-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="61e8c-120">Välj den unika ID:t för transportföretaget och transportföretagstjänsten.</span><span class="sxs-lookup"><span data-stu-id="61e8c-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="61e8c-121">Välj den transportstatuskoden som du vill mappa till det valda transportföretagets kod.</span><span class="sxs-lookup"><span data-stu-id="61e8c-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="61e8c-122">Ange den externa kod som används av transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="61e8c-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="61e8c-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="61e8c-123">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]