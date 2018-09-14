--- 
title: Skapa in en kravbrevsserie
description: "Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens."
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: db5264f6d8d7723ff01d13e99728c2bfebcb4515
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="61367-103">Skapa in en kravbrevsserie</span><span class="sxs-lookup"><span data-stu-id="61367-103">Create a collection letter sequence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61367-104">Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens.</span><span class="sxs-lookup"><span data-stu-id="61367-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="61367-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="61367-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="61367-106">Gå till Kredit och inkasso > Inställningar > Ställ in kravbrevsserier.</span><span class="sxs-lookup"><span data-stu-id="61367-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="61367-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="61367-107">Click New.</span></span>
3. <span data-ttu-id="61367-108">Ange sekvens-ID för att representera sekvensen i fältet Kravbrevsserie.</span><span class="sxs-lookup"><span data-stu-id="61367-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="61367-109">Detta kan användas, när du ställer in en bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="61367-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="61367-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="61367-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="61367-111">Betalningsvillkoren är valfri.</span><span class="sxs-lookup"><span data-stu-id="61367-111">The terms of payment is optional.</span></span> <span data-ttu-id="61367-112">Om du anger ett värde här, ska kravbrevsavgift fakturan använda dessa betalningsvillkor istället för de betalningsvillkor som lagras med kunden.</span><span class="sxs-lookup"><span data-stu-id="61367-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="61367-113">Välj kod för det första kravbrevet som du vill skicka i kravbrevskodfältet.</span><span class="sxs-lookup"><span data-stu-id="61367-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="61367-114">Det första kravbrevet skapas med hjälp av förfallodatumet på fakturan, det värde som du anger för respitperioden i fältet och den information som du anger på denna rad.</span><span class="sxs-lookup"><span data-stu-id="61367-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="61367-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="61367-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="61367-116">Valutan för avgiften anpassas till kundens valuta.</span><span class="sxs-lookup"><span data-stu-id="61367-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="61367-117">Denna valutakod kan skilja sig från fakturavalutan.</span><span class="sxs-lookup"><span data-stu-id="61367-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="61367-118">Klicka på Lägg till om du vill lägga till nästa kravbrev som ska skickas i sekvensen</span><span class="sxs-lookup"><span data-stu-id="61367-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="61367-119">I många fall är det första kravbrevet bara en varning.</span><span class="sxs-lookup"><span data-stu-id="61367-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="61367-120">Du kan lägga till tillägg, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="61367-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="61367-121">Välj kod för nästa kravbrev som du vill skicka i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="61367-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="61367-122">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="61367-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="61367-123">Välj intäktskontot som ska användas för tillägg i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="61367-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="61367-124">Ange den avgift som debiteras kravbrev, när den bokförs.</span><span class="sxs-lookup"><span data-stu-id="61367-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="61367-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="61367-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="61367-126">Ange en artikelmomsgrupp, om moms måste beräknas på avgiften.</span><span class="sxs-lookup"><span data-stu-id="61367-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="61367-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61367-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="61367-128">Ange det minsta förfallna saldobeloppet som krävs innan ett kravbrev skickas.</span><span class="sxs-lookup"><span data-stu-id="61367-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="61367-129">Ange antalet respitdagar som tillåts.</span><span class="sxs-lookup"><span data-stu-id="61367-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="61367-130">Detta är antal dagar efter förfallodatumet att ett kravbrev kan genereras.</span><span class="sxs-lookup"><span data-stu-id="61367-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="61367-131">Förfallodatumet som används för beräkning beror på positionen för kravbrevet i kravbrevserien: ⦁ Respitperioden för kravbrev 1 är relaterat till förfallodatumet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="61367-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="61367-132">⦁ Respitperioden för kravbrev 2 och högre är relaterade till det datum då det föregående kravbrevet bokfördes eller skrevs ut, beroende på vad som valts i fältet Uppdatera kravbrevskod på sidan Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="61367-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="61367-133">Klicka på Lägg till om du vill lägga till det sista kravbrevet i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="61367-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="61367-134">Du kan lägga till upp till fem kravbrevskoder för en kravbrevsserie.</span><span class="sxs-lookup"><span data-stu-id="61367-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="61367-135">Välj kod för nästa kravbrev som du vill skicka i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="61367-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="61367-136">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="61367-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="61367-137">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="61367-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="61367-138">Ange ett nummer i fältet Avgift i valuta.</span><span class="sxs-lookup"><span data-stu-id="61367-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="61367-139">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="61367-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="61367-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61367-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="61367-141">Ange ett värde i fältet Minsta förfallet saldo.</span><span class="sxs-lookup"><span data-stu-id="61367-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="61367-142">Välj ett tal i fältet Dagar.</span><span class="sxs-lookup"><span data-stu-id="61367-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="61367-143">Markera kryssrutan om du vill stoppa ytterligare leveranser till och fakturering av kunden.</span><span class="sxs-lookup"><span data-stu-id="61367-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="61367-144">Om du vill ta bort spärren från kontot väljer du Nej i fältet Spärrad fakturering och leverans på sidan Kunder.</span><span class="sxs-lookup"><span data-stu-id="61367-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="61367-145">Expandera snabbfliken Anmärkning.</span><span class="sxs-lookup"><span data-stu-id="61367-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="61367-146">Ange den text som ska visas i kravbrevet för den valda kravbrevskoden.</span><span class="sxs-lookup"><span data-stu-id="61367-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="61367-147">Du kan översätta den här texten in på språk med hjälp av översättningsmenyn över anmärkningsasken.</span><span class="sxs-lookup"><span data-stu-id="61367-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  


