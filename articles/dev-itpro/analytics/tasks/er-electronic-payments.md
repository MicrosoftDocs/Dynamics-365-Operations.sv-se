--- 
title: "Generera elektroniska dokument för betalningar genom att använda formatkonfigurationer"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan använda en ny formatkonfiguration för Elektronisk rapportering (ER) för att skapa elektroniska dokument för bearbetning av betalningar."
author: NickSelin
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
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 805e6f377d452e9c50240c8c9fc2ea6f5cb487e6
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="generate-electronic-documents-for-payments-by-using-format-configurations"></a><span data-ttu-id="129aa-103">Generera elektroniska dokument för betalningar genom att använda formatkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="129aa-103">Generate electronic documents for payments by using format configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="129aa-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan använda en ny formatkonfiguration för Elektronisk rapportering (ER) för att skapa elektroniska dokument för bearbetning av betalningar.</span><span class="sxs-lookup"><span data-stu-id="129aa-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="129aa-105">Dessa steg kan utföras i GBSI-exempelföretaget.</span><span class="sxs-lookup"><span data-stu-id="129aa-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="129aa-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfiguration med formatet betalningsdokument”.</span><span class="sxs-lookup"><span data-stu-id="129aa-106">To complete these steps, you must first complete the steps in the “Create a configuration with format of payment document” procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="129aa-107">Ändra konfigurationen för den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="129aa-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="129aa-108">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="129aa-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="129aa-109">Växla avsnittet filformat för att visa det vid behov.</span><span class="sxs-lookup"><span data-stu-id="129aa-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="129aa-110">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="129aa-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="129aa-111">Filtrera till exempel efter fältet Betalningsmetod med värdet "Electronic".</span><span class="sxs-lookup"><span data-stu-id="129aa-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="129aa-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="129aa-112">Click Edit.</span></span>
5. <span data-ttu-id="129aa-113">Ange Allmän elektronisk rapportering till Ja.</span><span class="sxs-lookup"><span data-stu-id="129aa-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="129aa-114">Välj Ja om du vill använda det allmänna elektroniska rapporteringmönstret för generering av betalningsfil.</span><span class="sxs-lookup"><span data-stu-id="129aa-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="129aa-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="129aa-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="129aa-116">Välj formatkonfigurationen BACS (fiktiv från Storbritannien).</span><span class="sxs-lookup"><span data-stu-id="129aa-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="129aa-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="129aa-117">Click Save.</span></span>
9. <span data-ttu-id="129aa-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="129aa-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="129aa-119">Testa formatet för skapade betalningsfiler</span><span class="sxs-lookup"><span data-stu-id="129aa-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="129aa-120">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="129aa-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="129aa-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="129aa-121">Click New.</span></span>
3. <span data-ttu-id="129aa-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="129aa-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="129aa-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="129aa-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="129aa-125">Välj VendPay.</span><span class="sxs-lookup"><span data-stu-id="129aa-125">Select VendPay.</span></span>  
6. <span data-ttu-id="129aa-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="129aa-126">Click Save.</span></span>
7. <span data-ttu-id="129aa-127">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="129aa-127">Click Lines.</span></span>
8. <span data-ttu-id="129aa-128">Ange "DEMF" i fältet Företag.</span><span class="sxs-lookup"><span data-stu-id="129aa-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="129aa-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="129aa-129">DEMF</span></span>  
9. <span data-ttu-id="129aa-130">Ange värdet "DE-0100" i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="129aa-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="129aa-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="129aa-131">DE-01001</span></span>  
10. <span data-ttu-id="129aa-132">Ange "Betalning" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="129aa-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="129aa-133">Betalning</span><span class="sxs-lookup"><span data-stu-id="129aa-133">Payment</span></span>  
11. <span data-ttu-id="129aa-134">Ange ett tal i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="129aa-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="129aa-135">1 000</span><span class="sxs-lookup"><span data-stu-id="129aa-135">1000</span></span>  
12. <span data-ttu-id="129aa-136">Klicka på fliken Betalning.</span><span class="sxs-lookup"><span data-stu-id="129aa-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="129aa-137">I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="129aa-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="129aa-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="129aa-139">Välj det elektroniska värdet.</span><span class="sxs-lookup"><span data-stu-id="129aa-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="129aa-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="129aa-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="129aa-141">Click Save.</span></span>
17. <span data-ttu-id="129aa-142">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="129aa-142">Click Generate payments.</span></span>
18. <span data-ttu-id="129aa-143">I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="129aa-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="129aa-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="129aa-145">Välj det elektroniska värdet.</span><span class="sxs-lookup"><span data-stu-id="129aa-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="129aa-146">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="129aa-147">Välj det elektroniska värdet.</span><span class="sxs-lookup"><span data-stu-id="129aa-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="129aa-148">Ange ett värde i fältet Filnamn.</span><span class="sxs-lookup"><span data-stu-id="129aa-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="129aa-149">Skriv till exempel "betalningar".</span><span class="sxs-lookup"><span data-stu-id="129aa-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="129aa-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="129aa-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="129aa-151">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="129aa-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="129aa-152">Välj värdet GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="129aa-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="129aa-153">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="129aa-153">Click OK.</span></span>
25. <span data-ttu-id="129aa-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="129aa-154">Click OK.</span></span>
    * <span data-ttu-id="129aa-155">Analysera den skapade betalningsfilen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="129aa-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="129aa-156">Jämför den med den designade dokumentlayouten och de definierade betalningstransaktionsattributen.</span><span class="sxs-lookup"><span data-stu-id="129aa-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  


