---
title: Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: Det här ämnet beskriver hur du skapar konfigurationer som genererar elektroniska dokument i Excel- och Word-format som innehåller inbäddade bilder.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944567"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="f53e9-103">Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder</span><span class="sxs-lookup"><span data-stu-id="f53e9-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f53e9-104">För att slutföra stegen i den här proceduren ska du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv".</span><span class="sxs-lookup"><span data-stu-id="f53e9-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="f53e9-105">Den här proceduren förklarar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel eller Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="f53e9-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="f53e9-106">I den här proceduren skapar du de nödvändiga ER-konfigurationerna för exempelföretaget Litware, Inc. Dessa steg kan slutföras med hjälp av USMF-datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="f53e9-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="f53e9-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f53e9-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f53e9-108">Hämta och spara följande filer innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="f53e9-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="f53e9-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f53e9-109">Description</span></span>                                          | <span data-ttu-id="f53e9-110">Filnamn</span><span class="sxs-lookup"><span data-stu-id="f53e9-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="f53e9-111">Exempel på konfiguration av ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="f53e9-111">ER data model configuration</span></span>                          | [<span data-ttu-id="f53e9-112">Modell för checkar.xml</span><span class="sxs-lookup"><span data-stu-id="f53e9-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="f53e9-113">Konfiguration för ER-fomat</span><span class="sxs-lookup"><span data-stu-id="f53e9-113">ER format configuration</span></span>                              | [<span data-ttu-id="f53e9-114">Checkar utskriftsformat.xml</span><span class="sxs-lookup"><span data-stu-id="f53e9-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="f53e9-115">Bild av företagslogotypen</span><span class="sxs-lookup"><span data-stu-id="f53e9-115">Company logo image</span></span>                                   | [<span data-ttu-id="f53e9-116">Företagslogotyp.png</span><span class="sxs-lookup"><span data-stu-id="f53e9-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="f53e9-117">Signaturbild</span><span class="sxs-lookup"><span data-stu-id="f53e9-117">Signature image</span></span>                                      | [<span data-ttu-id="f53e9-118">Signaturbild.png</span><span class="sxs-lookup"><span data-stu-id="f53e9-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="f53e9-119">Alternativ signaturbild</span><span class="sxs-lookup"><span data-stu-id="f53e9-119">Alternative signature image</span></span>                          | [<span data-ttu-id="f53e9-120">Signaturbild 2.png</span><span class="sxs-lookup"><span data-stu-id="f53e9-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="f53e9-121">Microsoft Word-mall för utskrift av betalningscheckar</span><span class="sxs-lookup"><span data-stu-id="f53e9-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="f53e9-122">Checkmall Word.docx</span><span class="sxs-lookup"><span data-stu-id="f53e9-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="f53e9-123">Verifiera förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f53e9-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="f53e9-124">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f53e9-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="f53e9-125">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f53e9-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="f53e9-126">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="f53e9-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="f53e9-127">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="f53e9-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="f53e9-128">Lägg till en ny konfiguration för ER-modell</span><span class="sxs-lookup"><span data-stu-id="f53e9-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="f53e9-129">Du kan läsa in konfigurationsfilen för ER-modell (modell för cheques.xml) som du sparat tidigare istället för att skapa en ny modell.</span><span class="sxs-lookup"><span data-stu-id="f53e9-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="f53e9-130">Den här filen innehåller exempeldatamodellen för betalningscheckar och mappning av datamodellen till datakomponenterna i programmet Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f53e9-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="f53e9-131">Klicka på Utbyte på snabbfliken Versioner.</span><span class="sxs-lookup"><span data-stu-id="f53e9-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="f53e9-132">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="f53e9-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="f53e9-133">Klicka på Bläddra och välj Modell för cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="f53e9-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="f53e9-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f53e9-134">Click OK.</span></span>  
 6. <span data-ttu-id="f53e9-135">Den inlästa modellen ska användas som en datakälla för information för att skapa dokument som innehåller bilder i Excel och Word.</span><span class="sxs-lookup"><span data-stu-id="f53e9-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="f53e9-136">Lägg till en ny konfiguration för ER-format</span><span class="sxs-lookup"><span data-stu-id="f53e9-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="f53e9-137">Du kan läsa in konfigurationsfilen för ER-format (Checkutskrift för format.xml) som du sparat tidigare istället för att skapa ett nytt format.</span><span class="sxs-lookup"><span data-stu-id="f53e9-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="f53e9-138">Den här filen innehåller exempellayouten på formatet för att skriva ut checkar med det förtryckta formuläret och mappning av detta format till datamodellen ”modell för checkar”.</span><span class="sxs-lookup"><span data-stu-id="f53e9-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="f53e9-139">Klicka på Byt.</span><span class="sxs-lookup"><span data-stu-id="f53e9-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="f53e9-140">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="f53e9-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="f53e9-141">Klicka på Bläddra och välj checkutskriftsformat (format).xml.</span><span class="sxs-lookup"><span data-stu-id="f53e9-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="f53e9-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f53e9-142">Click OK.</span></span>  
 6. <span data-ttu-id="f53e9-143">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f53e9-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="f53e9-144">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="f53e9-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="f53e9-145">Det inlästa formatet ska användas för att skapa dokument som innehåller bilder i Excel och Word.</span><span class="sxs-lookup"><span data-stu-id="f53e9-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="f53e9-146">Konfigurera ER-användarparametrar</span><span class="sxs-lookup"><span data-stu-id="f53e9-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="f53e9-147">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f53e9-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="f53e9-148">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="f53e9-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="f53e9-149">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="f53e9-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="f53e9-150">Aktivera flaggan ”kör utkast" för att starta utkastversionen av det markerade formatet i stället för den slutfördaslutfört.</span><span class="sxs-lookup"><span data-stu-id="f53e9-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="f53e9-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f53e9-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="f53e9-152">Konfigurera parametrar för kassa och bankhantering</span><span class="sxs-lookup"><span data-stu-id="f53e9-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="f53e9-153">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f53e9-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="f53e9-154">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="f53e9-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="f53e9-155">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f53e9-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="f53e9-156">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="f53e9-156">Click Check.</span></span>  
 5. <span data-ttu-id="f53e9-157">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="f53e9-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="f53e9-158">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f53e9-158">Click Edit.</span></span>  
 7. <span data-ttu-id="f53e9-159">Välj Ja i fältet Företagslogo.</span><span class="sxs-lookup"><span data-stu-id="f53e9-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="f53e9-160">Klicka på Företagslogo.</span><span class="sxs-lookup"><span data-stu-id="f53e9-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="f53e9-161">Klicka på Ändra.</span><span class="sxs-lookup"><span data-stu-id="f53e9-161">Click Change.</span></span>  
 10. <span data-ttu-id="f53e9-162">Klicka på Bläddra och välj filen som du hämtade förut, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="f53e9-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="f53e9-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f53e9-163">Click Save.</span></span>  
 12. <span data-ttu-id="f53e9-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f53e9-164">Close the page.</span></span>  
 13. <span data-ttu-id="f53e9-165">Expandera avsnittet Signatur.</span><span class="sxs-lookup"><span data-stu-id="f53e9-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="f53e9-166">Välj Ja i fältet Skriv ut första signatur.</span><span class="sxs-lookup"><span data-stu-id="f53e9-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="f53e9-167">Klicka på Ändra.</span><span class="sxs-lookup"><span data-stu-id="f53e9-167">Click Change.</span></span>  
 16. <span data-ttu-id="f53e9-168">Klicka på Bläddra och välj filen som du hämtade förut, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="f53e9-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="f53e9-169">Expandera avsnittet Kopior.</span><span class="sxs-lookup"><span data-stu-id="f53e9-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="f53e9-170">Markera ett alternativ i fältet Vattenstämpel.</span><span class="sxs-lookup"><span data-stu-id="f53e9-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="f53e9-171">Välj Ja i fältet Allmänt elektroniskt exportformat.</span><span class="sxs-lookup"><span data-stu-id="f53e9-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="f53e9-172">Välj konfigurationen "checkutskriftsformat".</span><span class="sxs-lookup"><span data-stu-id="f53e9-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="f53e9-173">Nu kommer det valda ER-formatet att användas för utskrift av checkar.</span><span class="sxs-lookup"><span data-stu-id="f53e9-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="f53e9-174">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="f53e9-174">Click Attach.</span></span>  
 23. <span data-ttu-id="f53e9-175">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f53e9-175">Click New.</span></span>  
 24. <span data-ttu-id="f53e9-176">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="f53e9-176">Click File.</span></span>  
 25. <span data-ttu-id="f53e9-177">Klicka på Bläddra och välj filen som du hämtade förut, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="f53e9-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="f53e9-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f53e9-178">Close the page.</span></span>  
 27. <span data-ttu-id="f53e9-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f53e9-179">Close the page.</span></span>  
 28. <span data-ttu-id="f53e9-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f53e9-180">Close the page.</span></span>  
 29. <span data-ttu-id="f53e9-181">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="f53e9-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="f53e9-182">Välj Ja i fältet Tillåt att reservationer skapas för inaktiva bankkonton:</span><span class="sxs-lookup"><span data-stu-id="f53e9-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="f53e9-183">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f53e9-183">Click Save.</span></span>  
 32. <span data-ttu-id="f53e9-184">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f53e9-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
