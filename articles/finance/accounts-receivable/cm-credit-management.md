---
title: Hantering av kundkredit
description: Med hjälp av hantering av kundkredit kan du hantera kreditgränser och styra flödet av försäljningsorder via bokföringsprocessen baserat på de kreditregler som du skapar.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1e7d3325587d7cfc876e8f8c7b9207d44046ccd4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124287"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="252e9-103">Hantering av kundkredit - översikt</span><span class="sxs-lookup"><span data-stu-id="252e9-103">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="252e9-104">Med hjälp av hantering av kundkredit kan du hantera kreditgränser och styra flödet av försäljningsorder via bokföringsprocessen baserat på de kreditregler som du skapar.</span><span class="sxs-lookup"><span data-stu-id="252e9-104">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="252e9-105">Processen för att använda kredithantering kan omfatta en del av eller alla av följande steg:</span><span class="sxs-lookup"><span data-stu-id="252e9-105">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="252e9-106">Uppdatera kunder med kreditegenskaper som ger ytterligare information om deras kreditvärdighet</span><span class="sxs-lookup"><span data-stu-id="252e9-106">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="252e9-107">Skapa kreditgränser för kunder genom att använda kreditgränsjusteringar</span><span class="sxs-lookup"><span data-stu-id="252e9-107">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="252e9-108">Skapa tillfälliga kreditgränser för kunder som använder kreditgränsjusteringar när de tillfälligt vill öka eller minska sin kreditgräns baserat på affärsbehov</span><span class="sxs-lookup"><span data-stu-id="252e9-108">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="252e9-109">Lägg till ytterligare information som kan påverka kreditgränsen, t.ex. försäkring och garantier</span><span class="sxs-lookup"><span data-stu-id="252e9-109">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="252e9-110">Skapa kundkreditgrupper som kopplar samman kunder så att de kan dela en enda kreditgräns</span><span class="sxs-lookup"><span data-stu-id="252e9-110">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="252e9-111">Tilldela riskpoäng till kunder och använd sedan poängen för att automatiskt generera kreditgränser för kunder genom att använda kreditgränsjusteringar</span><span class="sxs-lookup"><span data-stu-id="252e9-111">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="252e9-112">Skapa spärrningsregler som gör att en order spärras under en eller flera bokföringsprocesser baserat på faktorer som risk, betalningsvillkor, kreditgränser, förfallna belopp och procent av kreditgräns som används</span><span class="sxs-lookup"><span data-stu-id="252e9-112">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="252e9-113">Hantera en lista över försäljningsorder som är spärrade, granska orsakerna till undantaget och minska problemen</span><span class="sxs-lookup"><span data-stu-id="252e9-113">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="252e9-114">Frisläpp försäljningsorder och tillåt det att fortsätta under bokföringsprocessen</span><span class="sxs-lookup"><span data-stu-id="252e9-114">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="252e9-115">Ställ in arbetsflöde för att hantera godkännandet av kreditgränsändringar och frisläppning av försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="252e9-115">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="252e9-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="252e9-116">Additional resources</span></span>
--------
[<span data-ttu-id="252e9-117">Inställningar för parametrar för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="252e9-117">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="252e9-118">Inställningar för information för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="252e9-118">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="252e9-119">Lägg till information för kredithantering för en kund</span><span class="sxs-lookup"><span data-stu-id="252e9-119">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="252e9-120">Kreditgrupper för kund</span><span class="sxs-lookup"><span data-stu-id="252e9-120">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="252e9-121">Justering av kundkreditgräns</span><span class="sxs-lookup"><span data-stu-id="252e9-121">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="252e9-122">Kreditspärrar för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="252e9-122">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="252e9-123">Periodiska kredithanteringsuppgifter för kund</span><span class="sxs-lookup"><span data-stu-id="252e9-123">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


