---
title: Exekveringsorder för initial synkronisering av Finance and Operations-appar och Common Data Service
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
ms.openlocfilehash: 3110cb809558d168e9d97f640701b249caf73f6c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184518"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="dfbec-103">Exekveringsorder för initial synkronisering av Finance and Operations-appar och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="dfbec-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="dfbec-104">Innan du använder dataintegrering måste du skapa de ursprungliga data som krävs för kunder, leverantörer och kontakter.</span><span class="sxs-lookup"><span data-stu-id="dfbec-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="dfbec-105">Du vill till exempel skapa en ny **leverantörsgruppartikel** och ange värdet för **betalningsvillkor** till **Net30.**</span><span class="sxs-lookup"><span data-stu-id="dfbec-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="dfbec-106">I det här fallet måste du, innan du försöker skapa artikeln **leverantörsgrupp**, se till **Net30** finns i både appen och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="dfbec-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="dfbec-107">(I framtiden kommer Microsoft att släppa en funktion för dubbelriktad skrivning som kallas initial synkronisering. Den kommer att göra en engångsdatasynkronisering mellan appen och Common Data Service som en del av inställningen dubbelriktad skrivning.)</span><span class="sxs-lookup"><span data-stu-id="dfbec-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="dfbec-108">Microsoft släpper en karta för dubbelriktad skrivning för alla referensdata, inklusive **Betalningsvillkor** (betalningsvillkor).</span><span class="sxs-lookup"><span data-stu-id="dfbec-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="dfbec-109">Om du redan har de ursprungliga data i ett system kan en liten uppdateringsåtgärd på en post utlösa dubbel-skriv på posten.</span><span class="sxs-lookup"><span data-stu-id="dfbec-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="dfbec-110">Du måste följa följande prioritetsordning och kontrollera att de ursprungliga data är tillgängliga i appen och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="dfbec-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="dfbec-111">Leverantör</span><span class="sxs-lookup"><span data-stu-id="dfbec-111">Vendor</span></span>

<span data-ttu-id="dfbec-112">Här är ordningsföljden för entiteten **Leverantör**:</span><span class="sxs-lookup"><span data-stu-id="dfbec-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="dfbec-113">Leverantörsgrupp</span><span class="sxs-lookup"><span data-stu-id="dfbec-113">Vendor group</span></span>

    1. <span data-ttu-id="dfbec-114">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="dfbec-114">Terms of payment</span></span>

        1. <span data-ttu-id="dfbec-115">Betalningsdag och rader</span><span class="sxs-lookup"><span data-stu-id="dfbec-115">Payment day and lines</span></span>
        2. <span data-ttu-id="dfbec-116">Betalningsplan</span><span class="sxs-lookup"><span data-stu-id="dfbec-116">Payment schedule</span></span>

2. <span data-ttu-id="dfbec-117">Betalningsmetod för leverantör</span><span class="sxs-lookup"><span data-stu-id="dfbec-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="dfbec-118">Kund (organisation)</span><span class="sxs-lookup"><span data-stu-id="dfbec-118">Customer (Organization)</span></span>

<span data-ttu-id="dfbec-119">Här är ordningsföljden för entiteten **Kund**:</span><span class="sxs-lookup"><span data-stu-id="dfbec-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="dfbec-120">Kundgrupp</span><span class="sxs-lookup"><span data-stu-id="dfbec-120">Customer group</span></span>

    1. <span data-ttu-id="dfbec-121">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="dfbec-121">Terms of payment</span></span>

        1. <span data-ttu-id="dfbec-122">Betalningsdag och rader</span><span class="sxs-lookup"><span data-stu-id="dfbec-122">Payment day and lines</span></span>
        2. <span data-ttu-id="dfbec-123">Betalning</span><span class="sxs-lookup"><span data-stu-id="dfbec-123">Payment</span></span> 

2. <span data-ttu-id="dfbec-124">Kundbetalningsmetod</span><span class="sxs-lookup"><span data-stu-id="dfbec-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="dfbec-125">Kontakt (person)</span><span class="sxs-lookup"><span data-stu-id="dfbec-125">Contact (Person)</span></span>

<span data-ttu-id="dfbec-126">Här är ordningsföljden för entiteten **Kontakt**:</span><span class="sxs-lookup"><span data-stu-id="dfbec-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="dfbec-127">Kund</span><span class="sxs-lookup"><span data-stu-id="dfbec-127">Customer</span></span>
2. <span data-ttu-id="dfbec-128">Leverantör</span><span class="sxs-lookup"><span data-stu-id="dfbec-128">Vendor</span></span>
