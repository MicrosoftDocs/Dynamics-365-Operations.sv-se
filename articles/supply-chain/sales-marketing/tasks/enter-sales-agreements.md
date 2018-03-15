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
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a0d49068d2c6a62bf7912c2fd7cccd53308bd196
ms.contentlocale: sv-se
ms.lasthandoff: 02/13/2018

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="2964d-103">Ange försäljningsavtal</span><span class="sxs-lookup"><span data-stu-id="2964d-103">Enter sales agreements</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2964d-104">I den här proceduren visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter.</span><span class="sxs-lookup"><span data-stu-id="2964d-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="2964d-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="2964d-105">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="2964d-106">Ställ in försäljningsavtalshuvudet</span><span class="sxs-lookup"><span data-stu-id="2964d-106">Set up sales agreement header</span></span>
1. <span data-ttu-id="2964d-107">Gå till försäljning och marknadsföring > Försäljning avtal > försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="2964d-107">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="2964d-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2964d-108">Click New.</span></span>
3. <span data-ttu-id="2964d-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="2964d-109">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2964d-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2964d-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2964d-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2964d-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2964d-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Klassificering av försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="2964d-112">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2964d-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2964d-113">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2964d-114">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="2964d-114">Expand the General section.</span></span>
9. <span data-ttu-id="2964d-115">I fältet Standardutfästelse, välj Utfästelse för produktvärde.</span><span class="sxs-lookup"><span data-stu-id="2964d-115">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="2964d-116">En utfästelsetyp är ett obligatoriskt kriterium som du måste tilldela till avtalet för att definiera hur avtalskontraktet uppfylls.</span><span class="sxs-lookup"><span data-stu-id="2964d-116">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="2964d-117">De fyra fördefinierade typer kan du ställa in kundens åtagande mål, uttryckt som en kvantitet eller ett värde.</span><span class="sxs-lookup"><span data-stu-id="2964d-117">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="2964d-118">Kvantitetutfästelsetypen kan endast tillämpas på en specifik produkt, men de hierarkibaserade typerna kan användas för både försäljning och icke-specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="2964d-118">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="2964d-119">I fältet Utgångsdatum, ange datumet till ett framtida datum när du vill att avtalet ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="2964d-119">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="2964d-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2964d-120">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="2964d-121">Ställ in utfästelserader för produktvärde</span><span class="sxs-lookup"><span data-stu-id="2964d-121">Set up product value commitment lines</span></span>
1. <span data-ttu-id="2964d-122">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="2964d-122">Click Add line.</span></span>
2. <span data-ttu-id="2964d-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2964d-123">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2964d-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2964d-124">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2964d-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2964d-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2964d-126">Typen av åtagande som du har valt för avtalet påverkar den typ av information som du kan ange för avtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="2964d-126">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="2964d-127">För exempelvis en värde-baserade avtal måste du ange det totala nettobeloppet (i den överenskomna valuta) för vilken kunden förbinder sig att köpa varor från dig.</span><span class="sxs-lookup"><span data-stu-id="2964d-127">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="2964d-128">I det här exemplet är fälten Kvantitet och Enhet på raden inte tillgängliga eftersom du skapar ett avtal för att kunden om att köpa för ett visst värde av en produkt.</span><span class="sxs-lookup"><span data-stu-id="2964d-128">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="2964d-129">I fältet Nettobelopp, ange penningbeloppet som kunden har åtagit sig att köpa för.</span><span class="sxs-lookup"><span data-stu-id="2964d-129">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="2964d-130">I fältet Rabatt i procent, ange en procentsats som ska användas för kundens försäljningsorderrader, som är kopplade till detta avtal.</span><span class="sxs-lookup"><span data-stu-id="2964d-130">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="2964d-131">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="2964d-131">Expand the Line details section.</span></span>
8. <span data-ttu-id="2964d-132">Välj Ja i fältet Max framtvingas.</span><span class="sxs-lookup"><span data-stu-id="2964d-132">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="2964d-133">Om du väljer Max framtvingas innebär att det totala beloppet för alla försäljningsorderrader som använder utfästelsens särskilda priser, rabatter och/eller betalningsvillkor inte får överstiga beloppet som anges på utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="2964d-133">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="2964d-134">Minsta och högsta frisläppningsbeloppen anger ett värdeintervall som måste säljas på varje försäljningsorder som använder det valda avtalet.</span><span class="sxs-lookup"><span data-stu-id="2964d-134">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="2964d-135">Expandera huvudavsnittet Försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="2964d-135">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="2964d-136">Om inte avtalets status anges till Giltighet kan försäljningsorder inte kopplas till avtalet och kan därför inte bidra till uppfyllandet av avtalet.</span><span class="sxs-lookup"><span data-stu-id="2964d-136">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="2964d-137">Du kan ändra status manuellt i detta skede.</span><span class="sxs-lookup"><span data-stu-id="2964d-137">You can change the status manually at this stage.</span></span> <span data-ttu-id="2964d-138">Emellertid ändras statusen normalt när du bekräftar avtalet för kunden.</span><span class="sxs-lookup"><span data-stu-id="2964d-138">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="2964d-139">Klicka på Försäljningsavtal i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2964d-139">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="2964d-140">Klicka på Bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="2964d-140">Click Confirmation.</span></span>
    * <span data-ttu-id="2964d-141">Kontrollera att Ja är valt för alternativet Markera avtal som giltigt.</span><span class="sxs-lookup"><span data-stu-id="2964d-141">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="2964d-142">Välj Ja i fältet Skriv ut rapport.</span><span class="sxs-lookup"><span data-stu-id="2964d-142">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="2964d-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2964d-143">Click OK.</span></span>
14. <span data-ttu-id="2964d-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2964d-144">Close the page.</span></span>
    * <span data-ttu-id="2964d-145">Avtalet är nu effektivt och du kan börja att länka kundens order till avtalet för att motboka mot det utfästa målet.</span><span class="sxs-lookup"><span data-stu-id="2964d-145">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


