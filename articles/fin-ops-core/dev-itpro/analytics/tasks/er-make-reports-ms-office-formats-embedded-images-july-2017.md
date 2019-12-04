---
title: Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: I detta avsnitt finns information steg för steg om hur du skapar konfigurationer för elektronisk rapportering (ER) som skapar elektroniska dokument i Microsoft Office-format (Excel och Word) och som innehåller inbäddade bilder.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
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
ms.openlocfilehash: 143782413359d87f3d4c46940f9a699fbf0e8f90
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769819"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="08e90-103">Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder</span><span class="sxs-lookup"><span data-stu-id="08e90-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08e90-104">För att slutföra stegen i den här proceduren ska du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv".</span><span class="sxs-lookup"><span data-stu-id="08e90-104">To complete the steps in this procedure, first complete the procedure, “ER Create a configuration provider and mark it as active.”</span></span> <span data-ttu-id="08e90-105">Den här proceduren förklarar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel eller Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="08e90-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="08e90-106">I den här proceduren skapar du de nödvändiga ER-konfigurationerna för exempelföretaget Litware, Inc. Dessa steg kan slutföras med hjälp av USMF-datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="08e90-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="08e90-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="08e90-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="08e90-108">Innan du börjar ska du hämta och spara filerna i hjälpavsnittet [bädda in bilder och former i dokument som du skapar med ER](../electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="08e90-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="08e90-109">Filerna är: modell för checkar.xml, utskriftsformat för checkar.xml, företagslogotyp.png, signatur.png, signaturbild 2.png och checkmall för Word.docx.</span><span class="sxs-lookup"><span data-stu-id="08e90-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="08e90-110">Verifiera förutsättningar</span><span class="sxs-lookup"><span data-stu-id="08e90-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="08e90-111">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="08e90-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="08e90-112">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="08e90-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="08e90-113">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv".</span><span class="sxs-lookup"><span data-stu-id="08e90-113">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>   
 3. <span data-ttu-id="08e90-114">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="08e90-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="08e90-115">Lägg till en ny konfiguration för ER-modell</span><span class="sxs-lookup"><span data-stu-id="08e90-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="08e90-116">Du kan läsa in konfigurationsfilen för ER-modell (modell för cheques.xml) som du sparat tidigare istället för att skapa en ny modell.</span><span class="sxs-lookup"><span data-stu-id="08e90-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="08e90-117">Den här filen innehåller exempeldatamodellen för betalningscheckar och mappning av datamodellen till datakomponenterna i programmet Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="08e90-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="08e90-118">Klicka på Utbyte på snabbfliken Versioner.</span><span class="sxs-lookup"><span data-stu-id="08e90-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="08e90-119">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="08e90-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="08e90-120">Klicka på Bläddra och välj Modell för cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="08e90-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="08e90-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08e90-121">Click OK.</span></span>  
 6. <span data-ttu-id="08e90-122">Den inlästa modellen ska användas som en datakälla för information för att skapa dokument som innehåller bilder i Excel och Word.</span><span class="sxs-lookup"><span data-stu-id="08e90-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="08e90-123">Lägg till en ny konfiguration för ER-format</span><span class="sxs-lookup"><span data-stu-id="08e90-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="08e90-124">Du kan läsa in konfigurationsfilen för ER-format (Checkutskrift för format.xml) som du sparat tidigare istället för att skapa ett nytt format.</span><span class="sxs-lookup"><span data-stu-id="08e90-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="08e90-125">Den här filen innehåller exempellayouten på formatet för att skriva ut checkar med det förtryckta formuläret och mappning av detta format till datamodellen ”modell för checkar”.</span><span class="sxs-lookup"><span data-stu-id="08e90-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the ‘Model for cheques’ data model.</span></span>   
 2. <span data-ttu-id="08e90-126">Klicka på Byt.</span><span class="sxs-lookup"><span data-stu-id="08e90-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="08e90-127">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="08e90-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="08e90-128">Klicka på Bläddra och välj checkutskriftsformat (format).xml.</span><span class="sxs-lookup"><span data-stu-id="08e90-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="08e90-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08e90-129">Click OK.</span></span>  
 6. <span data-ttu-id="08e90-130">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="08e90-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="08e90-131">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="08e90-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="08e90-132">Det inlästa formatet ska användas för att skapa dokument som innehåller bilder i Excel och Word.</span><span class="sxs-lookup"><span data-stu-id="08e90-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="08e90-133">Konfigurera ER-användarparametrar</span><span class="sxs-lookup"><span data-stu-id="08e90-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="08e90-134">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08e90-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="08e90-135">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="08e90-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="08e90-136">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="08e90-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="08e90-137">Aktivera flaggan ”kör utkast" för att starta utkastversionen av det markerade formatet i stället för den slutfördaslutfört.</span><span class="sxs-lookup"><span data-stu-id="08e90-137">Turn on the ‘Run draft’ flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="08e90-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08e90-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="08e90-139">Konfigurera parametrar för kassa och bankhantering</span><span class="sxs-lookup"><span data-stu-id="08e90-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="08e90-140">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="08e90-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="08e90-141">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="08e90-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="08e90-142">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08e90-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="08e90-143">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="08e90-143">Click Check.</span></span>  
 5. <span data-ttu-id="08e90-144">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="08e90-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="08e90-145">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="08e90-145">Click Edit.</span></span>  
 7. <span data-ttu-id="08e90-146">Välj Ja i fältet Företagslogo.</span><span class="sxs-lookup"><span data-stu-id="08e90-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="08e90-147">Klicka på Företagslogo.</span><span class="sxs-lookup"><span data-stu-id="08e90-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="08e90-148">Klicka på Ändra.</span><span class="sxs-lookup"><span data-stu-id="08e90-148">Click Change.</span></span>  
 10. <span data-ttu-id="08e90-149">Klicka på Bläddra och välj filen som du hämtade förut, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="08e90-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="08e90-150">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="08e90-150">Click Save.</span></span>  
 12. <span data-ttu-id="08e90-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08e90-151">Close the page.</span></span>  
 13. <span data-ttu-id="08e90-152">Expandera avsnittet Signatur.</span><span class="sxs-lookup"><span data-stu-id="08e90-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="08e90-153">Välj Ja i fältet Skriv ut första signatur.</span><span class="sxs-lookup"><span data-stu-id="08e90-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="08e90-154">Klicka på Ändra.</span><span class="sxs-lookup"><span data-stu-id="08e90-154">Click Change.</span></span>  
 16. <span data-ttu-id="08e90-155">Klicka på Bläddra och välj filen som du hämtade förut, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="08e90-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="08e90-156">Expandera avsnittet Kopior.</span><span class="sxs-lookup"><span data-stu-id="08e90-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="08e90-157">Markera ett alternativ i fältet Vattenstämpel.</span><span class="sxs-lookup"><span data-stu-id="08e90-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="08e90-158">Välj Ja i fältet Allmänt elektroniskt exportformat.</span><span class="sxs-lookup"><span data-stu-id="08e90-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="08e90-159">Välj konfigurationen "checkutskriftsformat".</span><span class="sxs-lookup"><span data-stu-id="08e90-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="08e90-160">Nu kommer det valda ER-formatet att användas för utskrift av checkar.</span><span class="sxs-lookup"><span data-stu-id="08e90-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="08e90-161">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="08e90-161">Click Attach.</span></span>  
 23. <span data-ttu-id="08e90-162">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="08e90-162">Click New.</span></span>  
 24. <span data-ttu-id="08e90-163">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="08e90-163">Click File.</span></span>  
 25. <span data-ttu-id="08e90-164">Klicka på Bläddra och välj filen som du hämtade förut, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="08e90-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="08e90-165">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08e90-165">Close the page.</span></span>  
 27. <span data-ttu-id="08e90-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08e90-166">Close the page.</span></span>  
 28. <span data-ttu-id="08e90-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08e90-167">Close the page.</span></span>  
 29. <span data-ttu-id="08e90-168">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="08e90-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="08e90-169">Välj Ja i fältet Tillåt att reservationer skapas för inaktiva bankkonton:</span><span class="sxs-lookup"><span data-stu-id="08e90-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="08e90-170">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="08e90-170">Click Save.</span></span>  
 32. <span data-ttu-id="08e90-171">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08e90-171">Close the page.</span></span>  
