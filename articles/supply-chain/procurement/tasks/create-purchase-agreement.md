--- 
title: "Skapa ett nytt inköpsavtal"
description: "I den här proceduren får du hjälp med att skapa ett inköpsavtal."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 84b8f08c5e72d3bae597d78cd8f1f77d59355917
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="8adb4-103">Skapa ett nytt inköpsavtal</span><span class="sxs-lookup"><span data-stu-id="8adb4-103">Create a purchase agreement</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8adb4-104">I den här proceduren får du hjälp med att skapa ett inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="8adb4-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="8adb4-105">Detta görs normalt av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="8adb4-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="8adb4-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="8adb4-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="8adb4-107">Du måste ha ställt in klassificeringar av inköpsavtal innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="8adb4-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="8adb4-108">När du har skapat ett avtal kan du använda det när du skapar en IO. Villkoren för inköpsavtalet kopieras då till huvudet och till alla rader i den ordning som påverkas av avtalet.</span><span class="sxs-lookup"><span data-stu-id="8adb4-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="8adb4-109">Skapa ett nytt inköpsavtal</span><span class="sxs-lookup"><span data-stu-id="8adb4-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="8adb4-110">Gå till Anskaffning och källa > Inköpsavtal > Inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="8adb4-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="8adb4-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8adb4-111">Click New.</span></span>
3. <span data-ttu-id="8adb4-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="8adb4-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8adb4-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8adb4-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8adb4-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Klassificering av inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="8adb4-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8adb4-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8adb4-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8adb4-118">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8adb4-118">Expand the General section.</span></span>
10. <span data-ttu-id="8adb4-119">Ange ett datum i fältet Utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="8adb4-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="8adb4-120">Det här utgångsdatumet ska vara standard för alla utfästelserader och bestämmer hur länge varje specifik utfästelse är giltig.</span><span class="sxs-lookup"><span data-stu-id="8adb4-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="8adb4-121">Ange ett namn på inköpsavtalet i fältet Dokumenttitel.</span><span class="sxs-lookup"><span data-stu-id="8adb4-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="8adb4-122">Lämna fältet Standardutfästelse angett till Utfästelse för produktkvantitet (eller ändra det om det inte är inställt på denna).</span><span class="sxs-lookup"><span data-stu-id="8adb4-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="8adb4-123">Standardutfästelsevärdet bestämmer alternativen på avtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="8adb4-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="8adb4-124">Om du behöver en ny utfästelsetyp när du skapar avtalsraderna måste du ändra standardutfästelsen i rubriken.</span><span class="sxs-lookup"><span data-stu-id="8adb4-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="8adb4-125">Det finns 4 typer av utfästelser: Produktkvantitetsutfästelse - för en viss kvantitet av en produkt; Produktvärdeutfästelse - för ett visst valutabelopp av en produkt; Värdeutfästelse för produktkategori - för ett visst valutabelopp i en anskaffningskategori där beloppet kan användas för en katalogartikel eller en artikel som inte finns i någon katalog; Värdeutfästelse - för ett visst valutabelopp som kan uppfyllas av vilken produkt som helst eller med valfri anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="8adb4-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="8adb4-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8adb4-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="8adb4-127">Lägg till en utfästelse</span><span class="sxs-lookup"><span data-stu-id="8adb4-127">Add a commitment</span></span>
1. <span data-ttu-id="8adb4-128">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="8adb4-128">Click Add line.</span></span>
2. <span data-ttu-id="8adb4-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="8adb4-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8adb4-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8adb4-131">Välj den produkt som du vill lägga till en utfästelse för.</span><span class="sxs-lookup"><span data-stu-id="8adb4-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="8adb4-132">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8adb4-133">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="8adb4-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8adb4-134">Detta är den totala kvantitet som du har avtalat att köpa från leverantören.</span><span class="sxs-lookup"><span data-stu-id="8adb4-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="8adb4-135">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="8adb4-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="8adb4-136">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="8adb4-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="8adb4-137">Ställ in alternativet Max framtvingas till Ja.</span><span class="sxs-lookup"><span data-stu-id="8adb4-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="8adb4-138">Alternativet Max framtvingas begränsar användningen av utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="8adb4-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="8adb4-139">Du kan bara köpa upp till den kvantitet som har angetts i fältet Kvantitet för raden.</span><span class="sxs-lookup"><span data-stu-id="8adb4-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="8adb4-140">Komprimera avsnittet Raddetalj.</span><span class="sxs-lookup"><span data-stu-id="8adb4-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="8adb4-141">Lägg till huvudvillkor</span><span class="sxs-lookup"><span data-stu-id="8adb4-141">Add header conditions</span></span>
1. <span data-ttu-id="8adb4-142">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8adb4-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="8adb4-143">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="8adb4-143">Click Change view.</span></span>
3. <span data-ttu-id="8adb4-144">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="8adb4-144">Click Header view.</span></span>
4. <span data-ttu-id="8adb4-145">Expandera villkorsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="8adb4-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="8adb4-146">I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="8adb4-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8adb4-147">Betalningsvillkoren från leverantörskontot visas här som standard.</span><span class="sxs-lookup"><span data-stu-id="8adb4-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="8adb4-148">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8adb4-149">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8adb4-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="8adb4-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="8adb4-151">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="8adb4-152">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leveransvillkor.</span><span class="sxs-lookup"><span data-stu-id="8adb4-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8adb4-153">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="8adb4-154">Bekräfta och aktivera avtalet</span><span class="sxs-lookup"><span data-stu-id="8adb4-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="8adb4-155">Klicka på Inköpsavtal i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8adb4-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="8adb4-156">Klicka på Bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="8adb4-156">Click Confirmation.</span></span>
    * <span data-ttu-id="8adb4-157">Ange alternativet Markera avtal som giltigt till Ja.</span><span class="sxs-lookup"><span data-stu-id="8adb4-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="8adb4-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8adb4-158">Click OK.</span></span>
4. <span data-ttu-id="8adb4-159">Klicka på Inköpsavtal i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8adb4-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="8adb4-160">Klicka på Bekräftelser av inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="8adb4-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="8adb4-161">Med alternativet Förhandsgranska/Skriv ut kan du generera ett dokument för inköpsavtalet som du sedan kan skriva ut eller skicka till leverantören.</span><span class="sxs-lookup"><span data-stu-id="8adb4-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="8adb4-162">Om du uppdaterar avtalet senare och bekräftar det på nytt visas båda versionerna här.</span><span class="sxs-lookup"><span data-stu-id="8adb4-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="8adb4-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8adb4-163">Close the page.</span></span>


