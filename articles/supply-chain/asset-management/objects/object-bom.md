---
title: Tillgångsstrukturer
description: Det här avsnittet beskriver tillgångsstrukturer i tillgångshanteraren
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7222db087c40a7a5a47902944a69671ad5a8878d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839641"
---
# <a name="asset-boms"></a><span data-ttu-id="eb98e-103">Tillgångsstrukturer</span><span class="sxs-lookup"><span data-stu-id="eb98e-103">Asset BOMs</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="eb98e-104">Det här avsnittet beskriver tillgångsstrukturer i tillgångshanteraren</span><span class="sxs-lookup"><span data-stu-id="eb98e-104">This topic describes asset bills of materials (BOMs) in Asset Management.</span></span> <span data-ttu-id="eb98e-105">Sidan **Tillgångsstrukturer** visar en lista över alla artiklar (reservdelar och andra artiklar) som används på en tillgång under hela dess livstid.</span><span class="sxs-lookup"><span data-stu-id="eb98e-105">The **Asset BOM** page shows a list of all items (spare parts and other items) that are used on an asset during its whole lifetime.</span></span> <span data-ttu-id="eb98e-106">När du skapar en ny tillgång bör du överväga att ställa in en tillgångsstruktur som en del av inställningsproceduren.</span><span class="sxs-lookup"><span data-stu-id="eb98e-106">When you create a new asset, you should consider setting up an asset BOM as a part of the setup procedure.</span></span> <span data-ttu-id="eb98e-107">På så sätt kan du spåra artikelhistoriken för tillgången från datumet för skapandet.</span><span class="sxs-lookup"><span data-stu-id="eb98e-107">In this way, you can track item history for the asset from the creation date.</span></span>

<span data-ttu-id="eb98e-108">När du har slutfört ett underhållsjobb och artikelförbrukning har registrerats på en arbetsorder kan du spåra förbrukning av reservdelar och andra artiklar som används på tillgången.</span><span class="sxs-lookup"><span data-stu-id="eb98e-108">After you've completed a maintenance job, and item consumption has been registered on a work order, you can track consumption of spare parts and other items that are used on the asset.</span></span> <span data-ttu-id="eb98e-109">Den här funktionen kan du behålla en fullständig artikelförbrukningspost för alla dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="eb98e-109">This functionality lets you keep a complete item consumption record for all your assets.</span></span> <span data-ttu-id="eb98e-110">Du kan till exempel använda posten för att övervaka om en viss reservdel ofta ersätts eller för att hålla reda på de reservdelar eller andra artiklar som för närvarande används på en tillgång.</span><span class="sxs-lookup"><span data-stu-id="eb98e-110">For example, you can use the record to monitor whether a specific spare part is often replaced, or to keep track of the spare parts or other items that are currently used on an asset.</span></span>

> [!NOTE]
> <span data-ttu-id="eb98e-111">På en arbetsorder kan artikelförbrukning innehålla både reservdelar och andra, ytterligare artiklar, till exempel smörjmedel, bultar och packningar.</span><span class="sxs-lookup"><span data-stu-id="eb98e-111">On a work order, item consumption might include both spare parts and other, additional items, such as lubricants, bolts, and gaskets.</span></span>

<span data-ttu-id="eb98e-112">En tillgångsstruktur kan uppdateras automatiskt baserat på inställningarna i tillgångshanteraren.</span><span class="sxs-lookup"><span data-stu-id="eb98e-112">An asset BOM can be automatically updated based on the setup in Asset Management.</span></span> <span data-ttu-id="eb98e-113">Om ett livscykeltillstånd för arbetsorder har skapats för att hantera färdiga eller slutförda arbetsorder och alternativet **uppdatera tillgångsstruktur** för den arbetsorderns livscykeltillstånd anges till **Ja** i **livscykeltillstånd för arbetsorder** kommer alla artiklar som används på den arbetsordern att uppdateras automatiskt på sidan **tillgångsstruktur** när arbetsordern uppdateras till det livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="eb98e-113">If a work order lifecycle state has been created to handle finished or completed work orders, and if the **Update asset BOM** option for that work order lifecycle state is set to **Yes** on the **Work order lifecycle states** page, all items that are used on the work order will be automatically updated on the **Asset BOM** page when the work order is updated to that lifecycle state.</span></span> 


<span data-ttu-id="eb98e-114">Du kan också manuellt uppdatera en tillgångsstruktur genom att skapa nya artikelrader på sidan **tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-114">You can also manually update an asset BOM by creating new item lines on the **Asset BOM** page.</span></span>

<span data-ttu-id="eb98e-115">På sidan **tillgångsstruktur** kan du spåra reservdelshistorik för tillgångar när artikelförbrukningen har registrerats på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="eb98e-115">On the **Asset BOM** page, you can track spare parts history for assets after item consumption is registered on a work order.</span></span> <span data-ttu-id="eb98e-116">Om du vill använda den här funktionen måste du välja de artikelgrupper som ska användas för reservdelsregistrering på sidan **artikelgrupper för reservdelar**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-116">To use this functionality, you must select the item groups that should be used for spare parts registration on the **Spare parts item groups** page.</span></span>

<span data-ttu-id="eb98e-117">Om du vill använda funktionen för tillgångsstruktur måste du först ställa in nödvändiga artikelgrupper för reservdelar.</span><span class="sxs-lookup"><span data-stu-id="eb98e-117">To use asset BOM functionality, you must first set up the required spare parts items groups.</span></span> <span data-ttu-id="eb98e-118">Om du vill att tillgångsstrukturen ska uppdateras automatiskt när en arbetsorder slutförs, kan du ställa in ett livscykeltillstånd för arbetsorder för att hantera uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="eb98e-118">Then, if you want the asset BOM to be automatically updated when a work order is completed, you can set up a work order lifecycle state to handle that update.</span></span> 


## <a name="set-up-spare-parts-item-groups"></a><span data-ttu-id="eb98e-119">Ställ in artikelgrupper för reservdelar</span><span class="sxs-lookup"><span data-stu-id="eb98e-119">Set up spare parts item groups</span></span>

<span data-ttu-id="eb98e-120">Inställningen av reservdelshistoriken baseras på artikelgrupper som skapas i modulen **hantering av lager och lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-120">The setup of spare parts history is based on item groups that are created in the **Inventory and warehouse management** module.</span></span> <span data-ttu-id="eb98e-121">I tillgångshantering ställer du in artikelgrupper så att du kan spåra reservdelshistorik för artiklarna i de valda artikelgrupperna.</span><span class="sxs-lookup"><span data-stu-id="eb98e-121">In Asset Management, you set up item groups so that you can track spare parts history for the items in the selected item groups.</span></span>

1. <span data-ttu-id="eb98e-122">Välj **tillgångshantering** \> **inställningar** \> **tillgång** \> **artikelgrupper för reservdelar**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-122">Select **Asset management** \> **Setup** \> **Asset** \> **Spare parts item groups**.</span></span>
2. <span data-ttu-id="eb98e-123">Välj **ny** om du vill ställa in en artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="eb98e-123">Select **New** to set up an item group.</span></span>
3. <span data-ttu-id="eb98e-124">I fältet **artikelgrupp** väljer du gruppen.</span><span class="sxs-lookup"><span data-stu-id="eb98e-124">In the **Item group** field, select the group.</span></span> <span data-ttu-id="eb98e-125">Namnet på gruppen anges automatiskt i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-125">The name of the group is automatically entered in the **Name** field.</span></span>

## <a name="view-and-update-asset-boms"></a><span data-ttu-id="eb98e-126">Visa och uppdatera tillgångsstrukturlistor</span><span class="sxs-lookup"><span data-stu-id="eb98e-126">View and update asset BOMs</span></span>

<span data-ttu-id="eb98e-127">När du bokför artikelförbrukning på en arbetsorder kan du visa den registrerade artikelförbrukningen på sidan **tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-127">After you post item consumption on a work order, you can view the registered item consumption on the **Asset BOM** page.</span></span>

1. <span data-ttu-id="eb98e-128">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Aktiva tillgångar**</span><span class="sxs-lookup"><span data-stu-id="eb98e-128">Select **Asset management** \> **Common** \> **Assets** \> **Active assets**.</span></span> <span data-ttu-id="eb98e-129">Välj tillgången i listan och välj sedan **tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-129">Select the asset in the list, and then select **Asset BOM**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb98e-130">Om du vill visa alla artikelförbrukningsregistreringar på alla tillgångar, välj **tillgångshantering** \> **förfrågningar** \> **tillgångar** \> **tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-130">To view all item consumption registrations on all assets, select **Asset management** \> **Inquiries** \> **Assets** \> **Asset BOM**.</span></span>

2. <span data-ttu-id="eb98e-131">Välj **uppdatera tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-131">Select **Update asset BOM**.</span></span> <span data-ttu-id="eb98e-132">Du kan lägga till tillgångar, tillgångstyper och resurser till uppdateringen som du behöver genom att välja **Välj**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-132">You can add assets, asset types, and resources to the update as you require by selecting **Select**.</span></span> <span data-ttu-id="eb98e-133">Starta uppdateringen genom att välja **OK**,</span><span class="sxs-lookup"><span data-stu-id="eb98e-133">Select **OK** to start the update.</span></span> <span data-ttu-id="eb98e-134">Du kan också ställa in uppdateringsfunktionen som ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="eb98e-134">You can also set up the Update function as a batch job.</span></span>
3. <span data-ttu-id="eb98e-135">Om du vill se mer information som är relaterad till artiklarna kan du lägga till lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="eb98e-135">If you want to see more information that is related to the items, you can add inventory dimensions.</span></span> <span data-ttu-id="eb98e-136">Välj **Lager** \> **Dimensionsvisning** och markera sedan kryssrutorna för de dimensioner som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="eb98e-136">Select **Inventory** \> **Dimensions display**, and then select the check boxes for the dimensions that you want to see.</span></span> <span data-ttu-id="eb98e-137">Om du vill behålla den här inställningen för alla **tillgångsstrukturer** anger du alternativet **spara inställningar** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-137">To keep this setup for all assets on the **Asset BOM** page, set the **Save setup** option to **Yes**.</span></span>
4. <span data-ttu-id="eb98e-138">Om du vill få en översikt över var i tillgångshantering som artikeln på den valda raden används, i relation till tillgångar, jobbtypstandard, reservdelar och arbetsorder väljer du **artikel där den används**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-138">To get an overview of where in Asset Management the item on the selected line is used, in relation to assets, job type defaults, spare parts, and work orders, select **Item where used**.</span></span> 
5. <span data-ttu-id="eb98e-139">Om du bara vill visa aktiva artikelrader väljer du **visa** \> **aktuell**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-139">If you want to see only active item lines, select **View** \> **Current**.</span></span> <span data-ttu-id="eb98e-140">Om du vill visa alla artikelrader, inklusive rader där förfallodatumet infaller tidigare än det aktuella datumet väljer du **Visa** \> **Alla**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-140">To see all item lines, including lines where the expiration date is earlier than the current date, select **View** \> **All**.</span></span>

> [!NOTE]
> <span data-ttu-id="eb98e-141">När du har slutfört en arbetsorder, om vissa artiklar eller reservdelar som är relaterade till den relaterade tillgången har upphört att gälla eller har ersatts av andra artiklar eller reservdelar, rekommenderar vi att du uppdaterar tillgångsstrukturen i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="eb98e-141">When you've completed a work order, if some items or spare parts that are related to the related asset have expired or have been replaced by other items or spare parts, we recommend that you update the asset BOM accordingly.</span></span>

## <a name="create-a-new-item-line-in-an-asset-bom"></a><span data-ttu-id="eb98e-142">Skapa en ny artikelrad i en tillgångsstruktur</span><span class="sxs-lookup"><span data-stu-id="eb98e-142">Create a new item line in an asset BOM</span></span>

<span data-ttu-id="eb98e-143">Du kan manuellt skapa artikelrader för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="eb98e-143">You can manually create item lines for assets.</span></span>

1. <span data-ttu-id="eb98e-144">Välj **Nytt** på sidan **Tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-144">On the **Asset BOM** page, select **New**.</span></span>
2. <span data-ttu-id="eb98e-145">I fältet **Tillgång** väljer du den tillgång du vill lägga till en artikelrad för.</span><span class="sxs-lookup"><span data-stu-id="eb98e-145">In the **Asset** field, select the asset to add an item line for.</span></span>
3. <span data-ttu-id="eb98e-146">Ange ett sekventiellt radnummer i fältet **Radnummer**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-146">In the **Line number** field, enter a sequential line number.</span></span>
4. <span data-ttu-id="eb98e-147">Ange ett startdatum för artikeln i fältet **Giltighet**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-147">In the **Effective** field, enter a start date for the item.</span></span>
5. <span data-ttu-id="eb98e-148">Om artikeln upphör att gälla anger du ett slutdatum i fältet **förfallodatum**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-148">If the item will expire, in the **Expiration** field, enter an end date.</span></span>
6. <span data-ttu-id="eb98e-149">Välj en artikel i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-149">In the **Item number** field, select the item.</span></span> <span data-ttu-id="eb98e-150">Namnet anges automatiskt i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="eb98e-150">The name is automatically entered in the **Product name** field.</span></span>
7. <span data-ttu-id="eb98e-151">I fältet **Kvantitet** anger du kvantiteten som används.</span><span class="sxs-lookup"><span data-stu-id="eb98e-151">In the **Quantity** field, enter the quantity that is used.</span></span> <span data-ttu-id="eb98e-152">Fältet **Enhet** uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="eb98e-152">The **Unit** field is automatically updated.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]