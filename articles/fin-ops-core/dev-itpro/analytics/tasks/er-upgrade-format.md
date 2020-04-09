---
title: ER Uppgradera ditt format genom att implementera en ny basversion för det formatet
description: I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan behålla en formatkonfiguration för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52bc276a4a88971a7214fa09087cb1323b91aaf5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143293"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="7ea51-103">ER Uppgradera ditt format genom att implementera en ny basversion för det formatet</span><span class="sxs-lookup"><span data-stu-id="7ea51-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ea51-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan behålla en formatkonfiguration för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="7ea51-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="7ea51-105">I den här proceduren förklaras hur en anpassad version av ett format kan skapas baserat på det format som tas emot från en konfigurationsleverantör (CP).</span><span class="sxs-lookup"><span data-stu-id="7ea51-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="7ea51-106">Den förklarar också hur du antar en ny basversion av det formatet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="7ea51-107">För att slutföra dessa steg måste du först avsluta stegen i procedurerna ”Skapa en konfigurationsleverantör och markera den som aktiv" och "Använd skapade format för att skapa elektroniska handlingar för betalningar".</span><span class="sxs-lookup"><span data-stu-id="7ea51-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="7ea51-108">Dessa steg kan utföras i GBSI-företaget.</span><span class="sxs-lookup"><span data-stu-id="7ea51-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="7ea51-109">Välj formatkonfigurationen för anpassning</span><span class="sxs-lookup"><span data-stu-id="7ea51-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="7ea51-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7ea51-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="7ea51-111">I det här exemplet kommer exempelföretaget Litware, Inc. (https://www.litware.com) att fungera som en konfigurationsleverantör som stöder formatkonfigurationer för elektroniska betalningar för ett angivet land.</span><span class="sxs-lookup"><span data-stu-id="7ea51-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="7ea51-112">Eexempelföretaget Proseware, Inc. (http://www.proseware.com) kommer att fungera som en konsument av formatkonfigurationen som Litware, Inc. tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="7ea51-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="7ea51-113">Proseware, Inc. använder format i vissa regioner för det landet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="7ea51-114">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7ea51-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="7ea51-115">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="7ea51-115">Click Show filters.</span></span>
4. <span data-ttu-id="7ea51-116">Använd följande filter: Ange filtervärdet "BACS (fiktivt, Storbritannien)" i fältet "Namn" med hjälp av filteroperatorn "Börjar med".</span><span class="sxs-lookup"><span data-stu-id="7ea51-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="7ea51-117">Den valda formatkonfigurationen BACS (fiktiv, från Storbritannien) ägs av leverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7ea51-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="7ea51-118">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="7ea51-118">Click Show filters.</span></span>
6. <span data-ttu-id="7ea51-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7ea51-120">Versionen av formatet med statusen avslutad ska användas av Proseware, Inc. för anpassning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="7ea51-121">Skapa en ny konfiguration för ditt anpassade format för elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="7ea51-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="7ea51-122">Proseware, Inc. tog emot version 1.1 av BACS-konfigurationen (fiktiv från Storbritannien) som innehåller det initiala formatet för att skapa elektroniska betalningsdokument från Litware, Inc. i enlighet med deras serviceabonnemang.</span><span class="sxs-lookup"><span data-stu-id="7ea51-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="7ea51-123">Proseware, Inc. vill börja använda detta som standard för deras land, men det krävs en del anpassning för att stödja specifika regionala krav.</span><span class="sxs-lookup"><span data-stu-id="7ea51-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="7ea51-124">Proseware, Inc. vill behålla förmågan att uppgradera ett allmänt format så snart som en ny version av den (med ändringar som stöder nya landsspecifika behov) kommer från Litware, Inc. och de vill utföra denna uppgradering med den lägsta kostnaden.</span><span class="sxs-lookup"><span data-stu-id="7ea51-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="7ea51-125">För att göra detta måste Prosewares, Inc. skapa en konfiguration med Litware Inc. konfiguration BACS (fiktiva UK) som bas.</span><span class="sxs-lookup"><span data-stu-id="7ea51-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="7ea51-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-126">Close the page.</span></span>
2. <span data-ttu-id="7ea51-127">Välj Prosewares Inc. för att göra den till en aktiv leverantör.</span><span class="sxs-lookup"><span data-stu-id="7ea51-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="7ea51-128">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="7ea51-128">Click Set active.</span></span>
4. <span data-ttu-id="7ea51-129">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7ea51-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="7ea51-130">Visa "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="7ea51-131">Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="7ea51-132">Välj konfigurationen (fiktiva UK) från Litware, Inc. Prosewares Inc. kommer att använda 1.1 som bas för din anpassade version.</span><span class="sxs-lookup"><span data-stu-id="7ea51-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="7ea51-133">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="7ea51-134">Detta låter dig skapa en ny konfiguration för ett anpassat betalningsformat.</span><span class="sxs-lookup"><span data-stu-id="7ea51-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="7ea51-135">Ange ”Härled från namn: BACS (UK fiktivt) Litware, Inc.” i fältet Nytt.</span><span class="sxs-lookup"><span data-stu-id="7ea51-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="7ea51-136">Välj alternativet Härled för att bekräfta användningen av BACS (fiktivt UK) som bas för att skapa den anpassade versionen.</span><span class="sxs-lookup"><span data-stu-id="7ea51-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="7ea51-137">Skriv "BACS (fiktiv UK kund) i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7ea51-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="7ea51-138">Skriv "BACS-leverantörsbetalnings (fiktivt, Storbritannien)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="7ea51-139">Den aktiva konfigurationsleverantören (Proseware, Inc.) anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="7ea51-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="7ea51-140">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7ea51-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="7ea51-141">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="7ea51-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="7ea51-142">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="7ea51-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="7ea51-143">Anpassa ditt format för elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="7ea51-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="7ea51-144">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="7ea51-144">Click Designer.</span></span>
2. <span data-ttu-id="7ea51-145">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="7ea51-146">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="7ea51-147">Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="7ea51-148">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="7ea51-149">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="7ea51-150">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7ea51-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="7ea51-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-151">Click OK.</span></span>
9. <span data-ttu-id="7ea51-152">Välj "Xml\Message\Payments\Item\Vendor\Bank\IBAN" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="7ea51-153">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="7ea51-154">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="7ea51-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-155">Click OK.</span></span>
13. <span data-ttu-id="7ea51-156">Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="7ea51-157">Ange "60" i fältet Maximal längd.</span><span class="sxs-lookup"><span data-stu-id="7ea51-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="7ea51-158">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="7ea51-159">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="7ea51-160">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="7ea51-161">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="7ea51-162">Expandera "modell\Betalningar\Betalningsmottagare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="7ea51-163">Välj "model\Payments\Creditor\Account\IBAN" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="7ea51-164">Välj "Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="7ea51-165">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="7ea51-165">Click Bind.</span></span>
23. <span data-ttu-id="7ea51-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ea51-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="7ea51-167">Validera det anpassade formatet</span><span class="sxs-lookup"><span data-stu-id="7ea51-167">Validate the customized format</span></span>
1. <span data-ttu-id="7ea51-168">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-168">Click Validate.</span></span>

    <span data-ttu-id="7ea51-169">Validera det anpassade formatlayoutet och datamappningändringarna för att se till att alla bindningar är ok.</span><span class="sxs-lookup"><span data-stu-id="7ea51-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="7ea51-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="7ea51-171">Ändra statusen för den aktuella versionen av den anpassade formatkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="7ea51-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="7ea51-172">Ändra statusen för den utformade formatkonfigurationen från Utkast till Slutfört för att göra den tillgänglig för generering av betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7ea51-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="7ea51-173">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="7ea51-173">Click Change status.</span></span>

    <span data-ttu-id="7ea51-174">Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="7ea51-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="7ea51-175">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="7ea51-175">Click Complete.</span></span>
3. <span data-ttu-id="7ea51-176">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="7ea51-177">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-177">Click OK.</span></span>
5. <span data-ttu-id="7ea51-178">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7ea51-179">Observera att den skapade konfigurationen sparas som slutförd version 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="7ea51-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="7ea51-180">Det innebär att det är version 1 av det anpassade BACS-formatet (fiktiv kund från Storbritannien) baserat på version 1 av BACS-formatet (fiktiv från Storbritannien) baserat på version 1 av datamodellen Betalningar (förenklad modell).</span><span class="sxs-lookup"><span data-stu-id="7ea51-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="7ea51-181">Testa det anpassade formatet för att skapa betalningsfiler</span><span class="sxs-lookup"><span data-stu-id="7ea51-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="7ea51-182">Slutför stegen i sessionen "Använd skapade format för att generera elektroniska dokument för betalningar" i en parallell Finance and Operations-session.</span><span class="sxs-lookup"><span data-stu-id="7ea51-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="7ea51-183">Välj det BACS-formatet (fiktiv kund från Storbritannien) i parametrar för elektronisk betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="7ea51-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="7ea51-184">Kontrollera att den skapade betalningsfilen innehåller den för en tid eftersom introducerade XML-noden som innehåller IBANkod i korrespondens till regionala kraven.</span><span class="sxs-lookup"><span data-stu-id="7ea51-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="7ea51-185">Uppdatera den befintliga landsspecifika konfigurationen</span><span class="sxs-lookup"><span data-stu-id="7ea51-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="7ea51-186">Litware, Inc. behöver uppdatera BACS-konfigurationen (fiktivt UK) och anta nya landskrav för hantering av formatet för elektroniskt dokument.</span><span class="sxs-lookup"><span data-stu-id="7ea51-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="7ea51-187">Senare kommer detta att bifogas i en ny version av den här konfigurationen som ska erbjudas abonnenter, inklusive Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7ea51-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="7ea51-188">I verkliga tjänsterelaterade processer kan varje ny version av BACS (fiktiv från Storbritannien) importeras av Proseware, Inc. från Litware, Inc. konfigurationers LCS-databas.</span><span class="sxs-lookup"><span data-stu-id="7ea51-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="7ea51-189">I den här proceduren kommer vi att simulera detta genom att uppdatera BACS (fiktiv från Storbritannien) på uppdrag av en tjänsteleverantör.</span><span class="sxs-lookup"><span data-stu-id="7ea51-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="7ea51-190">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-190">Close the page.</span></span>
2. <span data-ttu-id="7ea51-191">Välj leverantören Litware, inc.</span><span class="sxs-lookup"><span data-stu-id="7ea51-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="7ea51-192">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="7ea51-192">Click Set active.</span></span>
4. <span data-ttu-id="7ea51-193">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7ea51-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="7ea51-194">Visa "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="7ea51-195">Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="7ea51-196">Utkastversionen som ägs av Litware, Inc. leverantören BACS (fiktivt UK) för att ta in ändringar som stödjer nya landsspecifika krav.</span><span class="sxs-lookup"><span data-stu-id="7ea51-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="7ea51-197">Lokalisera basformat för elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="7ea51-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="7ea51-198">Anta att det finns nya landsspecifika krav som stöds av Litware, Inc.:</span><span class="sxs-lookup"><span data-stu-id="7ea51-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="7ea51-199">Ett värde för betalningsmottagarens SWFT-kod i varje betalningstransaktion.</span><span class="sxs-lookup"><span data-stu-id="7ea51-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="7ea51-200">En gräns på 100 tecken för textlängden för leverantörens namn i en genereringsfil.</span><span class="sxs-lookup"><span data-stu-id="7ea51-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="7ea51-201">Nya landsspecifika krav</span><span class="sxs-lookup"><span data-stu-id="7ea51-201">New country-specific requirements</span></span>  
- <span data-ttu-id="7ea51-202">Välj utkastversionen av önskad konfiguration för att införa nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="7ea51-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="7ea51-203">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="7ea51-203">Click Designer.</span></span>
2. <span data-ttu-id="7ea51-204">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="7ea51-205">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="7ea51-206">Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="7ea51-207">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="7ea51-208">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="7ea51-209">Skriv "SWIFT" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7ea51-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="7ea51-210">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-210">Click OK.</span></span>
9. <span data-ttu-id="7ea51-211">Välj "Xml\Message\Payments\Item\Vendor\Bank\SWIFT" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="7ea51-212">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="7ea51-213">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="7ea51-214">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-214">Click OK.</span></span>
13. <span data-ttu-id="7ea51-215">Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="7ea51-216">Ange "100" i fältet Maximal längd.</span><span class="sxs-lookup"><span data-stu-id="7ea51-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="7ea51-217">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="7ea51-218">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="7ea51-219">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="7ea51-220">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="7ea51-221">Expandera "modell\Betalningar\Betalningsmottagare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="7ea51-222">Välj "model\Payments\Creditor\Agent\SWIFT" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="7ea51-223">Välj "Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="7ea51-224">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="7ea51-224">Click Bind.</span></span>
23. <span data-ttu-id="7ea51-225">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ea51-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="7ea51-226">Validera det lokaliserade formatet</span><span class="sxs-lookup"><span data-stu-id="7ea51-226">Validate the localized format</span></span>
1. <span data-ttu-id="7ea51-227">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="7ea51-227">Click Validate.</span></span>
2. <span data-ttu-id="7ea51-228">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="7ea51-229">Ändra statusen för den aktuella versionen av basformatkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="7ea51-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="7ea51-230">Ändra status för den uppdaterade basformatkonfigurationen från utkast till slutfört om du vill göra den tillgänglig för generering av betalningdokument och uppdatering av formatkonfigurationer som härleds från den.</span><span class="sxs-lookup"><span data-stu-id="7ea51-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="7ea51-231">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="7ea51-231">Click Change status.</span></span>

    <span data-ttu-id="7ea51-232">Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="7ea51-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="7ea51-233">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="7ea51-233">Click Complete.</span></span>
3. <span data-ttu-id="7ea51-234">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="7ea51-235">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-235">Click OK.</span></span>
5. <span data-ttu-id="7ea51-236">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="7ea51-237">Ändra basversionen för anpassad formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7ea51-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="7ea51-238">Proseware, Inc. informeras att en ny version 1.2 av BACS-konfigurationen (fiktivt UK) är tillgänglig om du vill skapa elektroniska betalningsdokument i enlighet med tillkännagivna landsspecifika krav.</span><span class="sxs-lookup"><span data-stu-id="7ea51-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="7ea51-239">Proseware, Inc. vill börja använda den som standard för landet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="7ea51-240">För att göra detta måste Proseware, Inc. ändra baskonfigurationversionen för den anpassade BACS-konfigurationen för (fiktiv UK kund).</span><span class="sxs-lookup"><span data-stu-id="7ea51-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="7ea51-241">I stället för version 1.1 för BACS (fiktivt UK), använd version 1.2.</span><span class="sxs-lookup"><span data-stu-id="7ea51-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="7ea51-242">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7ea51-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7ea51-243">Välj Prosewares Inc. leverantör för att markera den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="7ea51-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="7ea51-244">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="7ea51-244">Click Set active.</span></span>
4. <span data-ttu-id="7ea51-245">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="7ea51-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="7ea51-246">Visa "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="7ea51-247">Expandera "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="7ea51-248">Välj "Betalningar (förenklad modell)\BACS (UK fiktiv kund)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="7ea51-249">Välj BACS-konfigurationen (fiktiv kund från Storbritannien), som ägs av Proseware Inc.</span><span class="sxs-lookup"><span data-stu-id="7ea51-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="7ea51-250">Använd utkastversionen av den valda konfiguration för att införa nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="7ea51-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="7ea51-251">Klicka på Basera om.</span><span class="sxs-lookup"><span data-stu-id="7ea51-251">Click Rebase.</span></span>

    <span data-ttu-id="7ea51-252">Välj den nya versionen 1.2 av baskonfigurationen som ska användas som ett nytt underlag för att uppdatera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7ea51-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="7ea51-253">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-253">Click OK.</span></span>

    <span data-ttu-id="7ea51-254">Observera att eventuella konflikter har upptäckts mellan sammanslagning av den anpassade version och en ny basversion som representerar en del formatändringar som inte kan sammanslås automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7ea51-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="7ea51-255">Lös basera om konflikter</span><span class="sxs-lookup"><span data-stu-id="7ea51-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="7ea51-256">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="7ea51-256">Click Designer.</span></span>
    
    <span data-ttu-id="7ea51-257">Observera att ändringar i textlängdgränsen för leverantörens namn inte kan lösas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7ea51-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="7ea51-258">Därför visas den i en konfliktlista.</span><span class="sxs-lookup"><span data-stu-id="7ea51-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="7ea51-259">För varje konflikt av typen Uppdatera är följande alternativ tillgängliga: - Använd ett tidigare basvärde (knappen överst i rutnätet) om du vill ta med det föregående basversionsvärdet (0 i vårt fall).</span><span class="sxs-lookup"><span data-stu-id="7ea51-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="7ea51-260">- Använd ett basvärde (knappen överst i rutnätet) om du vill ta med det nya basversionsvärdet (100 i vårt fall).</span><span class="sxs-lookup"><span data-stu-id="7ea51-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="7ea51-261">- Behåll ditt eget (anpassade) värde (60 i det här fallet).</span><span class="sxs-lookup"><span data-stu-id="7ea51-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="7ea51-262">Klicka på Tillämpa basvärde för att använda den landsspecifika gränsen på 100 tecken för textländen på leverantörsnamnet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="7ea51-263">Observera att Proseware, Inc. och Litware, Inc. har anpassade och lokala versioner av det här formatet med hjälp av IBAN och SWIFT-koder med tillhörande komponenter som sammanslås automatiskt i det hanterade formatet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="7ea51-264">Klicka på Tillämpa innan basvärde.</span><span class="sxs-lookup"><span data-stu-id="7ea51-264">Click Apply base value.</span></span>

    <span data-ttu-id="7ea51-265">Klicka på Tillämpa basvärde för att använda den landsspecifika gränsen på 100 tecken för leverantörsnamn.</span><span class="sxs-lookup"><span data-stu-id="7ea51-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="7ea51-266">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ea51-266">Click Save.</span></span>

    <span data-ttu-id="7ea51-267">När du sparar formatet kommer lösta konflikter att tas bort från konfliktlistan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="7ea51-268">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7ea51-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="7ea51-269">Ändra statusen för den nya versionen av den anpassade formatkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="7ea51-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="7ea51-270">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="7ea51-270">Click Change status.</span></span>

    <span data-ttu-id="7ea51-271">Ändra status för den uppdaterade anpassade formatkonfigurationen från Utkast till Slutförd.</span><span class="sxs-lookup"><span data-stu-id="7ea51-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="7ea51-272">Detta kommer att göra formatkonfigurationen tillgänglig för att skapa betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="7ea51-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="7ea51-273">Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="7ea51-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="7ea51-274">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="7ea51-274">Click Complete.</span></span>
3. <span data-ttu-id="7ea51-275">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7ea51-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="7ea51-276">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ea51-276">Click OK.</span></span>

    <span data-ttu-id="7ea51-277">Observera att den skapade konfigurationen sparas som slutförd version 1.2.2: version 2 av BACS-basformatet (fiktiv UK kund) baserat på version 2 av BACS-basformatet (UK fiktivt) som baseras på version 1 av datamodellen Betalningar (förenklad modell).</span><span class="sxs-lookup"><span data-stu-id="7ea51-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="7ea51-278">Testa det anpassade formatet för att skapa betalningsfiler</span><span class="sxs-lookup"><span data-stu-id="7ea51-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="7ea51-279">Slutför stegen i sessionen "Använd skapade format för att generera elektroniska dokument för betalningar" i en parallell Finance and Operations-session.</span><span class="sxs-lookup"><span data-stu-id="7ea51-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="7ea51-280">Välj det skapade BACS-formatet (fiktiv kund från Storbritannien) i parametrar för elektronisk betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="7ea51-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="7ea51-281">Kontrollera att den skapade betalningsfilen innehåller den för en tid eftersom Proseware, Inc. introducerade XML-noden som innehåller IBAN-kontokoden i korrespondens till regionala kraven.</span><span class="sxs-lookup"><span data-stu-id="7ea51-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="7ea51-282">Filen ska också innehålla nyligen introducerade genom Litware Inc. XML-noden som presenterar SWIFT-bankkoden i enlighet med kraven i landet.</span><span class="sxs-lookup"><span data-stu-id="7ea51-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  

