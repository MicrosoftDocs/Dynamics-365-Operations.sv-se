---
title: ER designar domänspecifika datamodeller
description: I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7882a7a17f5736d9d5a11cd91ac963fa89ff12f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042906"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="7a3f3-103">ER designar domänspecifika datamodeller</span><span class="sxs-lookup"><span data-stu-id="7a3f3-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a3f3-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="7a3f3-105">Den här datamodellen ska senare användas som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="7a3f3-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="7a3f3-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="7a3f3-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="7a3f3-109">Välj konfigurationsleverantören för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="7a3f3-110">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
    
2. <span data-ttu-id="7a3f3-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="7a3f3-112">Du skapar en konfiguration som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="7a3f3-113">Den här datamodellen ska användas senare som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="7a3f3-114">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="7a3f3-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="7a3f3-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="7a3f3-116">Skriv "Betalningar (förenklad modell)" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="7a3f3-117">Skriv "Konfiguration av betalningsmodell" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="7a3f3-118">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="7a3f3-119">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="7a3f3-120">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="7a3f3-121">Klicka på "Skapa konfiguration" om du vill slutföra skapandet av konfigurationsuppgiften</span><span class="sxs-lookup"><span data-stu-id="7a3f3-121">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="7a3f3-122">Skapa datamodell</span><span class="sxs-lookup"><span data-stu-id="7a3f3-122">Create a data model</span></span>
<span data-ttu-id="7a3f3-123">Du skapar en ny datamodell för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="7a3f3-124">Den här konfigurationsversionen ska ha statusen Utkast.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="7a3f3-125">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="7a3f3-126">Definiera strukturen för en part som deltar i en betalningsprocess</span><span class="sxs-lookup"><span data-stu-id="7a3f3-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="7a3f3-127">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7a3f3-128">Ange "Part" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="7a3f3-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-129">Click Add.</span></span>
4. <span data-ttu-id="7a3f3-130">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="7a3f3-131">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="7a3f3-132">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="7a3f3-133">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-133">Click Add.</span></span>
8. <span data-ttu-id="7a3f3-134">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="7a3f3-135">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="7a3f3-136">Definiera bankstrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="7a3f3-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="7a3f3-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7a3f3-138">Skriv "Agent" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="7a3f3-139">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="7a3f3-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-140">Click Add.</span></span>
5. <span data-ttu-id="7a3f3-141">Ange "Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="7a3f3-142">Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär).</span><span class="sxs-lookup"><span data-stu-id="7a3f3-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="7a3f3-143">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="7a3f3-144">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="7a3f3-145">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="7a3f3-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-146">Click Add.</span></span>
10. <span data-ttu-id="7a3f3-147">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="7a3f3-148">Skriv "SWIFT" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="7a3f3-149">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-149">Click Add.</span></span>
13. <span data-ttu-id="7a3f3-150">Ange "Bankidentifieringskod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="7a3f3-151">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="7a3f3-152">Skriv "RoutingNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="7a3f3-153">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-153">Click Add.</span></span>
17. <span data-ttu-id="7a3f3-154">Ange "Ruttnummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="7a3f3-155">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="7a3f3-156">Definiera bankkontostrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="7a3f3-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="7a3f3-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7a3f3-158">Skriv "Konto" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="7a3f3-159">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="7a3f3-160">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-160">Click Add.</span></span>
5. <span data-ttu-id="7a3f3-161">Ange "Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="7a3f3-162">Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank).</span><span class="sxs-lookup"><span data-stu-id="7a3f3-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="7a3f3-163">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="7a3f3-164">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="7a3f3-165">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="7a3f3-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-166">Click Add.</span></span>
10. <span data-ttu-id="7a3f3-167">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="7a3f3-168">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="7a3f3-169">Skriv "Nummer" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="7a3f3-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-170">Click Add.</span></span>
14. <span data-ttu-id="7a3f3-171">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="7a3f3-172">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="7a3f3-173">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-173">Click Add.</span></span>
17. <span data-ttu-id="7a3f3-174">Ange "Internationellt bankkontonummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="7a3f3-175">Definiera betalningsmeddelandestrukturen för kreditöverföringens betalningstyp</span><span class="sxs-lookup"><span data-stu-id="7a3f3-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="7a3f3-176">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="7a3f3-177">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="7a3f3-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="7a3f3-178">Skriv "CustomerCreditTransferInitiation" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="7a3f3-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-179">Click Add.</span></span>
5. <span data-ttu-id="7a3f3-180">Ange "CustomerCreditTransferInitiation" i fältet Sök fält.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="7a3f3-181">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-181">Click Find previous.</span></span>
7. <span data-ttu-id="7a3f3-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="7a3f3-183">Skriv "MessageIdentification" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="7a3f3-184">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-184">Click Add.</span></span>
10. <span data-ttu-id="7a3f3-185">Ange "Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="7a3f3-186">Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="7a3f3-187">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="7a3f3-188">Skriv "ProcessingDateTime" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="7a3f3-189">Välj "DateTime" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="7a3f3-190">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-190">Click Add.</span></span>
15. <span data-ttu-id="7a3f3-191">Ange "Datum och tid då betalningsmeddelandet skapades" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="7a3f3-192">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="7a3f3-193">Definiera betalningstransaktionsstrukturen för den här modellen.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="7a3f3-194">Skriv "Betalningar" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="7a3f3-195">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="7a3f3-196">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-196">Click Add.</span></span>
20. <span data-ttu-id="7a3f3-197">Ange "Betalningsrader för det aktuella meddelandet" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="7a3f3-198">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="7a3f3-199">Skriv "Betalningsmottagare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="7a3f3-200">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="7a3f3-201">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-201">Click Add.</span></span>
25. <span data-ttu-id="7a3f3-202">Ange "Part till vilken ett penningbelopp ska betalas" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="7a3f3-203">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="7a3f3-204">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="7a3f3-205">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-205">Click Find next.</span></span>
29. <span data-ttu-id="7a3f3-206">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-206">Click OK.</span></span>
30. <span data-ttu-id="7a3f3-207">Ange "Betalningar" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="7a3f3-208">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-208">Click Find next.</span></span>
32. <span data-ttu-id="7a3f3-209">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="7a3f3-210">Skriv "Betalare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="7a3f3-211">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-211">Click Add.</span></span>
35. <span data-ttu-id="7a3f3-212">Ange "Part som är skyldig den (slutliga) borgenären en viss summa pengar" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="7a3f3-213">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="7a3f3-214">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="7a3f3-215">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-215">Click Find next.</span></span>
39. <span data-ttu-id="7a3f3-216">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-216">Click OK.</span></span>
40. <span data-ttu-id="7a3f3-217">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-217">Click Find next.</span></span>
41. <span data-ttu-id="7a3f3-218">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="7a3f3-219">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="7a3f3-220">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="7a3f3-221">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-221">Click Add.</span></span>
45. <span data-ttu-id="7a3f3-222">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="7a3f3-223">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="7a3f3-224">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-224">Click Add.</span></span>
48. <span data-ttu-id="7a3f3-225">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="7a3f3-226">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="7a3f3-227">Skriv "TransactionDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="7a3f3-228">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="7a3f3-229">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-229">Click Add.</span></span>
53. <span data-ttu-id="7a3f3-230">Ange "Transaktionsdatum" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="7a3f3-231">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="7a3f3-232">Skriv "InstructedAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="7a3f3-233">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="7a3f3-234">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-234">Click Add.</span></span>
58. <span data-ttu-id="7a3f3-235">Ange "Det penningbelopp som ska flyttas mellan gäldenär och borgenär, före avdrag för avgifter"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="7a3f3-236">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="7a3f3-237">Det penningbelopp som ska flyttas mellan betalaren och betalningsmottagaren, före avdrag för avgifter.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="7a3f3-238">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="7a3f3-239">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="7a3f3-240">Skriv "End2EndID" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="7a3f3-241">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="7a3f3-242">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-242">Click Add.</span></span>
63. <span data-ttu-id="7a3f3-243">Ange "Den unika identifiering som tilldelats av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="7a3f3-244">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="7a3f3-245">Skriv "PaymentModel" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="7a3f3-246">Namnet PaymentModel justeras med fördefinierade gränssnitt för betalningsformulär.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="7a3f3-247">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-247">Click Save.</span></span>
66. <span data-ttu-id="7a3f3-248">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-248">Close the page.</span></span>

