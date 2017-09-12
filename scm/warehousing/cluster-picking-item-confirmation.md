---
title: "Produktbekräftelse för klusterplockning"
description: "Det här avsnittet beskrivs hur du konfigurerar artikelverifieraing tillsammans med klusterplockning."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 17f5761df4294abfea28e7cb8d50c86f1e3e136f
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

[!include[banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="ff9b0-103">Produktbekräftelse för klusterplockning</span><span class="sxs-lookup"><span data-stu-id="ff9b0-103">Product confirmation for cluster picking</span></span>
<span data-ttu-id="ff9b0-104">Klusterplockning kan du plockar artiklar för flera order samtidigt.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="ff9b0-105">När klusterplockning används, är objektbekräftelse avgörande för att kontrollera de objekt som läggs till ett kluster.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="ff9b0-106">Du kan kontrollera objekt i klusterplockning vid klusterplockningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="ff9b0-107">När det gäller</span><span class="sxs-lookup"><span data-stu-id="ff9b0-107">Where it applies</span></span>
<span data-ttu-id="ff9b0-108">Objektverifiering för klusterplockning fungerar på samma sätt som när du kontrollerar objekt i en icke-klusterplockningsprocess.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="ff9b0-109">Inställningen är baserad på inställning av produktstreckkoder.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="ff9b0-110">Ställa in objektverifiering med klusterplockning</span><span class="sxs-lookup"><span data-stu-id="ff9b0-110">Set up item verification with cluster picking</span></span>
1.  <span data-ttu-id="ff9b0-111">På den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: **lagerstyrning** > **lagerstyrning** > **inställningar** > **mobil enhet** > **mobila enhetens menyalternativ**.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
2.  <span data-ttu-id="ff9b0-112">Från mobila enhetens menyalternativ öppnar du **Inställning av arbetsbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

| <span data-ttu-id="ff9b0-113">Alternativ</span><span class="sxs-lookup"><span data-stu-id="ff9b0-113">Option</span></span>        | <span data-ttu-id="ff9b0-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff9b0-114">Description</span></span>   | 
| ------------- | ------------- |
|<span data-ttu-id="ff9b0-115">Produktbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ff9b0-115">Product confirmation</span></span> | <span data-ttu-id="ff9b0-116">Låter dig kontrollera varje lagerenhet från den mobila enheten när du har skannat.</span><span class="sxs-lookup"><span data-stu-id="ff9b0-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span>|

