---
title: Övervaka försändelselagret med hjälp av leverantörssamarbete
description: I den här proceduren visas hur du använder leverantörssamarbete om du vill visa information om lagernivån för den produkt som du har placerat i försändelse med en kund.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 589b478fa59f2fb2a5008d02e39f2808391d0994
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145598"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="8dc13-103">Övervaka försändelselagret med hjälp av leverantörssamarbete</span><span class="sxs-lookup"><span data-stu-id="8dc13-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8dc13-104">I den här proceduren visas hur du använder leverantörssamarbete om du vill visa information om lagernivån för den produkt som du har placerat i försändelse med en kund.</span><span class="sxs-lookup"><span data-stu-id="8dc13-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="8dc13-105">Du kan även övervaka lagerförbrukningen när kunden tar över ägarskapet för lagret.</span><span class="sxs-lookup"><span data-stu-id="8dc13-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="8dc13-106">Du kan använda den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="8dc13-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="8dc13-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="8dc13-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="8dc13-108">Visa förbrukat lager</span><span class="sxs-lookup"><span data-stu-id="8dc13-108">View consumed inventory</span></span>
1. <span data-ttu-id="8dc13-109">Gå till Leverantörssamarbete > Försändelselager > Mottagna produkter från försändelselager.</span><span class="sxs-lookup"><span data-stu-id="8dc13-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="8dc13-110">I listan visas produktinleveransraderna som genererades när ägarskapet för försändelselagret ändrades från leverantör till kund.</span><span class="sxs-lookup"><span data-stu-id="8dc13-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="8dc13-111">Du kanske måste rulla åt höger för att se kvantiteter och annan information.</span><span class="sxs-lookup"><span data-stu-id="8dc13-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="8dc13-112">Du kan använda informationen i den här listan om du vill generera fakturor för kunden.</span><span class="sxs-lookup"><span data-stu-id="8dc13-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="8dc13-113">Du kan även exportera datan till Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="8dc13-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="8dc13-114">Klicka på View purchase order.</span><span class="sxs-lookup"><span data-stu-id="8dc13-114">Click View purchase order.</span></span>
3. <span data-ttu-id="8dc13-115">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="8dc13-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="8dc13-116">Raden har markerats som Consignment (leverans), och huvudavsnittet visar att inköpsordern har statusen Received (mottagen).</span><span class="sxs-lookup"><span data-stu-id="8dc13-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="8dc13-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8dc13-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="8dc13-118">Visa lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="8dc13-118">View on-hand inventory</span></span>
1. <span data-ttu-id="8dc13-119">Gå till Leverantörssamarbete > Försändelselager > Behållning i försändelselager.</span><span class="sxs-lookup"><span data-stu-id="8dc13-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="8dc13-120">Lagersidan för behållningsförsändelse (On-hand consignment inventory) visar det lager som du äger på kundens lagerställe.</span><span class="sxs-lookup"><span data-stu-id="8dc13-120">The On-hand consignment inventory page shows the stock that you own at the customer's warehouse.</span></span> <span data-ttu-id="8dc13-121">Du kan visa ytterligare dimensioner, till exempel plats och lagerställe, genom att klicka på fliken Display dimensions.</span><span class="sxs-lookup"><span data-stu-id="8dc13-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

