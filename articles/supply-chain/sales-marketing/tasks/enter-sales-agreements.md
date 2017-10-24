--- 
title: "Ange försäljningsavtal"
description: "I den här proceduren visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8c11164f7edb8e05b93f3c58b9707c0bf2482228
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="92ec2-103">Ange försäljningsavtal</span><span class="sxs-lookup"><span data-stu-id="92ec2-103">Enter sales agreements</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92ec2-104">I den här proceduren beskrivs hur du skapar ett försäljningsavtal som ålägger en av dina kunder att köpa en produkt för ett</span><span class="sxs-lookup"><span data-stu-id="92ec2-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="92ec2-105">överenskommet belopp över tiden i utbyte mot eventuella rabatter som avtalats.</span><span class="sxs-lookup"><span data-stu-id="92ec2-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="92ec2-106">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="92ec2-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="92ec2-107">Ställ in försäljningsavtalshuvudet</span><span class="sxs-lookup"><span data-stu-id="92ec2-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="92ec2-108">Gå till försäljning och marknadsföring > Försäljning avtal > försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="92ec2-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="92ec2-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="92ec2-109">Click New.</span></span>
3. <span data-ttu-id="92ec2-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="92ec2-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="92ec2-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="92ec2-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="92ec2-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Klassificering av försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="92ec2-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="92ec2-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="92ec2-115">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="92ec2-115">Expand the General section.</span></span>
9. <span data-ttu-id="92ec2-116">I fältet Standardutfästelse, välj Utfästelse för produktvärde.</span><span class="sxs-lookup"><span data-stu-id="92ec2-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="92ec2-117">En utfästelsetyp är ett obligatoriskt kriterium som du måste tilldela till avtalet för att definiera hur avtalskontraktet uppfylls.</span><span class="sxs-lookup"><span data-stu-id="92ec2-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="92ec2-118">De fyra fördefinierade typer kan du ställa in kundens åtagande mål, uttryckt som en kvantitet eller ett värde.</span><span class="sxs-lookup"><span data-stu-id="92ec2-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="92ec2-119">Kvantitetutfästelsetypen kan endast tillämpas på en specifik produkt, men de hierarkibaserade typerna kan användas för både försäljning och icke-specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="92ec2-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="92ec2-120">I fältet Utgångsdatum, ange datumet till ett framtida datum när du vill att avtalet ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="92ec2-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="92ec2-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="92ec2-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="92ec2-122">Ställ in utfästelserader för produktvärde</span><span class="sxs-lookup"><span data-stu-id="92ec2-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="92ec2-123">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="92ec2-123">Click Add line.</span></span>
2. <span data-ttu-id="92ec2-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="92ec2-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="92ec2-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="92ec2-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="92ec2-127">Typen av åtagande som du har valt för avtalet påverkar den typ av information som du kan ange för avtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="92ec2-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="92ec2-128">För exempelvis en värde-baserade avtal måste du ange det totala nettobeloppet (i den överenskomna valuta) för vilken kunden förbinder sig att köpa varor från dig.</span><span class="sxs-lookup"><span data-stu-id="92ec2-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="92ec2-129">I det här exemplet är fälten Kvantitet och Enhet på raden inte tillgängliga eftersom du skapar ett avtal för att kunden om att köpa för ett visst värde av en produkt.</span><span class="sxs-lookup"><span data-stu-id="92ec2-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="92ec2-130">I fältet Nettobelopp, ange penningbeloppet som kunden har åtagit sig att köpa för.</span><span class="sxs-lookup"><span data-stu-id="92ec2-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="92ec2-131">I fältet Rabatt i procent, ange en procentsats som ska användas för kundens försäljningsorderrader, som är kopplade till detta avtal.</span><span class="sxs-lookup"><span data-stu-id="92ec2-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="92ec2-132">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="92ec2-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="92ec2-133">Välj Ja i fältet Max framtvingas.</span><span class="sxs-lookup"><span data-stu-id="92ec2-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="92ec2-134">Om du väljer Max framtvingas innebär att det totala beloppet för alla försäljningsorderrader som använder utfästelsens särskilda priser, rabatter och/eller betalningsvillkor inte får överstiga beloppet som anges på utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="92ec2-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="92ec2-135">Minsta och högsta frisläppningsbeloppen anger ett värdeintervall som måste säljas på varje försäljningsorder som använder det valda avtalet.</span><span class="sxs-lookup"><span data-stu-id="92ec2-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="92ec2-136">Expandera huvudavsnittet Försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="92ec2-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="92ec2-137">Om inte avtalets status anges till Giltighet kan försäljningsorder inte kopplas till avtalet och kan därför inte bidra till uppfyllandet av avtalet.</span><span class="sxs-lookup"><span data-stu-id="92ec2-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="92ec2-138">Du kan ändra status manuellt i detta skede.</span><span class="sxs-lookup"><span data-stu-id="92ec2-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="92ec2-139">Emellertid ändras statusen normalt när du bekräftar avtalet för kunden.</span><span class="sxs-lookup"><span data-stu-id="92ec2-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="92ec2-140">Klicka på Försäljningsavtal i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="92ec2-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="92ec2-141">Klicka på Bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="92ec2-141">Click Confirmation.</span></span>
    * <span data-ttu-id="92ec2-142">Kontrollera att Ja är valt för alternativet Markera avtal som giltigt.</span><span class="sxs-lookup"><span data-stu-id="92ec2-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="92ec2-143">Välj Ja i fältet Skriv ut rapport.</span><span class="sxs-lookup"><span data-stu-id="92ec2-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="92ec2-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="92ec2-144">Click OK.</span></span>
14. <span data-ttu-id="92ec2-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="92ec2-145">Close the page.</span></span>
    * <span data-ttu-id="92ec2-146">Avtalet är nu effektivt och du kan börja att länka kundens order till avtalet för att motboka mot det utfästa målet.</span><span class="sxs-lookup"><span data-stu-id="92ec2-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


