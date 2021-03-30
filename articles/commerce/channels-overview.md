---
title: Översikt över kanaler
description: Det här ämnet innehåller en översikt över kanaler i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8ac188832bdaeba430eed7f08e91a9c2214a0e15
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219111"
---
# <a name="channels-overview"></a><span data-ttu-id="091a6-103">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="091a6-104">Det här ämnet innehåller en översikt över kanaler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="091a6-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="091a6-105">Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in varje kanal.</span><span class="sxs-lookup"><span data-stu-id="091a6-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="091a6-106">Typer av kanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-106">Types of Channels</span></span>

<span data-ttu-id="091a6-107">Dynamics 365 Commerce har stöd för tre olika kanaltyper: butik, kundtjänst och onlinekanaler.</span><span class="sxs-lookup"><span data-stu-id="091a6-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="091a6-108">Butikskanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-108">Retail channels</span></span>

<span data-ttu-id="091a6-109">Butikskanaler utgör fysiska standardbutiker.</span><span class="sxs-lookup"><span data-stu-id="091a6-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="091a6-110">Varje butik kan ha egna kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="091a6-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="091a6-111">Kundtjänstkanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-111">Call center channels</span></span>

<span data-ttu-id="091a6-112">Kundtjänstkanaler representerar kundtjänstorder och kundhantering.</span><span class="sxs-lookup"><span data-stu-id="091a6-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="091a6-113">Onlinekanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-113">Online channels</span></span>

<span data-ttu-id="091a6-114">Online-kanaler representerar onlinebutiker.</span><span class="sxs-lookup"><span data-stu-id="091a6-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="091a6-115">När en onlinekanal har skapats måste en webbplats skapas med hjälp av Microsoft Dynamics 365 Commerce verktyg för webbplatsskapare eller någon annan näthandelslösning från tredje part.</span><span class="sxs-lookup"><span data-stu-id="091a6-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="091a6-116">Grundläggande kanalinställningar</span><span class="sxs-lookup"><span data-stu-id="091a6-116">Channel setup basics</span></span>

<span data-ttu-id="091a6-117">Konfigurera kanaler utförs i handelsverktyget.</span><span class="sxs-lookup"><span data-stu-id="091a6-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="091a6-118">Varje kanal kan ha sina egna betalsätt, prisgrupper, produktvarianter, sortiment och produktuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="091a6-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="091a6-119">När du har skapat en kanal tilldelar du produkter som du vill ha och sälja i butiken.</span><span class="sxs-lookup"><span data-stu-id="091a6-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="091a6-120">Varje kanaltyp har en unik uppsättning funktioner som kan behöva konfigureras.</span><span class="sxs-lookup"><span data-stu-id="091a6-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="091a6-121">Till exempel behöver en butikskanal tilldelade medarbetare, register och kunder.</span><span class="sxs-lookup"><span data-stu-id="091a6-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="091a6-122">När en ny kanal har skapats måste den tilldelas en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="091a6-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="091a6-123">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-123">Channel setup prerequisites</span></span>

<span data-ttu-id="091a6-124">Innan du kan ställa in en kanal måste du slutföra några nödvändiga uppgifter baserade på kanaltypen.</span><span class="sxs-lookup"><span data-stu-id="091a6-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="091a6-125">Mer information finns i [krav för kanalinställning](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="091a6-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="091a6-126">Ställ in en kanal</span><span class="sxs-lookup"><span data-stu-id="091a6-126">Set up a channel</span></span>

<span data-ttu-id="091a6-127">När du har slutfört nödvändiga uppgifter kan du använda följande länkar för ytterligare installationsanvisningar.</span><span class="sxs-lookup"><span data-stu-id="091a6-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="091a6-128">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="091a6-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="091a6-129">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="091a6-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="091a6-130">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="091a6-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="091a6-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="091a6-131">Additional resources</span></span>

[<span data-ttu-id="091a6-132">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="091a6-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="091a6-133">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="091a6-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="091a6-134">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="091a6-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="091a6-135">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="091a6-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="091a6-136">Ange organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="091a6-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]