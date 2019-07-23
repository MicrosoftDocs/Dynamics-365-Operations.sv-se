---
title: Få åtkomst till programmets metadata med hjälp av ER-konfiguration
description: Stegen i det här avsnittet beskriver hur en RCS-användare (Regulatory Configuration Service) kan utforma en ny ER-modellmappning genom att använda metadata i Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
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
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b95b41b27cecd4c71ed7646f329cf5736a01b561
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727039"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="e4862-103">Få åtkomst till programmets metadata med hjälp av ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="e4862-103">Access application metadata by using ER configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4862-104">I följande steg förklaras hur en användare av Regulatory configuration service (RCS) i rollen Systemadministratör eller Utvecklare av elektronisk rapportering kan utforma en ny modellmappning för elektronisk rapportering (ER) genom att använda metadata i Dynamics 365 for Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="e4862-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the metadata of the Dynamics 365 for Finance and Operations application.</span></span> <span data-ttu-id="e4862-105">Programmetadata kommer att användas genom att använda en ER-metadatakonfiguration som innehåller en exempeluppsättning med metadata för att komma åt transaktioner i utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="e4862-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="e4862-106">För att slutföra dessa steg, i RCS måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="e4862-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="e4862-107">Sedan i Finance and Operations, slutför stegen i ämnet [(ER) förbered programmetadata att användas i RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="e4862-107">Then, in Finance and Operations, complete the steps in the topic, [(ER) Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4862-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e4862-108">Prerequisites</span></span>
1. <span data-ttu-id="e4862-109">Gå till **Alla arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e4862-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="e4862-110">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e4862-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e4862-111">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e4862-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="e4862-112">Importera metadatakonfiguration</span><span class="sxs-lookup"><span data-stu-id="e4862-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="e4862-113">Klicka på **Metadatakonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e4862-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="e4862-114">Importera ER-metadatakonfigurationen som innehåller metadata från Finance and Operations-programmet som är konfigurerat att generera elektroniska dokument för utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="e4862-114">Import the ER metadata configuration that contains metadata from the Finance and Operations application that is configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="e4862-115">Denna ER-metadatakonfiguration har exporterats som XML-fil medan stegen i [(ER) för att använda programdata för användning i RCS](prepare-application-metadata-rcs.md)-proceduren har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e4862-115">This ER metadata configuration has been exported as XML file while the steps in the [(ER) Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="e4862-116">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="e4862-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="e4862-117">Klicka på **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="e4862-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="e4862-118">Klicka på **Bläddra** och välj filen Utländsk handel metadata.xml.</span><span class="sxs-lookup"><span data-stu-id="e4862-118">Click **Browse** and select the ‘Foreign trade metadata.xml’ file.</span></span> 
6. <span data-ttu-id="e4862-119">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4862-119">Click **OK**.</span></span> 
7. <span data-ttu-id="e4862-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4862-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="e4862-121">Skapa en datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e4862-121">Create data model configuration</span></span>
1. <span data-ttu-id="e4862-122">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e4862-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="e4862-123">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="e4862-124">Ange "Foreign trade model" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="e4862-125">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e4862-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="e4862-126">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e4862-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="e4862-127">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="e4862-128">Ange "Root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="e4862-129">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e4862-129">Click **Add**.</span></span> 
9. <span data-ttu-id="e4862-130">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-130">Click **New** to open the drop dialog.</span></span> 
10. <span data-ttu-id="e4862-131">Ange "Transaction" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-131">In the **Name** field, type 'Transaction'.</span></span> 
11. <span data-ttu-id="e4862-132">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e4862-132">In the **Item type** field, select **Record list**.</span></span> 
12. <span data-ttu-id="e4862-133">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e4862-133">Click **Add**.</span></span> 
13. <span data-ttu-id="e4862-134">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-134">Click **New** to open the drop dialog.</span></span> 
14. <span data-ttu-id="e4862-135">Ange "Commodity code" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-135">In the **Name** field, type 'Commodity code'.</span></span> 
15. <span data-ttu-id="e4862-136">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e4862-136">In the **Item type** field, select **String**.</span></span> 
16. <span data-ttu-id="e4862-137">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e4862-137">Click **Add**.</span></span> 
17. <span data-ttu-id="e4862-138">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-138">Click **New** to open the drop dialog.</span></span> 
18. <span data-ttu-id="e4862-139">Ange "Invoiced amount" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19. <span data-ttu-id="e4862-140">Välj **Realtal** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e4862-140">In the **Item type** field, select **Real**.</span></span> 
20. <span data-ttu-id="e4862-141">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e4862-141">Click **Add**.</span></span> 
21. <span data-ttu-id="e4862-142">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-142">Click **New** to open the drop dialog.</span></span> 
22. <span data-ttu-id="e4862-143">Ange "Date" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-143">In the **Name** field, type 'Date'.</span></span> 
23. <span data-ttu-id="e4862-144">Välj **Datum** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e4862-144">In the **Item type** field, select **Date**.</span></span> 
24. <span data-ttu-id="e4862-145">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e4862-145">Click **Add**.</span></span> 
25. <span data-ttu-id="e4862-146">Klicka på **Rotreferens**.</span><span class="sxs-lookup"><span data-stu-id="e4862-146">Click **Root reference**.</span></span> 
26. <span data-ttu-id="e4862-147">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4862-147">Click **OK**.</span></span> 
27. <span data-ttu-id="e4862-148">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4862-148">Click **Save**.</span></span> 
28. <span data-ttu-id="e4862-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4862-149">Close the page.</span></span> 
29. <span data-ttu-id="e4862-150">Klicka på **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="e4862-150">Click **Change status**.</span></span> 
30. <span data-ttu-id="e4862-151">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e4862-151">Click **Complete**.</span></span> 
31. <span data-ttu-id="e4862-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4862-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="e4862-153">Skapa konfiguration av modellmappning</span><span class="sxs-lookup"><span data-stu-id="e4862-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="e4862-154">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e4862-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="e4862-155">Ange "Model Mapping based on Foreign trade model" i fältet **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e4862-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="e4862-156">Ange "Foreign trade mapping" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="e4862-157">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e4862-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="e4862-158">Expandera avsnittet **Förutsättningar**.</span><span class="sxs-lookup"><span data-stu-id="e4862-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="e4862-159">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e4862-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="e4862-160">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e4862-160">Click **New**.</span></span> 
8. <span data-ttu-id="e4862-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e4862-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="e4862-162">Välj **konfiguration** i fältet **förutsättningskomponenttyp**.</span><span class="sxs-lookup"><span data-stu-id="e4862-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10. <span data-ttu-id="e4862-163">Välj konfiguration av **metadata för utländsk handel**.</span><span class="sxs-lookup"><span data-stu-id="e4862-163">Select **Foreign trade metadata** configuration.</span></span> 
11. <span data-ttu-id="e4862-164">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4862-164">Click **Save**.</span></span> 
12. <span data-ttu-id="e4862-165">Referensen till version 1 av konfigurationen av metadata för utländsk handel lades till i version 1.</span><span class="sxs-lookup"><span data-stu-id="e4862-165">We added the reference to the version 1 of the ‘Foreign trade metadata’ configuration.</span></span> <span data-ttu-id="e4862-166">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="e4862-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13. <span data-ttu-id="e4862-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4862-167">Close the page.</span></span> 
14. <span data-ttu-id="e4862-168">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e4862-168">Click **Designer**.</span></span> 
15. <span data-ttu-id="e4862-169">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e4862-169">Click **Designer**.</span></span> 
16. <span data-ttu-id="e4862-170">Välj **Dynamics 365 for Operations\Tabellregister** i trädet.</span><span class="sxs-lookup"><span data-stu-id="e4862-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17. <span data-ttu-id="e4862-171">Klicka på **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e4862-171">Click **Add root**.</span></span> 
18. <span data-ttu-id="e4862-172">Ange "Intrastat" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e4862-172">In the **Name** field, type 'Intrastat'.</span></span> 
19. <span data-ttu-id="e4862-173">Välj tabellregister **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="e4862-173">Select **Intrastat** table records.</span></span> 
20. <span data-ttu-id="e4862-174">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4862-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4862-175">De enda 2 tabellerna erbjöds eftersom de enda två tabellerna lades till i uppsättningen metadata som används för tillfället.</span><span class="sxs-lookup"><span data-stu-id="e4862-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21. <span data-ttu-id="e4862-176">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="e4862-176">Click **Bind**.</span></span> 
22. <span data-ttu-id="e4862-177">Expandera **Intrastat** i trädet.</span><span class="sxs-lookup"><span data-stu-id="e4862-177">In the tree, expand **Intrastat**.</span></span> 
23. <span data-ttu-id="e4862-178">I trädet väljer du **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="e4862-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24. <span data-ttu-id="e4862-179">Expandera **Transaktion = Intrastat** i trädet.</span><span class="sxs-lookup"><span data-stu-id="e4862-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25. <span data-ttu-id="e4862-180">Välj **Transaktion = Intrastat\Fakturerat belopp** i trädet.</span><span class="sxs-lookup"><span data-stu-id="e4862-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26. <span data-ttu-id="e4862-181">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="e4862-181">Click **Bind**.</span></span> 
27. <span data-ttu-id="e4862-182">I trädet väljer du **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="e4862-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28. <span data-ttu-id="e4862-183">I trädet väljer du **Transaktion = Intrastat\Datum**.</span><span class="sxs-lookup"><span data-stu-id="e4862-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29. <span data-ttu-id="e4862-184">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="e4862-184">Click **Bind**.</span></span> 
30. <span data-ttu-id="e4862-185">I trädet expanderar du **Intrastat\>Relationer**.</span><span class="sxs-lookup"><span data-stu-id="e4862-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31. <span data-ttu-id="e4862-186">I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="e4862-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32. <span data-ttu-id="e4862-187">I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity\Code**.</span><span class="sxs-lookup"><span data-stu-id="e4862-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33. <span data-ttu-id="e4862-188">Välj **Transaction = Intrastat\Commodity code** i trädet.</span><span class="sxs-lookup"><span data-stu-id="e4862-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34. <span data-ttu-id="e4862-189">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="e4862-189">Click **Bind**.</span></span> 
35. <span data-ttu-id="e4862-190">Klicka på **Validera.**</span><span class="sxs-lookup"><span data-stu-id="e4862-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4862-191">Vi har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om programdata från den ER-metadatakonfiguration som refereras till.</span><span class="sxs-lookup"><span data-stu-id="e4862-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36. <span data-ttu-id="e4862-192">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4862-192">Click **Save**.</span></span> 
37. <span data-ttu-id="e4862-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4862-193">Close the page.</span></span> 
38. <span data-ttu-id="e4862-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4862-194">Close the page.</span></span> 
39. <span data-ttu-id="e4862-195">När du behöver utöka den befintliga uppsättningen metadata kan du göra det i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e4862-195">When you need to extend the existing set of metadata, you can do it in Finance and Operations.</span></span> <span data-ttu-id="e4862-196">Sedan kan du exportera den nya slutförda versionen av konfigurationen för ER-metadata från Finance and Operations, importera den till RCS och uppdatera förutsättningarna för den konfigurerade modellmappningskonfigurationen som hänvisar till en ny version av importerad metadatakonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4862-196">Then you can export the new completed version of ER metadata configuration from Finance and Operation,s import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4862-197">Det här sättet att hämta information om programdata det enda som är tillgängligt för lokalt distribuerade program (när lokala affärsdata (LBD) eller lokalt, distributionsmodell används för Dynamics 365 for Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="e4862-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used for Dynamics 365 for Finance and Operations).</span></span>
        
