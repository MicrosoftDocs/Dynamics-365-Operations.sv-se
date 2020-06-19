---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I det här avsnittet finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426992"
---
# <a name="inventory-availability"></a><span data-ttu-id="26817-103">Lagertillgänglighet</span><span class="sxs-lookup"><span data-stu-id="26817-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="26817-104">Med hjälp av lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt i formulären **Offerter**, **Order** eller **Fakturor** i modellstyrda appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="26817-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="26817-105">Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="26817-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="26817-106">Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser.</span><span class="sxs-lookup"><span data-stu-id="26817-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="26817-107">Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="26817-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="26817-108">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="26817-108">On-hand Inventory</span></span> 

<span data-ttu-id="26817-109">I rubriken på formulären **Offerter**, **Order** eller **Fakturor** i Dynamics 365 Sales läggs en ny knapp för **Lagerbehållning** till.</span><span class="sxs-lookup"><span data-stu-id="26817-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="26817-110">När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för.</span><span class="sxs-lookup"><span data-stu-id="26817-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="26817-111">Den returnerar lagerinformationen från Dynamics 365 Supply Chain Management och visar samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="26817-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="26817-112">Informationen omfattar följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="26817-112">The information includes these quantities:</span></span>

- <span data-ttu-id="26817-113">**Lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="26817-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="26817-114">**Reserverad lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="26817-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="26817-115">**Tillgänglig lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="26817-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="26817-116">**Orderkvantitet**</span><span class="sxs-lookup"><span data-stu-id="26817-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="26817-117">**Kvantitet som har beställts**</span><span class="sxs-lookup"><span data-stu-id="26817-117">**On-order Quantity**</span></span>
- <span data-ttu-id="26817-118">**Reserverad beställd kvantitet**</span><span class="sxs-lookup"><span data-stu-id="26817-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="26817-119">**Total tillgänglig kvantitet**</span><span class="sxs-lookup"><span data-stu-id="26817-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="26817-120">Information om ATP</span><span class="sxs-lookup"><span data-stu-id="26817-120">ATP information</span></span>

<span data-ttu-id="26817-121">Online artiklar i formulären **Offerter**, **Order** eller **Fakturor** i Dynamics 365 Sales läggs en ny knapp för **ATP-information** till.</span><span class="sxs-lookup"><span data-stu-id="26817-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="26817-122">När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet.</span><span class="sxs-lookup"><span data-stu-id="26817-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="26817-123">Den returnerar **ATP-information** från Supply Chain Management och visar inställningarna som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="26817-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="26817-124">Informationen innehåller **ATP-kvantitet**, **inleveranskvantitet**, **utleveranskvantitet** och **lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="26817-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
