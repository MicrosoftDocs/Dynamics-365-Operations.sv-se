---
title: Skapa en standardskund
description: I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799189"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="e4ba2-103">Skapa en standardskund</span><span class="sxs-lookup"><span data-stu-id="e4ba2-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e4ba2-104">I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e4ba2-105">När du skapar en kanal måste du ange en standardkund.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="e4ba2-106">En standardkund kan enkelt skapas efter att du först har skapat kundgruppen och kundadressboken.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="e4ba2-107">Skapa en kundgrupp</span><span class="sxs-lookup"><span data-stu-id="e4ba2-107">Create a customer group</span></span>

<span data-ttu-id="e4ba2-108">Om det inte finns några kundgrupper ännu kan du skapa en.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="e4ba2-109">Exempel på det kan vara grupper att representera olika kundgrupper, till exempel grossist, butik, Internet, anställda osv.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="e4ba2-110">Gör så här om du vill skapa en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="e4ba2-111">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="e4ba2-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e4ba2-113">I rutan **kundgrupp** anger du ett kundgrupp-ID.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="e4ba2-114">I rutan **beskrivning** ange en lämplig beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="e4ba2-115">I rutan **Betalningsvillkor** ange ett lämpligt värde.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="e4ba2-116">I rutan **Tid mellan fakturadatum och betalningsdatum** anger du ett lämpligt datum.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="e4ba2-117">I rutan **Standardmomsgrupp** anger du en momsgrupp om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="e4ba2-118">Markera kryssrutan **Priser inkluderar moms** om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="e4ba2-119">I rutan **Standardorsak till avskrivning** anger du ett lämpligt värde, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="e4ba2-120">I följande bild visas flera konfigurerade kundgrupper.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-120">The following image shows several configured customer groups.</span></span>

![Kundgrupper](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="e4ba2-122">Skapa en kundadressbok</span><span class="sxs-lookup"><span data-stu-id="e4ba2-122">Create a customer address book</span></span>

<span data-ttu-id="e4ba2-123">En kund måste vara kopplad till en adressbok.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="e4ba2-124">Om en sådan inte ännu har skapats måste du skapa en.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="e4ba2-125">Följ dessa steg för att skapa en kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="e4ba2-126">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Adressböcker**.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="e4ba2-127">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e4ba2-128">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="e4ba2-129">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="e4ba2-130">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="e4ba2-131">I bilden nedan visas ett exempel på adressbok.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-131">The following image shows an example address book.</span></span>

![Adressbok](media/address-book.png)

## <a name="create-a-default-customer&quot;></a><span data-ttu-id=&quot;e4ba2-133&quot;>Skapa en standardskund</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e4ba2-133&quot;>Create a default customer</span></span>

<span data-ttu-id=&quot;e4ba2-134&quot;>Gör så här om du vill skapa en standardkund.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e4ba2-134&quot;>To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id=&quot;e4ba2-135&quot;>I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Alla kunder**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e4ba2-135&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id=&quot;e4ba2-136&quot;>Klicka på **Ny** i åtgärdsfönstret.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e4ba2-136&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;e4ba2-137&quot;>I listrutan **Typ** väljer du &quot;Person&quot;.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e4ba2-137&quot;>In the **Type** drop-down list, select &quot;Person&quot;.</span></span>
1. <span data-ttu-id=&quot;e4ba2-138&quot;>I listrutan **kundkonto** väljer du eller anger ett kontonummer (t.ex. &quot;100001").</span><span class="sxs-lookup"><span data-stu-id="e4ba2-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="e4ba2-139">I listrutan **Förnamn** väljer du eller anger ett namn (till exempel "standard").</span><span class="sxs-lookup"><span data-stu-id="e4ba2-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="e4ba2-140">I listrutan **Mellannamn** väljer du eller anger ett namn (till exempel "butik").</span><span class="sxs-lookup"><span data-stu-id="e4ba2-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="e4ba2-141">I listrutan **Efternamn** väljer du eller anger ett namn (till exempel "kund").</span><span class="sxs-lookup"><span data-stu-id="e4ba2-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="e4ba2-142">I listrutan **Valuta** väljer du eller anger en valuta (till exempel "USD").</span><span class="sxs-lookup"><span data-stu-id="e4ba2-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="e4ba2-143">I listrutan **valuta** väljer du den kundgrupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="e4ba2-144">I listrutan **Adressböcker** väljer du en befintlig kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="e4ba2-145">Välj **spara** om du vill spara och återgå till fönstret med kundinformation för den nya kunden.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="e4ba2-146">Det är inte nödvändigt att lägga till en adress för en standardkund.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="e4ba2-147">I bilden nedan visas ett exempel på skapande av kund.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-147">The following image shows an example of customer creation.</span></span>

![Skapa en standardkund](media/default-customer-creation.png)

<span data-ttu-id="e4ba2-149">Följande bild visar en standardkundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-149">The following image shows a default customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration1.png)

<span data-ttu-id="e4ba2-151">De flesta standardvärdena i informationsskärmen kund kan vara kvar, men två värden ska ändras.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="e4ba2-152">På informationsskärmen för kund expanderar du **standardvärden för försäljningsorde**.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="e4ba2-153">I listrutan **Webbplats** välj eller ange en förkonfigurerad webbplats.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="e4ba2-154">I listrutan **Lagerställe** välj eller ange ett förkonfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="e4ba2-155">I bilden nedan visas ett exempel på skapande av kundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4ba2-155">The following image shows an example customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="e4ba2-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e4ba2-157">Additional resources</span></span>

[<span data-ttu-id="e4ba2-158">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="e4ba2-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="e4ba2-159">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="e4ba2-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
