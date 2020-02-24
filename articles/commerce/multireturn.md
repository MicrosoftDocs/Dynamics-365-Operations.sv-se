---
title: Returnera artiklar för flera kunder, order och fakturor
description: I det här avsnittet beskrivs funktionen som gör det möjligt att returnera via flera kundorder och fakturor i Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004468"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="2e379-103">Returnera artiklar för flera kunder, order och fakturor</span><span class="sxs-lookup"><span data-stu-id="2e379-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="2e379-104">Returer kan göras för flera order och fakturor.</span><span class="sxs-lookup"><span data-stu-id="2e379-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="2e379-105">Konfigurera Commerce så att det går att göra returer för flera kundorder och fakturor</span><span class="sxs-lookup"><span data-stu-id="2e379-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="2e379-106">Gå till **Commerce-parametrar \> Kundorder**.</span><span class="sxs-lookup"><span data-stu-id="2e379-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="2e379-107">Aktivera parametern **Aktivera returer för flera order**.</span><span class="sxs-lookup"><span data-stu-id="2e379-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="2e379-108">Bearbeta returer</span><span class="sxs-lookup"><span data-stu-id="2e379-108">Process returns</span></span>

<span data-ttu-id="2e379-109">När parametern är aktiverad och ändringarna synkroniserats till butikerna, kan kassören i butiken välja flera försäljningsorder för en kund och göra returer.</span><span class="sxs-lookup"><span data-stu-id="2e379-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="2e379-110">När ordern har valts visas en lista över alla produkter på alla fakturor som kan returneras för ordern.</span><span class="sxs-lookup"><span data-stu-id="2e379-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="2e379-111">Kassören kan sedan välja vilka produkter som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="2e379-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="2e379-112">En enda returorder skapas för alla valda produkter.</span><span class="sxs-lookup"><span data-stu-id="2e379-112">A single return order will be created for all the selected products.</span></span>
