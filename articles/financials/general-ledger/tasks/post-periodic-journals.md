---
title: Bokför periodiska journaler
description: Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deae523d922e1d6a4f7bb05433e9b1568c9c1ee9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562240"
---
# <a name="post-periodic-journals"></a><span data-ttu-id="c71f9-103">Bokför periodiska journaler</span><span class="sxs-lookup"><span data-stu-id="c71f9-103">Post periodic journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c71f9-104">Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas.</span><span class="sxs-lookup"><span data-stu-id="c71f9-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="c71f9-105">När du skapar och bokför en periodisk journal anger du periodintervallet för upprepningen, till exempel dagar eller månader.</span><span class="sxs-lookup"><span data-stu-id="c71f9-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="c71f9-106">I den här uppgiftsguiden skapas en periodisk journal med månadsvis upprepningar.</span><span class="sxs-lookup"><span data-stu-id="c71f9-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>



1. <span data-ttu-id="c71f9-107">Gå till Redovisning > Periodiska uppgifter > Periodiska journaler.</span><span class="sxs-lookup"><span data-stu-id="c71f9-107">Go to General ledger > Periodic tasks > Periodic journals.</span></span>
2. <span data-ttu-id="c71f9-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71f9-108">Click New.</span></span>
3. <span data-ttu-id="c71f9-109">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c71f9-109">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="c71f9-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71f9-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c71f9-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c71f9-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="c71f9-112">Beskrivningen är namnet på den periodiska journalen när den hämtas senare, så se till att ge den ett relevant namn.</span><span class="sxs-lookup"><span data-stu-id="c71f9-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>  
6. <span data-ttu-id="c71f9-113">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="c71f9-113">Click Lines.</span></span>
    * <span data-ttu-id="c71f9-114">En periodisk journal vanligtvis kommer att innehålla flera journalrader.</span><span class="sxs-lookup"><span data-stu-id="c71f9-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="c71f9-115">Men i den här uppgiftguiden ska vi bara lägga till en rad.</span><span class="sxs-lookup"><span data-stu-id="c71f9-115">this task guide will however only add one line.</span></span>  
7. <span data-ttu-id="c71f9-116">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="c71f9-116">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="c71f9-117">Fältet Datum innehåller bokföringsdatumet för nästa överföring till den dagliga journalen.</span><span class="sxs-lookup"><span data-stu-id="c71f9-117">The Date field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="c71f9-118">För journaler som ska hämtas varje månad rekommenderas du att använda datumet i månaden när de bokförs, vanligen det första eller sista datumet i perioden.</span><span class="sxs-lookup"><span data-stu-id="c71f9-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="c71f9-119">Det går att lämna datumfältet tomt och ange ett datum när journalen hämtas, med det tomma datumfältet.</span><span class="sxs-lookup"><span data-stu-id="c71f9-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span>    <span data-ttu-id="c71f9-120">Fältet uppdateras automatiskt till nästa återkommande datum då transaktioner hämtas.</span><span class="sxs-lookup"><span data-stu-id="c71f9-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span>  
8. <span data-ttu-id="c71f9-121">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="c71f9-121">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="c71f9-122">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c71f9-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="c71f9-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71f9-123">Close the page.</span></span>
11. <span data-ttu-id="c71f9-124">Ange ett tal i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="c71f9-124">In the Debit field, enter a number.</span></span>
12. <span data-ttu-id="c71f9-125">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="c71f9-125">In the Offset account field, specify the desired values.</span></span>
13. <span data-ttu-id="c71f9-126">Välj "Månader" i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="c71f9-126">In the Unit field, select 'Months'.</span></span>
14. <span data-ttu-id="c71f9-127">Ange "1" i fältet Antal enheter.</span><span class="sxs-lookup"><span data-stu-id="c71f9-127">In the Number of units field, enter '1'.</span></span>
15. <span data-ttu-id="c71f9-128">Ange ett datum i fältet för senaste datum.</span><span class="sxs-lookup"><span data-stu-id="c71f9-128">In the Last date field, enter a date.</span></span>
    * <span data-ttu-id="c71f9-129">Om du anger det senaste datumet i den föregående perioden förhindras den återkommande journalen att skapas av misstag i fel startperiod.</span><span class="sxs-lookup"><span data-stu-id="c71f9-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="c71f9-130">Senaste datum kommer att uppdateras senare, varje gång den periodiska journalen hämtas.</span><span class="sxs-lookup"><span data-stu-id="c71f9-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span>  
16. <span data-ttu-id="c71f9-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71f9-131">Click Save.</span></span>
17. <span data-ttu-id="c71f9-132">Gå till standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="c71f9-132">Go to Default dashboard.</span></span>
18. <span data-ttu-id="c71f9-133">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="c71f9-133">Go to General ledger > Journal entries > General journals.</span></span>
19. <span data-ttu-id="c71f9-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71f9-134">Click New.</span></span>
20. <span data-ttu-id="c71f9-135">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c71f9-135">In the Name field, enter or select a value.</span></span>
21. <span data-ttu-id="c71f9-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c71f9-136">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="c71f9-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71f9-137">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="c71f9-138">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c71f9-138">In the Description field, type a value.</span></span>
24. <span data-ttu-id="c71f9-139">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="c71f9-139">Click Lines.</span></span>
25. <span data-ttu-id="c71f9-140">Klicka på Periodjournal.</span><span class="sxs-lookup"><span data-stu-id="c71f9-140">Click Period journal.</span></span>
26. <span data-ttu-id="c71f9-141">Klicka på Hämta journal.</span><span class="sxs-lookup"><span data-stu-id="c71f9-141">Click Retrieve journal.</span></span>
27. <span data-ttu-id="c71f9-142">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="c71f9-142">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="c71f9-143">Till-datumet fungerar som brytdatum för de periodiska verifikationsraderna.</span><span class="sxs-lookup"><span data-stu-id="c71f9-143">The To date serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="c71f9-144">Baserat på återkommandeinställningen kan senaste datum och till-datum på samma rad inkluderas mer än en gång i den resulterande journalen.</span><span class="sxs-lookup"><span data-stu-id="c71f9-144">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="c71f9-145">Till-datum uppdateras automatiskt på grundval av sessiondatumet för den senaste gången den periodiska raden överfördes till en journal.</span><span class="sxs-lookup"><span data-stu-id="c71f9-145">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span>  
28. <span data-ttu-id="c71f9-146">Ange eller välj ett värde i fältet Periodisk journal.</span><span class="sxs-lookup"><span data-stu-id="c71f9-146">In the Periodic journal number field, enter or select a value.</span></span>
29. <span data-ttu-id="c71f9-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71f9-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="c71f9-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c71f9-148">Click OK.</span></span>
    * <span data-ttu-id="c71f9-149">Periodjournalen kan nu granskas, godkännas eller bokföras beroende på inställningar och krav.</span><span class="sxs-lookup"><span data-stu-id="c71f9-149">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>  

