---
title: Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service
description: Det här avsnittet anger ordningen för synkroniseringen som du måste följa för att skapa de ursprungliga data.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873138"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="a030e-103">Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a030e-103">Execution order for initial synchronization of Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="a030e-104">Innan du använder dataintegrering måste du skapa de ursprungliga data som krävs för kunder, leverantörer och kontakter.</span><span class="sxs-lookup"><span data-stu-id="a030e-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="a030e-105">Du vill till exempel skapa en ny **leverantörsgruppartikel** och ange värdet för **betalningsvillkor** till **Net30.**</span><span class="sxs-lookup"><span data-stu-id="a030e-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="a030e-106">I det här fallet måste du, innan du försöker skapa **leverantörsgruppsartikeln**, se till **Net30** finns i både Microsoft Dynamics 365 for Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a030e-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both Microsoft Dynamics 365 for Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="a030e-107">(I framtiden kommer Microsoft att släppa en funktion för dubbelriktad skrivning som kallas initial synkronisering. Den kommer att göra en engångsdatasynkronisering mellan Finance and Operations och Common Data Service som en del av inställningen dubbelriktad skrivning.)</span><span class="sxs-lookup"><span data-stu-id="a030e-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="a030e-108">Microsoft släpper en karta för dubbelriktad skrivning för alla referensdata, inklusive **Betalningsvillkor** (betalningsvillkor).</span><span class="sxs-lookup"><span data-stu-id="a030e-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="a030e-109">Om du redan har de ursprungliga data i ett system kan en liten uppdateringsåtgärd på en post utlösa dubbel-skriv på posten.</span><span class="sxs-lookup"><span data-stu-id="a030e-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="a030e-110">Du måste följa följande prioritetsordning och kontrollera att de ursprungliga data är tillgängliga i både Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a030e-110">You must follow the following order of precedence and make sure that the initial data is available in both Finance and Operations and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="a030e-111">Leverantör</span><span class="sxs-lookup"><span data-stu-id="a030e-111">Vendor</span></span>

<span data-ttu-id="a030e-112">Här är ordningsföljden för entiteten **Leverantör**:</span><span class="sxs-lookup"><span data-stu-id="a030e-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="a030e-113">Leverantörsgrupp</span><span class="sxs-lookup"><span data-stu-id="a030e-113">Vendor group</span></span>

    1. <span data-ttu-id="a030e-114">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="a030e-114">Terms of payment</span></span>

        1. <span data-ttu-id="a030e-115">Betalningsdag och rader</span><span class="sxs-lookup"><span data-stu-id="a030e-115">Payment day and lines</span></span>
        2. <span data-ttu-id="a030e-116">Betalningsplan</span><span class="sxs-lookup"><span data-stu-id="a030e-116">Payment schedule</span></span>

2. <span data-ttu-id="a030e-117">Betalningsmetod för leverantör</span><span class="sxs-lookup"><span data-stu-id="a030e-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="a030e-118">Kund (organisation)</span><span class="sxs-lookup"><span data-stu-id="a030e-118">Customer (Organization)</span></span>

<span data-ttu-id="a030e-119">Här är ordningsföljden för entiteten **Kund**:</span><span class="sxs-lookup"><span data-stu-id="a030e-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="a030e-120">Kundgrupp</span><span class="sxs-lookup"><span data-stu-id="a030e-120">Customer group</span></span>

    1. <span data-ttu-id="a030e-121">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="a030e-121">Terms of payment</span></span>

        1. <span data-ttu-id="a030e-122">Betalningsdag och rader</span><span class="sxs-lookup"><span data-stu-id="a030e-122">Payment day and lines</span></span>
        2. <span data-ttu-id="a030e-123">Betalning</span><span class="sxs-lookup"><span data-stu-id="a030e-123">Payment</span></span> 

2. <span data-ttu-id="a030e-124">Kundbetalningsmetod</span><span class="sxs-lookup"><span data-stu-id="a030e-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="a030e-125">Kontakt (person)</span><span class="sxs-lookup"><span data-stu-id="a030e-125">Contact (Person)</span></span>

<span data-ttu-id="a030e-126">Här är ordningsföljden för entiteten **Kontakt**:</span><span class="sxs-lookup"><span data-stu-id="a030e-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="a030e-127">Kund</span><span class="sxs-lookup"><span data-stu-id="a030e-127">Customer</span></span>
2. <span data-ttu-id="a030e-128">Leverantör</span><span class="sxs-lookup"><span data-stu-id="a030e-128">Vendor</span></span>
