---
title: Skapa tillgångar baserade på inköpsorder
description: I det här avsnittet beskrivs hur du kan skapa en lista över tillgångsartiklar som kan användas som underlag för att skapa tillgångar för underhållsjobb i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dd52d877ee7f862577d8bfea113f22eca03c597
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209891"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="b46ea-103">Skapa tillgångar baserade på inköpsorder</span><span class="sxs-lookup"><span data-stu-id="b46ea-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b46ea-104">I det här avsnittet beskrivs hur du kan skapa en lista över tillgångsartiklar som kan användas som underlag för att skapa tillgångar för underhållsjobb i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="b46ea-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="b46ea-105">Baserat på tillgångsartiklarna kan du visa en lista över inköpsorderrader som har skapats på dessa artiklar.</span><span class="sxs-lookup"><span data-stu-id="b46ea-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="b46ea-106">Syftet med den här funktionen är att enkelt skapa en tillgång i tillgångshantering baserat på en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b46ea-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="b46ea-107">Först ställer du in de artiklar som ska användas för att skapa tillgångar från en inköpsorder i **tillgångsartiklar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="b46ea-108">När du har skapat en inköpsorderrad skapar du tillgångarna i **väntande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="b46ea-109">Det är möjligt att bestämma i vilket skede av inköpsordern som tillgången ska skapas.</span><span class="sxs-lookup"><span data-stu-id="b46ea-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="b46ea-110">Välj tillgångsartiklar</span><span class="sxs-lookup"><span data-stu-id="b46ea-110">Select asset items</span></span>

1. <span data-ttu-id="b46ea-111">Klicka på **tillgångshantering** > **inställningar** > **tillgångar** > **artiklar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="b46ea-112">Klicka på **Ny** om du vill skapa en ny tillgångsartikel.</span><span class="sxs-lookup"><span data-stu-id="b46ea-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="b46ea-113">Välj artikeln i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="b46ea-114">När du lämnar fältet infogas artikelnamnet automatiskt i fältet **produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="b46ea-115">På snabbfliken **Allmänt** väljer du en tillgångstyp för artikeln.</span><span class="sxs-lookup"><span data-stu-id="b46ea-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="b46ea-116">Välj tillgångstillverkare och modell för artikeln.</span><span class="sxs-lookup"><span data-stu-id="b46ea-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="b46ea-117">Spara artikeln.</span><span class="sxs-lookup"><span data-stu-id="b46ea-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="b46ea-118">Skapa tillgångar från väntande tillgångar</span><span class="sxs-lookup"><span data-stu-id="b46ea-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="b46ea-119">Klicka på **tillgångshantering** > **allmänt** > **tillgångar** > **väntande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="b46ea-120">Du kommer att se en uppdaterad lista över inköpsorder baserat på de artiklar som valts i **tillgångsartiklar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="b46ea-121">Du kan filtrera status för inköpsorder för att välja vid vilket livscykeltillstånd som tillgången ska skapas.</span><span class="sxs-lookup"><span data-stu-id="b46ea-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="b46ea-122">Du kanske till exempel bara vill skapa tillgångar när en produktinleverans har bokförts på en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b46ea-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="b46ea-123">Välj länken **referensnummer** på en inköpsorderrad om du vill visa detaljerad information om artikeln.</span><span class="sxs-lookup"><span data-stu-id="b46ea-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="b46ea-124">Om du vill redigera vilka dimensioner som visas på snabbfliken **lagerdimensioner** klickar du på knappen **Visa dimensioner** och gör dina val.</span><span class="sxs-lookup"><span data-stu-id="b46ea-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="b46ea-125">Om du vill skapa en tillgång baserat på en inköpsorderrad markerar du kryssrutan i kolumnen **Markera** för den raden på listsidan och klickar på **skapa tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="b46ea-126">Ett meddelande visas som informerar dig om tillgångs-ID.</span><span class="sxs-lookup"><span data-stu-id="b46ea-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="b46ea-127">Välj tillgången i listan **alla tillgångar** och klicka på knappen **redigera** för att lägga till mer information till tillgången.</span><span class="sxs-lookup"><span data-stu-id="b46ea-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="b46ea-128">I **väntande tillgångar**, om du vill ta bort en rad eftersom du inte vill skapa en tillgång, markerar du kryssrutan i kolumnen **Markera** för raden och klickar på **ignorera väntande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="b46ea-129">Ett meddelande visas som informerar dig om tillgångs-ID.</span><span class="sxs-lookup"><span data-stu-id="b46ea-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="b46ea-130">Du tar inte bort inköpsordern eller försäljningsordern, bara den post som du kunde ha skapat en tillgång för i **tillgångshanteraren**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="b46ea-131">Alla produktdimensioner (storlek, färg, konfiguration etc.) överförs automatiskt till tillgångsattribut.</span><span class="sxs-lookup"><span data-stu-id="b46ea-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="b46ea-132">Spårningsdimensioner (serienummer) lagras direkt på tillgången när tillgången skapas.</span><span class="sxs-lookup"><span data-stu-id="b46ea-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="b46ea-133">Hitta väntande tillgångar</span><span class="sxs-lookup"><span data-stu-id="b46ea-133">Find pending assets</span></span>

<span data-ttu-id="b46ea-134">Du kan köra en **väntande tillgångsräkning** för att kontrollera väntande tillgångar.</span><span class="sxs-lookup"><span data-stu-id="b46ea-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="b46ea-135">Den här funktionen kan till exempel användas för att ta emot ett meddelande varje gång en väntande tillgång är redo att skapas som en tillgång.</span><span class="sxs-lookup"><span data-stu-id="b46ea-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="b46ea-136">Klicka på **tillgångshantering** > **periodisk** > **tillgångar** > **väntande tillgångsräkning**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="b46ea-137">Klicka på **OK** för att köra jobbet och uppdatera listan i **väntande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b46ea-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="b46ea-138">Du kan ställa in det här jobbet så att det körs som ett batchjobb, till exempel en gång per dag.</span><span class="sxs-lookup"><span data-stu-id="b46ea-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="b46ea-139">**Varning:** om data ändras på en inköpsorder *efter* att du har skapat en tillgång baserat på artikeln, återspeglas inte dessa ändringar på tillgången.</span><span class="sxs-lookup"><span data-stu-id="b46ea-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>
