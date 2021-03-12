---
title: Skapa en online funktionsprofil
description: I det här avsnittet beskrivs hur du skapar en funktionsprofil online i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1b0afeabfecb60672156692f3cd809445624020c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969986"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="37281-103">Skapa en online funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="37281-103">Create an online functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="37281-104">Det här ämnet innehåller en översikt över hur du konfigurerar en online funktionsprofil för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="37281-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="37281-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="37281-105">Overview</span></span>

<span data-ttu-id="37281-106">Funktionsprofilen online innehåller olika inställningar som används för onlinekanaler.</span><span class="sxs-lookup"><span data-stu-id="37281-106">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="37281-107">Varje onlinekanal måste ange en funktionsprofil online.</span><span class="sxs-lookup"><span data-stu-id="37281-107">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="37281-108">Skapa en online funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="37281-108">Create an online functionality profile</span></span>

<span data-ttu-id="37281-109">I proceduren nedan beskrivs hur du skapar en funktionsprofil online från appen administration för Commerce.</span><span class="sxs-lookup"><span data-stu-id="37281-109">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="37281-110">I navigeringsfönstret, gå till **Moduler \> Kanalinställningar \> Online butiksinställningar \> Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="37281-110">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="37281-111">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="37281-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="37281-112">I fältet **Profil** ange ett ID för profilen.</span><span class="sxs-lookup"><span data-stu-id="37281-112">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="37281-113">I fältet **Beskrivning** anger du ett värde ("Adventure Works Profile" i exempelbilden nedan).</span><span class="sxs-lookup"><span data-stu-id="37281-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="37281-114">I avsnittet **funktioner** ändrar du inställningarna för **KUNDVAGN**, **BUTIKSKUNDER** eller **KASSA** efter behov.</span><span class="sxs-lookup"><span data-stu-id="37281-114">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="37281-115">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="37281-115">On the action pane, select **Save**.</span></span>

<span data-ttu-id="37281-116">I bilden nedan visas ett exempel på funktionsprofil online.</span><span class="sxs-lookup"><span data-stu-id="37281-116">The following image shows an example online functionality profile.</span></span>
  
![Exempel på funktionsprofiler online](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="37281-118">Funktioner</span><span class="sxs-lookup"><span data-stu-id="37281-118">Functions</span></span>

- <span data-ttu-id="37281-119">**Aggregera produkter**: när den här funktionen är aktiverad kan kundvagnen uppdatera kvantitet när samma artikel läggs till flera gånger.</span><span class="sxs-lookup"><span data-stu-id="37281-119">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="37281-120">**Tillåt kassa utan betalningar**: när det här funktionen är aktiverad hanteras scenariot när artiklar som läggs till i vagnen har priset 0,00 $.</span><span class="sxs-lookup"><span data-stu-id="37281-120">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="37281-121">**Skapa kund i asynkront läge**: det här är en äldre inställning som gäller näthandelskanaler från tredje part och kan inte användas på näthandelssajten Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="37281-121">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="37281-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="37281-122">Additional resources</span></span>

[<span data-ttu-id="37281-123">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="37281-123">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="37281-124">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="37281-124">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="37281-125">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="37281-125">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="37281-126">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="37281-126">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="37281-127">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="37281-127">Set up a call center channel</span></span>](channel-setup-callcenter.md)
