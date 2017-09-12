---
title: "Orderspärrar"
description: "I det här avsnittet beskrivs spärrar på order i Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 14dab07075a3f042e0095b912e51768ccb086f0e
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="order-holds"></a><span data-ttu-id="f5fc2-103">Orderspärrar</span><span class="sxs-lookup"><span data-stu-id="f5fc2-103">Order holds</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="f5fc2-104">I det här avsnittet beskrivs spärrar på order i Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="f5fc2-105">En order kan parkeras för diverse skäl.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="f5fc2-106">Du kan till exempel lägga en order tills kundens adress eller betalningssätt kan verifieras, eller tills en chef kan granska kundens kreditgräns.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="f5fc2-107">Under säljprocessen, finns det tillfällen när beställningar måste läggas på is.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="f5fc2-108">Till exempel, en säljorder kan parkeras på grund av problem med en kundbetalning, på grund av misstänkt bedrägeri eller eftersom en chef måste granska ordinationen.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="f5fc2-109">När en försäljningsorder parkeras en order håll kod tilldelas försäljning för att ange orsaken till avbrottet.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="f5fc2-110">Försäljningsorder håll koder är konfigurerade på **Försäljning och marknadsföring** &gt; **Installation** &gt; **Försäljningsorder** &gt; **Orderspärrningskoder**.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="f5fc2-111">En kundorder kan parkeras manuellt vid beställningen skapas eller senare.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="f5fc2-112">Dessutom kan en order kan parkeras automatiskt, baserat på bedrägeri.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="f5fc2-113">Medan en försäljningsorder är i vänteläge kan du behöva uppdatera den med mer information.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="f5fc2-114">Alternativt kanske du vill kolla så du fortsätter att arbeta på det.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="f5fc2-115">Du kan checka ut en försäljningsorder, checka in den igen och även åsidosätta utcheckning för en annan användare genom att använda arbetsbänken för att spärra order (**Detaljhandel** &gt; **Kunder** &gt; **Orderspärrar**).</span><span class="sxs-lookup"><span data-stu-id="f5fc2-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="f5fc2-116">När en order är klar att utföras, måste du ta bort spärren innan du kan slutföra orderprocessen.</span><span class="sxs-lookup"><span data-stu-id="f5fc2-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




