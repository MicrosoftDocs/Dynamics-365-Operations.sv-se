---
title: Returnera artiklar för flera kunder, order och fakturor
description: I det här avsnittet beskrivs funktionen som gör det möjligt att returnera via flera kundorder och fakturor i Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
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
ms.openlocfilehash: e95f06ffaaf2d250b02a8458faa2d9e0b5ef5631
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459933"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="a08c1-103">Returnera artiklar för flera kunder, order och fakturor</span><span class="sxs-lookup"><span data-stu-id="a08c1-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="a08c1-104">I den här artikeln beskrivs två funktioner som optimerar kundorderreturer för flera fakturor.</span><span class="sxs-lookup"><span data-stu-id="a08c1-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="a08c1-105">Aktivera återbetalningar för flera poster</span><span class="sxs-lookup"><span data-stu-id="a08c1-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="a08c1-106">Den här funktionen aktiverar flera kopplade återbetalningar mot samma kundorder.</span><span class="sxs-lookup"><span data-stu-id="a08c1-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="a08c1-107">Gå till arbetsytan **Funktionshantering** och sök efter **Aktivera återbetalningar för flera poster**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="a08c1-108">Välj **Aktivera återbetalningar för flera order** och klicka sedan på **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="a08c1-109">Aktivera korrekt momsberäkning för returer med delkvantitet</span><span class="sxs-lookup"><span data-stu-id="a08c1-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="a08c1-110">Med hjälp av den här funktionen kan du se till att momsen blir lika med det momsbelopp som ursprungligen debiterades när en order returneras med hjälp av flera fakturor.</span><span class="sxs-lookup"><span data-stu-id="a08c1-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="a08c1-111">Gå till arbetsytan **Funktionshantering** och sök efter **Aktivera korrekt momsberäkning för returer med delkvantitet**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="a08c1-112">Välj **Aktivera korrekt momsberäkning för returer med delkvantitet** och klicka sedan på **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="a08c1-113">Bearbeta returer</span><span class="sxs-lookup"><span data-stu-id="a08c1-113">Process returns</span></span>

<span data-ttu-id="a08c1-114">När dessa funktioner har aktiverats och ändringarna synkroniserats till butikerna, kan kassören i butiken välja flera försäljningsorder för en kund och göra returer.</span><span class="sxs-lookup"><span data-stu-id="a08c1-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="a08c1-115">När ordern har valts visas en lista över alla produkter på alla fakturor som kan returneras för ordern.</span><span class="sxs-lookup"><span data-stu-id="a08c1-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="a08c1-116">Kassören kan sedan välja vilka produkter som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="a08c1-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="a08c1-117">En enda returorder skapas för alla valda produkter.</span><span class="sxs-lookup"><span data-stu-id="a08c1-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="a08c1-118">Om ordern har returnerats till fullo kommer momsbeloppet som har returnerats till kunden att vara lika med det momsbelopp som ursprungligen debiterades.</span><span class="sxs-lookup"><span data-stu-id="a08c1-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>

