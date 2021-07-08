---
title: Produkten är spärrad för transaktioner
description: När du har bekräftat planeringsorder visas ett felmeddelande med information om att artikeln är spärrad för transaktioner
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301289"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="d0bd4-103">Produkten är spärrad för transaktioner</span><span class="sxs-lookup"><span data-stu-id="d0bd4-103">Product is on hold for transactions</span></span>

<span data-ttu-id="d0bd4-104">Felkod: SYS13295</span><span class="sxs-lookup"><span data-stu-id="d0bd4-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="d0bd4-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="d0bd4-105">Symptoms</span></span>

<span data-ttu-id="d0bd4-106">När du har bekräftat planerade order visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="d0bd4-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="d0bd4-107">Artikel %1 har spärrats för transaktioner i %2.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="d0bd4-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="d0bd4-108">Cause</span></span>

<span data-ttu-id="d0bd4-109">När de beskriver spärrade artiklar använder systemet villkoren *spärrade*, *stoppade* och *spärrade* utan att göra det.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="d0bd4-110">Det här felet innebär att artikeln har ställts in som **Stoppad** i sina standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="d0bd4-111">Om en artikel är spärrad och du lägger till den på en inköpsorder- eller försäljningsorderrad visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="d0bd4-112">När artikeln är spärrad kan lagertransaktioner som gäller inköps- eller försäljningsorderraden inte ändras, till exempel när du bokför en följesedel eller en faktura.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="d0bd4-113">Du kan spärra en inköpt artikel och samtidigt sälja artikeln.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="d0bd4-114">I det här fallet markeras kryssrutan **Stoppad** på en inköpsorder, men det är inte spärrat i lager eller på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="d0bd4-115">Här är några av villkoren som kan göra så att ett artikelnummer spärras från att säljas:</span><span class="sxs-lookup"><span data-stu-id="d0bd4-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="d0bd4-116">Artikeln fortfarande är under utveckling eller tillverkning.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="d0bd4-117">Därför vill du inte att den ska säljas eller reserveras.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="d0bd4-118">Du har fått många defekta artiklar, och defekterna måste korrigeras innan artikeln kan säljas.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="d0bd4-119">I fall av denna typ kan du spärra artikeln tills problemet har lösts.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="d0bd4-120">När en artikel är spärrad och du skapar en returorderrad får du ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="d0bd4-121">Du kan inte spärra en serie eller ett parti av artikeln.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="d0bd4-122">Om delar av artikeln ska spärras, kan du göra detta genom att flytta lagret eller genom att spärra hela lagret av denna artikel under den aktuella perioden.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="d0bd4-123">Lösning</span><span class="sxs-lookup"><span data-stu-id="d0bd4-123">Resolution</span></span>

- <span data-ttu-id="d0bd4-124">Öppna sidan **Standardorderinställningar** för artikeln och avmarkera kryssrutan **Stoppat**.</span><span class="sxs-lookup"><span data-stu-id="d0bd4-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
