---
title: Välj datamodelldefinitioner när du skapar format
description: För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: 374c31b5ea9160fba773e82f658e8de05c67cab4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143256"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a><span data-ttu-id="05975-103">Välj datamodelldefinitioner när du skapar format</span><span class="sxs-lookup"><span data-stu-id="05975-103">Select data model definitions when you create formats</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="05975-104">För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv".</span><span class="sxs-lookup"><span data-stu-id="05975-104">To complete the steps in this procedure, you must first complete the procedure, ER Create a configuration provider and mark it as active.</span></span> 

<span data-ttu-id="05975-105">Den här proceduren visar hur en modells rotobjekt kan väljas som en datamodelldefinition för att infoga en ER-formatkonfiguration (elektronisk rapportering) som syftar till att skapa elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="05975-105">This procedure shows how a model's root item can be selected as a data model definition for inserting an Electronic reporting (ER) format configuration that is designed to generate electronic documents.</span></span> <span data-ttu-id="05975-106">I den här proceduren ska du skapa en ER-formatkonfiguration för exempelföretaget Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="05975-106">In this procedure, you will add a new ER format configuration for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="05975-107">Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="05975-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="05975-108">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="05975-108">The steps can be completed by using any dataset.</span></span>

1. <span data-ttu-id="05975-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="05975-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="05975-110">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="05975-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="05975-111">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="05975-111">If you don't see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
2. <span data-ttu-id="05975-112">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="05975-112">Click Reporting configurations.</span></span>

## <a name="add-a-new-er-data-model-configuration"></a><span data-ttu-id="05975-113">Lägg till en ny konfiguration för ER-datamodell</span><span class="sxs-lookup"><span data-stu-id="05975-113">Add a new ER data model configuration</span></span>
1. <span data-ttu-id="05975-114">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-114">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="05975-115">Vi lägger till en ny ER-modellkonfiguration som innehåller en datamodell som ska användas som datakälla för generering av ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="05975-115">We add a new ER model configuration containing a data model that is designed to be used as data source for generation ER reports.</span></span>  
2. <span data-ttu-id="05975-116">Skriv "Payment model (fictitious)" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="05975-116">In the Name field, type 'Payment model (fictitious)'.</span></span>
    * <span data-ttu-id="05975-117">Betalningsmodell (fiktiv)</span><span class="sxs-lookup"><span data-stu-id="05975-117">Payment model (fictitious)</span></span>  
3. <span data-ttu-id="05975-118">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="05975-118">Click Create configuration.</span></span>
4. <span data-ttu-id="05975-119">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="05975-119">Click Designer.</span></span>
    * <span data-ttu-id="05975-120">Öppna ER-designern för att ange strukturen på datamodellen för den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="05975-120">Open the ER designer to specify the structure of data model of this configuration.</span></span>  
    * <span data-ttu-id="05975-121">Anta att vi utformar datamodellen för betalningens företagsdomän till att stödja två betalningsmetoder – kreditöverföring och autogiro.</span><span class="sxs-lookup"><span data-stu-id="05975-121">Assume that we design the data model for payments business domain to support 2 payment methods – credit transfer and direct debit ones.</span></span>  
5. <span data-ttu-id="05975-122">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-122">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="05975-123">Skriv "Payments – credit transfer" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="05975-123">In the Name field, type 'Payments – credit transfer'.</span></span>
    * <span data-ttu-id="05975-124">Betalningar - kreditöverföring</span><span class="sxs-lookup"><span data-stu-id="05975-124">Payments – credit transfer</span></span>  
7. <span data-ttu-id="05975-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="05975-125">Click Add.</span></span>
8. <span data-ttu-id="05975-126">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-126">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="05975-127">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="05975-127">In the New node as a field, enter 'Model root'.</span></span>
10. <span data-ttu-id="05975-128">Skriv "Payments – direct debit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="05975-128">In the Name field, type 'Payments – direct debit'.</span></span>
    * <span data-ttu-id="05975-129">Betalningar - autogirobetalningar</span><span class="sxs-lookup"><span data-stu-id="05975-129">Payments – direct debit</span></span>  
11. <span data-ttu-id="05975-130">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="05975-130">Click Add.</span></span>
12. <span data-ttu-id="05975-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="05975-131">Click Save.</span></span>
13. <span data-ttu-id="05975-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05975-132">Close the page.</span></span>
14. <span data-ttu-id="05975-133">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="05975-133">Click Change status.</span></span>
    * <span data-ttu-id="05975-134">Slutför utkastversionen av modellen för att göra den tillgänglig i nya modellmappningar och format.</span><span class="sxs-lookup"><span data-stu-id="05975-134">Complete the draft version of the model to make it available in new model mappings and formats.</span></span>  
15. <span data-ttu-id="05975-135">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="05975-135">Click Complete.</span></span>
16. <span data-ttu-id="05975-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="05975-136">Click OK.</span></span>

## <a name="start-to-enter-a-new-er-format-configuration"></a><span data-ttu-id="05975-137">Börja ange en ny ER-formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="05975-137">Start to enter a new ER format configuration</span></span>
1. <span data-ttu-id="05975-138">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="05975-139">Ange "Format based on data model Payment model (fictitious)" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="05975-139">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="05975-140">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="05975-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="05975-141">Observera att alla rotobjekt i den valda datamodellen kan väljas som datamodelldefinition.</span><span class="sxs-lookup"><span data-stu-id="05975-141">Note that all root items of the selected data model are currently available for selection as a data model definition.</span></span> <span data-ttu-id="05975-142">Du kan fortsätta att utforma formatet genom att använda de rotobjekt som behövs för datamodellen.</span><span class="sxs-lookup"><span data-stu-id="05975-142">You can continue to design your format by using any of the required root items of the data model.</span></span> <span data-ttu-id="05975-143">Du kan fortsätta även om det saknas en modellmappning för valda rotobjektet.</span><span class="sxs-lookup"><span data-stu-id="05975-143">A missing model mapping for the selected root item doesn't prevent you from continuing.</span></span>  
4. <span data-ttu-id="05975-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05975-144">Close the page.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="05975-145">Lägg till en ny konfiguration för ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="05975-145">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="05975-146">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-146">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="05975-147">Ange "Model Mapping based on data model Payment model (fictitious)" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="05975-147">In the New field, enter 'Model Mapping based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="05975-148">Skriv "Payment model mappings (fictitious)" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="05975-148">In the Name field, type 'Payment model mappings (fictitious)'.</span></span>
    * <span data-ttu-id="05975-149">Betalningsmodellmappningar (fiktiv)</span><span class="sxs-lookup"><span data-stu-id="05975-149">Payment model mappings (fictitious)</span></span>  
4. <span data-ttu-id="05975-150">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="05975-150">In the Data model definition field, enter or select a value.</span></span>
5. <span data-ttu-id="05975-151">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="05975-151">Click Create configuration.</span></span>

## <a name="design-er-model-mappings"></a><span data-ttu-id="05975-152">Utforma ER-modellmappningar</span><span class="sxs-lookup"><span data-stu-id="05975-152">Design ER model mappings</span></span>
1. <span data-ttu-id="05975-153">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="05975-153">Click Designer.</span></span>
    * <span data-ttu-id="05975-154">Använd ER-designern om du vill ange modellmappningar för de nödvändiga rotobjekten.</span><span class="sxs-lookup"><span data-stu-id="05975-154">Use the ER designer to specify the model mappings for the required root items.</span></span>  
2. <span data-ttu-id="05975-155">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="05975-155">Click Designer.</span></span>
    * <span data-ttu-id="05975-156">Simulera inställningen för den valda modellmappningen för den valda modellens rotobjekt.</span><span class="sxs-lookup"><span data-stu-id="05975-156">Simulate setting of selected model mapping for the selected model's root item.</span></span>  
3. <span data-ttu-id="05975-157">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="05975-157">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
4. <span data-ttu-id="05975-158">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="05975-158">Click Add root.</span></span>
5. <span data-ttu-id="05975-159">Skriv "Ledger" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="05975-159">In the Name field, type 'Ledger'.</span></span>
6. <span data-ttu-id="05975-160">Skriv "LedgerJournalTrans" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="05975-160">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="05975-161">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="05975-161">LedgerJournalTrans</span></span>  
7. <span data-ttu-id="05975-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="05975-162">Click OK.</span></span>
8. <span data-ttu-id="05975-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="05975-163">Click Save.</span></span>
9. <span data-ttu-id="05975-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05975-164">Close the page.</span></span>
10. <span data-ttu-id="05975-165">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05975-165">Close the page.</span></span>

## <a name="start-to-enter-another-new-er-format-configuration"></a><span data-ttu-id="05975-166">Börja ange en till ny ER-formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="05975-166">Start to enter another new ER format configuration</span></span>
1. <span data-ttu-id="05975-167">Välj "Payment model (fictitious)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="05975-167">In the tree, select 'Payment model (fictitious)'.</span></span>
2. <span data-ttu-id="05975-168">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="05975-168">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="05975-169">Ange "Format based on data model Payment model (fictitious)" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="05975-169">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
4. <span data-ttu-id="05975-170">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="05975-170">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="05975-171">Observera att det nu bara finns ett rotobjekt tillgängligt att mappa till programmets datakällor.</span><span class="sxs-lookup"><span data-stu-id="05975-171">Note that now only one root item is available to map to the application data sources.</span></span> <span data-ttu-id="05975-172">När minst en modellmappning har tagits i bruk kan bara modellens rotobjekt som är mappade till programmet datakällor väljas som modelldefinition när ER-formatet läggs till.</span><span class="sxs-lookup"><span data-stu-id="05975-172">When at least one model mapping is introduced, only the model's root items that are mapped to application data sources can be selected as a model definition while the ER format is added.</span></span>   
5. <span data-ttu-id="05975-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05975-173">Close the page.</span></span>

