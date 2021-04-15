---
title: Butiksbutik visas inte i listan över butiker som ska hämtas från
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan plockas.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801613"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="bcb84-103">Butiksbutik visas inte i listan över butiker som ska hämtas från</span><span class="sxs-lookup"><span data-stu-id="bcb84-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bcb84-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan plockas.</span><span class="sxs-lookup"><span data-stu-id="bcb84-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="bcb84-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="bcb84-105">Description</span></span>

<span data-ttu-id="bcb84-106">En butik visas inte i listan över butiker där artiklar kan hämtas.</span><span class="sxs-lookup"><span data-stu-id="bcb84-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="bcb84-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="bcb84-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="bcb84-108">Konfigurera för butiksadressen i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="bcb84-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="bcb84-109">Konfigurera för butiksadressen i Commerce-administration med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="bcb84-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="bcb84-110">Gå till **Retail och Commerce \> Kanaler \> Butiker \> Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="bcb84-111">Hitta den butik som du vill ska visas bland upphämtningsalternativen på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="bcb84-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="bcb84-112">Anteckna dess värde för **Driftenhetsnummer**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="bcb84-113">Gå till **Organisationsadministration \> Organisationer \> Driftenheter**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="bcb84-114">Sök efter numret för den driftenhet som du tidigare noterar och välj sedan driftenhet i sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="bcb84-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="bcb84-115">På snabbfliken **Adresser**, välj **Fler alternativ** och välj **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="bcb84-116">PÅ snabbflikarna **Allmänt** ska du kontrollera att fälten **Longitud** och **Latitud** är korrekt inställda.</span><span class="sxs-lookup"><span data-stu-id="bcb84-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="bcb84-117">Som en del av det här steget ska du kontrollera att värdena har angetts korrekt som positiva eller negativa tal.</span><span class="sxs-lookup"><span data-stu-id="bcb84-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="bcb84-118">Konfigurera uppfyllelsegrupper i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="bcb84-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="bcb84-119">För att konfigurera uppfyllande grupper i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="bcb84-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="bcb84-120">Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="bcb84-121">Välj onlinebutiken som ska konfigureras.</span><span class="sxs-lookup"><span data-stu-id="bcb84-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="bcb84-122">I åtgärdsfönstret, välj **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.</span><span class="sxs-lookup"><span data-stu-id="bcb84-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="bcb84-123">På sidan **Tilldelning av uppfyllelsegrupp**, välj uppfyllelsegrupp för onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="bcb84-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="bcb84-124">Under **Inställningar** bör du kontrollera att butiksbutiken är korrekt konfigurerad för uppfyllelsegruppen.</span><span class="sxs-lookup"><span data-stu-id="bcb84-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bcb84-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bcb84-125">Additional resources</span></span> 

[<span data-ttu-id="bcb84-126">Skapa en driftenhet</span><span class="sxs-lookup"><span data-stu-id="bcb84-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="bcb84-127">Ställa in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="bcb84-127">Set up an online channel</span></span>](../channel-setup-online.md)
