---
title: Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: Det här ämnet beskriver hur du skapar konfigurationer för rapportering för att skapa elektroniska dokument som innehåller inbäddade bilder. (Del 1 - Ställa in parametrar).
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eee6300350dd96c34f2eab44704d1895e6171ff
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093655"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="3f361-104">Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder</span><span class="sxs-lookup"><span data-stu-id="3f361-104">Review configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f361-105">För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 1: Ställ in parametrar)".</span><span class="sxs-lookup"><span data-stu-id="3f361-105">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)" task guide.</span></span>

<span data-ttu-id="3f361-106">Den här proceduren visar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel och Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="3f361-106">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="3f361-107">I det här exemplet ska du granska ER-konfigurationer för exempelföretaget Litware, Inc..</span><span class="sxs-lookup"><span data-stu-id="3f361-107">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="3f361-108">Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="3f361-108">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="3f361-109">Stegen kan utföras med hjälp av datauppsättningen USMF.</span><span class="sxs-lookup"><span data-stu-id="3f361-109">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="3f361-110">Granska den importerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="3f361-110">Review the imported data model</span></span>
1. <span data-ttu-id="3f361-111">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="3f361-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3f361-112">Välj "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-112">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="3f361-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="3f361-113">Click Designer.</span></span>
    * <span data-ttu-id="3f361-114">Den här modellen är utformad för betalningscheckar för företag och mappningen av den här modellen till programmets datakällor.</span><span class="sxs-lookup"><span data-stu-id="3f361-114">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application's data sources.</span></span> <span data-ttu-id="3f361-115">Granska den här modellen av ER-verksamhetens designer.</span><span class="sxs-lookup"><span data-stu-id="3f361-115">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="3f361-116">Observera attributen för modellelementen som visas: struktur, namn, beskrivning, datatyp och så vidare.</span><span class="sxs-lookup"><span data-stu-id="3f361-116">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="3f361-117">Expandera root i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-117">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="3f361-118">Välj root\cheques i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-118">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="3f361-119">Expandera root\cheques i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-119">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="3f361-120">Expandera root\cheques\attribute i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-120">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="3f361-121">Expandera root\payer i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-121">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="3f361-122">Välj root\istestrun i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-122">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="3f361-123">Välj root\layout i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-123">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="3f361-124">Layoutelementet för den här modellen representerar detaljerna i den utskrivna checkens formulärlayout för det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="3f361-124">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="3f361-125">Den innehåller också två noder för datatypen Behållare för att lagra bilder.</span><span class="sxs-lookup"><span data-stu-id="3f361-125">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="3f361-126">Expandera root\layout i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-126">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="3f361-127">Välj root\layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-127">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="3f361-128">Expandera root\layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-128">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="3f361-129">Välj root\layout\company logo\image i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-129">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="3f361-130">Välj root\layout\company logo\isprinted i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-130">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="3f361-131">Välj root\layout\signature i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-131">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="3f361-132">Expandera root\layout\signature i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-132">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="3f361-133">Välj root\layout\signature\image i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-133">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="3f361-134">Välj root\layout\signature\isprinted i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-134">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="3f361-135">Observera att två modellelement för bilddata är bundna till fälten i de register som innehåller bilder av företagets logotyp och den behöriga personens underskrift i binärt format.</span><span class="sxs-lookup"><span data-stu-id="3f361-135">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person's signature in binary format.</span></span>  
20. <span data-ttu-id="3f361-136">Expandera root\layout\watermark i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-136">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="3f361-137">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="3f361-137">Click Map model to datasource.</span></span>
22. <span data-ttu-id="3f361-138">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="3f361-138">Click Designer.</span></span>
23. <span data-ttu-id="3f361-139">Expandera chequesselected i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-139">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="3f361-140">Expandera "layout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-140">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="3f361-141">Expandera layout\company logo i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-141">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="3f361-142">Expandera "layout\signature" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-142">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="3f361-143">Expandera layout\watermark i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-143">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="3f361-144">Ange "Visa detaljerad information" som PÅ.</span><span class="sxs-lookup"><span data-stu-id="3f361-144">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="3f361-145">Observera att datamodellelementet för checkar är kopplat till registret TmpChequePrintout som vid körning innehåller poster för checkar som användaren har valt för utskrift.</span><span class="sxs-lookup"><span data-stu-id="3f361-145">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="3f361-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-146">Close the page.</span></span>
30. <span data-ttu-id="3f361-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-147">Close the page.</span></span>
31. <span data-ttu-id="3f361-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-148">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="3f361-149">Granska det importerade formatet</span><span class="sxs-lookup"><span data-stu-id="3f361-149">Review the imported format</span></span>
1. <span data-ttu-id="3f361-150">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-150">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="3f361-151">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-151">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="3f361-152">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="3f361-152">Click Designer.</span></span>
4. <span data-ttu-id="3f361-153">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="3f361-153">Click Attachments.</span></span>
5. <span data-ttu-id="3f361-154">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="3f361-154">Click Open.</span></span>
    * <span data-ttu-id="3f361-155">Öppna den bifogade rapportens mall i Excel.</span><span class="sxs-lookup"><span data-stu-id="3f361-155">Open the attached report's template in Excel.</span></span>  
    * <span data-ttu-id="3f361-156">Granska den bifogade rapportens Excel-mall som ska användas för att skriva ut checkar.</span><span class="sxs-lookup"><span data-stu-id="3f361-156">Review the attached report's Excel template that will be used to print cheques.</span></span> <span data-ttu-id="3f361-157">Mallen är utformad för att skriva ut checkar på det förtryckta formuläret och innehåller två checkar per sida.</span><span class="sxs-lookup"><span data-stu-id="3f361-157">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="3f361-158">Observera att två tomma bilder bäddas in.</span><span class="sxs-lookup"><span data-stu-id="3f361-158">Note that two blank images are embedded.</span></span> <span data-ttu-id="3f361-159">Dessa tomma bilder är till för företagets logotyp och underskriften av den person som auktoriserar en betalning.</span><span class="sxs-lookup"><span data-stu-id="3f361-159">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="3f361-160">Kontrollera i Excel att bilderna har namnen CompLogo respektive SignatureImage.</span><span class="sxs-lookup"><span data-stu-id="3f361-160">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="3f361-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-161">Close the page.</span></span>
7. <span data-ttu-id="3f361-162">Expandera Report i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-162">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="3f361-163">Expandera Report\ChequeLines i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-163">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="3f361-164">Välj Report\ChequeLines\CompLogo i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-164">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="3f361-165">Ange "Visa detaljerad information" som PÅ.</span><span class="sxs-lookup"><span data-stu-id="3f361-165">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="3f361-166">Observera att CompLogo-formatets cellelement representerar det Excel-objekt som används för att fylla i företagets logotyp i rapporten.</span><span class="sxs-lookup"><span data-stu-id="3f361-166">Note that the 'CompLogo' format's cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="3f361-167">Det här formatelementet är bundet till bildens datamodellelement som under körning innehåller en logotyp för företaget i binärformat.</span><span class="sxs-lookup"><span data-stu-id="3f361-167">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="3f361-168">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="3f361-168">Click the Mapping tab.</span></span>
12. <span data-ttu-id="3f361-169">Klicka på Redigering aktiverad.</span><span class="sxs-lookup"><span data-stu-id="3f361-169">Click Edit enabled.</span></span>
    * <span data-ttu-id="3f361-170">Observera att du kan ändra formatet CompLogo-formatets cellelement så att det inte längre är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="3f361-170">Note that you can make the 'CompLogo' format's cell element so that it's no longer enabled.</span></span> <span data-ttu-id="3f361-171">Då döljer det associerade Excel-bildelement företagets logotyp i den skapade rapporten.</span><span class="sxs-lookup"><span data-stu-id="3f361-171">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="3f361-172">Om det aktiverade uttrycket returnerar TRUE och den definierade bindningen inte hämtar någon bild, visar det associerade Excel-bildelementet en bild som har sparats i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="3f361-172">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="3f361-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-173">Close the page.</span></span>
14. <span data-ttu-id="3f361-174">Expandera "labels: Container" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3f361-174">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="3f361-175">Vissa etiketter som visas i det förtryckta checkformuläret inkluderas i rapporten när den skapas i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="3f361-175">Some labels that are presented in the preprinted cheque form will be included in the report when it's created for testing purposes.</span></span> <span data-ttu-id="3f361-176">Dessa etiketter skrivs dock inte ut vid den verkliga utskriften eftersom det förtryckta formuläret redan innehåller dem.</span><span class="sxs-lookup"><span data-stu-id="3f361-176">However, those labels won't be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="3f361-177">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f361-177">Close the page.</span></span>

