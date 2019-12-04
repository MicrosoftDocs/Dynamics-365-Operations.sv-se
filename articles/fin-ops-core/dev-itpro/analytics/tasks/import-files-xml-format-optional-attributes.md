---
title: (RCS) Importera filer i XML-format med valfria attribut
description: Det här avsnittet innehåller information om hur en användare kan utforma ER-formatkonfiguration för import av filer i XML-format som innehåller valfria attribut.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f34302a32b2e06f281dc93d6df160b88ffac7123
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769795"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="98850-103">(RCS) Importera filer i XML-format med valfria attribut</span><span class="sxs-lookup"><span data-stu-id="98850-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98850-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan designa ER-formatkonfiguration att importera filer i XML-format med valfria attribut.</span><span class="sxs-lookup"><span data-stu-id="98850-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="98850-105">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="98850-105">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="98850-106">Innan du börjar hämtar du filen IncomingDocumentToLearnHowToHandleOptionalAttributes.xml från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684) och sparar den lokalt.</span><span class="sxs-lookup"><span data-stu-id="98850-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.  <span data-ttu-id="98850-107">Gå till **Alla arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="98850-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.  <span data-ttu-id="98850-108">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="98850-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="98850-109">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="98850-109">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.  <span data-ttu-id="98850-110">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="98850-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="98850-111">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="98850-111">Create a new data model configuration</span></span>
1.  <span data-ttu-id="98850-112">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-112">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="98850-113">I fältet **Namn** skriver du "Model to import xml file".</span><span class="sxs-lookup"><span data-stu-id="98850-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.  <span data-ttu-id="98850-114">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="98850-114">Click **Create configuration**.</span></span>
4.  <span data-ttu-id="98850-115">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="98850-115">Click **Designer**.</span></span>
5.  <span data-ttu-id="98850-116">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-116">Click **New** to open the drop dialog.</span></span>
6.  <span data-ttu-id="98850-117">Ange "Root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-117">In the **Name** field, type 'Root'.</span></span>
7.  <span data-ttu-id="98850-118">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="98850-118">Click **Add**.</span></span>
8.  <span data-ttu-id="98850-119">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-119">Click **New** to open the drop dialog.</span></span>
9.  <span data-ttu-id="98850-120">Ange "List" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-120">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="98850-121">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="98850-121">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="98850-122">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="98850-122">Click **Add**.</span></span>
12. <span data-ttu-id="98850-123">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-123">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="98850-124">Ange "Code" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-124">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="98850-125">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="98850-125">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="98850-126">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="98850-126">Click **Add**.</span></span>
16. <span data-ttu-id="98850-127">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98850-127">Click **Save**.</span></span>
17. <span data-ttu-id="98850-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98850-128">Close the page.</span></span>
18. <span data-ttu-id="98850-129">Klicka på **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="98850-129">Click **Change status**.</span></span>
19. <span data-ttu-id="98850-130">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="98850-130">Click **Complete**.</span></span>
20. <span data-ttu-id="98850-131">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="98850-132">Skapa ett format för dataimport</span><span class="sxs-lookup"><span data-stu-id="98850-132">Create a format for data import</span></span>
1.  <span data-ttu-id="98850-133">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-133">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="98850-134">Ange "Format based on data model Model to import xml file" i fältet **Ny**.</span><span class="sxs-lookup"><span data-stu-id="98850-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.  <span data-ttu-id="98850-135">I fältet **Namn** skriver du "Format för att importera xml-fil".</span><span class="sxs-lookup"><span data-stu-id="98850-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.  <span data-ttu-id="98850-136">Välj **Ja** i fältet **Stöder dataimport**.</span><span class="sxs-lookup"><span data-stu-id="98850-136">Select **Yes** in the **Supports data import** field.</span></span>
5.  <span data-ttu-id="98850-137">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="98850-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="98850-138">Utforma ett format för att tolka inkommande filer i XML-format</span><span class="sxs-lookup"><span data-stu-id="98850-138">Design a format to parse incoming file in xml format</span></span>
1.  <span data-ttu-id="98850-139">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="98850-139">Click **Designer**.</span></span>
2.  <span data-ttu-id="98850-140">Klicka på **Lägg till rot** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-140">Click **Add root** to open the drop dialog.</span></span>
3.  <span data-ttu-id="98850-141">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="98850-141">In the tree, select **XML\Element**.</span></span>
4.  <span data-ttu-id="98850-142">Ange "root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-142">In the **Name** field, type 'root'.</span></span>
5.  <span data-ttu-id="98850-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-143">Click **OK**.</span></span>
6.  <span data-ttu-id="98850-144">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-144">Click **Add** to open the drop dialog.</span></span>
7.  <span data-ttu-id="98850-145">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="98850-145">In the tree, select **XML\Element**.</span></span>
8.  <span data-ttu-id="98850-146">Ange "document" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-146">In the **Name** field, type 'document'.</span></span>
9.  <span data-ttu-id="98850-147">Välj **Ett många** i fältet **Sammansatt**.</span><span class="sxs-lookup"><span data-stu-id="98850-147">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="98850-148">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-148">Click **OK**.</span></span>
11. <span data-ttu-id="98850-149">Välj **root\document** i trädet.</span><span class="sxs-lookup"><span data-stu-id="98850-149">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="98850-150">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98850-150">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="98850-151">I trädet välj **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="98850-151">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="98850-152">I fältet **Namn**, ange "ID".</span><span class="sxs-lookup"><span data-stu-id="98850-152">In the **Name** field, type 'ID'.</span></span>
15. <span data-ttu-id="98850-153">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-153">Click **OK**.</span></span>
16. <span data-ttu-id="98850-154">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98850-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="98850-155">Utforma en formatmappning för att spara analyserad information till datamodellen</span><span class="sxs-lookup"><span data-stu-id="98850-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="98850-156">Klicka på **Mappa format till modell**.</span><span class="sxs-lookup"><span data-stu-id="98850-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="98850-157">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="98850-157">Click **New**.</span></span>
3. <span data-ttu-id="98850-158">Ange eller välj ett värde i fältet **Definition**.</span><span class="sxs-lookup"><span data-stu-id="98850-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="98850-159">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="98850-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="98850-160">Ange "Mapping" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="98850-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="98850-161">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98850-161">Click **Save**.</span></span>
7. <span data-ttu-id="98850-162">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="98850-162">Click **Designer**.</span></span>
8. <span data-ttu-id="98850-163">Expandera **format** i trädet.</span><span class="sxs-lookup"><span data-stu-id="98850-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="98850-164">I trädet expandera **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="98850-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10. <span data-ttu-id="98850-165">I trädet väljer du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="98850-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="98850-166">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="98850-166">(document)\*\*.</span></span>
11. <span data-ttu-id="98850-167">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="98850-167">Click **Bind**.</span></span>
12. <span data-ttu-id="98850-168">I trädet expanderar du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="98850-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="98850-169">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="98850-169">(document)\*\*.</span></span>
13. <span data-ttu-id="98850-170">I trädet väljer du \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="98850-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="98850-171">(dokument)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="98850-171">(document)\id\*\*.</span></span>
14. <span data-ttu-id="98850-172">Expandera **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="98850-172">In the tree, expand **List = format.root.document**.</span></span>
15. <span data-ttu-id="98850-173">Välj **List = format.root.document\Code** i trädet.</span><span class="sxs-lookup"><span data-stu-id="98850-173">In the tree, select **List = format.root.document\Code**.</span></span>
16. <span data-ttu-id="98850-174">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="98850-174">Click **Bind**.</span></span>
17. <span data-ttu-id="98850-175">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98850-175">Click **Save**.</span></span>
18. <span data-ttu-id="98850-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98850-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="98850-177">Kör mappning av format</span><span class="sxs-lookup"><span data-stu-id="98850-177">Run format mapping</span></span>
1. <span data-ttu-id="98850-178">Klicka på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="98850-178">Click **Run**.</span></span>
2. <span data-ttu-id="98850-179">Klicka på **Bläddra** och välj **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="98850-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="98850-180">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="98850-181">Den valda filen har inte importerats eftersom formatdesignen innehåller attributet "id" för elementet "document", men den importerade filen innehåller inget sådant attribut.</span><span class="sxs-lookup"><span data-stu-id="98850-181">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="98850-182">Ändra formatstrukturen så att XML-attributet hanteras som valfritt</span><span class="sxs-lookup"><span data-stu-id="98850-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="98850-183">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98850-183">Close the page.</span></span>
2. <span data-ttu-id="98850-184">Expandera **root\document** i trädet.</span><span class="sxs-lookup"><span data-stu-id="98850-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="98850-185">Välj **root\document\id** i trädet.</span><span class="sxs-lookup"><span data-stu-id="98850-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="98850-186">Välj **ja** i fältet **tom sträng för saknat attribut**.</span><span class="sxs-lookup"><span data-stu-id="98850-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="98850-187">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98850-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="98850-188">Kör formatmappning fär att testa ändringar</span><span class="sxs-lookup"><span data-stu-id="98850-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="98850-189">Klicka på **Mappa format till modell**.</span><span class="sxs-lookup"><span data-stu-id="98850-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="98850-190">Klicka på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="98850-190">Click **Run**.</span></span>
3. <span data-ttu-id="98850-191">Klicka på **Bläddra** och välj fältet **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="98850-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="98850-192">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="98850-192">Click **OK**.</span></span>
5. <span data-ttu-id="98850-193">Granska den skapade filen.</span><span class="sxs-lookup"><span data-stu-id="98850-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="98850-194">Samma fil har importerats som formatdesignen betraktar nu attributet "ID" för "dokument"-elementet som valfritt.</span><span class="sxs-lookup"><span data-stu-id="98850-194">The same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
