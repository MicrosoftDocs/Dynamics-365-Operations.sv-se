---
title: Få åtkomst till programmets metadata med hjälp av ER-konfiguration
description: Det här avsnittet beskriver hur en användare av Regulatory Configuration Service kan utforma en ny modellmappning för elektronisk rapportering genom att använda metadata.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c50047781fdc21c9157ceb634822c6cfb5a075
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559661"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="51ff8-103">Få åtkomst till programmets metadata med hjälp av ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="51ff8-103">Access application metadata by using ER configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51ff8-104">I följande steg förklaras hur en användare av Regulatory configuration service (RCS) i rollen Systemadministratör eller Utvecklare av elektronisk rapportering kan utforma en ny modellmappning för elektronisk rapportering (ER) genom att använda metadata i programmet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="51ff8-105">Programmetadata kommer att användas genom att använda en ER-metadatakonfiguration som innehåller en exempeluppsättning med metadata för att komma åt transaktioner i utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="51ff8-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="51ff8-106">För att slutföra dessa steg, i RCS måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="51ff8-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="51ff8-107">Slutför sedan stegen i ämnet [Förbered programmetadata att användas i RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="51ff8-107">Then complete the steps in the topic, [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51ff8-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="51ff8-108">Prerequisites</span></span>
1. <span data-ttu-id="51ff8-109">Gå till **Alla arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="51ff8-110">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="51ff8-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="51ff8-111">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="51ff8-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="51ff8-112">Importera metadatakonfiguration</span><span class="sxs-lookup"><span data-stu-id="51ff8-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="51ff8-113">Klicka på **Metadatakonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="51ff8-114">Importera ER-metadatakonfigurationen som innehåller metadata har konfigurerats för att generera elektroniska dokument för utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="51ff8-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="51ff8-115">Denna ER-metadatakonfiguration har exporterats som XML-fil medan stegen i [Förbered programmetadata för användning i RCS](prepare-application-metadata-rcs.md)-proceduren har slutförts.</span><span class="sxs-lookup"><span data-stu-id="51ff8-115">This ER metadata configuration has been exported as XML file while the steps in the [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="51ff8-116">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="51ff8-117">Klicka på **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="51ff8-118">Klicka på **Bläddra** och välj filen Utländsk handel metadata.xml.</span><span class="sxs-lookup"><span data-stu-id="51ff8-118">Click **Browse** and select the 'Foreign trade metadata.xml' file.</span></span> 
6. <span data-ttu-id="51ff8-119">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-119">Click **OK**.</span></span> 
7. <span data-ttu-id="51ff8-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="51ff8-121">Skapa en datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="51ff8-121">Create data model configuration</span></span>
1. <span data-ttu-id="51ff8-122">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="51ff8-123">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="51ff8-124">Ange "Foreign trade model" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="51ff8-125">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="51ff8-126">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="51ff8-127">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="51ff8-128">Ange "Root" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="51ff8-129">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-129">Click **Add**.</span></span> 
9. <span data-ttu-id="51ff8-130">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-130">Click **New** to open the drop dialog.</span></span> 
10.    <span data-ttu-id="51ff8-131">Ange "Transaction" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-131">In the **Name** field, type 'Transaction'.</span></span> 
11.    <span data-ttu-id="51ff8-132">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-132">In the **Item type** field, select **Record list**.</span></span> 
12.    <span data-ttu-id="51ff8-133">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-133">Click **Add**.</span></span> 
13.    <span data-ttu-id="51ff8-134">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-134">Click **New** to open the drop dialog.</span></span> 
14.    <span data-ttu-id="51ff8-135">Ange "Commodity code" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-135">In the **Name** field, type 'Commodity code'.</span></span> 
15.    <span data-ttu-id="51ff8-136">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-136">In the **Item type** field, select **String**.</span></span> 
16.    <span data-ttu-id="51ff8-137">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-137">Click **Add**.</span></span> 
17.    <span data-ttu-id="51ff8-138">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-138">Click **New** to open the drop dialog.</span></span> 
18.    <span data-ttu-id="51ff8-139">Ange "Invoiced amount" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19.    <span data-ttu-id="51ff8-140">Välj **Realtal** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-140">In the **Item type** field, select **Real**.</span></span> 
20.    <span data-ttu-id="51ff8-141">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-141">Click **Add**.</span></span> 
21.    <span data-ttu-id="51ff8-142">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-142">Click **New** to open the drop dialog.</span></span> 
22.    <span data-ttu-id="51ff8-143">Ange "Date" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-143">In the **Name** field, type 'Date'.</span></span> 
23.    <span data-ttu-id="51ff8-144">Välj **Datum** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-144">In the **Item type** field, select **Date**.</span></span> 
24.    <span data-ttu-id="51ff8-145">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-145">Click **Add**.</span></span> 
25.    <span data-ttu-id="51ff8-146">Klicka på **Rotreferens**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-146">Click **Root reference**.</span></span> 
26.    <span data-ttu-id="51ff8-147">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-147">Click **OK**.</span></span> 
27.    <span data-ttu-id="51ff8-148">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-148">Click **Save**.</span></span> 
28.    <span data-ttu-id="51ff8-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-149">Close the page.</span></span> 
29.    <span data-ttu-id="51ff8-150">Klicka på **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-150">Click **Change status**.</span></span> 
30.    <span data-ttu-id="51ff8-151">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-151">Click **Complete**.</span></span> 
31.    <span data-ttu-id="51ff8-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="51ff8-153">Skapa konfiguration av modellmappning</span><span class="sxs-lookup"><span data-stu-id="51ff8-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="51ff8-154">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="51ff8-155">Ange "Model Mapping based on Foreign trade model" i fältet **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="51ff8-156">Ange "Foreign trade mapping" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="51ff8-157">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="51ff8-158">Expandera avsnittet **Förutsättningar**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="51ff8-159">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="51ff8-160">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-160">Click **New**.</span></span> 
8. <span data-ttu-id="51ff8-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="51ff8-162">Välj **konfiguration** i fältet **förutsättningskomponenttyp**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10.    <span data-ttu-id="51ff8-163">Välj konfiguration av **metadata för utländsk handel**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-163">Select **Foreign trade metadata** configuration.</span></span> 
11.    <span data-ttu-id="51ff8-164">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-164">Click **Save**.</span></span> 
12.    <span data-ttu-id="51ff8-165">Referensen till version 1 av konfigurationen av metadata för utländsk handel lades till i version 1.</span><span class="sxs-lookup"><span data-stu-id="51ff8-165">We added the reference to the version 1 of the 'Foreign trade metadata' configuration.</span></span> <span data-ttu-id="51ff8-166">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="51ff8-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13.    <span data-ttu-id="51ff8-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-167">Close the page.</span></span> 
14.    <span data-ttu-id="51ff8-168">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-168">Click **Designer**.</span></span> 
15.    <span data-ttu-id="51ff8-169">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-169">Click **Designer**.</span></span> 
16.    <span data-ttu-id="51ff8-170">Välj **Dynamics 365 for Operations\Tabellregister** i trädet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17.    <span data-ttu-id="51ff8-171">Klicka på **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-171">Click **Add root**.</span></span> 
18.    <span data-ttu-id="51ff8-172">Ange "Intrastat" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-172">In the **Name** field, type 'Intrastat'.</span></span> 
19.    <span data-ttu-id="51ff8-173">Välj tabellregister **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-173">Select **Intrastat** table records.</span></span> 
20.    <span data-ttu-id="51ff8-174">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="51ff8-175">De enda 2 tabellerna erbjöds eftersom de enda två tabellerna lades till i uppsättningen metadata som används för tillfället.</span><span class="sxs-lookup"><span data-stu-id="51ff8-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21.    <span data-ttu-id="51ff8-176">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-176">Click **Bind**.</span></span> 
22.    <span data-ttu-id="51ff8-177">Expandera **Intrastat** i trädet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-177">In the tree, expand **Intrastat**.</span></span> 
23.    <span data-ttu-id="51ff8-178">I trädet väljer du **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24.    <span data-ttu-id="51ff8-179">Expandera **Transaktion = Intrastat** i trädet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25.    <span data-ttu-id="51ff8-180">Välj **Transaktion = Intrastat\Fakturerat belopp** i trädet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26.    <span data-ttu-id="51ff8-181">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-181">Click **Bind**.</span></span> 
27.    <span data-ttu-id="51ff8-182">I trädet väljer du **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28.    <span data-ttu-id="51ff8-183">I trädet väljer du **Transaktion = Intrastat\Datum**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29.    <span data-ttu-id="51ff8-184">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-184">Click **Bind**.</span></span> 
30.    <span data-ttu-id="51ff8-185">I trädet expanderar du **Intrastat\>Relationer**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31.    <span data-ttu-id="51ff8-186">I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32.    <span data-ttu-id="51ff8-187">I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity\Code**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33.    <span data-ttu-id="51ff8-188">Välj **Transaction = Intrastat\Commodity code** i trädet.</span><span class="sxs-lookup"><span data-stu-id="51ff8-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34.    <span data-ttu-id="51ff8-189">Klicka på **Bind**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-189">Click **Bind**.</span></span> 
35.    <span data-ttu-id="51ff8-190">Klicka på **Validera.**</span><span class="sxs-lookup"><span data-stu-id="51ff8-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="51ff8-191">Vi har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om programdata från den ER-metadatakonfiguration som refereras till.</span><span class="sxs-lookup"><span data-stu-id="51ff8-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36.    <span data-ttu-id="51ff8-192">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51ff8-192">Click **Save**.</span></span> 
37.    <span data-ttu-id="51ff8-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-193">Close the page.</span></span> 
38.    <span data-ttu-id="51ff8-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51ff8-194">Close the page.</span></span> 
39.    <span data-ttu-id="51ff8-195">Om det behövs kan du utöka den befintliga uppsättningen metadata och sedan exportera den nya slutförda versionen av konfigurationen för ER-metadata.</span><span class="sxs-lookup"><span data-stu-id="51ff8-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="51ff8-196">Du kan sedan importera den till RCS och uppdatera förutsättningarna för den konfigurerade modellmappningskonfigurationen som hänvisar till en ny version av importerad metadatakonfiguration.</span><span class="sxs-lookup"><span data-stu-id="51ff8-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="51ff8-197">Det här sättet att hämta information om programdata det enda som är tillgängligt för lokalt distribuerade program (när lokala affärsdata (LBD) eller lokalt, distributionsmodell används).</span><span class="sxs-lookup"><span data-stu-id="51ff8-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]