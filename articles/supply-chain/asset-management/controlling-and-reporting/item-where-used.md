---
title: Artikeln har använts
description: I det här avsnittet beskrivs hur du får en översikt över var en artikel används i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: aa1f00ba6b8259221aa2b1ee460be43ee9a311b2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205491"
---
# <a name="item-where-used"></a><span data-ttu-id="d423e-103">Artikeln har använts</span><span class="sxs-lookup"><span data-stu-id="d423e-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d423e-104">Du kan göra en beräkning för en viss artikel för att få en översikt över var i Tillgångshantering artikeln har använts.</span><span class="sxs-lookup"><span data-stu-id="d423e-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="d423e-105">Resultaten visar i vilket sammanhang artikeln har använts under dess livstid.</span><span class="sxs-lookup"><span data-stu-id="d423e-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="d423e-106">Sidan **Artikel där den används** kan öppnas från huvudmenyn för hantering av tillgångar och kan även öppnas från följande sidor:</span><span class="sxs-lookup"><span data-stu-id="d423e-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="d423e-107">Tillgångsstrukturer</span><span class="sxs-lookup"><span data-stu-id="d423e-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="d423e-108">Reservdelar för standardtyp av tillgång</span><span class="sxs-lookup"><span data-stu-id="d423e-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="d423e-109">Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor</span><span class="sxs-lookup"><span data-stu-id="d423e-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="d423e-110">Underhållsprognoser</span><span class="sxs-lookup"><span data-stu-id="d423e-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="d423e-111">Anskaffning</span><span class="sxs-lookup"><span data-stu-id="d423e-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="d423e-112">Inköp för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="d423e-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="d423e-113">Göra en beräkning av artikel-där-den-används</span><span class="sxs-lookup"><span data-stu-id="d423e-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="d423e-114">Klicka på **Tillgångshantering** > **Förfrågningar** > **Artikel där den används**, eller välj knappen **Artikel där den används** på en av sidorna som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="d423e-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="d423e-115">I dialogrutan **Artikel där den används** välj den artikel som du vill göra beräkningen för i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="d423e-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="d423e-116">Du kan använda fältet **Nivå** för att indikera hur detaljerade artikelraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="d423e-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="d423e-117">Om du till exempel infogar numret "1" i fältet och har en funktionsplatsstruktur med flera nivåer, så visas alla artikelrader för en funktionsplats på den översta nivån.</span><span class="sxs-lookup"><span data-stu-id="d423e-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="d423e-118">Därför kan relationen/kvantiteten på en rad läggas till från funktionsplatserna på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="d423e-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="d423e-119">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla artikelrader på alla de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="d423e-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="d423e-120">Välj "Ja" i avsnittet **Inkludera** på växlingsknapparna som du vill inkludera i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="d423e-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="d423e-121">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="d423e-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="d423e-122">På fliken **Artikel där den används**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="d423e-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="d423e-123">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="d423e-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="d423e-124">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="d423e-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="d423e-125">Om du vill visa relaterade dimensioner för artikeln klickar du på **Visa dimensioner** och väljer de dimensioner som ska visas.</span><span class="sxs-lookup"><span data-stu-id="d423e-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="d423e-126">Exempel</span><span class="sxs-lookup"><span data-stu-id="d423e-126">Example</span></span>

<span data-ttu-id="d423e-127">I skärmbilden nedan visas ett exempel på en beräkning av artikel-där-den-används för artikelnummer "1000".</span><span class="sxs-lookup"><span data-stu-id="d423e-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Exempel på artikel där beräkningen används](media/12-controlling-and-reporting.png)

