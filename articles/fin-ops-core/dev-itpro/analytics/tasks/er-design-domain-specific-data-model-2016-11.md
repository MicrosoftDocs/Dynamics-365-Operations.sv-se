---
title: ER designar domänspecifika datamodeller
description: I det här avsnittet beskrivs hur du skapar en ny konfiguration av elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 284fad8b6646c35217789cc9936cbe9fe75a03d0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567820"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="7cc73-103">ER designar domänspecifika datamodeller</span><span class="sxs-lookup"><span data-stu-id="7cc73-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7cc73-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7cc73-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="7cc73-105">Den här datamodellen ska senare användas som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="7cc73-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="7cc73-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="7cc73-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="7cc73-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="7cc73-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="7cc73-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7cc73-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="7cc73-109">Välj konfigurationsleverantören för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7cc73-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="7cc73-110">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="7cc73-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="7cc73-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7cc73-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="7cc73-112">Du skapar en konfiguration som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7cc73-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="7cc73-113">Den här datamodellen ska användas senare som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="7cc73-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="7cc73-114">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="7cc73-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="7cc73-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="7cc73-116">Skriv "Betalningar (förenklad modell)" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="7cc73-117">Skriv "Konfiguration av betalningsmodell" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="7cc73-118">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="7cc73-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="7cc73-119">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7cc73-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="7cc73-120">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="7cc73-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="7cc73-121">Klicka på "Skapa konfiguration" om du vill slutföra skapandet av konfigurationsuppgiften</span><span class="sxs-lookup"><span data-stu-id="7cc73-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="7cc73-122">Skapa datamodell</span><span class="sxs-lookup"><span data-stu-id="7cc73-122">Create a data model</span></span>
<span data-ttu-id="7cc73-123">Du skapar en ny datamodell för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7cc73-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="7cc73-124">Den här konfigurationsversionen ska ha statusen Utkast.</span><span class="sxs-lookup"><span data-stu-id="7cc73-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="7cc73-125">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="7cc73-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="7cc73-126">Definiera strukturen för en part som deltar i en betalningsprocess</span><span class="sxs-lookup"><span data-stu-id="7cc73-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="7cc73-127">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7cc73-128">Ange "Part" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="7cc73-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-129">Click Add.</span></span>
4. <span data-ttu-id="7cc73-130">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="7cc73-131">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="7cc73-132">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="7cc73-133">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-133">Click Add.</span></span>
8. <span data-ttu-id="7cc73-134">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7cc73-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="7cc73-135">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7cc73-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="7cc73-136">Definiera bankstrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="7cc73-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="7cc73-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7cc73-138">Skriv "Agent" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="7cc73-139">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="7cc73-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-140">Click Add.</span></span>
5. <span data-ttu-id="7cc73-141">Ange "Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="7cc73-142">Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär).</span><span class="sxs-lookup"><span data-stu-id="7cc73-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="7cc73-143">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="7cc73-144">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="7cc73-145">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="7cc73-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-146">Click Add.</span></span>
10. <span data-ttu-id="7cc73-147">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="7cc73-148">Skriv "SWIFT" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="7cc73-149">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-149">Click Add.</span></span>
13. <span data-ttu-id="7cc73-150">Ange "Bankidentifieringskod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="7cc73-151">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="7cc73-152">Skriv "RoutingNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="7cc73-153">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-153">Click Add.</span></span>
17. <span data-ttu-id="7cc73-154">Ange "Ruttnummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="7cc73-155">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7cc73-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="7cc73-156">Definiera bankkontostrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="7cc73-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="7cc73-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7cc73-158">Skriv "Konto" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="7cc73-159">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="7cc73-160">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-160">Click Add.</span></span>
5. <span data-ttu-id="7cc73-161">Ange "Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="7cc73-162">Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank).</span><span class="sxs-lookup"><span data-stu-id="7cc73-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="7cc73-163">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="7cc73-164">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="7cc73-165">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="7cc73-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-166">Click Add.</span></span>
10. <span data-ttu-id="7cc73-167">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="7cc73-168">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="7cc73-169">Skriv "Nummer" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="7cc73-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-170">Click Add.</span></span>
14. <span data-ttu-id="7cc73-171">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="7cc73-172">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="7cc73-173">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-173">Click Add.</span></span>
17. <span data-ttu-id="7cc73-174">Ange "Internationellt bankkontonummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="7cc73-175">Definiera betalningsmeddelandestrukturen för kreditöverföringens betalningstyp</span><span class="sxs-lookup"><span data-stu-id="7cc73-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="7cc73-176">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7cc73-177">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="7cc73-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="7cc73-178">Skriv "CustomerCreditTransferInitiation" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="7cc73-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-179">Click Add.</span></span>
5. <span data-ttu-id="7cc73-180">Ange "CustomerCreditTransferInitiation" i fältet Sök fält.</span><span class="sxs-lookup"><span data-stu-id="7cc73-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="7cc73-181">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7cc73-181">Click Find previous.</span></span>
7. <span data-ttu-id="7cc73-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="7cc73-183">Skriv "MessageIdentification" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="7cc73-184">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-184">Click Add.</span></span>
10. <span data-ttu-id="7cc73-185">Ange "Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="7cc73-186">Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="7cc73-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="7cc73-187">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="7cc73-188">Skriv "ProcessingDateTime" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="7cc73-189">Välj "DateTime" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="7cc73-190">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-190">Click Add.</span></span>
15. <span data-ttu-id="7cc73-191">Ange "Datum och tid då betalningsmeddelandet skapades" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="7cc73-192">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="7cc73-193">Definiera betalningstransaktionsstrukturen för den här modellen.</span><span class="sxs-lookup"><span data-stu-id="7cc73-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="7cc73-194">Skriv "Betalningar" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="7cc73-195">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="7cc73-196">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-196">Click Add.</span></span>
20. <span data-ttu-id="7cc73-197">Ange "Betalningsrader för det aktuella meddelandet" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="7cc73-198">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="7cc73-199">Skriv "Betalningsmottagare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="7cc73-200">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="7cc73-201">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-201">Click Add.</span></span>
25. <span data-ttu-id="7cc73-202">Ange "Part till vilken ett penningbelopp ska betalas" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="7cc73-203">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="7cc73-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="7cc73-204">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7cc73-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="7cc73-205">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7cc73-205">Click Find next.</span></span>
29. <span data-ttu-id="7cc73-206">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7cc73-206">Click OK.</span></span>
30. <span data-ttu-id="7cc73-207">Ange "Betalningar" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7cc73-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="7cc73-208">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7cc73-208">Click Find next.</span></span>
32. <span data-ttu-id="7cc73-209">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="7cc73-210">Skriv "Betalare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="7cc73-211">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-211">Click Add.</span></span>
35. <span data-ttu-id="7cc73-212">Ange "Part som är skyldig den (slutliga) borgenären en viss summa pengar" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="7cc73-213">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="7cc73-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="7cc73-214">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7cc73-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="7cc73-215">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7cc73-215">Click Find next.</span></span>
39. <span data-ttu-id="7cc73-216">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7cc73-216">Click OK.</span></span>
40. <span data-ttu-id="7cc73-217">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7cc73-217">Click Find next.</span></span>
41. <span data-ttu-id="7cc73-218">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="7cc73-219">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="7cc73-220">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="7cc73-221">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-221">Click Add.</span></span>
45. <span data-ttu-id="7cc73-222">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="7cc73-223">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="7cc73-224">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-224">Click Add.</span></span>
48. <span data-ttu-id="7cc73-225">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="7cc73-226">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="7cc73-227">Skriv "TransactionDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="7cc73-228">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="7cc73-229">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-229">Click Add.</span></span>
53. <span data-ttu-id="7cc73-230">Ange "Transaktionsdatum" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="7cc73-231">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="7cc73-232">Skriv "InstructedAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="7cc73-233">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="7cc73-234">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-234">Click Add.</span></span>
58. <span data-ttu-id="7cc73-235">Ange "Det penningbelopp som ska flyttas mellan gäldenär och borgenär, före avdrag för avgifter"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="7cc73-236">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="7cc73-237">Det penningbelopp som ska flyttas mellan betalaren och betalningsmottagaren, före avdrag för avgifter.</span><span class="sxs-lookup"><span data-stu-id="7cc73-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="7cc73-238">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="7cc73-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="7cc73-239">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="7cc73-240">Skriv "End2EndID" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="7cc73-241">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7cc73-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="7cc73-242">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7cc73-242">Click Add.</span></span>
63. <span data-ttu-id="7cc73-243">Ange "Den unika identifiering som tilldelats av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="7cc73-244">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7cc73-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="7cc73-245">Skriv "PaymentModel" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7cc73-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="7cc73-246">Namnet PaymentModel justeras med fördefinierade gränssnitt för betalningsformulär.</span><span class="sxs-lookup"><span data-stu-id="7cc73-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="7cc73-247">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7cc73-247">Click Save.</span></span>
66. <span data-ttu-id="7cc73-248">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7cc73-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]