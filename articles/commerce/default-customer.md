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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9e1087821b357c578993cdd5742399c5ec0ecc95
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001816"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="4ec40-103">Skapa en standardskund</span><span class="sxs-lookup"><span data-stu-id="4ec40-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4ec40-104">I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ec40-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4ec40-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4ec40-105">Overview</span></span>

<span data-ttu-id="4ec40-106">När du skapar en butiks- eller onlinekanal måste du ange en standardkund.</span><span class="sxs-lookup"><span data-stu-id="4ec40-106">When creating a retail or online channel, you will need to provide a default customer.</span></span> <span data-ttu-id="4ec40-107">En standardkund kan enkelt skapas efter att du först har skapat kundgruppen och kundadressboken.</span><span class="sxs-lookup"><span data-stu-id="4ec40-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="4ec40-108">Skapa en kundgrupp</span><span class="sxs-lookup"><span data-stu-id="4ec40-108">Create a customer group</span></span>

<span data-ttu-id="4ec40-109">Om det inte finns några kundgrupper ännu kan du skapa en.</span><span class="sxs-lookup"><span data-stu-id="4ec40-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="4ec40-110">Exempel på det kan vara grupper att representera olika kundgrupper, till exempel grossist, butik, Internet, anställda osv.</span><span class="sxs-lookup"><span data-stu-id="4ec40-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="4ec40-111">Gör så här om du vill skapa en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="4ec40-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="4ec40-112">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="4ec40-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4ec40-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4ec40-114">I rutan **kundgrupp** anger du ett kundgrupp-ID.</span><span class="sxs-lookup"><span data-stu-id="4ec40-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="4ec40-115">I rutan **beskrivning** ange en lämplig beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4ec40-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="4ec40-116">I rutan **Betalningsvillkor** ange ett lämpligt värde.</span><span class="sxs-lookup"><span data-stu-id="4ec40-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="4ec40-117">I rutan **Tid mellan fakturadatum och betalningsdatum** anger du ett lämpligt datum.</span><span class="sxs-lookup"><span data-stu-id="4ec40-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="4ec40-118">I rutan **Standardmomsgrupp** anger du en momsgrupp om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="4ec40-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="4ec40-119">Markera kryssrutan **Priser inkluderar moms** om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="4ec40-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="4ec40-120">I rutan **Standardorsak till avskrivning** anger du ett lämpligt värde, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="4ec40-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="4ec40-121">I följande bild visas flera konfigurerade kundgrupper.</span><span class="sxs-lookup"><span data-stu-id="4ec40-121">The following image shows several configured customer groups.</span></span>

![Kundgrupper](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="4ec40-123">Skapa en kundadressbok</span><span class="sxs-lookup"><span data-stu-id="4ec40-123">Create a customer address book</span></span>

<span data-ttu-id="4ec40-124">En kund måste vara kopplad till en adressbok.</span><span class="sxs-lookup"><span data-stu-id="4ec40-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="4ec40-125">Om en sådan inte ännu har skapats måste du skapa en.</span><span class="sxs-lookup"><span data-stu-id="4ec40-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="4ec40-126">Följ dessa steg för att skapa en kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="4ec40-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="4ec40-127">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Adressböcker**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="4ec40-128">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4ec40-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4ec40-129">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="4ec40-130">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="4ec40-131">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4ec40-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="4ec40-132">I bilden nedan visas ett exempel på adressbok.</span><span class="sxs-lookup"><span data-stu-id="4ec40-132">The following image shows an example address book.</span></span>

![Adressbok](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="4ec40-134">Skapa en standardskund</span><span class="sxs-lookup"><span data-stu-id="4ec40-134">Create a default customer</span></span>

<span data-ttu-id="4ec40-135">Gör så här om du vill skapa en standardkund.</span><span class="sxs-lookup"><span data-stu-id="4ec40-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="4ec40-136">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="4ec40-137">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4ec40-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4ec40-138">I listrutan **Typ** väljer du "Person".</span><span class="sxs-lookup"><span data-stu-id="4ec40-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="4ec40-139">I listrutan **kundkonto** väljer du eller anger ett kontonummer (t.ex. "100001").</span><span class="sxs-lookup"><span data-stu-id="4ec40-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="4ec40-140">I listrutan **Förnamn** väljer du eller anger ett namn (till exempel "standard").</span><span class="sxs-lookup"><span data-stu-id="4ec40-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="4ec40-141">I listrutan **Mellannamn** väljer du eller anger ett namn (till exempel "butik").</span><span class="sxs-lookup"><span data-stu-id="4ec40-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="4ec40-142">I listrutan **Efternamn** väljer du eller anger ett namn (till exempel "kund").</span><span class="sxs-lookup"><span data-stu-id="4ec40-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="4ec40-143">I listrutan **Valuta** väljer du eller anger en valuta (till exempel "USD").</span><span class="sxs-lookup"><span data-stu-id="4ec40-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="4ec40-144">I listrutan **valuta** väljer du den kundgrupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="4ec40-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="4ec40-145">I listrutan **Adressböcker** väljer du en befintlig kundadressbok.</span><span class="sxs-lookup"><span data-stu-id="4ec40-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="4ec40-146">Välj **spara** om du vill spara och återgå till fönstret med kundinformation för den nya kunden.</span><span class="sxs-lookup"><span data-stu-id="4ec40-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="4ec40-147">Det är inte nödvändigt att lägga till en adress för en standardkund.</span><span class="sxs-lookup"><span data-stu-id="4ec40-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="4ec40-148">I bilden nedan visas ett exempel på skapande av kund.</span><span class="sxs-lookup"><span data-stu-id="4ec40-148">The following image shows an example of customer creation.</span></span>

![Skapa en standardkund](media/default-customer-creation.png)

<span data-ttu-id="4ec40-150">Följande bild visar en standardkundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ec40-150">The following image shows a default customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration1.png)

<span data-ttu-id="4ec40-152">De flesta standardvärdena i informationsskärmen kund kan vara kvar, men två värden ska ändras.</span><span class="sxs-lookup"><span data-stu-id="4ec40-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="4ec40-153">På informationsskärmen för kund expanderar du **standardvärden för försäljningsorde**.</span><span class="sxs-lookup"><span data-stu-id="4ec40-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="4ec40-154">I listrutan **Webbplats** välj eller ange en förkonfigurerad webbplats.</span><span class="sxs-lookup"><span data-stu-id="4ec40-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="4ec40-155">I listrutan **Lagerställe** välj eller ange ett förkonfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="4ec40-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="4ec40-156">I bilden nedan visas ett exempel på skapande av kundkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ec40-156">The following image shows an example customer configuration.</span></span>

![Exempel på kundkonfiguration](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="4ec40-158">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4ec40-158">Additional resources</span></span>

[<span data-ttu-id="4ec40-159">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="4ec40-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="4ec40-160">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="4ec40-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)
