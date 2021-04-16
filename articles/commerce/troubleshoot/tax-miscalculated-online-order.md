---
title: Moms på online-order beräknas felaktigt
description: Det här ämnet ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f71add679e1d24f80db8ce3990058b591128ec1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801421"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="6213b-103">Moms på online-order beräknas felaktigt</span><span class="sxs-lookup"><span data-stu-id="6213b-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6213b-104">Det här ämnet ger felsökningsvägledning som kan hjälpa till när moms på onlineorder beräknas felaktigt, eller när momsgruppen på försäljningsraden inte stämmer.</span><span class="sxs-lookup"><span data-stu-id="6213b-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="6213b-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6213b-105">Description</span></span>

<span data-ttu-id="6213b-106">När en e-handelsorder läggs beräknas momsen på fel sätt, eller också ställs momsgruppen på försäljningsraden in på fel sätt.</span><span class="sxs-lookup"><span data-stu-id="6213b-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="6213b-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="6213b-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="6213b-108">Konfigurera momsen för en butiksbutik i Commerce -administration</span><span class="sxs-lookup"><span data-stu-id="6213b-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="6213b-109">Konfigurera momsen för en butiksbutik i Commerce-administrationmed dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6213b-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6213b-110">Gå till **Retail och Commerce \> Kanaler \> Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="6213b-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="6213b-111">Välj den butik du vill konfigurera moms för.</span><span class="sxs-lookup"><span data-stu-id="6213b-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="6213b-112">Snabbfliken **Allmänt** i avsnittet **Moms**, konfigurera moms för butiken.</span><span class="sxs-lookup"><span data-stu-id="6213b-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="6213b-113">För produktupphämtning från en butik kommer momsgruppen från den butik som är vald för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="6213b-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="6213b-114">För mer information, se [Ställa in övriga momsalternativ för butiker](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="6213b-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="6213b-115">Konfigurera momsen för en kunds adress i Commerce -administration</span><span class="sxs-lookup"><span data-stu-id="6213b-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="6213b-116">Konfigurera momsen för en kundens adress i Commerce-administrationmed dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6213b-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6213b-117">Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="6213b-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="6213b-118">Välj den kund du vill konfigurera moms för.</span><span class="sxs-lookup"><span data-stu-id="6213b-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="6213b-119">På snabbfliken **Adresser**, välj adressen att konfigurera moms för, välj **Fler alternativ** och sedan **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="6213b-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="6213b-120">På snabbfliken **Allmänt**, välj **Momsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="6213b-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="6213b-121">I fältet **Moms**, välj lämpligt värde.</span><span class="sxs-lookup"><span data-stu-id="6213b-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="6213b-122">För leverans som omfattar moms på kundens adress bestämmer leveransadressen för raden momsgruppen för raden.</span><span class="sxs-lookup"><span data-stu-id="6213b-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="6213b-123">Om kunden levererar till en befintlig adress som har en momsgrupp som redan konfigurerats, används den befintliga skattegruppen.</span><span class="sxs-lookup"><span data-stu-id="6213b-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="6213b-124">Som standard har adresserna ingen momsgrupp när de skapas.</span><span class="sxs-lookup"><span data-stu-id="6213b-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="6213b-125">Konfigurera allmänna momsgrupper i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="6213b-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="6213b-126">För att konfigurera allmänna momsgrupper i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6213b-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6213b-127">Gå till **Skatt \> Indirekta skatter \> Moms \> Momsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="6213b-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="6213b-128">Välj den momsgrupp du vill konfigurera i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="6213b-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="6213b-129">På snabbfliken **Destinationsbaserad skatt för detaljhandel** konfigurera skatterna för momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="6213b-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="6213b-130">För leverans som inte innefattar moms på kundens adress bestämmer leveransadressen för raden och målbaserad moms som är konfigurerad för momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="6213b-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="6213b-131">Mer information finns i [Konfigurera moms för onlinebutiker baserat på destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="6213b-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6213b-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6213b-132">Additional resources</span></span>

[<span data-ttu-id="6213b-133">Konfigurera moms för onlinebeställningar</span><span class="sxs-lookup"><span data-stu-id="6213b-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)
