--- 
title: " Definiera förmånsscheman"
description: "Den här proceduren går igenom hur du definierar ett bonusprogram."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 23c8876b1983d6bc20b68f24fa7cd5b042cfd488
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="define-loyalty-schemes"></a><span data-ttu-id="5aa18-103"> Definiera förmånsscheman</span><span class="sxs-lookup"><span data-stu-id="5aa18-103">Define loyalty schemes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5aa18-104">Den här proceduren går igenom hur du definierar ett bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="5aa18-104">This procedure walks through how to define a loyalty scheme.</span></span> <span data-ttu-id="5aa18-105">Bonusplaner är regler för intjänande och inlösen av belöningar i ett bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="5aa18-105">Loyalty schemes are reward earning and redeeming rules for a loyalty program.</span></span> <span data-ttu-id="5aa18-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="5aa18-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="5aa18-107">Gå till butik och handel > kunder > lojalitet > lojalitetssystem.</span><span class="sxs-lookup"><span data-stu-id="5aa18-107">Go to Retail and commerce > Customers > Loyalty > Loyalty schemes.</span></span>
2. <span data-ttu-id="5aa18-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5aa18-108">Click New.</span></span>
3. <span data-ttu-id="5aa18-109">Skriv ett värde i fältet Program-ID.</span><span class="sxs-lookup"><span data-stu-id="5aa18-109">In the Scheme ID field, type a value.</span></span>
4. <span data-ttu-id="5aa18-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5aa18-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5aa18-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5aa18-111">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5aa18-112">Du kan ha flera lojalitetssystem för ett lojalitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="5aa18-112">You can have multiple loyalty schemes for a loyalty program.</span></span> <span data-ttu-id="5aa18-113">Bonusplaner kan gälla för alla kanaler eller endast en underuppsättning kanaler.</span><span class="sxs-lookup"><span data-stu-id="5aa18-113">Loyalty schemes can be for all channels or only a sub-set of channels.</span></span>  
6. <span data-ttu-id="5aa18-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5aa18-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5aa18-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5aa18-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5aa18-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5aa18-116">Click Save.</span></span>
9. <span data-ttu-id="5aa18-117">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="5aa18-117">Click Add line.</span></span>
10. <span data-ttu-id="5aa18-118">Välj ett alternativ i fältet Aktivitetstyp.</span><span class="sxs-lookup"><span data-stu-id="5aa18-118">In the Activity type field, select an option.</span></span>
    * <span data-ttu-id="5aa18-119">Välj Köp produkter efter belopp om du vill ge kunderna belöningar som baseras på hur mycket de spenderar.</span><span class="sxs-lookup"><span data-stu-id="5aa18-119">Select Purchase products by amount if you want customers to earn rewards based on how much they spend.</span></span> <span data-ttu-id="5aa18-120">Välj köpa produkter av kvantitet om du vill kunderna att få belöningar baseras på hur många produkter de köper.</span><span class="sxs-lookup"><span data-stu-id="5aa18-120">Select Purchase products by quantity if you want customers to earn rewards based on how many products they buy.</span></span>  <span data-ttu-id="5aa18-121">Välj Antal försäljningstransaktioner om kunden ska få belöningar för varje försäljningstransaktion, oavsett vad som köps eller hur mycket.</span><span class="sxs-lookup"><span data-stu-id="5aa18-121">Select Sales transaction count if you want customers to earn rewards for each sales transaction, regardless of what or how much is purchased.</span></span>  
    * <span data-ttu-id="5aa18-122">Markera en kategori.</span><span class="sxs-lookup"><span data-stu-id="5aa18-122">Select a category.</span></span> <span data-ttu-id="5aa18-123">Kategorin avgränsar vilka produkter den här förtjänstregeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="5aa18-123">The category will limit which products this earning rule applies to.</span></span>  
    * <span data-ttu-id="5aa18-124">Lämna fältet tomt om du vill att intäktsregeln ska gälla för alla produkter.</span><span class="sxs-lookup"><span data-stu-id="5aa18-124">If you want the earning rule to apply to all products, leave this field blank.</span></span>  
11. <span data-ttu-id="5aa18-125">I fältet Aktivitetens belopp/kvantitet, ange ett nummer.</span><span class="sxs-lookup"><span data-stu-id="5aa18-125">In the Activity amount/quantity field, enter a number.</span></span>
    *  <span data-ttu-id="5aa18-126">För aktivitetstyp försäljningstransaktion räknar, bör du alltid använda ett värde på '1.0'.</span><span class="sxs-lookup"><span data-stu-id="5aa18-126">For activity type Sales transaction count, you should always use a value of '1.0'.</span></span> <span data-ttu-id="5aa18-127">För aktivitet typer av inköp av beloppet eller köp av kvantitet, varje transaktion som är mindre än det angivna värdet utlöser inte tjäna regeln.</span><span class="sxs-lookup"><span data-stu-id="5aa18-127">For activity types of Purchase by amount or Purchase by quantity, any transaction that is less than the value entered will not trigger the earning rule.</span></span> <span data-ttu-id="5aa18-128">Om till exempel aktivitetstypen är Köp efter belopp och du anger 10,00 ger en försäljningstransaktion på 9,00 ingen intjänad belöning för den här förtjänstregeln.</span><span class="sxs-lookup"><span data-stu-id="5aa18-128">For example, if the activity type is Purchase by amount, and you enter '10.00', then a sales transaction for '9.00' will not earn rewards for this earning rule.</span></span>  
12. <span data-ttu-id="5aa18-129">Ange ett värde i fältet Aktivitetsvaluta.</span><span class="sxs-lookup"><span data-stu-id="5aa18-129">In the Activity currency field, type a value.</span></span>
13. <span data-ttu-id="5aa18-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng-ID.</span><span class="sxs-lookup"><span data-stu-id="5aa18-130">In the Reward point ID field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="5aa18-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5aa18-131">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="5aa18-132">Välj ett nummer i fältet Belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="5aa18-132">In the Reward points field, enter a number.</span></span>
    * <span data-ttu-id="5aa18-133">Belöningspoängen för beloppstypen lagrar intjänade belopp med decimaler.</span><span class="sxs-lookup"><span data-stu-id="5aa18-133">Amount type reward points will record earned amounts with decimals.</span></span> <span data-ttu-id="5aa18-134">Om till exempel intjäningsregeln anger att medlemmen får en belöningspoäng för varje kanadensisk dollar som spenderas och medlemmen spenderar 1,25 kanadensiska dollar får hon eller han 1,25 belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="5aa18-134">For example, if the earning rule states 1 reward point earned for every 1 Canadian Dollar spent, and the customer spends 1.25 Canadian Canadian Dollars, then the customer will earn 1.25 reward points.</span></span> <span data-ttu-id="5aa18-135">Kvantitetstyp extrapoäng kommer posten intjänat belopp i heltal.</span><span class="sxs-lookup"><span data-stu-id="5aa18-135">Quantity type reward points will record earned amounts in integers.</span></span> <span data-ttu-id="5aa18-136">Om till exempel intjäningsregeln anger att medlemmen får en belöningspoäng för varje kanadensisk dollar som spenderas och medlemmen spenderar 1,25 kanadensiska dollar får hon eller han 1,0 belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="5aa18-136">Using the example where the earning rule states 1 reward point earned for every 1 Canadian Dollar spent, and the customer spends 1.25 Canadian Canadian Dollars, then the customer will earn 1.0 reward points.</span></span>  
16. <span data-ttu-id="5aa18-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5aa18-137">Click Save.</span></span>
17. <span data-ttu-id="5aa18-138">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="5aa18-138">Click Add line.</span></span>
    * <span data-ttu-id="5aa18-139">Regler för inlösen används när lojalitetbetalningsmetoden används.</span><span class="sxs-lookup"><span data-stu-id="5aa18-139">Redemption rules are used when the loyalty payment method is used.</span></span>  
18. <span data-ttu-id="5aa18-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng-ID.</span><span class="sxs-lookup"><span data-stu-id="5aa18-140">In the Reward point ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5aa18-141">Endast inlösbara belöningspoäng visas.</span><span class="sxs-lookup"><span data-stu-id="5aa18-141">Only redeemable reward points are shown.</span></span>  
19. <span data-ttu-id="5aa18-142">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5aa18-142">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="5aa18-143">Välj ett nummer i fältet Belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="5aa18-143">In the Reward points field, enter a number.</span></span>
21. <span data-ttu-id="5aa18-144">Välj ett alternativ i fältet Inlösningstyp.</span><span class="sxs-lookup"><span data-stu-id="5aa18-144">In the Redemption type field, select an option.</span></span>
    * <span data-ttu-id="5aa18-145">Om du väljer Betalning efter belopp gör detta att fältet Belopp eller Kvantitet behandlas som ett valutavärde.</span><span class="sxs-lookup"><span data-stu-id="5aa18-145">Selecting Payment by amount causes the Amount or quantity field to be treated as a currency value.</span></span> <span data-ttu-id="5aa18-146">I detta fall skall beloppet av extrapoäng per valuta betalningsmedel är ett fast förhållande.</span><span class="sxs-lookup"><span data-stu-id="5aa18-146">In this case, the amount of reward points used per currency unit of payment is a fixed ratio.</span></span> <span data-ttu-id="5aa18-147">För att välja betalning av kvantiteten orsakar beloppet eller kvantitet som ska behandlas som en kvantitet.</span><span class="sxs-lookup"><span data-stu-id="5aa18-147">Selecting Payment by quantity causes the Amount or quantity field to be treated as a quantity value.</span></span> <span data-ttu-id="5aa18-148">I detta fall skall beloppet av extrapoäng per kvantitet är ett fast förhållande, men beloppet i valutan kan variera om priset på poster betalas med lojalitet extrapoäng varierar för samma kvantitet.</span><span class="sxs-lookup"><span data-stu-id="5aa18-148">In this case, the amount of reward points used per item quantity is a fixed ratio, however, the amount in currency can vary if the price of items paid for with loyalty reward points varies for the same quantity.</span></span> <span data-ttu-id="5aa18-149">Inlösentypen för lojalitetspoängrabatt är endast giltig när konfigurationsnyckeln för Ryssland – lands-/regionsspecifika funktioner – är aktiverad och kassafunktionsprofilerna har ISO-koden RU.</span><span class="sxs-lookup"><span data-stu-id="5aa18-149">Redemption type of Loyalty points discount is only valid when the 'Russia' Country/Regional specific features configuration key is enabled, and the POS functionality profiles has an ISO code of 'RU'.</span></span>  
    * <span data-ttu-id="5aa18-150">Markera en kategori.</span><span class="sxs-lookup"><span data-stu-id="5aa18-150">Select a category.</span></span> <span data-ttu-id="5aa18-151">Kategorin avgränsar vilka produkter den här inlösenregeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="5aa18-151">The category will limit which products this redemption rule applies to.</span></span>  
    * <span data-ttu-id="5aa18-152">Lämna fältet tomt om du vill att inlösenregeln ska gälla för alla produkter.</span><span class="sxs-lookup"><span data-stu-id="5aa18-152">If you want the redemption rule to apply to all products, leave this field blank.</span></span>  
22. <span data-ttu-id="5aa18-153">I fältet Belopp eller kvantitet, ange ett nummer.</span><span class="sxs-lookup"><span data-stu-id="5aa18-153">In the Amount or quantity field, enter a number.</span></span>
23. <span data-ttu-id="5aa18-154">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="5aa18-154">In the Currency field, type a value.</span></span>
24. <span data-ttu-id="5aa18-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5aa18-155">Click Save.</span></span>
25. <span data-ttu-id="5aa18-156">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="5aa18-156">Click Add line.</span></span>
    * <span data-ttu-id="5aa18-157">Markera en eller flera noder i listan Tillgängliga organisationsnoder och flytta dem till listan Valda organisationsnoder genom att klicka på pilen mellan de två listorna.</span><span class="sxs-lookup"><span data-stu-id="5aa18-157">Select one or more nodes from the Available organization nodes list and move them to the Selected organization nodes list by clicking the arrow between the two lists.</span></span>  
26. <span data-ttu-id="5aa18-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5aa18-158">Click OK.</span></span>
27. <span data-ttu-id="5aa18-159">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5aa18-159">Click Save.</span></span>
    * <span data-ttu-id="5aa18-160">Så snart du ändrar kanalerna för ett bonusprogram måste du köra Bearbeta förmånsscheman.</span><span class="sxs-lookup"><span data-stu-id="5aa18-160">Anytime you change the channels for a loyalty scheme, you must run Process loyalty schemes.</span></span> <span data-ttu-id="5aa18-161">Det kanaler uppdateras lojalitetssystem.</span><span class="sxs-lookup"><span data-stu-id="5aa18-161">That way, the channels will get updated loyalty schemes.</span></span>  

