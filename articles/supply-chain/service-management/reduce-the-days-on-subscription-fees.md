---
title: "Minska antalet dagar på abonnemangsavgifter"
description: "Om du vill minska antalet dagar för en befintlig abonnemangsavgift kan du skapa en ny transaktion där du tar bort en tidsperiod som inte längre ska ingå i intervallet för abonnemangsavgiften."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c70e393c125eecef85e8711d1635250f5ff408d9
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="5e01d-103">Minska antalet dagar på abonnemangsavgifter</span><span class="sxs-lookup"><span data-stu-id="5e01d-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5e01d-104">Om du vill minska antalet dagar för en befintlig abonnemangsavgift kan du skapa en ny transaktion där du tar bort en tidsperiod som inte längre ska ingå i intervallet för abonnemangsavgiften.</span><span class="sxs-lookup"><span data-stu-id="5e01d-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="5e01d-105">Minska antalet dagar för en abonnemangsavgift</span><span class="sxs-lookup"><span data-stu-id="5e01d-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="5e01d-106">Klicka på **Servicehantering** \> **Vanligt** \> **Serviceabonnemang** \> **Alla serviceabonnemang**.</span><span class="sxs-lookup"><span data-stu-id="5e01d-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="5e01d-107">Välj serviceabonnemanget, och i åtgärdsfönstret, klickar du på **Abonnemangsavgifter**</span><span class="sxs-lookup"><span data-stu-id="5e01d-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="5e01d-108">I fältet **abonnemang** väljer du **reduceringsdagar**.</span><span class="sxs-lookup"><span data-stu-id="5e01d-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="5e01d-109">Ange datumintervallet i fältet **Från-datum** och **Till-datum** för abonnemangsavgiften som du vill ta bort från abonnemangsavgiftsperioden, och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e01d-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="5e01d-110">Om du vill visa den transaktion som skapas klickar du på **Abonnemang**, klicka på **Avgiftstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="5e01d-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="5e01d-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="5e01d-111">Example</span></span>

<span data-ttu-id="5e01d-112">Om en abonnemangstransaktionsperiod löper från 1 januari till 31 januari, och du vill minska perioden med 10 dagar, skapar du en ny transaktion där reduceringsperioden är 1 januari till den 10 januari.</span><span class="sxs-lookup"><span data-stu-id="5e01d-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="5e01d-113">(Reduceringsperioden kan också vara 5 januari till 15 januari eller någon annan 10-dagars period.)</span><span class="sxs-lookup"><span data-stu-id="5e01d-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="5e01d-114">Om **Från-datum** för reduceringsperioden är 21 januari (31 minus 10) kan du också ställa in **Till-datum** till något datum efter 31 januari och 10 dagar tas ändå bort från avgiftstransaktionsperioden.</span><span class="sxs-lookup"><span data-stu-id="5e01d-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e01d-115">Se även</span><span class="sxs-lookup"><span data-stu-id="5e01d-115">See also</span></span>

[<span data-ttu-id="5e01d-116">Exempel på avdragsdagar</span><span class="sxs-lookup"><span data-stu-id="5e01d-116">Reduction days example</span></span>](reduction-days-example.md)

  


