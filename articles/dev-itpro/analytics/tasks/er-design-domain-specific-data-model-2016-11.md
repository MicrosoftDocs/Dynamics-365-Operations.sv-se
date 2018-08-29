--- 
title: "Utforma domänspecifika datamodeller"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.openlocfilehash: c59bdea789c4eafd2443a5d1cf802768259858c6
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="design-domain-specific-data-models"></a><span data-ttu-id="f495a-103">Utforma domänspecifika datamodeller</span><span class="sxs-lookup"><span data-stu-id="f495a-103">Design domain-specific data models</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f495a-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="f495a-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="f495a-105">Den här datamodellen ska senare användas som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="f495a-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="f495a-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="f495a-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="f495a-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="f495a-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="f495a-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f495a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f495a-109">Välj konfigurationsleverantören för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="f495a-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="f495a-110">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="f495a-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="f495a-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="f495a-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="f495a-112">Du skapar en konfiguration som innehåller en datamodell för elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="f495a-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="f495a-113">Den här datamodellen ska användas senare som en datakälla när du skapar formatet för betalningsdokumenten.</span><span class="sxs-lookup"><span data-stu-id="f495a-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="f495a-114">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="f495a-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="f495a-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="f495a-116">Skriv "Betalningar (förenklad modell)" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="f495a-117">Betalningar (förenklad modell)</span><span class="sxs-lookup"><span data-stu-id="f495a-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="f495a-118">Skriv "Konfiguration av betalningsmodell" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="f495a-119">Konfiguration av betalningsmodell</span><span class="sxs-lookup"><span data-stu-id="f495a-119">Payment model configuration</span></span>  
    * <span data-ttu-id="f495a-120">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="f495a-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f495a-121">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f495a-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f495a-122">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="f495a-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="f495a-123">Klicka på "Skapa konfiguration" om du vill slutföra skapandet av konfigurationsuppgiften</span><span class="sxs-lookup"><span data-stu-id="f495a-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="f495a-124">Skapa datamodell</span><span class="sxs-lookup"><span data-stu-id="f495a-124">Create a data model</span></span>
    * <span data-ttu-id="f495a-125">Du skapar en ny datamodell för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f495a-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="f495a-126">Den här konfigurationsversionen ska ha statusen Utkast.</span><span class="sxs-lookup"><span data-stu-id="f495a-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="f495a-127">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f495a-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="f495a-128">Definiera strukturen för en part som deltar i en betalningsprocess</span><span class="sxs-lookup"><span data-stu-id="f495a-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="f495a-129">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="f495a-130">Ange "Part" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="f495a-131">Part</span><span class="sxs-lookup"><span data-stu-id="f495a-131">Party</span></span>  
3. <span data-ttu-id="f495a-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-132">Click Add.</span></span>
4. <span data-ttu-id="f495a-133">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="f495a-134">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="f495a-135">Namn</span><span class="sxs-lookup"><span data-stu-id="f495a-135">Name</span></span>  
6. <span data-ttu-id="f495a-136">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="f495a-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-137">Click Add.</span></span>
8. <span data-ttu-id="f495a-138">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="f495a-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="f495a-139">Part</span><span class="sxs-lookup"><span data-stu-id="f495a-139">Party</span></span>  
9. <span data-ttu-id="f495a-140">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="f495a-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="f495a-141">Definiera bankstrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="f495a-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="f495a-142">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="f495a-143">Skriv "Agent" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="f495a-144">Handläggare</span><span class="sxs-lookup"><span data-stu-id="f495a-144">Agent</span></span>  
3. <span data-ttu-id="f495a-145">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="f495a-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-146">Click Add.</span></span>
5. <span data-ttu-id="f495a-147">Ange "Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="f495a-148">Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär).</span><span class="sxs-lookup"><span data-stu-id="f495a-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="f495a-149">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="f495a-150">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="f495a-151">Namn</span><span class="sxs-lookup"><span data-stu-id="f495a-151">Name</span></span>  
8. <span data-ttu-id="f495a-152">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="f495a-153">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-153">Click Add.</span></span>
10. <span data-ttu-id="f495a-154">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="f495a-155">Skriv "SWIFT" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="f495a-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="f495a-156">SWIFT</span></span>  
12. <span data-ttu-id="f495a-157">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-157">Click Add.</span></span>
13. <span data-ttu-id="f495a-158">Ange "Bankidentifieringskod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="f495a-159">Bankens identifieringskod</span><span class="sxs-lookup"><span data-stu-id="f495a-159">Bank identification code</span></span>  
14. <span data-ttu-id="f495a-160">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="f495a-161">Skriv "RoutingNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="f495a-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="f495a-162">RoutingNumber</span></span>  
16. <span data-ttu-id="f495a-163">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-163">Click Add.</span></span>
17. <span data-ttu-id="f495a-164">Ange "Ruttnummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="f495a-165">Clearingnummer</span><span class="sxs-lookup"><span data-stu-id="f495a-165">Routing number</span></span>  
18. <span data-ttu-id="f495a-166">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="f495a-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="f495a-167">Definiera bankkontostrukturen för den här modellen</span><span class="sxs-lookup"><span data-stu-id="f495a-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="f495a-168">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="f495a-169">Skriv "Konto" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="f495a-170">Konto</span><span class="sxs-lookup"><span data-stu-id="f495a-170">Account</span></span>  
3. <span data-ttu-id="f495a-171">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="f495a-172">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-172">Click Add.</span></span>
5. <span data-ttu-id="f495a-173">Ange "Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="f495a-174">Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank).</span><span class="sxs-lookup"><span data-stu-id="f495a-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="f495a-175">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="f495a-176">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="f495a-177">Valuta</span><span class="sxs-lookup"><span data-stu-id="f495a-177">Currency</span></span>  
8. <span data-ttu-id="f495a-178">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="f495a-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-179">Click Add.</span></span>
10. <span data-ttu-id="f495a-180">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="f495a-181">Valutakod</span><span class="sxs-lookup"><span data-stu-id="f495a-181">Currency code</span></span>  
11. <span data-ttu-id="f495a-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="f495a-183">Skriv "Nummer" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="f495a-184">Nummer</span><span class="sxs-lookup"><span data-stu-id="f495a-184">Number</span></span>  
13. <span data-ttu-id="f495a-185">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-185">Click Add.</span></span>
14. <span data-ttu-id="f495a-186">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="f495a-187">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="f495a-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="f495a-188">IBAN</span></span>  
16. <span data-ttu-id="f495a-189">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-189">Click Add.</span></span>
17. <span data-ttu-id="f495a-190">Ange "Internationellt bankkontonummer" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="f495a-191">Internationellt bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="f495a-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="f495a-192">Definiera betalningsmeddelandestrukturen för kreditöverföringens betalningstyp</span><span class="sxs-lookup"><span data-stu-id="f495a-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="f495a-193">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="f495a-194">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="f495a-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="f495a-195">Skriv "CustomerCreditTransferInitiation" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="f495a-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="f495a-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="f495a-197">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-197">Click Add.</span></span>
5. <span data-ttu-id="f495a-198">Ange "CustomerCreditTransferInitiation" i fältet Sök fält.</span><span class="sxs-lookup"><span data-stu-id="f495a-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="f495a-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="f495a-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="f495a-200">Klicka på Sök föregående.</span><span class="sxs-lookup"><span data-stu-id="f495a-200">Click Find previous.</span></span>
7. <span data-ttu-id="f495a-201">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="f495a-202">Skriv "MessageIdentification" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="f495a-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="f495a-203">MessageIdentification</span></span>  
9. <span data-ttu-id="f495a-204">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-204">Click Add.</span></span>
10. <span data-ttu-id="f495a-205">Ange "Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="f495a-206">Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="f495a-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="f495a-207">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="f495a-208">Skriv "ProcessingDateTime" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="f495a-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="f495a-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="f495a-210">Välj "DateTime" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="f495a-211">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-211">Click Add.</span></span>
15. <span data-ttu-id="f495a-212">Ange "Datum och tid då betalningsmeddelandet skapades" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="f495a-213">Datum och tid då betalningsmeddelandet skapades.</span><span class="sxs-lookup"><span data-stu-id="f495a-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="f495a-214">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="f495a-215">Definiera betalningstransaktionsstrukturen för den här modellen.</span><span class="sxs-lookup"><span data-stu-id="f495a-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="f495a-216">Skriv "Betalningar" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="f495a-217">Betalningar</span><span class="sxs-lookup"><span data-stu-id="f495a-217">Payments</span></span>  
18. <span data-ttu-id="f495a-218">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="f495a-219">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-219">Click Add.</span></span>
20. <span data-ttu-id="f495a-220">Ange "Betalningsrader för det aktuella meddelandet" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="f495a-221">Betalningsrader för det aktuella meddelandet</span><span class="sxs-lookup"><span data-stu-id="f495a-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="f495a-222">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="f495a-223">Skriv "Betalningsmottagare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="f495a-224">Betalningsmottagare</span><span class="sxs-lookup"><span data-stu-id="f495a-224">Creditor</span></span>  
23. <span data-ttu-id="f495a-225">Välj "Post" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="f495a-226">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-226">Click Add.</span></span>
25. <span data-ttu-id="f495a-227">Ange "Part till vilken ett penningbelopp ska betalas" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="f495a-228">Part till vilken ett penningbelopp ska betalas.</span><span class="sxs-lookup"><span data-stu-id="f495a-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="f495a-229">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="f495a-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="f495a-230">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="f495a-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="f495a-231">Part</span><span class="sxs-lookup"><span data-stu-id="f495a-231">Party</span></span>  
28. <span data-ttu-id="f495a-232">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="f495a-232">Click Find next.</span></span>
29. <span data-ttu-id="f495a-233">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f495a-233">Click OK.</span></span>
30. <span data-ttu-id="f495a-234">Ange "Betalningar" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="f495a-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="f495a-235">Betalningar</span><span class="sxs-lookup"><span data-stu-id="f495a-235">Payments</span></span>  
31. <span data-ttu-id="f495a-236">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="f495a-236">Click Find next.</span></span>
32. <span data-ttu-id="f495a-237">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="f495a-238">Skriv "Betalare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="f495a-239">Betalare</span><span class="sxs-lookup"><span data-stu-id="f495a-239">Debtor</span></span>  
34. <span data-ttu-id="f495a-240">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-240">Click Add.</span></span>
35. <span data-ttu-id="f495a-241">Ange "Part som är skyldig den (slutliga) borgenären en viss summa pengar" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="f495a-242">Part som är skyldig den (slutliga) borgenären en viss summa pengar.</span><span class="sxs-lookup"><span data-stu-id="f495a-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="f495a-243">Klicka på Byt artikelreferens.</span><span class="sxs-lookup"><span data-stu-id="f495a-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="f495a-244">Ange "Part" i fältet Sök.</span><span class="sxs-lookup"><span data-stu-id="f495a-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="f495a-245">Part</span><span class="sxs-lookup"><span data-stu-id="f495a-245">Party</span></span>  
38. <span data-ttu-id="f495a-246">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="f495a-246">Click Find next.</span></span>
39. <span data-ttu-id="f495a-247">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f495a-247">Click OK.</span></span>
40. <span data-ttu-id="f495a-248">Klicka på Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="f495a-248">Click Find next.</span></span>
41. <span data-ttu-id="f495a-249">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="f495a-250">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="f495a-251">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f495a-251">Description</span></span>  
43. <span data-ttu-id="f495a-252">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="f495a-253">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-253">Click Add.</span></span>
45. <span data-ttu-id="f495a-254">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="f495a-255">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="f495a-256">Valuta</span><span class="sxs-lookup"><span data-stu-id="f495a-256">Currency</span></span>  
47. <span data-ttu-id="f495a-257">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-257">Click Add.</span></span>
48. <span data-ttu-id="f495a-258">Ange "Valutakod" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="f495a-259">Valutakod</span><span class="sxs-lookup"><span data-stu-id="f495a-259">Currency code</span></span>  
49. <span data-ttu-id="f495a-260">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="f495a-261">Skriv "TransactionDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="f495a-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="f495a-262">TransactionDate</span></span>  
51. <span data-ttu-id="f495a-263">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="f495a-264">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-264">Click Add.</span></span>
53. <span data-ttu-id="f495a-265">Ange "Transaktionsdatum" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="f495a-266">Transaktionsdatum</span><span class="sxs-lookup"><span data-stu-id="f495a-266">Transaction date</span></span>  
54. <span data-ttu-id="f495a-267">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="f495a-268">Skriv "InstructedAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="f495a-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="f495a-269">InstructedAmount</span></span>  
56. <span data-ttu-id="f495a-270">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="f495a-271">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-271">Click Add.</span></span>
58. <span data-ttu-id="f495a-272">Ange "Det penningbelopp som ska flyttas mellan gäldenär och borgenär, före avdrag för avgifter"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="f495a-273">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="f495a-274">Det penningbelopp som ska flyttas mellan betalaren och betalningsmottagaren, före avdrag för avgifter.</span><span class="sxs-lookup"><span data-stu-id="f495a-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="f495a-275">Beloppet bör uttryckas i den valuta som har beställts av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="f495a-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="f495a-276">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f495a-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="f495a-277">Skriv "End2EndID" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="f495a-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="f495a-278">End2EndID</span></span>  
61. <span data-ttu-id="f495a-279">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f495a-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="f495a-280">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f495a-280">Click Add.</span></span>
63. <span data-ttu-id="f495a-281">Ange "Den unika identifiering som tilldelats av den initierande parten" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="f495a-282">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f495a-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="f495a-283">Den unika identifiering som har tilldelats av den initierande parten.</span><span class="sxs-lookup"><span data-stu-id="f495a-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="f495a-284">Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan.</span><span class="sxs-lookup"><span data-stu-id="f495a-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="f495a-285">Skriv "PaymentModel" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f495a-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="f495a-286">Namnet PaymentModel justeras med fördefinierade gränssnitt för betalningsformulär.</span><span class="sxs-lookup"><span data-stu-id="f495a-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="f495a-287">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f495a-287">Click Save.</span></span>
66. <span data-ttu-id="f495a-288">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f495a-288">Close the page.</span></span>


