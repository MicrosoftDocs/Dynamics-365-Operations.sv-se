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
ms.openlocfilehash: 0d66cc69da08478ceb931fab594da51bafcacc38
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185093"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="5fa60-103">ER designar domänspecifika datamodeller</span><span class="sxs-lookup"><span data-stu-id="5fa60-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5fa60-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="5fa60-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="5fa60-105">Den här datamodellen ska senare användas som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="5fa60-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="5fa60-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="5fa60-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="5fa60-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="5fa60-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="5fa60-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="5fa60-109">Välj konfigurationsleverantören för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5fa60-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="5fa60-110">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="5fa60-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="5fa60-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="5fa60-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="5fa60-112">Du skapar en konfiguration som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="5fa60-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="5fa60-113">Den här datamodellen ska användas senare som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="5fa60-114">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="5fa60-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="5fa60-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="5fa60-116">Skriv "Betalningar (förenklad modell)" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="5fa60-117">Betalningar (förenklad modell)</span><span class="sxs-lookup"><span data-stu-id="5fa60-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="5fa60-118">Skriv "Konfiguration av betalningsmodell" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="5fa60-119">Konfiguration av betalningsmodell</span><span class="sxs-lookup"><span data-stu-id="5fa60-119">Payment model configuration</span></span>  
    * <span data-ttu-id="5fa60-120">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="5fa60-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="5fa60-121">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="5fa60-122">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="5fa60-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="5fa60-123">Klicka på "Skapa konfiguration" om du vill slutföra skapandet av konfigurationsuppgiften</span><span class="sxs-lookup"><span data-stu-id="5fa60-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="5fa60-124">Skapa datamodell</span><span class="sxs-lookup"><span data-stu-id="5fa60-124">Create a data model</span></span>
    * <span data-ttu-id="5fa60-125">Du skapar en ny datamodell för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="5fa60-126">Den här konfigurationsversionen ska ha statusen Utkast.</span><span class="sxs-lookup"><span data-stu-id="5fa60-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="5fa60-127">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="5fa60-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="5fa60-128">Definiera strukturen för en part som deltar i en betalningsprocess</span><span class="sxs-lookup"><span data-stu-id="5fa60-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="5fa60-129">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5fa60-130">Ange "Part" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="5fa60-131">Part</span><span class="sxs-lookup"><span data-stu-id="5fa60-131">Party</span></span>  
3. <span data-ttu-id="5fa60-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-132">Click Add.</span></span>
4. <span data-ttu-id="5fa60-133">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="5fa60-134">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="5fa60-135">Namn</span><span class="sxs-lookup"><span data-stu-id="5fa60-135">Name</span></span>  
6. <span data-ttu-id="5fa60-136">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="5fa60-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-137">Click Add.</span></span>
8. <span data-ttu-id="5fa60-138">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="5fa60-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="5fa60-139">Part</span><span class="sxs-lookup"><span data-stu-id="5fa60-139">Party</span></span>  
9. <span data-ttu-id="5fa60-140">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="5fa60-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="5fa60-141">Definiera bankstrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="5fa60-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="5fa60-142">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5fa60-143">Skriv "Agent" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="5fa60-144">Handläggare</span><span class="sxs-lookup"><span data-stu-id="5fa60-144">Agent</span></span>  
3. <span data-ttu-id="5fa60-145">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="5fa60-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-146">Click Add.</span></span>
5. <span data-ttu-id="5fa60-147">Ange "Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="5fa60-148">Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär).</span><span class="sxs-lookup"><span data-stu-id="5fa60-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="5fa60-149">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="5fa60-150">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="5fa60-151">Namn</span><span class="sxs-lookup"><span data-stu-id="5fa60-151">Name</span></span>  
8. <span data-ttu-id="5fa60-152">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="5fa60-153">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-153">Click Add.</span></span>
10. <span data-ttu-id="5fa60-154">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="5fa60-155">Skriv "SWIFT" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="5fa60-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="5fa60-156">SWIFT</span></span>  
12. <span data-ttu-id="5fa60-157">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-157">Click Add.</span></span>
13. <span data-ttu-id="5fa60-158">Ange "Bankidentifieringskod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="5fa60-159">Bankens identifieringskod</span><span class="sxs-lookup"><span data-stu-id="5fa60-159">Bank identification code</span></span>  
14. <span data-ttu-id="5fa60-160">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="5fa60-161">Skriv "RoutingNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="5fa60-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="5fa60-162">RoutingNumber</span></span>  
16. <span data-ttu-id="5fa60-163">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-163">Click Add.</span></span>
17. <span data-ttu-id="5fa60-164">Ange "Ruttnummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="5fa60-165">Clearingnummer</span><span class="sxs-lookup"><span data-stu-id="5fa60-165">Routing number</span></span>  
18. <span data-ttu-id="5fa60-166">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="5fa60-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="5fa60-167">Definiera bankkontostrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="5fa60-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="5fa60-168">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5fa60-169">Skriv "Konto" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="5fa60-170">Konto</span><span class="sxs-lookup"><span data-stu-id="5fa60-170">Account</span></span>  
3. <span data-ttu-id="5fa60-171">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="5fa60-172">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-172">Click Add.</span></span>
5. <span data-ttu-id="5fa60-173">Ange "Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="5fa60-174">Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank).</span><span class="sxs-lookup"><span data-stu-id="5fa60-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="5fa60-175">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="5fa60-176">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="5fa60-177">Valuta</span><span class="sxs-lookup"><span data-stu-id="5fa60-177">Currency</span></span>  
8. <span data-ttu-id="5fa60-178">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="5fa60-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-179">Click Add.</span></span>
10. <span data-ttu-id="5fa60-180">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="5fa60-181">Valutakod</span><span class="sxs-lookup"><span data-stu-id="5fa60-181">Currency code</span></span>  
11. <span data-ttu-id="5fa60-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="5fa60-183">Skriv "Nummer" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="5fa60-184">Nummer</span><span class="sxs-lookup"><span data-stu-id="5fa60-184">Number</span></span>  
13. <span data-ttu-id="5fa60-185">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-185">Click Add.</span></span>
14. <span data-ttu-id="5fa60-186">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="5fa60-187">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="5fa60-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="5fa60-188">IBAN</span></span>  
16. <span data-ttu-id="5fa60-189">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-189">Click Add.</span></span>
17. <span data-ttu-id="5fa60-190">Ange "Internationellt bankkontonummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="5fa60-191">Internationellt bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="5fa60-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="5fa60-192">Definiera betalningsmeddelandestrukturen för kreditöverföringens betalningstyp</span><span class="sxs-lookup"><span data-stu-id="5fa60-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="5fa60-193">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5fa60-194">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="5fa60-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="5fa60-195">Skriv "CustomerCreditTransferInitiation" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="5fa60-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="5fa60-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="5fa60-197">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-197">Click Add.</span></span>
5. <span data-ttu-id="5fa60-198">Ange "CustomerCreditTransferInitiation" i fältet Sök fält.</span><span class="sxs-lookup"><span data-stu-id="5fa60-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="5fa60-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="5fa60-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="5fa60-200">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="5fa60-200">Click Find previous.</span></span>
7. <span data-ttu-id="5fa60-201">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="5fa60-202">Skriv "MessageIdentification" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="5fa60-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="5fa60-203">MessageIdentification</span></span>  
9. <span data-ttu-id="5fa60-204">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-204">Click Add.</span></span>
10. <span data-ttu-id="5fa60-205">Ange "Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="5fa60-206">Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="5fa60-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="5fa60-207">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="5fa60-208">Skriv "ProcessingDateTime" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="5fa60-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="5fa60-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="5fa60-210">Välj "DateTime" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="5fa60-211">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-211">Click Add.</span></span>
15. <span data-ttu-id="5fa60-212">Ange "Datum och tid då betalningsmeddelandet skapades" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="5fa60-213">Datum och tid då betalningsmeddelandet skapades.</span><span class="sxs-lookup"><span data-stu-id="5fa60-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="5fa60-214">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="5fa60-215">Definiera betalningstransaktionsstrukturen för den här modellen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="5fa60-216">Skriv "Betalningar" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="5fa60-217">Betalningar</span><span class="sxs-lookup"><span data-stu-id="5fa60-217">Payments</span></span>  
18. <span data-ttu-id="5fa60-218">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="5fa60-219">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-219">Click Add.</span></span>
20. <span data-ttu-id="5fa60-220">Ange "Betalningsrader för det aktuella meddelandet" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="5fa60-221">Betalningsrader för det aktuella meddelandet</span><span class="sxs-lookup"><span data-stu-id="5fa60-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="5fa60-222">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="5fa60-223">Skriv "Betalningsmottagare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="5fa60-224">Betalningsmottagare</span><span class="sxs-lookup"><span data-stu-id="5fa60-224">Creditor</span></span>  
23. <span data-ttu-id="5fa60-225">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="5fa60-226">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-226">Click Add.</span></span>
25. <span data-ttu-id="5fa60-227">Ange "Part till vilken ett penningbelopp ska betalas" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="5fa60-228">Part till vilken ett penningbelopp ska betalas.</span><span class="sxs-lookup"><span data-stu-id="5fa60-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="5fa60-229">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="5fa60-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="5fa60-230">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="5fa60-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="5fa60-231">Part</span><span class="sxs-lookup"><span data-stu-id="5fa60-231">Party</span></span>  
28. <span data-ttu-id="5fa60-232">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="5fa60-232">Click Find next.</span></span>
29. <span data-ttu-id="5fa60-233">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5fa60-233">Click OK.</span></span>
30. <span data-ttu-id="5fa60-234">Ange "Betalningar" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="5fa60-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="5fa60-235">Betalningar</span><span class="sxs-lookup"><span data-stu-id="5fa60-235">Payments</span></span>  
31. <span data-ttu-id="5fa60-236">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="5fa60-236">Click Find next.</span></span>
32. <span data-ttu-id="5fa60-237">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="5fa60-238">Skriv "Betalare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="5fa60-239">Betalare</span><span class="sxs-lookup"><span data-stu-id="5fa60-239">Debtor</span></span>  
34. <span data-ttu-id="5fa60-240">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-240">Click Add.</span></span>
35. <span data-ttu-id="5fa60-241">Ange "Part som är skyldig den (slutliga) borgenären en viss summa pengar" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="5fa60-242">Part som är skyldig den (slutliga) borgenären en viss summa pengar.</span><span class="sxs-lookup"><span data-stu-id="5fa60-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="5fa60-243">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="5fa60-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="5fa60-244">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="5fa60-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="5fa60-245">Part</span><span class="sxs-lookup"><span data-stu-id="5fa60-245">Party</span></span>  
38. <span data-ttu-id="5fa60-246">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="5fa60-246">Click Find next.</span></span>
39. <span data-ttu-id="5fa60-247">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5fa60-247">Click OK.</span></span>
40. <span data-ttu-id="5fa60-248">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="5fa60-248">Click Find next.</span></span>
41. <span data-ttu-id="5fa60-249">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="5fa60-250">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="5fa60-251">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5fa60-251">Description</span></span>  
43. <span data-ttu-id="5fa60-252">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="5fa60-253">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-253">Click Add.</span></span>
45. <span data-ttu-id="5fa60-254">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="5fa60-255">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="5fa60-256">Valuta</span><span class="sxs-lookup"><span data-stu-id="5fa60-256">Currency</span></span>  
47. <span data-ttu-id="5fa60-257">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-257">Click Add.</span></span>
48. <span data-ttu-id="5fa60-258">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="5fa60-259">Valutakod</span><span class="sxs-lookup"><span data-stu-id="5fa60-259">Currency code</span></span>  
49. <span data-ttu-id="5fa60-260">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="5fa60-261">Skriv "TransactionDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="5fa60-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="5fa60-262">TransactionDate</span></span>  
51. <span data-ttu-id="5fa60-263">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="5fa60-264">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-264">Click Add.</span></span>
53. <span data-ttu-id="5fa60-265">Ange "Transaktionsdatum" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="5fa60-266">Transaktionsdatum</span><span class="sxs-lookup"><span data-stu-id="5fa60-266">Transaction date</span></span>  
54. <span data-ttu-id="5fa60-267">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="5fa60-268">Skriv "InstructedAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="5fa60-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="5fa60-269">InstructedAmount</span></span>  
56. <span data-ttu-id="5fa60-270">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="5fa60-271">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-271">Click Add.</span></span>
58. <span data-ttu-id="5fa60-272">Ange "Det penningbelopp som ska flyttas mellan gäldenär och borgenär, före avdrag för avgifter"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="5fa60-273">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="5fa60-274">Det penningbelopp som ska flyttas mellan betalaren och betalningsmottagaren, före avdrag för avgifter.</span><span class="sxs-lookup"><span data-stu-id="5fa60-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="5fa60-275">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="5fa60-276">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="5fa60-277">Skriv "End2EndID" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="5fa60-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="5fa60-278">End2EndID</span></span>  
61. <span data-ttu-id="5fa60-279">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="5fa60-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="5fa60-280">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fa60-280">Click Add.</span></span>
63. <span data-ttu-id="5fa60-281">Ange "Den unika identifiering som tilldelats av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="5fa60-282">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fa60-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="5fa60-283">Den unika identifiering som har tilldelats av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="5fa60-284">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="5fa60-285">Skriv "PaymentModel" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fa60-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="5fa60-286">Namnet PaymentModel justeras med fördefinierade gränssnitt för betalningsformulär.</span><span class="sxs-lookup"><span data-stu-id="5fa60-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="5fa60-287">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5fa60-287">Click Save.</span></span>
66. <span data-ttu-id="5fa60-288">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fa60-288">Close the page.</span></span>

