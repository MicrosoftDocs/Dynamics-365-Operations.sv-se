---
title: Översikt över arbetsflöde för abonnemang
description: Det här ämnet ger en översikt över arbetsflöde för abonnemang.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbc87dc9c6327550020270468346800a7b80f4c3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817399"
---
# <a name="subscription-workflow-overview"></a><span data-ttu-id="d8ebe-103">Översikt över arbetsflöde för abonnemang</span><span class="sxs-lookup"><span data-stu-id="d8ebe-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d8ebe-104">Du är abonnemangsadministratör för ett ljusföretag som erbjuder abonnemang på underhåll av ljusramper.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="d8ebe-105">En kund kommer till ditt företag för att köpa ett årsabonnemang på underhåll av ljusramper.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="d8ebe-106">Ställa in abonnemang</span><span class="sxs-lookup"><span data-stu-id="d8ebe-106">Setting up subscriptions</span></span>

<span data-ttu-id="d8ebe-107">När du vill ställa in ett abonnemang ska du först skapa en abonnemangsgrupp för det nya serviceavtalet, eller verifiera att det finns en abonnemangsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="d8ebe-108">Om det finns en abonnemangsgrupp, måste den ställas in att fakturera kunden per år och tillåta periodisering av försäljningsintäkter varje månad under året.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="d8ebe-109">Mer information om hur du ställer in abonnemang hittar du på [Ställ in abonnemangsgrupper](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="d8ebe-110">När du har skapat abonnemangsgruppen kan du skapa abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="d8ebe-111">Mer information om hur du skapar serviceabonnemang finns i [Skapa serviceabonnemang från en abonnemangsgrupp](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="d8ebe-112">Skapa och ändra abonnemangstransaktioner</span><span class="sxs-lookup"><span data-stu-id="d8ebe-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="d8ebe-113">När du har skapat abonnemanget skapar du abonnemangsavgiftstransaktionen för den första faktureringsperioden, som är ett år.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="d8ebe-114">Transaktionerna är av typen **Vanligt**.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="d8ebe-115">Du kan därför bara skapa abonnemangstransaktioner där från- och till-datumet motsvarar befintliga perioder som har skapats tidigare i formuläret **Periodtyper**.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="d8ebe-116">Mer information om avgiftstransaktioner finns i [skapa transaktioner för abonnemangsavgifter](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="d8ebe-117">När du har ställt in abonnemanget för kunden, kommer du ihåg att de har förhandlat fram 10 % rabatt på alla listpriser för service.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="d8ebe-118">Därför måste du minska priset på transaktionsavgiften som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="d8ebe-119">Senare under dagen ringer din kontaktperson upp dig och säger att de fortfarande vill ha serviceavtalet för ljusrampen, men planerar att skaffa en ny ljusramp senare under året.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="d8ebe-120">De behöver bara underhåll till och med oktober 2013.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="d8ebe-121">Du minskar antalet månader för kundens abonnemang genom att skapa en ny abonnemangsavgiftstransaktion av typen **Reduceringsdagar**.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="d8ebe-122">Mer information om hur du minskar dagar finns [minska antalet dagar på abonnemangsavgifter](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="d8ebe-123">Fakturering och periodisering av abonnemangstransaktioner</span><span class="sxs-lookup"><span data-stu-id="d8ebe-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="d8ebe-124">Du har nu ställt in abonnemangen och är redo att fakturera kunden för abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="d8ebe-125">Mer information om hur du ställer in fakturaabonnemang hittar du på [Fakturera abonnemangstransaktioner](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="d8ebe-126">Två dagar senare ringer kunden och säger att abonnemanget ska faktureras i amerikanska dollar och inte i euro.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="d8ebe-127">Du skapar en kreditnota och skapar en ny abonnemangstransaktion i korrekt valuta.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="d8ebe-128">Mer information om hur du ställer in Kreditera abonnemangstransaktioner hittar du på [Kreditera abonnemangstransaktioner](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="d8ebe-129">I slutet av varje månad periodiserar du en månads intäkt från kundens abonnemang på vinst- och förlustkontot och PIA-kontona.</span><span class="sxs-lookup"><span data-stu-id="d8ebe-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="d8ebe-130">Mer information om hur du periodiserar intäkt för abonnemang finns i [Periodisera abonnemangsintäkt ](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="d8ebe-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]