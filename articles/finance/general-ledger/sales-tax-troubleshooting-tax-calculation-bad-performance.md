---
title: Resultatet av momsberäkningen påverkar transaktioner
description: Detta ämne innehåller felsökningsinformation som är relaterad till momsberäkningsprestanda och dess effekt på transaktioner.
author: shtao
manager: beya
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ff9d9b80172c3b337737b1cd53b4c56d1befe57
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947713"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="22287-103">Resultatet av momsberäkningen påverkar transaktioner</span><span class="sxs-lookup"><span data-stu-id="22287-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22287-104">Ibland påverkas en transaktion av prestandaproblem som momsberäkningen har.</span><span class="sxs-lookup"><span data-stu-id="22287-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="22287-105">Felsök det här problemet genom att följa stegen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="22287-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="22287-106">Granska antalet transaktionsrader</span><span class="sxs-lookup"><span data-stu-id="22287-106">Review the transaction line count</span></span>

<span data-ttu-id="22287-107">Bestäm huruvida transaktionen har ett stort antal rader (t.ex. fler än flera hundra).</span><span class="sxs-lookup"><span data-stu-id="22287-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="22287-108">Om den inte gör det går du vidare till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="22287-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="22287-109">Om transaktionen har flera hundra rader försenar du momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="22287-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="22287-110">Mer information finns i [Aktivera fördröjd momsberäkning i journaler](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="22287-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="22287-111">Du kan sedan avgöra om något av följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="22287-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="22287-112">Det finns importtransaktioner från stora filer.</span><span class="sxs-lookup"><span data-stu-id="22287-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="22287-113">Flera sessioner bearbetar samma transaktionsskatteberäkning samtidigt.</span><span class="sxs-lookup"><span data-stu-id="22287-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="22287-114">Transaktionen har flera rader och vyerna uppdateras i realtid.</span><span class="sxs-lookup"><span data-stu-id="22287-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="22287-115">Till exempel uppdateras fältet **Beräknat momsbelopp** på sidan **Allmän journal** uppdateras i realtid när en rads fält ändras.</span><span class="sxs-lookup"><span data-stu-id="22287-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="22287-116">[![Beräknat momsbeloppsfält på sidan Journalverifikation](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="22287-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="22287-117">Om något av dessa villkor uppfylls ska du försena momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="22287-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="22287-118">Granska anropsstacken</span><span class="sxs-lookup"><span data-stu-id="22287-118">Review the call stack</span></span>

<span data-ttu-id="22287-119">Granska anropsstacken för att avgöra om momsberäkningen anropas flera gånger.</span><span class="sxs-lookup"><span data-stu-id="22287-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="22287-120">Om den inte gör det går du vidare till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="22287-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="22287-121">Om anropsstacken anropas flera gånger följer du dessa steg för att minska momsberäkningstiderna.</span><span class="sxs-lookup"><span data-stu-id="22287-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="22287-122">Om transaktionen har övervägts i journalen försenar du momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="22287-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="22287-123">Mer information finns i [Aktivera fördröjd momsberäkning i journaler](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="22287-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="22287-124">Om transaktionen är en inköpsorder och programversionen är senare än 10.0.15 kan du försena momsberäkningen till den slutliga beräkningen genom att aktivera förhandsversionen för **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="22287-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="22287-125">Granska tidslinjen för anropsstacken</span><span class="sxs-lookup"><span data-stu-id="22287-125">Review the call stack timeline</span></span>

<span data-ttu-id="22287-126">Granska tidslinjen för anropsstacken och ta reda på huruvida följande problem finns:</span><span class="sxs-lookup"><span data-stu-id="22287-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="22287-127">Om de gör det ska du aktivera förhandsversionen för **TaxUncommittedDoIsolateScopeFlighting** för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="22287-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="22287-128">Transaktionen gör att systemet slutar svara tills sessionen avslutas.</span><span class="sxs-lookup"><span data-stu-id="22287-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="22287-129">Därför kan momsresultatet inte beräknas i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="22287-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="22287-130">I följande bild visas meddelandet "Sessionen avslutad" som du får.</span><span class="sxs-lookup"><span data-stu-id="22287-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="22287-131">[![Meddelande om att sessionen avslutats](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="22287-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="22287-132">Metoden **TaxUncommitted** tar mer tid än andra metoder.</span><span class="sxs-lookup"><span data-stu-id="22287-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="22287-133">I följande illustration tar metoden **TaxUncommitted::updateTaxUncommitted()** 43 347,42 sekunder, men andra metoder tar 0,09 sekunder.</span><span class="sxs-lookup"><span data-stu-id="22287-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="22287-134">[![Tidslängder för metod](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="22287-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="22287-135">Anpassa och anropa momsberäkning</span><span class="sxs-lookup"><span data-stu-id="22287-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="22287-136">När du anpassar ska du inte anropa momsberäkningen vid metoden **insert()** eller **update()** för respektive rad.</span><span class="sxs-lookup"><span data-stu-id="22287-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="22287-137">Momsberäkning ska anropas på transaktionsnivå.</span><span class="sxs-lookup"><span data-stu-id="22287-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="22287-138">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="22287-138">Determine whether customization exists</span></span>

<span data-ttu-id="22287-139">Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="22287-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="22287-140">Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="22287-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
