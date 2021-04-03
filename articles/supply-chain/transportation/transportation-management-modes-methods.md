---
title: Transportföretagslägen och metoder
description: I det här avsnittet beskrivs hur du ställer in lägen och metoder för transporthantering.
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
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 0d41d8665252a978962bf6a2e307dce3dad64a5b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233449"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="e6fc2-103">Transportföretagslägen och metoder</span><span class="sxs-lookup"><span data-stu-id="e6fc2-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6fc2-104">Transporthanteringsläget representerar typen av transport som transportföretaget använder för fraktleveranser, till exempel hel lastbilslast, mindre än en lastbilslast eller paket.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="e6fc2-105">Transportmetoden representerar det transportsätt som transportföretaget använder för fraktleveranser, till exempel luft, land, hav eller järnväg.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="e6fc2-106">Lägen och transportmetoder används i flera sammanhang.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="e6fc2-107">Endast lägen används i flödesplaner, medan både lägen och transportmetoder används när transportföretag och transportföretagstjänster ställs in.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="e6fc2-108">Det finns ingen explicit relation eller hierarki mellan lägen och transportmetoder.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="e6fc2-109">Skapa ett läge</span><span class="sxs-lookup"><span data-stu-id="e6fc2-109">Create a mode</span></span>

<span data-ttu-id="e6fc2-110">Gör så här om du vill skapa ett läge:</span><span class="sxs-lookup"><span data-stu-id="e6fc2-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="e6fc2-111">Gå till **Transporthantering \> Inställningar \> Leverantörer \> Läge**.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="e6fc2-112">Välj **Nytt** för att skapa ett nytt läge.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="e6fc2-113">Ange ett unikt ID och ett beskrivande namn på läget.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="e6fc2-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="e6fc2-115">Skapa en transportmetod</span><span class="sxs-lookup"><span data-stu-id="e6fc2-115">Create a transportation method</span></span>

<span data-ttu-id="e6fc2-116">Följ dessa steg för att skapa en transportmetod:</span><span class="sxs-lookup"><span data-stu-id="e6fc2-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="e6fc2-117">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportmetoder**.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="e6fc2-118">Klicka på **Ny** om du vill skapa en ny tranportmetod.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="e6fc2-119">Ange ett unikt ID och ett beskrivande namn på transportmetoden.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="e6fc2-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e6fc2-120">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]