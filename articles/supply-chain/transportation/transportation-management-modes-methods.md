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
ms.openlocfilehash: b9b548212c6f1f3faac56cd7ca182d84cc339bd2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973920"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="425a8-103">Transportföretagslägen och metoder</span><span class="sxs-lookup"><span data-stu-id="425a8-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="425a8-104">Transporthanteringsläget representerar typen av transport som transportföretaget använder för fraktleveranser, till exempel hel lastbilslast, mindre än en lastbilslast eller paket.</span><span class="sxs-lookup"><span data-stu-id="425a8-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="425a8-105">Transportmetoden representerar det transportsätt som transportföretaget använder för fraktleveranser, till exempel luft, land, hav eller järnväg.</span><span class="sxs-lookup"><span data-stu-id="425a8-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="425a8-106">Lägen och transportmetoder används i flera sammanhang.</span><span class="sxs-lookup"><span data-stu-id="425a8-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="425a8-107">Endast lägen används i flödesplaner, medan både lägen och transportmetoder används när transportföretag och transportföretagstjänster ställs in.</span><span class="sxs-lookup"><span data-stu-id="425a8-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="425a8-108">Det finns ingen explicit relation eller hierarki mellan lägen och transportmetoder.</span><span class="sxs-lookup"><span data-stu-id="425a8-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="425a8-109">Skapa ett läge</span><span class="sxs-lookup"><span data-stu-id="425a8-109">Create a mode</span></span>

<span data-ttu-id="425a8-110">Gör så här om du vill skapa ett läge:</span><span class="sxs-lookup"><span data-stu-id="425a8-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="425a8-111">Gå till **Transporthantering \> Inställningar \> Leverantörer \> Läge**.</span><span class="sxs-lookup"><span data-stu-id="425a8-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="425a8-112">Välj **Nytt** för att skapa ett nytt läge.</span><span class="sxs-lookup"><span data-stu-id="425a8-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="425a8-113">Ange ett unikt ID och ett beskrivande namn på läget.</span><span class="sxs-lookup"><span data-stu-id="425a8-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="425a8-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="425a8-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="425a8-115">Skapa en transportmetod</span><span class="sxs-lookup"><span data-stu-id="425a8-115">Create a transportation method</span></span>

<span data-ttu-id="425a8-116">Följ dessa steg för att skapa en transportmetod:</span><span class="sxs-lookup"><span data-stu-id="425a8-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="425a8-117">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportmetoder**.</span><span class="sxs-lookup"><span data-stu-id="425a8-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="425a8-118">Klicka på **Ny** om du vill skapa en ny tranportmetod.</span><span class="sxs-lookup"><span data-stu-id="425a8-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="425a8-119">Ange ett unikt ID och ett beskrivande namn på transportmetoden.</span><span class="sxs-lookup"><span data-stu-id="425a8-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="425a8-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="425a8-120">Close the page.</span></span>
