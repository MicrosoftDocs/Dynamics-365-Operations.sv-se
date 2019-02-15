---
title: Returnera artiklar för flera kunder, order och fakturor
description: I det här avsnittet beskrivs funktionen som gör det möjligt att returnera via flera kundorder och fakturor i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 1/08/2019
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
ms.openlocfilehash: d2cf6f92e90ef196827abb599c65c732615ec7bb
ms.sourcegitcommit: e72eae546d48d41d4b07ff78cfc0242c32b793e7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2019
ms.locfileid: "373078"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="63b40-103">Returnera artiklar för flera kunder, order och fakturor</span><span class="sxs-lookup"><span data-stu-id="63b40-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="63b40-104">I Dynamics 365 for Finance and Operations version 10.0 kan du göra returer av flera order och fakturor. I tidigare versioner än 10.0 kunde bara returer bearbetas en faktura i taget.</span><span class="sxs-lookup"><span data-stu-id="63b40-104">In Dynamics 365 for Finance and Operations version 10.0, returns can be made across multiple orders and invoices, whereas in releases prior to 10.0, returns could only be processed by a single invoice at a time.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="63b40-105">Konfigurera Retail så att det går att göra returer för flera kundorder och fakturor</span><span class="sxs-lookup"><span data-stu-id="63b40-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="63b40-106">Gå till **Retail-parametrar \> Kundorder**.</span><span class="sxs-lookup"><span data-stu-id="63b40-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="63b40-107">Aktivera parametern **Aktivera returer för flera order**.</span><span class="sxs-lookup"><span data-stu-id="63b40-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="63b40-108">Bearbeta returer</span><span class="sxs-lookup"><span data-stu-id="63b40-108">Process returns</span></span>

<span data-ttu-id="63b40-109">När parametern är aktiverad och ändringarna synkroniserats till butikerna, kan kassören i butiken välja flera försäljningsorder för en kund och göra returer.</span><span class="sxs-lookup"><span data-stu-id="63b40-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="63b40-110">När ordern har valts visas en lista över alla produkter på alla fakturor som kan returneras för ordern.</span><span class="sxs-lookup"><span data-stu-id="63b40-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="63b40-111">Kassören kan sedan välja vilka produkter som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="63b40-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="63b40-112">En enda returorder skapas för alla valda produkter.</span><span class="sxs-lookup"><span data-stu-id="63b40-112">A single return order will be created for all the selected products.</span></span>
