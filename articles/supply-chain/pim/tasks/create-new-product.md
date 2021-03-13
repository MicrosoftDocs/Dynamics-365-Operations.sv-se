---
title: Skapa en ny produkt
description: I det här avsnittet beskrivs hur du skapar en ny delad produkt.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d313d76d40476bec5c8bc9c8ea5fc93b217e7e87
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007576"
---
# <a name="create-a-new-product"></a><span data-ttu-id="237a3-103">Skapa en ny produkt</span><span class="sxs-lookup"><span data-stu-id="237a3-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="237a3-104">I det här avsnittet beskrivs hur du skapar en ny delad produkt.</span><span class="sxs-lookup"><span data-stu-id="237a3-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="237a3-105">Den utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="237a3-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="237a3-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="237a3-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="237a3-107">Skapa en produkt</span><span class="sxs-lookup"><span data-stu-id="237a3-107">Create a product</span></span>
1. <span data-ttu-id="237a3-108">I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Produkter**.</span><span class="sxs-lookup"><span data-stu-id="237a3-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="237a3-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="237a3-109">Select **New**.</span></span>
3. <span data-ttu-id="237a3-110">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="237a3-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="237a3-111">Om en nummerserie inte har ställts in för den produktnumret, måste den anges manuellt.</span><span class="sxs-lookup"><span data-stu-id="237a3-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="237a3-112">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="237a3-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="237a3-113">Produktnamnet anges som standard till söknamnet.</span><span class="sxs-lookup"><span data-stu-id="237a3-113">The product name defaults to the search name.</span></span> <span data-ttu-id="237a3-114">Du kan ändra detta om det behövs.</span><span class="sxs-lookup"><span data-stu-id="237a3-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="237a3-115">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="237a3-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="237a3-116">Ställ in dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="237a3-116">Set up dimension groups</span></span>
1. <span data-ttu-id="237a3-117">Välj **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="237a3-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="237a3-118">Ange eller välj ett värde i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="237a3-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="237a3-119">Lagringsdimensiongruppen avgör vilka lagringsdimensioner du måste ange för varje transaktion för produkten och hur den ska spåras i lagret.</span><span class="sxs-lookup"><span data-stu-id="237a3-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="237a3-120">Ange eller välj ett värde i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="237a3-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="237a3-121">Spårningsdimensiongruppen avgör vilka spårningsdimensioner du måste ange för varje transaktion för produkten och hur den ska hanteras i lagret.</span><span class="sxs-lookup"><span data-stu-id="237a3-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="237a3-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="237a3-122">Select **OK**.</span></span>

