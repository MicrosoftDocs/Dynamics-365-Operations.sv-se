---
title: Kundposter visas inte i Commerce-administration
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce-administration.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: b8d065dd104df616ba8f10f7813e74c900fdcf77
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018492"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="0c1e8-103">Kundposter visas inte i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="0c1e8-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0c1e8-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="0c1e8-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0c1e8-105">Description</span></span>

<span data-ttu-id="0c1e8-106">När du skapar en ny kundpost med hjälp av inloggningsflödet i e-handelsbutiken visas inte motsvarande kundpost direkt i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="0c1e8-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="0c1e8-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="0c1e8-108">Inaktivera skapande av kunder i asynkront läge</span><span class="sxs-lookup"><span data-stu-id="0c1e8-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c1e8-109">Om du inaktiverar asynkrona kundgenereringen kan systemprestanda påverkas eftersom varje post skapas en begäran i realtid till Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="0c1e8-110">Om Commerce-administration dessutom är ned (till exempel under serviceflöden), orsakar eventuella nya kundgenereringsflöden fel.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="0c1e8-111">Om du vill inaktivera skapande av kunder i asynkrona läget i Commerce-administration följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="0c1e8-112">Gå till **Retail och Commerce \> Kanalinställningar \> Inställningen för onlinebutik \> Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="0c1e8-113">Om du inte redan använder en funktionsprofil för din onlinekanal skapar du en.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="0c1e8-114">Kontrollera att alternativet **Skapa kund i asynkront läge** anges till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="0c1e8-115">Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="0c1e8-116">Välj den onlinebutik som du vill inaktivera asynkront kundgenerering för.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="0c1e8-117">På fliken **Allmänt**, se till att fältet **funktionsprofilen** är inställd på den funktionsprofil som du använder för din onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="0c1e8-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c1e8-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0c1e8-118">Additional resources</span></span>

[<span data-ttu-id="0c1e8-119">Ställa in en B2C-klientorganisation i Commerce</span><span class="sxs-lookup"><span data-stu-id="0c1e8-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
