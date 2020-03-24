---
title: Förutsättningar för att ställa in kanaler
description: Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0da0457240cf12686fff2fa929c7fb510c11f242
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113792"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="9dddf-103">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="9dddf-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9dddf-104">Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9dddf-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9dddf-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="9dddf-105">Overview</span></span>

<span data-ttu-id="9dddf-106">Innan du kan skapa en Dynamics 365 Commerce-kanal måste flera nödvändiga uppgifter slutföras.</span><span class="sxs-lookup"><span data-stu-id="9dddf-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="9dddf-107">Följande lista över nödvändiga uppgifter är ordnade efter kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="9dddf-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="9dddf-108">En del dokumentation håller fortfarande på att skrivas och länkar uppdateras när nytt innehåll publiceras.</span><span class="sxs-lookup"><span data-stu-id="9dddf-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="9dddf-109">Initialisering</span><span class="sxs-lookup"><span data-stu-id="9dddf-109">Initialization</span></span>

- [<span data-ttu-id="9dddf-110">Initiera startdata</span><span class="sxs-lookup"><span data-stu-id="9dddf-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="9dddf-111">Globala förutsättningar krävs för alla kanaltyper</span><span class="sxs-lookup"><span data-stu-id="9dddf-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="9dddf-112">Definiera och konfigurera din juridiska organisationens struktur</span><span class="sxs-lookup"><span data-stu-id="9dddf-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="9dddf-113">Konfigurera din organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="9dddf-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="9dddf-114">Ställ in ett lagerställen</span><span class="sxs-lookup"><span data-stu-id="9dddf-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="9dddf-115">Konfigurera moms</span><span class="sxs-lookup"><span data-stu-id="9dddf-115">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="9dddf-116">Ange en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="9dddf-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="9dddf-117">Ställa in nummerserier</span><span class="sxs-lookup"><span data-stu-id="9dddf-117">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="9dddf-118">Ställa in en standardkund och adressbok</span><span class="sxs-lookup"><span data-stu-id="9dddf-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="9dddf-119">Förutsättningar för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="9dddf-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="9dddf-120">Infokoder och infokodgrupper</span><span class="sxs-lookup"><span data-stu-id="9dddf-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="9dddf-121">Konfigurera en butiksfunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="9dddf-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="9dddf-122">Konfigurera en medarbetaradressbok</span><span class="sxs-lookup"><span data-stu-id="9dddf-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="9dddf-123">Ställ in en skärmlayout</span><span class="sxs-lookup"><span data-stu-id="9dddf-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="9dddf-124">Konfigurera en maskinvarustation</span><span class="sxs-lookup"><span data-stu-id="9dddf-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="9dddf-125">Förutsättningar för kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="9dddf-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="9dddf-126">Parametrar för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="9dddf-126">Call center parameters</span></span>
- [<span data-ttu-id="9dddf-127">Kundtjänstorder och återbetalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="9dddf-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="9dddf-128">Leveranssätt och avgifter för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="9dddf-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="9dddf-129">Förutsättningar för onlinekanal</span><span class="sxs-lookup"><span data-stu-id="9dddf-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="9dddf-130">Skapa en onlinefunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="9dddf-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="9dddf-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9dddf-131">Additional resources</span></span>

[<span data-ttu-id="9dddf-132">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="9dddf-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9dddf-133">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="9dddf-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="9dddf-134">Ange organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="9dddf-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="9dddf-135">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="9dddf-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="9dddf-136">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="9dddf-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="9dddf-137">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="9dddf-137">Set up an online channel</span></span>](channel-setup-online.md)
