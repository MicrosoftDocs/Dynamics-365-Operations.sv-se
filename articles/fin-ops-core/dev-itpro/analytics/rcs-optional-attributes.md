---
title: Importera filer i XML-format med valfria attribut
description: Det här avsnittet innehåller information om hur du utformar ER-format, som anger XML-attribut för tolkning av inkommande elektroniska dokument i XML-format.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 10795c90cb90961c17a4326b71ed43dc72039f2b
ms.sourcegitcommit: 66eae22cd99e53fe8e4c6c94945ad8061b69a442
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "3117435"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="f0010-103">Importera filer i XML-format med valfria attribut</span><span class="sxs-lookup"><span data-stu-id="f0010-103">Import files in XML format with optional attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0010-104">Du kan utforma elektronisk rapportering (ER)-format som tolkar inkommande elektroniska dokument dokument i XML-format.</span><span class="sxs-lookup"><span data-stu-id="f0010-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="f0010-105">Vissa attribut för XML-element kan anges i designat ER-format som valfritt.</span><span class="sxs-lookup"><span data-stu-id="f0010-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="f0010-106">Det gör att du kan hantera inkommande filer med och utan sådana XML-attribut korrekt.</span><span class="sxs-lookup"><span data-stu-id="f0010-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="f0010-107">Du kan sedan använda innehållet från dessa filer till att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="f0010-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="f0010-108">Om du vill veta mer om den här funktionen följer du anvisningarna i avsnittet [(RCS) importerar filer i XML-format med valfria attribut](tasks/import-files-xml-format-optional-attributes.md) som ingår i affärsprocessen 7.5.4.3 Hämta/utveckla IT-/lösningskomponenter (10677).</span><span class="sxs-lookup"><span data-stu-id="f0010-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="f0010-109">Du kan hämta dne här uppgiftsguiden och kopplade exempelfiler från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="f0010-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="f0010-110">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="f0010-110">Content description</span></span>       | <span data-ttu-id="f0010-111">Fil</span><span class="sxs-lookup"><span data-stu-id="f0010-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="f0010-112">Exempelfiler iXML-format</span><span class="sxs-lookup"><span data-stu-id="f0010-112">Sample file in XML format</span></span> | <span data-ttu-id="f0010-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="f0010-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="f0010-114">Uppgiften guide</span><span class="sxs-lookup"><span data-stu-id="f0010-114">Task guide</span></span>                | <span data-ttu-id="f0010-115">RCS Importera filer i XML-format med valfria attribut.axtr</span><span class="sxs-lookup"><span data-stu-id="f0010-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="f0010-116">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan designa ER-formatkonfiguration att importera filer i XML-format med valfria attribut.</span><span class="sxs-lookup"><span data-stu-id="f0010-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="f0010-117">För att slutföra dessa steg måste du först slutföra stegen i proceduren [Skapa en konfigurationsleverantörer och välj de som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="f0010-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="f0010-118">Innan du börjar hämtar du filen IncomingDocumentToLearnHowToHandleOptionalAttributes.xml från Microsoft Download Center och sparar den lokalt https://go.microsoft.com/fwlink/?linkid=874684.</span><span class="sxs-lookup"><span data-stu-id="f0010-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="f0010-119">Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="f0010-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="f0010-120">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f0010-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="f0010-121">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i ämnet [Skapa konfigurationsleverantörer och välj dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="f0010-121">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="f0010-122">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f0010-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="f0010-123">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="f0010-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="f0010-124">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="f0010-125">I fältet **Namn** skriver du "Model to import xml file".</span><span class="sxs-lookup"><span data-stu-id="f0010-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="f0010-126">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f0010-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="f0010-127">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f0010-127">Click **Designer**.</span></span>
5. <span data-ttu-id="f0010-128">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="f0010-129">Ange "Root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="f0010-130">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f0010-130">Click **Add**.</span></span>
8. <span data-ttu-id="f0010-131">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="f0010-132">Ange "List" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-132">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="f0010-133">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="f0010-133">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="f0010-134">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f0010-134">Click **Add**.</span></span>
12.    <span data-ttu-id="f0010-135">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-135">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="f0010-136">Ange "Code" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-136">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="f0010-137">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="f0010-137">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="f0010-138">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f0010-138">Click **Add**.</span></span>
16.    <span data-ttu-id="f0010-139">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0010-139">Click **Save**.</span></span>
17.    <span data-ttu-id="f0010-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0010-140">Close the page.</span></span>
18.    <span data-ttu-id="f0010-141">Klicka på **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="f0010-141">Click **Change status**.</span></span>
19.    <span data-ttu-id="f0010-142">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="f0010-142">Click **Complete**.</span></span>
20.    <span data-ttu-id="f0010-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="f0010-144">Skapa ett format för dataimport</span><span class="sxs-lookup"><span data-stu-id="f0010-144">Create a format for data import</span></span>
1. <span data-ttu-id="f0010-145">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="f0010-146">Ange "Format based on data model Model to import xml file" i fältet **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f0010-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="f0010-147">I fältet **Namn** skriver du "Format för att importera xml-fil".</span><span class="sxs-lookup"><span data-stu-id="f0010-147">In the **Nam**e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="f0010-148">Välj **Ja** i fältet **Stöder dataimport**.</span><span class="sxs-lookup"><span data-stu-id="f0010-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="f0010-149">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f0010-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="f0010-150">Utforma ett format för att tolka inkommande filer i XML-format</span><span class="sxs-lookup"><span data-stu-id="f0010-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="f0010-151">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f0010-151">Click **Designer**.</span></span>
2. <span data-ttu-id="f0010-152">Klicka på **Lägg till rot** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="f0010-153">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f0010-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="f0010-154">Ange "root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="f0010-155">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-155">Click **OK**.</span></span>
6. <span data-ttu-id="f0010-156">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="f0010-157">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f0010-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="f0010-158">Ange "document" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="f0010-159">Välj **Ett många** i fältet **Sammansatt**.</span><span class="sxs-lookup"><span data-stu-id="f0010-159">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="f0010-160">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-160">Click **OK**.</span></span>
11.    <span data-ttu-id="f0010-161">Välj **root\document** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f0010-161">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="f0010-162">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0010-162">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="f0010-163">I trädet välj **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="f0010-163">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="f0010-164">I fältet **Namn**, ange "id".</span><span class="sxs-lookup"><span data-stu-id="f0010-164">In the **Name** field, type 'id'.</span></span>
15.    <span data-ttu-id="f0010-165">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-165">Click **OK**.</span></span>
16.    <span data-ttu-id="f0010-166">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0010-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="f0010-167">Utforma en formatmappning för att spara analyserad information till datamodellen</span><span class="sxs-lookup"><span data-stu-id="f0010-167">Design a format mapping to save parsed information to data model</span></span>
1.    <span data-ttu-id="f0010-168">Klicka på **Mappa format till modell**.</span><span class="sxs-lookup"><span data-stu-id="f0010-168">Click **Map format to model**.</span></span>
2.    <span data-ttu-id="f0010-169">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f0010-169">Click **New**.</span></span>
3.    <span data-ttu-id="f0010-170">Ange eller välj ett värde i fältet **Definition**.</span><span class="sxs-lookup"><span data-stu-id="f0010-170">In the **Definition** field, enter or select a value.</span></span>
4.    <span data-ttu-id="f0010-171">Ange "Mapping" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f0010-171">In the **Name** field, type 'Mapping'.</span></span>
5.    <span data-ttu-id="f0010-172">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0010-172">Click **Save**.</span></span>
6.    <span data-ttu-id="f0010-173">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f0010-173">Click **Designer**.</span></span>
7.    <span data-ttu-id="f0010-174">Expandera **format** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f0010-174">In the tree, expand **format**.</span></span>
8.    <span data-ttu-id="f0010-175">I trädet expandera **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="f0010-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.    <span data-ttu-id="f0010-176">I trädet väljer du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f0010-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f0010-177">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="f0010-177">(document)\*\*.</span></span>
10.    <span data-ttu-id="f0010-178">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="f0010-178">Click **Bind**.</span></span>
11.    <span data-ttu-id="f0010-179">I trädet expanderar du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f0010-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f0010-180">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="f0010-180">(document)\*\*.</span></span>
12.    <span data-ttu-id="f0010-181">I trädet väljer du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f0010-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f0010-182">(dokument)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="f0010-182">(document)\id\*\*.</span></span>
13.    <span data-ttu-id="f0010-183">Expandera **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="f0010-183">In the tree, expand **List = format.root.document**.</span></span>
14.    <span data-ttu-id="f0010-184">Välj **List = format.root.document\Code** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f0010-184">In the tree, select **List = format.root.document\Code**.</span></span>
15.    <span data-ttu-id="f0010-185">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="f0010-185">Click **Bind**.</span></span>
16.    <span data-ttu-id="f0010-186">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0010-186">Click **Save**.</span></span>
17.    <span data-ttu-id="f0010-187">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0010-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="f0010-188">Kör mappning av format</span><span class="sxs-lookup"><span data-stu-id="f0010-188">Run format mapping</span></span>
1. <span data-ttu-id="f0010-189">Klicka på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="f0010-189">Click **Run**.</span></span>
2. <span data-ttu-id="f0010-190">Klicka på **Bläddra** och välj filen **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="f0010-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="f0010-191">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="f0010-192">Den valda filen har inte importerats eftersom formatdesignen innehåller attributet "id" för elementet "document", men den importerade filen innehåller inget sådant attribut.</span><span class="sxs-lookup"><span data-stu-id="f0010-192">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="f0010-193">Ändra formatstrukturen så att XML-attributet hanteras som valfritt</span><span class="sxs-lookup"><span data-stu-id="f0010-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="f0010-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0010-194">Close the page.</span></span>
2. <span data-ttu-id="f0010-195">Expandera **root\document** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f0010-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="f0010-196">Välj **root\document\id** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f0010-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="f0010-197">Välj **ja** i fältet **tom sträng för saknat attribut**.</span><span class="sxs-lookup"><span data-stu-id="f0010-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="f0010-198">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0010-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="f0010-199">Kör formatmappning fär att testa ändringar</span><span class="sxs-lookup"><span data-stu-id="f0010-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="f0010-200">Klicka på **Mappa format till modell**.</span><span class="sxs-lookup"><span data-stu-id="f0010-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="f0010-201">Klicka på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="f0010-201">Click **Run**.</span></span>
3. <span data-ttu-id="f0010-202">Klicka på **Bläddra** och välj filen **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="f0010-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="f0010-203">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0010-203">Click **OK**.</span></span>
5. <span data-ttu-id="f0010-204">Granska den skapade filen.</span><span class="sxs-lookup"><span data-stu-id="f0010-204">Review the generated file.</span></span> <span data-ttu-id="f0010-205">Observera att samma fil har importerats som formatdesignen betraktar nu attributet "ID" för "dokument"-elementet som valfritt.</span><span class="sxs-lookup"><span data-stu-id="f0010-205">Note that same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>
