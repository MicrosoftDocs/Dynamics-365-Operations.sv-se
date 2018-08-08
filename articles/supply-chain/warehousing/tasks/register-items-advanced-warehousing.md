--- 
title: "Registrera artiklar för en avancerad lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal"
description: "I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerlagerstyrning."
author: ShylaThompson
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1dab4ba973f5a9d3a2d8f1b5a5afcdd821d1a6d0
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="3f932-103">Registrera artiklar för en avancerad lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="3f932-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f932-104">I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerlagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="3f932-104">This procedure shows you how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="3f932-105">Detta görs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="3f932-105">This would usually be done by a receiving clerk.</span></span> 

<span data-ttu-id="3f932-106">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="3f932-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="3f932-107">Du måste ha en bekräftad inköpsorder med en öppen inköpsorderrad innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="3f932-107">You need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="3f932-108">Artikeln på raden måste finnas i lager och får inte innehålla produktvarianter och spårningsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="3f932-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="3f932-109">Och artikeln måste associeras med en lagerstyrningsprocess för lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="3f932-109">And the item needs to be associated with a warehouse management process enabled storage dimension group.</span></span> <span data-ttu-id="3f932-110">Lagerstället som används måste aktiveras för lagerstyrningsprocesser och lagerplatsen som du använder för inleveranser måste vara id-nummerstyrd.</span><span class="sxs-lookup"><span data-stu-id="3f932-110">The warehouse that’s used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span> <span data-ttu-id="3f932-111">Om du använder USMF, kan du använda företagskontot 1001, lagerställe 51 och artikeln M9200 när du skapar inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="3f932-111">If you’re using USMF, you can use company account 1001, Warehouse 51, and item M9200 to create your PO.</span></span> 

<span data-ttu-id="3f932-112">Gör en notering om inköpsordernumret du skapar och anteckna också artikelnumret och lagerplatsen för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="3f932-112">Make a note of the number of the purchase order that you create, and also note the item number and the site that you used for your purchase order line.</span></span>


## <a name="create-an-item-arrival-journal-header"></a><span data-ttu-id="3f932-113">Skapa ett artikelinförseljournalhuvud</span><span class="sxs-lookup"><span data-stu-id="3f932-113">Create an item arrival journal header</span></span>
1. <span data-ttu-id="3f932-114">Gå till Artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="3f932-114">Go to Item arrival.</span></span>
2. <span data-ttu-id="3f932-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3f932-115">Click New.</span></span>
3. <span data-ttu-id="3f932-116">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="3f932-116">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3f932-117">Om du använder USMF kan du skriva WHS.</span><span class="sxs-lookup"><span data-stu-id="3f932-117">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="3f932-118">Om du använder andra data måste journalen vars namn du väljer ha följande egenskaper: Kontrollera plockplats måste anges till Nej och Karantänhantering måste anges till Nej.</span><span class="sxs-lookup"><span data-stu-id="3f932-118">If you’re using other data, the journal whose name you choose has to have the following properties: Check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="3f932-119">Ange ett värde i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="3f932-119">In the Number field, type a value.</span></span>
5. <span data-ttu-id="3f932-120">Ange ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="3f932-120">In the Site field, type a value.</span></span>
    * <span data-ttu-id="3f932-121">Markera platsen du använde till inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="3f932-121">Select the site that you used for your purchase order line.</span></span> <span data-ttu-id="3f932-122">Den fungerar som standardplats som blir förvalt värde för alla rader i journalen.</span><span class="sxs-lookup"><span data-stu-id="3f932-122">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f932-123">Om du använder lagerställe 51 i USMF, välj plats 5.</span><span class="sxs-lookup"><span data-stu-id="3f932-123">If you used warehouse 51 in USMF, choose site 5.</span></span>  
6. <span data-ttu-id="3f932-124">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="3f932-124">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="3f932-125">Välj ett giltigt lagerställe för den plats som du har valt.</span><span class="sxs-lookup"><span data-stu-id="3f932-125">Select a valid warehouse for the site that you’ve selected.</span></span> <span data-ttu-id="3f932-126">Den fungerar som standardplats som blir förvalt värde för alla rader i journalen.</span><span class="sxs-lookup"><span data-stu-id="3f932-126">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f932-127">Om du använder exempelvärdena i USMF, välj 51.</span><span class="sxs-lookup"><span data-stu-id="3f932-127">If you’re using the example values in USMF, select 51.</span></span>  
7. <span data-ttu-id="3f932-128">Skriv ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="3f932-128">In the Location field, type a value.</span></span>
    * <span data-ttu-id="3f932-129">Välj en giltig lagerplats på lagerstället du har valt.</span><span class="sxs-lookup"><span data-stu-id="3f932-129">Select a valid location in the warehouse that you’ve selected.</span></span> <span data-ttu-id="3f932-130">Platsen måste vara kopplade till en platsprofil som styrs av id-numret.</span><span class="sxs-lookup"><span data-stu-id="3f932-130">The location has to be associated with a location profile, which is license plate controlled.</span></span> <span data-ttu-id="3f932-131">Den fungerar som standardplats som blir förvalt värde för alla rader i journalen.</span><span class="sxs-lookup"><span data-stu-id="3f932-131">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f932-132">Om du använder exempelvärdena i USMF, välj Bulk-008.</span><span class="sxs-lookup"><span data-stu-id="3f932-132">If you’re using the example values in USMF, select Bulk-008.</span></span>  
8. <span data-ttu-id="3f932-133">Högerklicka på nedrullningspilen i id-nummerfältet och välj sedan Visa detaljer.</span><span class="sxs-lookup"><span data-stu-id="3f932-133">Right-click on the drop-down arrow in the License plate field and then select View details.</span></span>
9. <span data-ttu-id="3f932-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3f932-134">Click New.</span></span>
10. <span data-ttu-id="3f932-135">Ange ett värde i fältet för id-numret.</span><span class="sxs-lookup"><span data-stu-id="3f932-135">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3f932-136">Gör en notering av värdet.</span><span class="sxs-lookup"><span data-stu-id="3f932-136">Make a note of the value.</span></span>  
11. <span data-ttu-id="3f932-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="3f932-137">Click Save.</span></span>
12. <span data-ttu-id="3f932-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f932-138">Close the page.</span></span>
13. <span data-ttu-id="3f932-139">Ange ett värde i fältet för id-numret.</span><span class="sxs-lookup"><span data-stu-id="3f932-139">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3f932-140">Ange värdet för den registreringsskylt du just skapade.</span><span class="sxs-lookup"><span data-stu-id="3f932-140">Enter the value of the license plate that you just created.</span></span> <span data-ttu-id="3f932-141">Den fungerar som standardplats som blir förvalt värde för alla rader i journalen.</span><span class="sxs-lookup"><span data-stu-id="3f932-141">This will serve as a default value, which will default to all lines in the journal.</span></span>  
14. <span data-ttu-id="3f932-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-142">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="3f932-143">Lägga till en rad</span><span class="sxs-lookup"><span data-stu-id="3f932-143">Add a line</span></span>
1. <span data-ttu-id="3f932-144">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="3f932-144">Click Add line.</span></span>
2. <span data-ttu-id="3f932-145">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="3f932-145">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3f932-146">Ange artikelnumret som du använde på inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="3f932-146">Enter the item number that you used on the purchase order line.</span></span>  
3. <span data-ttu-id="3f932-147">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="3f932-147">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="3f932-148">Ange den kvantitet som du vill registrera.</span><span class="sxs-lookup"><span data-stu-id="3f932-148">Enter the quantity that you want to register.</span></span>  
    * <span data-ttu-id="3f932-149">Datumfältet bestämmer datumet då lagerbehållningen för artikeln ska registreras i lagret.</span><span class="sxs-lookup"><span data-stu-id="3f932-149">The Date field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    * <span data-ttu-id="3f932-150">Parti-id:t fylls i av systemet, om det kan identifieras av den tillhandahållna informationen.</span><span class="sxs-lookup"><span data-stu-id="3f932-150">The lot ID will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="3f932-151">Annars måste du lägga till det manuellt.</span><span class="sxs-lookup"><span data-stu-id="3f932-151">Otherwise you will have to add this manually.</span></span> <span data-ttu-id="3f932-152">Detta är ett obligatoriskt fält, som kopplar den här registreringen till en viss källdokumentrad.</span><span class="sxs-lookup"><span data-stu-id="3f932-152">This is a mandatory field, which links this registration to a specific source document line.</span></span>  

## <a name="complete-the-registration"></a><span data-ttu-id="3f932-153">Slutför registreringen</span><span class="sxs-lookup"><span data-stu-id="3f932-153">Complete the registration</span></span>
1. <span data-ttu-id="3f932-154">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="3f932-154">Click Validate.</span></span>
    * <span data-ttu-id="3f932-155">Detta kontrollerar att journalen är klar att bokföras.</span><span class="sxs-lookup"><span data-stu-id="3f932-155">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="3f932-156">Om valideringen misslyckas måste du korrigera felen innan du kan bokföra journalen.</span><span class="sxs-lookup"><span data-stu-id="3f932-156">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
2. <span data-ttu-id="3f932-157">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-157">Click OK.</span></span>
    * <span data-ttu-id="3f932-158">Kontrollera meddelandet när du har klickat på OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-158">After you clicked OK, check the message.</span></span> <span data-ttu-id="3f932-159">Det bör visas ett meddelande om att journalen är OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-159">There should be a message saying that the journal is OK.</span></span>  
3. <span data-ttu-id="3f932-160">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="3f932-160">Click Post.</span></span>
4. <span data-ttu-id="3f932-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-161">Click OK.</span></span>
    * <span data-ttu-id="3f932-162">Kontrollera meddelandefältet när du har klickat på OK.</span><span class="sxs-lookup"><span data-stu-id="3f932-162">After you have clicked OK, check the message bar.</span></span> <span data-ttu-id="3f932-163">Det bör visas ett meddelande om att åtgärden lyckades.</span><span class="sxs-lookup"><span data-stu-id="3f932-163">There should be a message saying that the operation completed.</span></span>  
5. <span data-ttu-id="3f932-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f932-164">Close the page.</span></span>


