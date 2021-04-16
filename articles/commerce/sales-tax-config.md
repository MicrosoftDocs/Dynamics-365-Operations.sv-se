---
title: Konfigurera moms för onlinebeställningar
description: Det här ämnet ger en översikt över momsgruppsval för olika typer av onlinebeställning i Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 68b7e59a1e1ea18bdcd4e7a9117e4892407f40ff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791857"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="02efb-103">Konfigurera moms för onlinebeställningar</span><span class="sxs-lookup"><span data-stu-id="02efb-103">Configure sales tax for online orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02efb-104">Det här ämnet ger en översikt över momsgruppsval för olika typer av onlinebeställning.</span><span class="sxs-lookup"><span data-stu-id="02efb-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="02efb-105">Din näthandelskanal kanske vill stödja alternativ som leverans eller upphämtning för onlinebeställningar.</span><span class="sxs-lookup"><span data-stu-id="02efb-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="02efb-106">Momstillämpbarheten baseras på det alternativ som valts av dina onlineanvändare.</span><span class="sxs-lookup"><span data-stu-id="02efb-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="02efb-107">När en webbplatskund väljer att köpa en artikel online och får den levererad till en adress bestäms momsen utifrån kundens inställning för momsgrupp för leveransadress.</span><span class="sxs-lookup"><span data-stu-id="02efb-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="02efb-108">När en kund väljer att hämta en inköpt artikel i en butik bestäms momsen baserat på upphämtningsbutikens inställning för momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="02efb-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="02efb-109">Order som levereras till en kundadress</span><span class="sxs-lookup"><span data-stu-id="02efb-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="02efb-110">I allmänhet definieras moms för onlineorder som levereras till kundadresser av målet.</span><span class="sxs-lookup"><span data-stu-id="02efb-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="02efb-111">Varje momsgrupp har en konfiguration för målbaserad momskonfiguration där ditt företag kan definiera destinationsinformation som exempelvis land/region, delstat, region och ort i ett hierarkiskt formulär.</span><span class="sxs-lookup"><span data-stu-id="02efb-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="02efb-112">När en onlineorder har lagts använder skattemotorn för Commerce leveransadressen för respektive radartikel i ordern och söker efter momsgrupper med matchande destinationsbaserade momskriterier.</span><span class="sxs-lookup"><span data-stu-id="02efb-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="02efb-113">För en onlinebeställning med en leveransadress för en radartikel till San Francisco, Kalifornien, kommer skattemotorn att hitta momsgrupp och momskod för Kalifornien och sedan beräkna momsen för respektive radartikel därefter.</span><span class="sxs-lookup"><span data-stu-id="02efb-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="02efb-114">Kundbaserade momsgrupper</span><span class="sxs-lookup"><span data-stu-id="02efb-114">Customer-based tax groups</span></span>

<span data-ttu-id="02efb-115">I Commerce-administrationen finns två platser där kundmomsgrupper konfigureras:</span><span class="sxs-lookup"><span data-stu-id="02efb-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="02efb-116">**Kundprofil**</span><span class="sxs-lookup"><span data-stu-id="02efb-116">**Customer's profile**</span></span>
- <span data-ttu-id="02efb-117">**Kundens leveransadress**</span><span class="sxs-lookup"><span data-stu-id="02efb-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="02efb-118">Om en kundprofil har en momsgrupp konfigurerad</span><span class="sxs-lookup"><span data-stu-id="02efb-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="02efb-119">En kunds profilpost i administrationen kan ha en konfigurerad momsgrupp, men för onlinebeställningar kan momsgruppen som konfigurerats i en kundprofil inte användas av skattemotorn.</span><span class="sxs-lookup"><span data-stu-id="02efb-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="02efb-120">Om en kunds leveransadress har en momsgrupp konfigurerad</span><span class="sxs-lookup"><span data-stu-id="02efb-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="02efb-121">Om en kunds leveransadresspost har en konfigurerad momsgrupp och en onlinebeställning (eller radartikel) levereras till kundens leveransadress, används den momsgrupp som konfigurerats i kundens adresspost av skattemotorn för momsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="02efb-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="02efb-122">Konfigurera en momsgrupp för en kunds leveransadresspost</span><span class="sxs-lookup"><span data-stu-id="02efb-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="02efb-123">Om du vill konfigurera en momsgrupp för en kunds leveransadresspost i Commerce-administrationen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02efb-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="02efb-124">Gå till **Alla kunder** och välj önskad kund.</span><span class="sxs-lookup"><span data-stu-id="02efb-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="02efb-125">I snabbfliken **Adresser** väljer du önskad adress och sedan **Fler alternativ \> Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="02efb-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="02efb-126">Under fliken **Allmänt** på sidan **Hantera adresser** anger du önskat momsvärde.</span><span class="sxs-lookup"><span data-stu-id="02efb-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="02efb-127">Momsgruppen definieras med hjälp av leveransadressen för orderraden, och de målbaserade momssatserna konfigureras i själva momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="02efb-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="02efb-128">Mer information finns i [Konfigurera moms för onlinebutiker baserat på destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="02efb-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="02efb-129">Orderupphämtning i butik</span><span class="sxs-lookup"><span data-stu-id="02efb-129">Order pickup in store</span></span>

<span data-ttu-id="02efb-130">För orderrader med upphämtning i butik eller drive in-upphämtning anges momsgruppen från den valda upphämtningsbutiken.</span><span class="sxs-lookup"><span data-stu-id="02efb-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="02efb-131">Mer information om hur du konfigurerar momsgruppen för en viss butik finns i [Ställa in andra momsalternativ för butiker](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="02efb-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="02efb-132">När en orderrad hämtas i en butik ignoreras skatteinställningarna för kundens adress (om dessa ställts in) av skattemotorn, och upphämtningsbutikens skattekonfiguration tillämpas.</span><span class="sxs-lookup"><span data-stu-id="02efb-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="02efb-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="02efb-133">Additional resources</span></span>

[<span data-ttu-id="02efb-134">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="02efb-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="02efb-135">Momsberäkningsmetoder i fältet Ursprung</span><span class="sxs-lookup"><span data-stu-id="02efb-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="02efb-136">Momstilldelning och åsidosättningar</span><span class="sxs-lookup"><span data-stu-id="02efb-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="02efb-137">Beräkningsalternativ för hela beloppet och intervall för momskoder</span><span class="sxs-lookup"><span data-stu-id="02efb-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="02efb-138">Beräkning av momsbefrielse</span><span class="sxs-lookup"><span data-stu-id="02efb-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]