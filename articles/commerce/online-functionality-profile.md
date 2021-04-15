---
title: Skapa en online funktionsprofil
description: I det här avsnittet beskrivs hur du skapar en funktionsprofil online i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791112"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="dda5a-103">Skapa en onlinefunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="dda5a-103">Create an online functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dda5a-104">Det här ämnet innehåller en översikt över hur du konfigurerar en online funktionsprofil för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dda5a-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dda5a-105">Funktionsprofilen online innehåller olika inställningar som används för onlinekanaler.</span><span class="sxs-lookup"><span data-stu-id="dda5a-105">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="dda5a-106">Varje onlinekanal måste ange en funktionsprofil online.</span><span class="sxs-lookup"><span data-stu-id="dda5a-106">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="dda5a-107">Skapa en online funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="dda5a-107">Create an online functionality profile</span></span>

<span data-ttu-id="dda5a-108">I proceduren nedan beskrivs hur du skapar en funktionsprofil online från appen administration för Commerce.</span><span class="sxs-lookup"><span data-stu-id="dda5a-108">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="dda5a-109">I navigeringsfönstret, gå till **Moduler \> Kanalinställningar \> Online butiksinställningar \> Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="dda5a-109">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="dda5a-110">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dda5a-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="dda5a-111">I fältet **Profil** ange ett ID för profilen.</span><span class="sxs-lookup"><span data-stu-id="dda5a-111">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="dda5a-112">I fältet **Beskrivning** anger du ett värde ("Adventure Works Profile" i exempelbilden nedan).</span><span class="sxs-lookup"><span data-stu-id="dda5a-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="dda5a-113">I avsnittet **funktioner** ändrar du inställningarna för **KUNDVAGN**, **BUTIKSKUNDER** eller **KASSA** efter behov.</span><span class="sxs-lookup"><span data-stu-id="dda5a-113">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="dda5a-114">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dda5a-114">On the action pane, select **Save**.</span></span>

<span data-ttu-id="dda5a-115">I bilden nedan visas ett exempel på funktionsprofil online.</span><span class="sxs-lookup"><span data-stu-id="dda5a-115">The following image shows an example online functionality profile.</span></span>
  
![Exempel på funktionsprofiler online](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="dda5a-117">Funktioner</span><span class="sxs-lookup"><span data-stu-id="dda5a-117">Functions</span></span>

- <span data-ttu-id="dda5a-118">**Aggregera produkter**: när den här funktionen är aktiverad kan kundvagnen uppdatera kvantitet när samma artikel läggs till flera gånger.</span><span class="sxs-lookup"><span data-stu-id="dda5a-118">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="dda5a-119">**Tillåt kassa utan betalningar**: när det här funktionen är aktiverad hanteras scenariot när artiklar som läggs till i vagnen har priset 0,00 $.</span><span class="sxs-lookup"><span data-stu-id="dda5a-119">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="dda5a-120">**Skapa kund i asynkront läge**: det här är en äldre inställning som gäller näthandelskanaler från tredje part och kan inte användas på näthandelssajten Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="dda5a-120">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dda5a-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dda5a-121">Additional resources</span></span>

[<span data-ttu-id="dda5a-122">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="dda5a-122">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="dda5a-123">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="dda5a-123">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="dda5a-124">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="dda5a-124">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="dda5a-125">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="dda5a-125">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="dda5a-126">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="dda5a-126">Set up a call center channel</span></span>](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
