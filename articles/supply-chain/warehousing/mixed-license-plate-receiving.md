---
title: Inleverans av blandad registreringsskylt
description: "Det här avsnittet beskriver hur du använder blandade registreringsskyltar för att registrera och skapa arbetsuppgifter för flera artiklar med en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 47587664c0c3ed553c724920168782a64fdaf9de
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="5f4d1-103">Inleverans av blandad registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="5f4d1-103">Mixed license plate receiving</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5f4d1-104">Mottagning av blandade registreringsskyltar låter dig skapa en registreringsskylt som består av flera artiklar innan du registrerar och skapar arbetsuppgifter med plats.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="5f4d1-105">En registreringsskylt som består av flera artiklar behöver inte delas vid mottagningsplatsen för att du ka kunna registrera varje artikel.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="5f4d1-106">Du kan skanna streckkoder via artikelstyrningen för att identifiera källdokumentrader när du använder ett artikelrelaterat flöde.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="5f4d1-107">Om streckkoden omfattar en konfigurerad kvantitet och en måttenhet (UOM), kommer artikeln och kvantiteten automatiskt att läggas tillför den blandade registreringsskylten, och du återförs till vyn för att skanna en annan artikel.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="5f4d1-108">På så sätt kan du snabbt scanna alla artiklar utan att behöva göra en bekräftelse i varje steg.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="5f4d1-109">I flödet för mottagande av blandade registreringsskyltar kan du visa listan med artiklar som du redan hr scannat för registreringsskylten, och härifrån kan du även ändra eller korrigera kvantiteten av en artikel.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5f4d1-110">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="5f4d1-110">Where it applies</span></span>

<span data-ttu-id="5f4d1-111">Mottagning av blandade registreringsskyltar är ett mottagningsflöde för mobila enheter med syfte att registrera och skapa arbetsuppgifter för flera rader/artiklar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="5f4d1-112">Detta är användbart om du tar emot inkommande registreringsskyltar med flera objekt.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="5f4d1-113">Konfigurera mottagning av blandade registreringsskyltar</span><span class="sxs-lookup"><span data-stu-id="5f4d1-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="5f4d1-114">Mottagning av blandade registreringsskyltar ställs in som ett menyobjekt på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="5f4d1-115">Du måste skapa ett nytt menyalternativ med läge för arbetsuppgifter som inte använder befintliga arbetsuppgifter och använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="5f4d1-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="5f4d1-116">Inleverans av blandad registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="5f4d1-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="5f4d1-117">Inleverans och inlagring för blandad registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="5f4d1-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="5f4d1-118">Alternativen för att identifiera källdokumentraderna är inköpsorderartikel, inköpsorderrad, returorder, överföring av orderartikel och överföringsorderrad.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="5f4d1-119">Dessa alternativ kan ändra mottagningsordningen på en enda registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="5f4d1-120">Det sista alternativet är per beläggningsartikel.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-120">The last option is by load item.</span></span> <span data-ttu-id="5f4d1-121">Du kan lägga till flera artiklar på en registreringsskylt, men du kan inte växla mellan flera olika beläggningar.</span><span class="sxs-lookup"><span data-stu-id="5f4d1-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>

