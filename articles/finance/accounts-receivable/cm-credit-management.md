---
title: Hantering av kundkredit
description: ''
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
ms.openlocfilehash: 11da8b7fb59bc8f3e2568ada27db753cc815b9c2
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015398"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="28034-102">Hantering av kundkredit - översikt</span><span class="sxs-lookup"><span data-stu-id="28034-102">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="28034-103">Med hjälp av hantering av kundkredit kan du hantera kreditgränser och styra flödet av försäljningsorder via bokföringsprocessen baserat på de kreditregler som du skapar.</span><span class="sxs-lookup"><span data-stu-id="28034-103">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="28034-104">Processen för att använda kredithantering kan omfatta en del av eller alla av följande steg:</span><span class="sxs-lookup"><span data-stu-id="28034-104">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="28034-105">Uppdatera kunder med kreditegenskaper som ger ytterligare information om deras kreditvärdighet</span><span class="sxs-lookup"><span data-stu-id="28034-105">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="28034-106">Skapa kreditgränser för kunder genom att använda kreditgränsjusteringar</span><span class="sxs-lookup"><span data-stu-id="28034-106">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="28034-107">Skapa tillfälliga kreditgränser för kunder som använder kreditgränsjusteringar när de tillfälligt vill öka eller minska sin kreditgräns baserat på affärsbehov</span><span class="sxs-lookup"><span data-stu-id="28034-107">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="28034-108">Lägg till ytterligare information som kan påverka kreditgränsen, t.ex. försäkring och garantier</span><span class="sxs-lookup"><span data-stu-id="28034-108">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="28034-109">Skapa kundkreditgrupper som kopplar samman kunder så att de kan dela en enda kreditgräns</span><span class="sxs-lookup"><span data-stu-id="28034-109">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="28034-110">Tilldela riskpoäng till kunder och använd sedan poängen för att automatiskt generera kreditgränser för kunder genom att använda kreditgränsjusteringar</span><span class="sxs-lookup"><span data-stu-id="28034-110">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="28034-111">Skapa spärrningsregler som gör att en order spärras under en eller flera bokföringsprocesser baserat på faktorer som risk, betalningsvillkor, kreditgränser, förfallna belopp och procent av kreditgräns som används</span><span class="sxs-lookup"><span data-stu-id="28034-111">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="28034-112">Hantera en lista över försäljningsorder som är spärrade, granska orsakerna till undantaget och minska problemen</span><span class="sxs-lookup"><span data-stu-id="28034-112">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="28034-113">Frisläpp försäljningsorder och tillåt det att fortsätta under bokföringsprocessen</span><span class="sxs-lookup"><span data-stu-id="28034-113">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="28034-114">Ställ in arbetsflöde för att hantera godkännandet av kreditgränsändringar och frisläppning av försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="28034-114">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="28034-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="28034-115">Additional resources</span></span>
--------
[<span data-ttu-id="28034-116">Inställningar för parametrar för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="28034-116">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="28034-117">Inställningar för information för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="28034-117">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="28034-118">Lägg till information för kredithantering för en kund</span><span class="sxs-lookup"><span data-stu-id="28034-118">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="28034-119">Kreditgrupper för kund</span><span class="sxs-lookup"><span data-stu-id="28034-119">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="28034-120">Justering av kundkreditgräns</span><span class="sxs-lookup"><span data-stu-id="28034-120">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="28034-121">Kreditspärrar för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="28034-121">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="28034-122">Periodiska kredithanteringsuppgifter för kund</span><span class="sxs-lookup"><span data-stu-id="28034-122">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


