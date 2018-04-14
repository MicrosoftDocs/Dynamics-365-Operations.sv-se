--- 
title: "Ställ in elektroniska signaturer"
description: "Använd den här proceduren för att konfigurera elektroniska signaturer."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d57fc2bcc514f7be8d6edffca5ada0b91aadf073
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-electronic-signatures"></a><span data-ttu-id="8d464-103">Ställ in elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="8d464-103">Set up electronic signatures</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d464-104">Använd den här proceduren för att konfigurera elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-104">Use this procedure to set up electronic signatures.</span></span> <span data-ttu-id="8d464-105">En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess.</span><span class="sxs-lookup"><span data-stu-id="8d464-105">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="8d464-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT.</span><span class="sxs-lookup"><span data-stu-id="8d464-106">The demo data company used to create this procedure is DAT.</span></span>


## <a name="enable-the-electronic-signature-configuration-key"></a><span data-ttu-id="8d464-107">Aktivera konfigurationsnyckeln för elektronisk signatur</span><span class="sxs-lookup"><span data-stu-id="8d464-107">Enable the Electronic signature configuration key</span></span>
1. <span data-ttu-id="8d464-108">Gå till Systemadministration > Inställningar > Licenskonfigurering.</span><span class="sxs-lookup"><span data-stu-id="8d464-108">Go to System administration > Setup > License configuration.</span></span>
2. <span data-ttu-id="8d464-109">Utöka Administration i trädet.</span><span class="sxs-lookup"><span data-stu-id="8d464-109">In the tree, expand 'Administration'.</span></span>
    * <span data-ttu-id="8d464-110">Kontrollera att kryssrutan Elektronisk signatur är markerad.</span><span class="sxs-lookup"><span data-stu-id="8d464-110">Verify that the Electronic signature check box is selected.</span></span>  
    * <span data-ttu-id="8d464-111">Om kryssrutan Elektronisk signatur inte markeras måste du aktivera underhållsläge.</span><span class="sxs-lookup"><span data-stu-id="8d464-111">If the Electronic signature check box is not selected, you must enable maintenance mode.</span></span> <span data-ttu-id="8d464-112">Underhållsläget kan aktiveras i den här miljön genom att ett underhållsjobb körs från Lifecycle Services eller genom att verktyget Deployment.Setup används lokalt.</span><span class="sxs-lookup"><span data-stu-id="8d464-112">Maintenance mode can be enabled in this environment by running a maintenance job from Lifecycle Services, or by using the Deployment.Setup tool locally.</span></span>  
3. <span data-ttu-id="8d464-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d464-113">Close the page.</span></span>

## <a name="set-up-electronic-signature-parameters"></a><span data-ttu-id="8d464-114">Ställ in parametrar för elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="8d464-114">Set up electronic signature parameters</span></span>
1. <span data-ttu-id="8d464-115">Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Parametrar för elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-115">Go to Organization administration > Setup > Electronic signature > Electronic signature parameters.</span></span>
2. <span data-ttu-id="8d464-116">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8d464-116">Click Edit.</span></span>
3. <span data-ttu-id="8d464-117">Ange ett värde i fältet Meddelande.</span><span class="sxs-lookup"><span data-stu-id="8d464-117">In the Notice field, type a value.</span></span>
    * <span data-ttu-id="8d464-118">Ange det meddelande som ska visas för undertecknarna när en signatur begärs.</span><span class="sxs-lookup"><span data-stu-id="8d464-118">Enter the notice that signers will receive when a signature is requested.</span></span> <span data-ttu-id="8d464-119">Du kan ange vilken text du vill.</span><span class="sxs-lookup"><span data-stu-id="8d464-119">You can enter any text.</span></span> <span data-ttu-id="8d464-120">I normalfallet beskriver denna text för användaren vad det innebär att signera ett dokument elektroniskt.</span><span class="sxs-lookup"><span data-stu-id="8d464-120">Typically, this text tells the user what it means to sign a document electronically.</span></span>  
    * <span data-ttu-id="8d464-121">Om du vill ange meddelandetexten på ytterligare språk, klicka på knappen Översättningar.</span><span class="sxs-lookup"><span data-stu-id="8d464-121">If you want to enter the Notice text in additional languages, click the Translations button.</span></span>  
4. <span data-ttu-id="8d464-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8d464-122">Click Save.</span></span>
5. <span data-ttu-id="8d464-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d464-123">Close the page.</span></span>

## <a name="set-up-reason-codes-for-electronic-signatures"></a><span data-ttu-id="8d464-124">Ställ in orsakskoder för elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="8d464-124">Set up reason codes for electronic signatures</span></span>
1. <span data-ttu-id="8d464-125">Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Orsakskoder för elektronisk signatur.</span><span class="sxs-lookup"><span data-stu-id="8d464-125">Go to Organization administration > Setup > Electronic signature > Electronic signature reason codes.</span></span>
2. <span data-ttu-id="8d464-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8d464-126">Click New.</span></span>
    * <span data-ttu-id="8d464-127">Du måste ange orsakskoder innan du använder elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-127">You must set up reason codes before using electronic signatures.</span></span> <span data-ttu-id="8d464-128">En giltig orsakskod krävs för att ett dokument ska kunna undertecknas.</span><span class="sxs-lookup"><span data-stu-id="8d464-128">A valid reason code is required when signing a document.</span></span>     <span data-ttu-id="8d464-129">En undertecknare väljer en orsakskod för att ange syftet med en elektronisk signatur.</span><span class="sxs-lookup"><span data-stu-id="8d464-129">A signer selects a reason code to indicate the purpose of an electronic signature.</span></span> <span data-ttu-id="8d464-130">En orsakskod kan till exempel användas för att visa juridiskt godkännande.</span><span class="sxs-lookup"><span data-stu-id="8d464-130">For example, a reason code could be used to indicate legal approval.</span></span>  
3. <span data-ttu-id="8d464-131">Skriv ett värde i fältet Orsak.</span><span class="sxs-lookup"><span data-stu-id="8d464-131">In the Reason code field, type a value.</span></span>
4. <span data-ttu-id="8d464-132">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8d464-132">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8d464-133">Ange ytterligare orsakskoder, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="8d464-133">Enter additional reason codes, if needed.</span></span>  
5. <span data-ttu-id="8d464-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8d464-134">Click Save.</span></span>
6. <span data-ttu-id="8d464-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d464-135">Close the page.</span></span>

## <a name="require-electronic-signatures-for-existing-processes"></a><span data-ttu-id="8d464-136">Kräv elektroniska signaturer för befintliga processer</span><span class="sxs-lookup"><span data-stu-id="8d464-136">Require electronic signatures for existing processes</span></span>
1. <span data-ttu-id="8d464-137">Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Krav för elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-137">Go to Organization administration > Setup > Electronic signature > Electronic signature requirements.</span></span>
2. <span data-ttu-id="8d464-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8d464-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8d464-139">Välj en process som kräver elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-139">Select a process that requires electronic signatures.</span></span>  
3. <span data-ttu-id="8d464-140">Markera eller avmarkera kryssrutan Signatur krävs.</span><span class="sxs-lookup"><span data-stu-id="8d464-140">Select or clear the Signature required check box.</span></span>
    * <span data-ttu-id="8d464-141">Upprepa de här stegen för de olika processer som kräver elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-141">Repeat these steps for each process that requires electronic signatures.</span></span>  
4. <span data-ttu-id="8d464-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8d464-142">Click Save.</span></span>

## <a name="create-a-custom-requirement-for-electronic-signatures"></a><span data-ttu-id="8d464-143">Skapa ett anpassat krav för elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="8d464-143">Create a custom requirement for electronic signatures</span></span>
1. <span data-ttu-id="8d464-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8d464-144">Click New.</span></span>
2. <span data-ttu-id="8d464-145">Markera eller avmarkera kryssrutan Signatur krävs.</span><span class="sxs-lookup"><span data-stu-id="8d464-145">Select or clear the Signature required check box.</span></span>
3. <span data-ttu-id="8d464-146">I fältet Namn, ange ett namn för processen som kräver elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="8d464-146">In the Name field, enter a name for the process that requires electronic signatures.</span></span>
4. <span data-ttu-id="8d464-147">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tabellnamn.</span><span class="sxs-lookup"><span data-stu-id="8d464-147">In the Table name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8d464-148">I listan, sök efter och välj den tabell där de data som måste signeras är lagrade.</span><span class="sxs-lookup"><span data-stu-id="8d464-148">In the list, find and select the table where the data that must be signed is stored.</span></span>
6. <span data-ttu-id="8d464-149">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8d464-149">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="8d464-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fältnamn.</span><span class="sxs-lookup"><span data-stu-id="8d464-150">In the Field name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="8d464-151">I listan, hitta och välj det fält i registret som du vill övervaka.</span><span class="sxs-lookup"><span data-stu-id="8d464-151">In the list, find and select the field in the table that you want to monitor.</span></span>
9. <span data-ttu-id="8d464-152">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8d464-152">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8d464-153">Ange när en signatur är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="8d464-153">Specify when a signature is required.</span></span>     <span data-ttu-id="8d464-154">Välj Alltid om en signatur krävs när data i fältet ändras.</span><span class="sxs-lookup"><span data-stu-id="8d464-154">Select Always if a signature is required when the data in the field changes.</span></span>     <span data-ttu-id="8d464-155">Välj Endast om du vill ange att en signatur enbart krävs under vissa förhållanden.</span><span class="sxs-lookup"><span data-stu-id="8d464-155">Select Only if a signature is required only under certain conditions.</span></span> <span data-ttu-id="8d464-156">Om du väljer Endast måste du även välja ett av följande alternativ: När en post infogas, När en post uppdateras eller När en post tas bort.</span><span class="sxs-lookup"><span data-stu-id="8d464-156">If you select Only, you must also select one of the following options: When a record is inserted, When a record is updated, or When a record is deleted.</span></span>  
10. <span data-ttu-id="8d464-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8d464-157">Click Save.</span></span>
11. <span data-ttu-id="8d464-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d464-158">Close the page.</span></span>


