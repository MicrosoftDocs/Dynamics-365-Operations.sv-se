---
title: Skapa ett nytt inköpsavtal
description: I den här avsnittet får du hjälp med att skapa ett inköpsavtal.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437611"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="e8a01-103">Skapa ett nytt inköpsavtal</span><span class="sxs-lookup"><span data-stu-id="e8a01-103">Create a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8a01-104">I den här avsnittet får du hjälp med att skapa ett inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="e8a01-104">This topic guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="e8a01-105">Detta görs normalt av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="e8a01-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="e8a01-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="e8a01-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e8a01-107">Du måste ha ställt in klassificeringar av inköpsavtal innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="e8a01-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="e8a01-108">När du har skapat ett avtal kan du använda det när du skapar en IO. Villkoren för inköpsavtalet kopieras då till huvudet och till alla rader i den ordning som påverkas av avtalet.</span><span class="sxs-lookup"><span data-stu-id="e8a01-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="e8a01-109">Skapa ett nytt inköpsavtal</span><span class="sxs-lookup"><span data-stu-id="e8a01-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="e8a01-110">Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsavtal > Inköpsavtal**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-110">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase agreements > Purchase agreements**.</span></span>
2. <span data-ttu-id="e8a01-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-111">Click **New**.</span></span>
3. <span data-ttu-id="e8a01-112">I fältet **Leverantörskonto** väljer du den nedrullningsbara menyn och välj raden för önskad post.</span><span class="sxs-lookup"><span data-stu-id="e8a01-112">In the **Vendor account** field, select the drop-down menu and select the row of the desired record.</span></span>
4. <span data-ttu-id="e8a01-113">I fältet **Klassificering av inköpsavtal** väljer du den nedrullningsbara menyn och välj raden för önskad post.</span><span class="sxs-lookup"><span data-stu-id="e8a01-113">In the **Purchase agreement classification** field, select the drop-down menu and select the row of the desired record.</span></span>
5. <span data-ttu-id="e8a01-114">Expandera **Allmänt** snabbflik.</span><span class="sxs-lookup"><span data-stu-id="e8a01-114">Expand the **General** FastTab.</span></span>
6. <span data-ttu-id="e8a01-115">Ange ett datum i fältet **Utgångsdatum**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-115">In the **Expiration date** field, enter a date.</span></span>

    - <span data-ttu-id="e8a01-116">Det här utgångsdatumet ska vara standard för alla utfästelserader och bestämmer hur länge varje specifik utfästelse är giltig.</span><span class="sxs-lookup"><span data-stu-id="e8a01-116">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  

7. <span data-ttu-id="e8a01-117">Ange ett namn på inköpsavtalet i fältet **Dokumenttitel**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-117">In the **Document title** field, type a name for your purchase agreement.</span></span>

    - <span data-ttu-id="e8a01-118">Lämna fältet **Standardutfästelse** angett till **Utfästelse för produktkvantitet** (eller ändra det om det inte är inställt på denna).</span><span class="sxs-lookup"><span data-stu-id="e8a01-118">Leave the **Default commitment** field set to **Product quantity commitment** (or change it if it's not set to this).</span></span>  
    - <span data-ttu-id="e8a01-119">Standardutfästelsevärdet bestämmer alternativen på avtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="e8a01-119">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="e8a01-120">Om du behöver en ny utfästelsetyp när du skapar avtalsraderna måste du ändra standardutfästelsen i rubriken.</span><span class="sxs-lookup"><span data-stu-id="e8a01-120">If you need a new commitment type when you're creating the agreement lines, you need to change the default commitment on the header.</span></span> <span data-ttu-id="e8a01-121">Det finns fyra typer av utfästelser: **Produktkvantitetsutfästelse** - för en viss kvantitet av en produkt; **Produktvärdeutfästelse** - för ett visst valutabelopp av en produkt; **Värdeutfästelse för produktkategori** - för ett visst valutabelopp i en anskaffningskategori där beloppet kan användas för en katalogartikel eller en artikel som inte finns i någon katalog; **Värdeutfästelse** - för ett visst valutabelopp som kan uppfyllas av vilken produkt som helst eller med valfri anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="e8a01-121">There are 4 types of commitments: **Product quantity commitment** - for a specific quantity of a product; **Product value commitment** - for a specific currency amount of a product; **Product category value commitment** - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; **Value commitment** - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  

8. <span data-ttu-id="e8a01-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-122">Select **OK**.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="e8a01-123">Lägg till en utfästelse</span><span class="sxs-lookup"><span data-stu-id="e8a01-123">Add a commitment</span></span>
1. <span data-ttu-id="e8a01-124">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-124">Select **Add line**.</span></span>
2. <span data-ttu-id="e8a01-125">I fältet **Artikelnummer** välj önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="e8a01-125">In the **Item number** field, select the desired record from the drop-down menu.</span></span>
3. <span data-ttu-id="e8a01-126">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-126">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="e8a01-127">Detta är den totala kvantitet som du har avtalat att köpa från leverantören.</span><span class="sxs-lookup"><span data-stu-id="e8a01-127">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
4. <span data-ttu-id="e8a01-128">Ange ett tal i fältet **Enhetspris**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-128">In the **Unit price** field, enter a number.</span></span>
5. <span data-ttu-id="e8a01-129">Visa avsnittet **Raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-129">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="e8a01-130">Ställ in alternativet **Max framtvingas** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-130">Set the **Max is enforced** option to **Yes**.</span></span> <span data-ttu-id="e8a01-131">Alternativet **Max framtvingas** begränsar användningen av utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="e8a01-131">The **Max is enforced** option limits the use of the commitment.</span></span> <span data-ttu-id="e8a01-132">Du kan bara köpa upp till den kvantitet som har angetts i fältet **Kvantitet** för raden.</span><span class="sxs-lookup"><span data-stu-id="e8a01-132">You can only purchase up to the quantity that's specified in the **Quantity** field for the line.</span></span>  

## <a name="add-header-conditions"></a><span data-ttu-id="e8a01-133">Lägg till huvudvillkor</span><span class="sxs-lookup"><span data-stu-id="e8a01-133">Add header conditions</span></span>
1. <span data-ttu-id="e8a01-134">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e8a01-134">On the Action Pane, select **Options**.</span></span>
2. <span data-ttu-id="e8a01-135">Välj **Byt visning**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-135">Select **Change view**.</span></span>
3. <span data-ttu-id="e8a01-136">Välj **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-136">Select **Header view**.</span></span>
4. <span data-ttu-id="e8a01-137">Expandera avsnittet **Villkor**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-137">Expand the **Terms** section.</span></span>
5. <span data-ttu-id="e8a01-138">I fältet **Betalningsmetod** väljer du önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="e8a01-138">In the **Method of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="e8a01-139">Betalningsvillkoren från leverantörskontot visas här som standard.</span><span class="sxs-lookup"><span data-stu-id="e8a01-139">The payment terms from the vendor account are shown here by default.</span></span>  
6. <span data-ttu-id="e8a01-140">I fältet **Leveranssätt** väljer du önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="e8a01-140">In the **Mode of delivery** field, select the desired record in the drop-down menu.</span></span>
7. <span data-ttu-id="e8a01-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leveransvillkor**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-141">In the **Delivery terms** field, select the drop-down button to open the lookup.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="e8a01-142">Bekräfta och aktivera avtalet</span><span class="sxs-lookup"><span data-stu-id="e8a01-142">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="e8a01-143">Klicka på **Inköpsavtal** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e8a01-143">On the Action Pane, select **Purchase agreement**.</span></span>
2. <span data-ttu-id="e8a01-144">VäljSelect **Bekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-144">Select **Confirmation**.</span></span> <span data-ttu-id="e8a01-145">Ange alternativet **Markera avtal som giltigt** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-145">Set the **Mark agreement as effective** option to **Yes**.</span></span>  
3. <span data-ttu-id="e8a01-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-146">Select **OK**.</span></span>
4. <span data-ttu-id="e8a01-147">Klicka på **Inköpsavtal** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e8a01-147">On the Action Pane, select **Purchase agreement**.</span></span>
5. <span data-ttu-id="e8a01-148">Välj **Bekräftelser av inköpsavtal**.</span><span class="sxs-lookup"><span data-stu-id="e8a01-148">Select **Purchase agreement confirmations**.</span></span> <span data-ttu-id="e8a01-149">Med alternativet **Förhandsgranska/Skriv ut** kan du generera ett dokument för inköpsavtalet som du sedan kan skriva ut eller skicka till leverantören.</span><span class="sxs-lookup"><span data-stu-id="e8a01-149">The **Preview/Print** option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="e8a01-150">Om du uppdaterar avtalet senare och bekräftar det på nytt visas båda versionerna här.</span><span class="sxs-lookup"><span data-stu-id="e8a01-150">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="e8a01-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e8a01-151">Close the page.</span></span>

