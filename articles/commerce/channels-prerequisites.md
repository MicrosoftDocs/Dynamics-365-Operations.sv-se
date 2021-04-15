---
title: Förutsättningar för att ställa in kanaler
description: Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
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
ms.openlocfilehash: 33fcead6c0b08db17f24b638376a23b8b6024a5b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800529"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="98d8c-103">Förutsättningar för kanalinställningar</span><span class="sxs-lookup"><span data-stu-id="98d8c-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="98d8c-104">Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="98d8c-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="98d8c-105">Innan du kan skapa en Dynamics 365 Commerce-kanal måste flera nödvändiga uppgifter slutföras.</span><span class="sxs-lookup"><span data-stu-id="98d8c-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="98d8c-106">Följande lista över nödvändiga uppgifter är ordnade efter kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="98d8c-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="98d8c-107">En del dokumentation håller fortfarande på att skrivas och länkar uppdateras när nytt innehåll publiceras.</span><span class="sxs-lookup"><span data-stu-id="98d8c-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="98d8c-108">Initialisering</span><span class="sxs-lookup"><span data-stu-id="98d8c-108">Initialization</span></span>

- [<span data-ttu-id="98d8c-109">Initiera startdata</span><span class="sxs-lookup"><span data-stu-id="98d8c-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="98d8c-110">Globala förutsättningar krävs för alla kanaltyper</span><span class="sxs-lookup"><span data-stu-id="98d8c-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="98d8c-111">Definiera och konfigurera din juridiska organisationens struktur</span><span class="sxs-lookup"><span data-stu-id="98d8c-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="98d8c-112">Konfigurera din organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="98d8c-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="98d8c-113">Ställ in ett lagerställen</span><span class="sxs-lookup"><span data-stu-id="98d8c-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="98d8c-114">Konfigurera moms</span><span class="sxs-lookup"><span data-stu-id="98d8c-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="98d8c-115">Ange en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="98d8c-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="98d8c-116">Ställa in nummerserier</span><span class="sxs-lookup"><span data-stu-id="98d8c-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="98d8c-117">Ställa in en standardkund och adressbok</span><span class="sxs-lookup"><span data-stu-id="98d8c-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="98d8c-118">Förutsättningar för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="98d8c-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="98d8c-119">Infokoder och infokodgrupper</span><span class="sxs-lookup"><span data-stu-id="98d8c-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="98d8c-120">Konfigurera en butiksfunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="98d8c-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="98d8c-121">Konfigurera en medarbetaradressbok</span><span class="sxs-lookup"><span data-stu-id="98d8c-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="98d8c-122">Ställ in en skärmlayout</span><span class="sxs-lookup"><span data-stu-id="98d8c-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="98d8c-123">Konfigurera en maskinvarustation</span><span class="sxs-lookup"><span data-stu-id="98d8c-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="98d8c-124">Förutsättningar för kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="98d8c-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="98d8c-125">Parametrar för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="98d8c-125">Call center parameters</span></span>
- [<span data-ttu-id="98d8c-126">Kundtjänstorder och återbetalsätt</span><span class="sxs-lookup"><span data-stu-id="98d8c-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="98d8c-127">Leveranssätt och avgifter för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="98d8c-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="98d8c-128">Förutsättningar för onlinekanal</span><span class="sxs-lookup"><span data-stu-id="98d8c-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="98d8c-129">Skapa en onlinefunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="98d8c-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="98d8c-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="98d8c-130">Additional resources</span></span>

[<span data-ttu-id="98d8c-131">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="98d8c-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="98d8c-132">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="98d8c-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="98d8c-133">Ange organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="98d8c-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="98d8c-134">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="98d8c-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="98d8c-135">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="98d8c-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="98d8c-136">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="98d8c-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
