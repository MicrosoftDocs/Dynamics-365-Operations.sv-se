---
title: Skapa en Retail-funktionsprofil
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
ms.openlocfilehash: a53fc77a7d457534428929bd431175be7cf450f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979657"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="623bb-103">Skapa en Retail-funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="623bb-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="623bb-104">I det här avsnittet beskrivs hur du skapar en funktionsprofil online i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="623bb-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="623bb-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="623bb-105">Overview</span></span>

<span data-ttu-id="623bb-106">Handelsfunktionsprofilen online innehåller olika inställningar som används för onlinekanaler.</span><span class="sxs-lookup"><span data-stu-id="623bb-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="623bb-107">Varje kanal måste ange en funktionsprofil online.</span><span class="sxs-lookup"><span data-stu-id="623bb-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="623bb-108">Skapa en funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="623bb-108">Create a functionality profile</span></span>

<span data-ttu-id="623bb-109">Följ dessa steg för att skapa en ny funktionsprofil.</span><span class="sxs-lookup"><span data-stu-id="623bb-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="623bb-110">I navigeringsfönstret, gå till **Moduler \> Kanalinställningar \> Kassaprofiler \> Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="623bb-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="623bb-111">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="623bb-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="623bb-112">I fältet **Profil** anger du ett ID för profilen ("FN006" i exempelbilden nedan).</span><span class="sxs-lookup"><span data-stu-id="623bb-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="623bb-113">I fältet **Beskrivning** anger du ett värde ("Adventure Works Profile" i exempelbilden nedan).</span><span class="sxs-lookup"><span data-stu-id="623bb-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="623bb-114">I avsnittet **Allmänt** väljer du ett land för **ISO** språk.</span><span class="sxs-lookup"><span data-stu-id="623bb-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="623bb-115">I avsnittet **Allmänt** ändrar du andra inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="623bb-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="623bb-116">I avsnittet **Allmänt**, välj **Kvittoprofil-ID** för e-postkvitton.</span><span class="sxs-lookup"><span data-stu-id="623bb-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="623bb-117">I avsnittet **Funktioner** ändrar du inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="623bb-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="623bb-118">I avsnittet **Belopp** ändrar du inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="623bb-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="623bb-119">I avsnittet **Informationskoder** ändrar du inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="623bb-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="623bb-120">I avsnittet **Kvittonumrering** ändrar du inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="623bb-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="623bb-121">I bilden nedan visas ett exempel på funktionsprofil.</span><span class="sxs-lookup"><span data-stu-id="623bb-121">The following image shows an example functionality profile.</span></span>
  
![Exempel på funktionsprofil](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="623bb-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="623bb-123">Additional resources</span></span>

[<span data-ttu-id="623bb-124">Infokoder och infokodgrupper</span><span class="sxs-lookup"><span data-stu-id="623bb-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="623bb-125">Skapa en ny adressbok.</span><span class="sxs-lookup"><span data-stu-id="623bb-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="623bb-126">Översikt över skärmlayout</span><span class="sxs-lookup"><span data-stu-id="623bb-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="623bb-127">Konfigurera och installera Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="623bb-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
