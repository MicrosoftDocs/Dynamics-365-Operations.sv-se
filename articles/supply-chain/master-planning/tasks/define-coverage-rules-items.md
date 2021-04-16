---
title: Definiera disponeringsregler för artiklar
description: Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.
author: ShylaThompson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff2d83a01f366517502bfc5c885b6f963bd945ca
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829724"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="fbdf9-103">Definiera disponeringsregler för artiklar</span><span class="sxs-lookup"><span data-stu-id="fbdf9-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fbdf9-104">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fbdf9-105">Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="fbdf9-106">Du ser även hur du anger standardlagerinställningar.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="fbdf9-107">Skapa en disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="fbdf9-107">Create a coverage group</span></span>
1. <span data-ttu-id="fbdf9-108">Gå till **navigeringsfönstret > moduler > huvudplanering > Inställningar > disponeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="fbdf9-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-109">Click **New**.</span></span>
3. <span data-ttu-id="fbdf9-110">Skriv ett värde i fältet **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="fbdf9-111">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="fbdf9-112">Ange ett värde i fältet **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="fbdf9-113">Välj den kalender som huvudplaneringen använder för att skapa återanskaffningsförslag för artiklar i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="fbdf9-114">Välj ett alternativ i fältet **Disponeringskod**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="fbdf9-115">Välj Krav för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="fbdf9-116">Ange "90" i fältet **Tidsgräns för disponering (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="fbdf9-117">Huvudplaneringen genererar återanskaffningsförslag för artiklar i den här gruppen i upp till 90 dagar framåt.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="fbdf9-118">Ange "1" i fältet **Negativa dagar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="fbdf9-119">Ange "1" i fältet **Positiva dagar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="fbdf9-120">Visa eller dölj avsnittet **Övrigt**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="fbdf9-121">Under avsnittet **säkerhetsmarginaler i dagar** i fältet **Inleveransmarginal som lagts till för behovsdatum** anger du "1".</span><span class="sxs-lookup"><span data-stu-id="fbdf9-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="fbdf9-122">Om inleveransmarginalen till exempel är satt till en dag och en inköpsorderrad har tidsplanerats för inleverans den 15 maj, beräknas i huvudplaneringen det justerade inleveransdatumet till den 16 maj.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="fbdf9-123">Ange "1" i fältet **Utleveransmarginal som dragits av från behovsdatum**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="fbdf9-124">Om säkerhetsmarginalen till exempel är satt till en dag och en försäljningsorderrad har tidsplanerats för leverans den 15 maj, beräknas i huvudplaneringen det justerade leveransdatumet till den 14 maj.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="fbdf9-125">Ange "1" i fältet **Ändra ordning på marginal som lagts till i artikelledtiden**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="fbdf9-126">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="fbdf9-127">Skapa en ny produkt</span><span class="sxs-lookup"><span data-stu-id="fbdf9-127">Create a new product</span></span>
1. <span data-ttu-id="fbdf9-128">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="fbdf9-129">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-129">Click **New**.</span></span>
3. <span data-ttu-id="fbdf9-130">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="fbdf9-131">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="fbdf9-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmodellgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="fbdf9-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="fbdf9-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="fbdf9-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="fbdf9-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="fbdf9-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="fbdf9-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="fbdf9-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="fbdf9-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="fbdf9-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="fbdf9-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="fbdf9-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="fbdf9-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="fbdf9-145">Ställ in standardorderinställningar</span><span class="sxs-lookup"><span data-stu-id="fbdf9-145">Setup default order settings</span></span>
1. <span data-ttu-id="fbdf9-146">Klicka på **Plan** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="fbdf9-147">Under **Orderinställningar**, klicka på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="fbdf9-148">Under **Inköpsorder**, i fältet **Standardplats** anger du den plats som används som standardinställning när inköpsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="fbdf9-149">Ange den plats där artikeln lagras i fältet **Standardlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="fbdf9-150">Visa eller dölj avsnittet **Lager**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="fbdf9-151">I fältet **Flera** skriver du "10".</span><span class="sxs-lookup"><span data-stu-id="fbdf9-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="fbdf9-152">I fältet **min. orderkvantitet** skriver du "10".</span><span class="sxs-lookup"><span data-stu-id="fbdf9-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="fbdf9-153">I fältet **max. orderkvantitet** skriver du "100".</span><span class="sxs-lookup"><span data-stu-id="fbdf9-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="fbdf9-154">I fältet **standardorderkvantitet** skriver du "10".</span><span class="sxs-lookup"><span data-stu-id="fbdf9-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="fbdf9-155">Ange ett värde i fältet **Ledtid för inköp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="fbdf9-156">Markera eller avmarkera kryssrutan **Arbetsdagar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="fbdf9-157">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-157">Click **Save**.</span></span>
13. <span data-ttu-id="fbdf9-158">Välj Inköpsorder i fältet **Standardordertyp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="fbdf9-159">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-159">Click **Save**.</span></span>
15. <span data-ttu-id="fbdf9-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-160">Close the page.</span></span> <span data-ttu-id="fbdf9-161">Stäng sidan Standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="fbdf9-162">Lägg till artikel i en disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="fbdf9-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="fbdf9-163">Visa eller dölj avsnittet **Plan**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="fbdf9-164">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="fbdf9-165">Sök efter **disponeringsgruppen** som du skapat i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="fbdf9-166">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="fbdf9-167">Skapa artikeldisponeringsregler</span><span class="sxs-lookup"><span data-stu-id="fbdf9-167">Create item coverage rules</span></span>
1. <span data-ttu-id="fbdf9-168">Klicka på **Plan** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="fbdf9-169">Under **disponering**, klicka på **artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="fbdf9-170">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-170">Click **New**.</span></span>
4. <span data-ttu-id="fbdf9-171">Klicka på fliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="fbdf9-172">Markera rutan i rubriken för **Åsidosätt inställningar för disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="fbdf9-173">Ange "60" i fältet **Tidsgräns för disponering (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="fbdf9-174">Även om artiklar i disponeringsgruppen Behov planeras 90 dagar framåt, kommer denna artikel att planeras 60 dagar framåt.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="fbdf9-175">Ange "2" i fältet **Negativa dagar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="fbdf9-176">Ange "2" i fältet **Positiva dagar**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="fbdf9-177">Klicka på fliken **Ledtid**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="fbdf9-178">Markera rutan i rubriken för **Inköp**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="fbdf9-179">Ange "5" i fältet **Inköpstid**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="fbdf9-180">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fbdf9-180">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]