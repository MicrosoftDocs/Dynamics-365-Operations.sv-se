---
title: Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: 'För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 1: Ställ in parametrar)".'
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f81f0f86c255d048393047965c0aa29cbef09d0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143087"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="19067-103">Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder</span><span class="sxs-lookup"><span data-stu-id="19067-103">Review configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="19067-104">För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 1: Ställ in parametrar)".</span><span class="sxs-lookup"><span data-stu-id="19067-104">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)" task guide.</span></span>

<span data-ttu-id="19067-105">Den här proceduren visar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel och Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="19067-105">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="19067-106">I det här exemplet ska du granska ER-konfigurationer för exempelföretaget Litware, Inc..</span><span class="sxs-lookup"><span data-stu-id="19067-106">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="19067-107">Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="19067-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="19067-108">Stegen kan utföras med hjälp av datauppsättningen USMF.</span><span class="sxs-lookup"><span data-stu-id="19067-108">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="19067-109">Granska den importerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="19067-109">Review the imported data model</span></span>
1. <span data-ttu-id="19067-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="19067-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="19067-111">Välj "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-111">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="19067-112">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="19067-112">Click Designer.</span></span>
    * <span data-ttu-id="19067-113">Den här modellen är utformad för betalningscheckar för företag och mappningen av den här modellen till programmets datakällor.</span><span class="sxs-lookup"><span data-stu-id="19067-113">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application's data sources.</span></span> <span data-ttu-id="19067-114">Granska den här modellen av ER-verksamhetens designer.</span><span class="sxs-lookup"><span data-stu-id="19067-114">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="19067-115">Observera attributen för modellelementen som visas: struktur, namn, beskrivning, datatyp och så vidare.</span><span class="sxs-lookup"><span data-stu-id="19067-115">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="19067-116">Expandera root i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-116">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="19067-117">Välj root\cheques i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-117">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="19067-118">Expandera root\cheques i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-118">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="19067-119">Expandera root\cheques\attribute i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-119">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="19067-120">Expandera root\payer i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-120">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="19067-121">Välj root\istestrun i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-121">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="19067-122">Välj root\layout i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-122">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="19067-123">Layoutelementet för den här modellen representerar detaljerna i den utskrivna checkens formulärlayout för det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="19067-123">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="19067-124">Den innehåller också två noder för datatypen Behållare för att lagra bilder.</span><span class="sxs-lookup"><span data-stu-id="19067-124">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="19067-125">Expandera root\layout i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-125">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="19067-126">Välj root\layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-126">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="19067-127">Expandera root\layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-127">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="19067-128">Välj root\layout\company logo\image i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-128">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="19067-129">Välj root\layout\company logo\isprinted i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-129">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="19067-130">Välj root\layout\signature i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-130">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="19067-131">Expandera root\layout\signature i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-131">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="19067-132">Välj root\layout\signature\image i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-132">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="19067-133">Välj root\layout\signature\isprinted i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-133">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="19067-134">Observera att två modellelement för bilddata är bundna till fälten i de register som innehåller bilder av företagets logotyp och den behöriga personens underskrift i binärt format.</span><span class="sxs-lookup"><span data-stu-id="19067-134">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person's signature in binary format.</span></span>  
20. <span data-ttu-id="19067-135">Expandera root\layout\watermark i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-135">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="19067-136">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="19067-136">Click Map model to datasource.</span></span>
22. <span data-ttu-id="19067-137">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="19067-137">Click Designer.</span></span>
23. <span data-ttu-id="19067-138">Expandera chequesselected i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-138">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="19067-139">Expandera "layout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-139">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="19067-140">Expandera layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-140">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="19067-141">Expandera "layout\signature" i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-141">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="19067-142">Expandera layout\watermark i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-142">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="19067-143">Ange "Visa detaljerad information" som PÅ.</span><span class="sxs-lookup"><span data-stu-id="19067-143">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="19067-144">Observera att datamodellelementet för checkar är kopplat till registret TmpChequePrintout som vid körning innehåller poster för checkar som användaren har valt för utskrift.</span><span class="sxs-lookup"><span data-stu-id="19067-144">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="19067-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-145">Close the page.</span></span>
30. <span data-ttu-id="19067-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-146">Close the page.</span></span>
31. <span data-ttu-id="19067-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-147">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="19067-148">Granska det importerade formatet</span><span class="sxs-lookup"><span data-stu-id="19067-148">Review the imported format</span></span>
1. <span data-ttu-id="19067-149">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-149">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="19067-150">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-150">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="19067-151">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="19067-151">Click Designer.</span></span>
4. <span data-ttu-id="19067-152">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="19067-152">Click Attachments.</span></span>
5. <span data-ttu-id="19067-153">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="19067-153">Click Open.</span></span>
    * <span data-ttu-id="19067-154">Öppna den bifogade rapportens mall i Excel.</span><span class="sxs-lookup"><span data-stu-id="19067-154">Open the attached report's template in Excel.</span></span>  
    * <span data-ttu-id="19067-155">Granska den bifogade rapportens Excel-mall som ska användas för att skriva ut checkar.</span><span class="sxs-lookup"><span data-stu-id="19067-155">Review the attached report's Excel template that will be used to print cheques.</span></span> <span data-ttu-id="19067-156">Mallen är utformad för att skriva ut checkar på det förtryckta formuläret och innehåller två checkar per sida.</span><span class="sxs-lookup"><span data-stu-id="19067-156">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="19067-157">Observera att två tomma bilder bäddas in.</span><span class="sxs-lookup"><span data-stu-id="19067-157">Note that two blank images are embedded.</span></span> <span data-ttu-id="19067-158">Dessa tomma bilder är till för företagets logotyp och underskriften av den person som auktoriserar en betalning.</span><span class="sxs-lookup"><span data-stu-id="19067-158">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="19067-159">Kontrollera i Excel att bilderna har namnen CompLogo respektive SignatureImage.</span><span class="sxs-lookup"><span data-stu-id="19067-159">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="19067-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-160">Close the page.</span></span>
7. <span data-ttu-id="19067-161">Expandera Report i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-161">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="19067-162">Expandera Report\ChequeLines i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-162">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="19067-163">Välj Report\ChequeLines\CompLogo i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-163">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="19067-164">Ange "Visa detaljerad information" som PÅ.</span><span class="sxs-lookup"><span data-stu-id="19067-164">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="19067-165">Observera att CompLogo-formatets cellelement representerar det Excel-objekt som används för att fylla i företagets logotyp i rapporten.</span><span class="sxs-lookup"><span data-stu-id="19067-165">Note that the 'CompLogo' format's cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="19067-166">Det här formatelementet är bundet till bildens datamodellelement som under körning innehåller en logotyp för företaget i binärformat.</span><span class="sxs-lookup"><span data-stu-id="19067-166">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="19067-167">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="19067-167">Click the Mapping tab.</span></span>
12. <span data-ttu-id="19067-168">Klicka på Redigering aktiverad.</span><span class="sxs-lookup"><span data-stu-id="19067-168">Click Edit enabled.</span></span>
    * <span data-ttu-id="19067-169">Observera att du kan ändra formatet CompLogo-formatets cellelement så att det inte längre är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="19067-169">Note that you can make the 'CompLogo' format's cell element so that it's no longer enabled.</span></span> <span data-ttu-id="19067-170">Då döljer det associerade Excel-bildelement företagets logotyp i den skapade rapporten.</span><span class="sxs-lookup"><span data-stu-id="19067-170">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="19067-171">Om det aktiverade uttrycket returnerar TRUE och den definierade bindningen inte hämtar någon bild, visar det associerade Excel-bildelementet en bild som har sparats i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="19067-171">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="19067-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-172">Close the page.</span></span>
14. <span data-ttu-id="19067-173">Expandera "labels: Container" i trädet.</span><span class="sxs-lookup"><span data-stu-id="19067-173">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="19067-174">Vissa etiketter som visas i det förtryckta checkformuläret inkluderas i rapporten när den skapas i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="19067-174">Some labels that are presented in the preprinted cheque form will be included in the report when it's created for testing purposes.</span></span> <span data-ttu-id="19067-175">Dessa etiketter skrivs dock inte ut vid den verkliga utskriften eftersom det förtryckta formuläret redan innehåller dem.</span><span class="sxs-lookup"><span data-stu-id="19067-175">However, those labels won't be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="19067-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="19067-176">Close the page.</span></span>

