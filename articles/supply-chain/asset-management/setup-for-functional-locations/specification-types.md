---
title: Underhåll av attributtyper
description: Det här avsnittet beskriver hur du skapar attributtyper i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b3247f693f5934b3fbf83b7b831c7ed221514cb
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783594"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="fb5d6-103">Underhåll av attributtyper</span><span class="sxs-lookup"><span data-stu-id="fb5d6-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="fb5d6-104">Det här avsnittet beskriver hur du skapar attributtyper i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="fb5d6-105">Attribut används för att beskriva egenskaperna för olika element.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="fb5d6-106">Du kan ställa in attribut på följande element:</span><span class="sxs-lookup"><span data-stu-id="fb5d6-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="fb5d6-107">Funktionsplatstyper</span><span class="sxs-lookup"><span data-stu-id="fb5d6-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="fb5d6-108">Funktionsplatser</span><span class="sxs-lookup"><span data-stu-id="fb5d6-108">Functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="fb5d6-109">tillgångstyper</span><span class="sxs-lookup"><span data-stu-id="fb5d6-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="fb5d6-110">Tillgångar</span><span class="sxs-lookup"><span data-stu-id="fb5d6-110">Assets</span></span>

<span data-ttu-id="fb5d6-111">Attributen som du kan ställa in varierar beroende på elementet.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="fb5d6-112">För en funktionsplats kan du till exempel ställa in attribut för konfigurationen och den fysiska storleken på platsen.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="fb5d6-113">För en tillgångstyp eller en tillgång kan du ställa in attribut för motorvolym, energiförbrukning och maximal lastkapacitet under olika förhållanden.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="fb5d6-114">Skapa attributstyper</span><span class="sxs-lookup"><span data-stu-id="fb5d6-114">Create attribute types</span></span>

<span data-ttu-id="fb5d6-115">Du kan skapa egna attributtyper.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-115">You can create your own attribute types.</span></span> <span data-ttu-id="fb5d6-116">Dessutom kan du överföra produktdimensioner från Microsoft Dynamics 365 for Finance and Operations till sidan **attributtyper**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-116">Additionally, you can transfer product dimensions from Microsoft Dynamics 365 for Finance and Operations to the **Attribute types** page.</span></span>

1. <span data-ttu-id="fb5d6-117">Välj **attributtyper** \> **inställningar** \> **attributtyper**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="fb5d6-118">Första gången du ställer in attributtyper väljer du **Skapa produktdimensioner** för att automatiskt överföra standardproduktdimensioner i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard Finance and Operations product dimensions.</span></span>
3. <span data-ttu-id="fb5d6-119">Skapa en ny attributtyp genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="fb5d6-120">I fältet **Attributtyp** anger du ett namn på attributtypen.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="fb5d6-121">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="fb5d6-122">I fältet **enhet** väljer du relevant attributenhet efter behov.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="fb5d6-123">I fältet **Datatyp** väljer du en datatyp för enheten.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="fb5d6-124">Om du har valt **sträng** som datatyp, så här om du vill skapa värden för attributtypen:</span><span class="sxs-lookup"><span data-stu-id="fb5d6-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="fb5d6-125">Välj attributtyp och välj sedan **Värden**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="fb5d6-126">I fältet **Attributvärden** väljer du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="fb5d6-127">I fältet **Attributtyp** väljer du en attributtyp (dimension).</span><span class="sxs-lookup"><span data-stu-id="fb5d6-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="fb5d6-128">I fältet **värde** anger du ett relaterat värde.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="fb5d6-129">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="fb5d6-130">Spara posten.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-130">Save the record.</span></span>
    7. <span data-ttu-id="fb5d6-131">Gå tillbaka till sidan **attributtyper**.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="fb5d6-132">Spara posten.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-132">Save the record.</span></span>

    <span data-ttu-id="fb5d6-133">I fältet **funktionsplatstyper** visas antalet funktionsplatser som använder attributtypen.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="fb5d6-134">Fältet **tillgångstyper** visar antalet tillgångstyper som använder den.</span><span class="sxs-lookup"><span data-stu-id="fb5d6-134">The **Asset types** field shows the number of asset types that are using it.</span></span>
