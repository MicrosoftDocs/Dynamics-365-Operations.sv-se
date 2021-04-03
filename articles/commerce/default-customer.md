---
title: Skapa en standardskund
description: I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f988732549ce82919f02c87b320623d8d4218735
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477910"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="2b650-103">Skapa en standardskund</span><span class="sxs-lookup"><span data-stu-id="2b650-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b650-104">I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b650-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2b650-105">När du skapar en kanal måste du ange en standardkund.</span><span class="sxs-lookup"><span data-stu-id="2b650-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="2b650-106">En standardkund kan enkelt skapas efter att du först har skapat kundgruppen och kundadressboken.</span><span class="sxs-lookup"><span data-stu-id="2b650-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="2b650-107">Skapa en kundgrupp</span><span class="sxs-lookup"><span data-stu-id="2b650-107">Create a customer group</span></span>

<span data-ttu-id="2b650-108">Om det inte finns några kundgrupper ännu kan du skapa en.</span><span class="sxs-lookup"><span data-stu-id="2b650-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="2b650-109">Exempel på det kan vara grupper att representera olika kundgrupper, till exempel grossist, butik, Internet, anställda osv.</span><span class="sxs-lookup"><span data-stu-id="2b650-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="2b650-110">Gör så här om du vill skapa en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="2b650-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="2b650-111">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="2b650-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="2b650-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b650-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="2b650-113">I rutan **kundgrupp** anger du ett kundgrupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2b650-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="2b650-114">I rutan **beskrivning** ange en lämplig beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2b650-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="2b650-115">I rutan **Betalningsvillkor** ange ett lämpligt värde.</span><span class="sxs-lookup"><span data-stu-id="2b650-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="2b650-116">I rutan **Tid mellan fakturadatum och betalningsdatum** anger du ett lämpligt datum.</span><span class="sxs-lookup"><span data-stu-id="2b650-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="2b650-117">I rutan **Standardmomsgrupp** anger du en momsgrupp om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="2b650-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="2b650-118">Markera kryssrutan **Priser inkluderar moms** om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="2b650-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="2b650-119">I rutan **Standardorsak till avskrivning** anger du ett lämpligt värde, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="2b650-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="2b650-120">I följande bild visas flera konfigurerade kundgrupper.</span><span class="sxs-lookup"><span data-stu-id="2b650-120">The following image shows several configured customer groups.</span></span>

![Kundgrupper](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="2b650-122">Skapa en kundadressbok</span><span class="sxs-lookup"><span data-stu-id="2b650-122">Create a customer address book</span></span>

<span data-ttu-id="2b650-123">En kund måste vara kopplad till en adressbok.</span><span class="sxs-lookup"><span data-stu-id="2b650-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="2b650-124">Om en sådan inte ännu har skapats måste du skapa en.</span><span class="sxs-lookup"><span data-stu-id="2b650-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="2b650-125">Följ dessa steg för att skapa en kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="2b650-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="2b650-126">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Adressböcker**.</span><span class="sxs-lookup"><span data-stu-id="2b650-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="2b650-127">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b650-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="2b650-128">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="2b650-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="2b650-129">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="2b650-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="2b650-130">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b650-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="2b650-131">I bilden nedan visas ett exempel på adressbok.</span><span class="sxs-lookup"><span data-stu-id="2b650-131">The following image shows an example address book.</span></span>

![Adressbok](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="2b650-133">Skapa en standardskund</span><span class="sxs-lookup"><span data-stu-id="2b650-133">Create a default customer</span></span>

<span data-ttu-id="2b650-134">Gör så här om du vill skapa en standardkund.</span><span class="sxs-lookup"><span data-stu-id="2b650-134">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="2b650-135">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="2b650-135">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="2b650-136">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b650-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="2b650-137">I listrutan **Typ** väljer du "Person".</span><span class="sxs-lookup"><span data-stu-id="2b650-137">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="2b650-138">I listrutan **kundkonto** väljer du eller anger ett kontonummer (t.ex. "100001").</span><span class="sxs-lookup"><span data-stu-id="2b650-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="2b650-139">I listrutan **Förnamn** väljer du eller anger ett namn (till exempel "standard").</span><span class="sxs-lookup"><span data-stu-id="2b650-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="2b650-140">I listrutan **Mellannamn** väljer du eller anger ett namn (till exempel "butik").</span><span class="sxs-lookup"><span data-stu-id="2b650-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="2b650-141">I listrutan **Efternamn** väljer du eller anger ett namn (till exempel "kund").</span><span class="sxs-lookup"><span data-stu-id="2b650-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="2b650-142">I listrutan **Valuta** väljer du eller anger en valuta (till exempel "USD").</span><span class="sxs-lookup"><span data-stu-id="2b650-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="2b650-143">I listrutan **valuta** väljer du den kundgrupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="2b650-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="2b650-144">I listrutan **Adressböcker** väljer du en befintlig kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="2b650-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="2b650-145">Välj **spara** om du vill spara och återgå till fönstret med kundinformation för den nya kunden.</span><span class="sxs-lookup"><span data-stu-id="2b650-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="2b650-146">Det är inte nödvändigt att lägga till en adress för en standardkund.</span><span class="sxs-lookup"><span data-stu-id="2b650-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="2b650-147">I bilden nedan visas ett exempel på skapande av kund.</span><span class="sxs-lookup"><span data-stu-id="2b650-147">The following image shows an example of customer creation.</span></span>

![Skapa en standardkund](media/default-customer-creation.png)

<span data-ttu-id="2b650-149">Följande bild visar en standardkundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2b650-149">The following image shows a default customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration1.png)

<span data-ttu-id="2b650-151">De flesta standardvärdena i informationsskärmen kund kan vara kvar, men två värden ska ändras.</span><span class="sxs-lookup"><span data-stu-id="2b650-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="2b650-152">På informationsskärmen för kund expanderar du **standardvärden för försäljningsorde**.</span><span class="sxs-lookup"><span data-stu-id="2b650-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="2b650-153">I listrutan **Webbplats** välj eller ange en förkonfigurerad webbplats.</span><span class="sxs-lookup"><span data-stu-id="2b650-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="2b650-154">I listrutan **Lagerställe** välj eller ange ett förkonfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="2b650-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="2b650-155">I bilden nedan visas ett exempel på skapande av kundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2b650-155">The following image shows an example customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="2b650-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2b650-157">Additional resources</span></span>

[<span data-ttu-id="2b650-158">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="2b650-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="2b650-159">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="2b650-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
