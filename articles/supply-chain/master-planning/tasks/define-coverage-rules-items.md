---
title: Definiera disponeringsregler för artiklar
description: Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02aa3b2b7924cdf6317225bfce23f182aa390b8c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "320637"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="988f6-103">Definiera disponeringsregler för artiklar</span><span class="sxs-lookup"><span data-stu-id="988f6-103">Define coverage rules for items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="988f6-104">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="988f6-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="988f6-105">Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel.</span><span class="sxs-lookup"><span data-stu-id="988f6-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="988f6-106">Du ser även hur du anger standardlagerinställningar.</span><span class="sxs-lookup"><span data-stu-id="988f6-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="988f6-107">Skapa en disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="988f6-107">Create a coverage group</span></span>
1. <span data-ttu-id="988f6-108">Gå till Disponeringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="988f6-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="988f6-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="988f6-109">Click New.</span></span>
3. <span data-ttu-id="988f6-110">Skriv ett värde i fältet Disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="988f6-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="988f6-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="988f6-112">Ange ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="988f6-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="988f6-113">Välj den kalender som huvudplaneringen använder för att skapa återanskaffningsförslag för artiklar i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="988f6-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="988f6-114">Välj ett alternativ i fältet Disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="988f6-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="988f6-115">Välj Krav för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="988f6-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="988f6-116">Ange "90" i fältet Tidsgräns för disponering (dagar).</span><span class="sxs-lookup"><span data-stu-id="988f6-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="988f6-117">Huvudplaneringen genererar återanskaffningsförslag för artiklar i den här gruppen i upp till 90 dagar framåt.</span><span class="sxs-lookup"><span data-stu-id="988f6-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="988f6-118">Ange "1" i fältet Negativa dagar.</span><span class="sxs-lookup"><span data-stu-id="988f6-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="988f6-119">Ange "1" i fältet Positiva dagar.</span><span class="sxs-lookup"><span data-stu-id="988f6-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="988f6-120">Visa eller dölj avsnittet Övrigt.</span><span class="sxs-lookup"><span data-stu-id="988f6-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="988f6-121">Ange "1" i i fältet Inleveransmarginal som lagts till för behovsdatum.</span><span class="sxs-lookup"><span data-stu-id="988f6-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="988f6-122">Om inleveransmarginalen till exempel är satt till en dag och en inköpsorderrad har tidsplanerats för inleverans den 15 maj, beräknas i huvudplaneringen det justerade inleveransdatumet till den 16 maj.</span><span class="sxs-lookup"><span data-stu-id="988f6-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="988f6-123">Ange "1" i fältet Utleveransmarginal som dragits av från behovsdatum.</span><span class="sxs-lookup"><span data-stu-id="988f6-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="988f6-124">Om säkerhetsmarginalen till exempel är satt till en dag och en försäljningsorderrad har tidsplanerats för leverans den 15 maj, beräknas i huvudplaneringen det justerade leveransdatumet till den 14 maj.</span><span class="sxs-lookup"><span data-stu-id="988f6-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="988f6-125">Ange "1" i fältet Ändra ordning på marginal som lagts till i artikelledtiden.</span><span class="sxs-lookup"><span data-stu-id="988f6-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="988f6-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="988f6-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="988f6-127">Skapa en ny produkt</span><span class="sxs-lookup"><span data-stu-id="988f6-127">Create a new product</span></span>
1. <span data-ttu-id="988f6-128">Gå till Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="988f6-128">Go to Released products.</span></span>
2. <span data-ttu-id="988f6-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="988f6-129">Click New.</span></span>
3. <span data-ttu-id="988f6-130">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="988f6-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="988f6-131">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="988f6-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="988f6-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="988f6-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="988f6-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="988f6-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="988f6-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="988f6-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="988f6-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="988f6-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="988f6-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="988f6-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="988f6-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="988f6-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="988f6-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="988f6-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="988f6-145">Ställ in standardorderinställningar</span><span class="sxs-lookup"><span data-stu-id="988f6-145">Setup default order settings</span></span>
1. <span data-ttu-id="988f6-146">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="988f6-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="988f6-147">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="988f6-147">Click Default order settings.</span></span>
3. <span data-ttu-id="988f6-148">Ange den plats som används som standardinställning när inköpsorder skapas i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="988f6-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="988f6-149">Ange den plats där artikeln lagras i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="988f6-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="988f6-150">Visa eller dölj avsnittet Lager.</span><span class="sxs-lookup"><span data-stu-id="988f6-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="988f6-151">Ange Flera som "10".</span><span class="sxs-lookup"><span data-stu-id="988f6-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="988f6-152">Ange min.</span><span class="sxs-lookup"><span data-stu-id="988f6-152">Set Min.</span></span> <span data-ttu-id="988f6-153">orderkvantitet som "10".</span><span class="sxs-lookup"><span data-stu-id="988f6-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="988f6-154">Ange Max.</span><span class="sxs-lookup"><span data-stu-id="988f6-154">Set Max.</span></span> <span data-ttu-id="988f6-155">orderkvantitet som "100".</span><span class="sxs-lookup"><span data-stu-id="988f6-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="988f6-156">Ange Standardorderkvantitet som "10".</span><span class="sxs-lookup"><span data-stu-id="988f6-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="988f6-157">Ange ett värde i fältet Ledtid för inköp.</span><span class="sxs-lookup"><span data-stu-id="988f6-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="988f6-158">Markera eller avmarkera kryssrutan Arbetsdagar.</span><span class="sxs-lookup"><span data-stu-id="988f6-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="988f6-159">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="988f6-159">Click Save.</span></span>
13. <span data-ttu-id="988f6-160">Välj Inköpsorder i fältet Standardordertyp.</span><span class="sxs-lookup"><span data-stu-id="988f6-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="988f6-161">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="988f6-161">Click Save.</span></span>
15. <span data-ttu-id="988f6-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="988f6-162">Close the page.</span></span>
    * <span data-ttu-id="988f6-163">Stäng sidan Standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="988f6-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="988f6-164">Lägg till artikel i en disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="988f6-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="988f6-165">Visa eller dölj avsnittet Plan.</span><span class="sxs-lookup"><span data-stu-id="988f6-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="988f6-166">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="988f6-167">Sök efter disponeringsgruppen som du skapat i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="988f6-168">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="988f6-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="988f6-169">Skapa artikeldisponeringsregler</span><span class="sxs-lookup"><span data-stu-id="988f6-169">Create item coverage rules</span></span>
1. <span data-ttu-id="988f6-170">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="988f6-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="988f6-171">Klicka på Artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="988f6-171">Click Item coverage.</span></span>
3. <span data-ttu-id="988f6-172">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="988f6-172">Click New.</span></span>
4. <span data-ttu-id="988f6-173">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="988f6-173">Click the General tab.</span></span>
5. <span data-ttu-id="988f6-174">Markera rutan i rubriken för Åsidosätt inställningar för disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="988f6-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="988f6-175">Ange "60" i fältet Tidsgräns för disponering (dagar).</span><span class="sxs-lookup"><span data-stu-id="988f6-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="988f6-176">Även om artiklar i disponeringsgruppen Behov planeras 90 dagar framåt, kommer denna artikel att planeras 60 dagar framåt.</span><span class="sxs-lookup"><span data-stu-id="988f6-176">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="988f6-177">Ange "2" i fältet Negativa dagar.</span><span class="sxs-lookup"><span data-stu-id="988f6-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="988f6-178">Ange "2" i fältet Positiva dagar.</span><span class="sxs-lookup"><span data-stu-id="988f6-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="988f6-179">Klicka på fliken Ledtid.</span><span class="sxs-lookup"><span data-stu-id="988f6-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="988f6-180">Markera rutan i rubriken för Inköp.</span><span class="sxs-lookup"><span data-stu-id="988f6-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="988f6-181">Ange "5" i fältet Inköpstid.</span><span class="sxs-lookup"><span data-stu-id="988f6-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="988f6-182">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="988f6-182">Click Save.</span></span>

