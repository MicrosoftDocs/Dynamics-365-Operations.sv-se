---
title: Förbered programspecifika metadata för RCS och ER
description: I det här avsnittet beskrivs hur du förbereder programspecifika metadata för RCS (Regulatory Configuration Service) och elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c036eab38845db8427c447b27cce0be8048669fd
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248664"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a><span data-ttu-id="b791f-103">Förbered programspecifika metadata för RCS</span><span class="sxs-lookup"><span data-stu-id="b791f-103">Prepare application-specific metadata for RCS</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b791f-104">I det här avsnittet får du stegvisa exempel på följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="b791f-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="b791f-105">Förbered programdata att användas i RCS</span><span class="sxs-lookup"><span data-stu-id="b791f-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="b791f-106">Få åtkomst till programmets metadata med hjälp av ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="b791f-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="b791f-107">Få åtkomst till programmets metadata med hjälp av anslutna program</span><span class="sxs-lookup"><span data-stu-id="b791f-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="b791f-108">Förbered programdata att användas i RCS</span><span class="sxs-lookup"><span data-stu-id="b791f-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="b791f-109">Följande procedur visas hur användare som har rollen **Systemadministratör** eller **utvecklare av ekonomiska rapporter** kan skapa en konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för program och som används för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="b791f-109">The following procedure shows how a user who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="b791f-110">Exempel på konfigurationen för ER-modellmappning som skapats i det här exemplet kommer att användas till utländska handelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="b791f-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="b791f-111">För det här exemplet vill du använda RCS för att utforma en ER-lösning för programmet som genererar elektroniska dokument som innehåller information från affärsdomänen för utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="b791f-111">For this example, you want to use RCS to design an ER solution for the application that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="b791f-112">Om du vill ange mappningen mellan ER-datamodellen och källorna till de data som krävs måste du ha tillgång till programdata i RCS.</span><span class="sxs-lookup"><span data-stu-id="b791f-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata in RCS.</span></span> <span data-ttu-id="b791f-113">Som en del av utformningen av processen att utforma ER-lösningen måste du konfigurera en ny konfiguration av ER-metadata som innehåller alla metadata som för närvarande krävs för att generera ER-rapporter för vald affärsdomän.</span><span class="sxs-lookup"><span data-stu-id="b791f-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b791f-114">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i något företag.</span><span class="sxs-lookup"><span data-stu-id="b791f-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="b791f-115">Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b791f-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="b791f-116">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b791f-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="b791f-117">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren[ Skapa en konfigurationsleverantör och välj den som aktiv.](tasks/er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="b791f-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="b791f-118">Välj **Metadatakonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="b791f-119">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="b791f-120">Ange ett namn i listrutan i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="b791f-121">I det här exemplet anger du **metadata för utländsk handel**.</span><span class="sxs-lookup"><span data-stu-id="b791f-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="b791f-122">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="b791f-123">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-123">Select **Designer**.</span></span>
8. <span data-ttu-id="b791f-124">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-125">Du kan välja alla metadata för antingen hela programmet eller valda modeller eller moduler.</span><span class="sxs-lookup"><span data-stu-id="b791f-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="b791f-126">I ba fall ska du tänka på att följande metadata kommer att läggas till automatiskt i det här fallet: register över poster, uppräkningar och utökade datatypern (ETD:er).</span><span class="sxs-lookup"><span data-stu-id="b791f-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="b791f-127">Om det behövs ytterligare typer av metadata måste de läggas till manuellt.</span><span class="sxs-lookup"><span data-stu-id="b791f-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="b791f-128">Du måste lägga till vissa metadata relaterade till externa handelstransaktioner pch markera metadataelement manuellt.</span><span class="sxs-lookup"><span data-stu-id="b791f-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="b791f-129">Välj **Lägg till datakälla \> Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="b791f-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="b791f-130">Filtrera på ett värde för **Intrastat** i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="b791f-131">Väljtabellregister **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b791f-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="b791f-132">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-132">Select **OK**.</span></span>

<span data-ttu-id="b791f-133">Du måste lägga till metadatainformation om Intrastat-tabellen med poster.</span><span class="sxs-lookup"><span data-stu-id="b791f-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="b791f-134">I trädet väljer du **Tabellregister Intrastat \> \>Relationer \> IntrastatCommodity (Tabellregister EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="b791f-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="b791f-135">Välj **Lägg till metadata**.</span><span class="sxs-lookup"><span data-stu-id="b791f-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-136">Du måste lägga till metadata för obligatoriska relationer för det valda register med poster manuellt.</span><span class="sxs-lookup"><span data-stu-id="b791f-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="b791f-137">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="b791f-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="b791f-138">Välj **uppräkning**.</span><span class="sxs-lookup"><span data-stu-id="b791f-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="b791f-139">Filtrera på ett värde för **IntrastatDirection** i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="b791f-140">Välj posten **IntrastatDirection** enumeration.</span><span class="sxs-lookup"><span data-stu-id="b791f-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="b791f-141">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-141">Select **OK**.</span></span>
20. <span data-ttu-id="b791f-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b791f-142">Select **Save**.</span></span>
21. <span data-ttu-id="b791f-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b791f-143">Close the page.</span></span>
22. <span data-ttu-id="b791f-144">Fyll i utkastet av konfigurationen av metadata;</span><span class="sxs-lookup"><span data-stu-id="b791f-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="b791f-145">Välj **Ändra status \> Slutför**.</span><span class="sxs-lookup"><span data-stu-id="b791f-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="b791f-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-146">Select **OK**.</span></span>
    3. <span data-ttu-id="b791f-147">Väljden slutförda versionen 1.</span><span class="sxs-lookup"><span data-stu-id="b791f-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="b791f-148">Exportera den slutförda versionen av metadata-konfigurationen från programmet som XML-fil:</span><span class="sxs-lookup"><span data-stu-id="b791f-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="b791f-149">Välj **Kurs \> Exportera som XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="b791f-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="b791f-150">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-150">Select **OK**.</span></span>

<span data-ttu-id="b791f-151">Konfigurationen för ER-metadata sparas som filen **utländska handelsmetadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="b791f-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="b791f-152">Du kan nu importera den till RCS så att den kan användas som källa för metadata för den utländskahandels domänen.</span><span class="sxs-lookup"><span data-stu-id="b791f-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain.</span></span> <span data-ttu-id="b791f-153">Utifrån den här informationen kan vi ange mappningen mellan programdata och ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="b791f-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="b791f-154">Få åtkomst till programmets metadata med hjälp av ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="b791f-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="b791f-155">Följande procedur visar hur en RCS.användare som har rollen **Systemadministratör** eller **Utvecklare av elektronisk rapportering** kan designa en ny ER-modellmappning genom att använda metadata från programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the application.</span></span> <span data-ttu-id="b791f-156">Programmetadata kommer att användas genom att använda en ER-metadatakonfiguration som innehåller en exempeluppsättning med metadata för att komma åt transaktioner i utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="b791f-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="b791f-157">Innan du kan slutföra proceduren, måste du först slutföra följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="b791f-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="b791f-158">Skapa en konfigurationsleverantör och välj den som aktiv</span><span class="sxs-lookup"><span data-stu-id="b791f-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="b791f-159">Förbered programdata att användas i RCS</span><span class="sxs-lookup"><span data-stu-id="b791f-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="b791f-160">Gå till **Alla arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b791f-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="b791f-161">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b791f-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="b791f-162">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren[ Skapa en konfigurationsleverantör och välj den som aktiv.](tasks/er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="b791f-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="b791f-163">Importera ER-metadatakonfigurationen som innehåller metadata från programmet som är konfigurerat att generera elektroniska dokument för domäner för utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="b791f-163">Import the ER metadata configuration that contains metadata for the application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="b791f-164">Du har skapat den här ER-konfigurationen av metadata och exporterat den som en XML-fil i proceduren [Förbereda programmetadata som kan användas i RCS](#prepare-application-metadata-that-can-be-used-in-rcs) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b791f-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="b791f-165">Välj **Metadatakonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="b791f-166">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="b791f-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="b791f-167">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="b791f-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="b791f-168">Bläddra och välj filen **Utländsk handel metadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="b791f-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="b791f-169">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-169">Select **OK**.</span></span>
    6. <span data-ttu-id="b791f-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b791f-170">Close the page.</span></span>

4. <span data-ttu-id="b791f-171">Skapa en datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="b791f-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="b791f-172">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="b791f-173">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="b791f-174">I listrutan i fältet **Namn** anger du **Utländsk handelsmodell**.</span><span class="sxs-lookup"><span data-stu-id="b791f-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="b791f-175">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="b791f-176">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="b791f-177">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b791f-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="b791f-178">Ange **root** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="b791f-179">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="b791f-180">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b791f-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="b791f-181">Ange **Transaktion** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="b791f-182">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="b791f-183">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="b791f-184">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b791f-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="b791f-185">Ange **Artikelkod** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="b791f-186">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="b791f-187">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-187">Select **Add**.</span></span>

    9. <span data-ttu-id="b791f-188">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b791f-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="b791f-189">Ange **Fakturerat belopp** i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b791f-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="b791f-190">Välj **Realtal** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="b791f-191">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-191">Select **Add**.</span></span>

    10. <span data-ttu-id="b791f-192">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b791f-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="b791f-193">Ange **Datum** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="b791f-194">Välj **Datum** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="b791f-195">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b791f-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="b791f-196">Välj **Lägg till \> Rotreferens**.</span><span class="sxs-lookup"><span data-stu-id="b791f-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="b791f-197">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-197">Select **OK**.</span></span>
    13. <span data-ttu-id="b791f-198">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b791f-198">Select **Save**.</span></span>
    14. <span data-ttu-id="b791f-199">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b791f-199">Close the page.</span></span>
    15. <span data-ttu-id="b791f-200">Välj **Ändra status \> Slutför**.</span><span class="sxs-lookup"><span data-stu-id="b791f-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="b791f-201">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-201">Select **OK**.</span></span>

5. <span data-ttu-id="b791f-202">Skapa konfiguration av modellmappning:</span><span class="sxs-lookup"><span data-stu-id="b791f-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="b791f-203">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="b791f-204">I listrutan i fältet **Ny** anger du **Modellmappning baserat på datamodellens utländsk handelsmodell**.</span><span class="sxs-lookup"><span data-stu-id="b791f-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="b791f-205">Ange **Utländsk handelsmappning** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="b791f-206">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791f-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="b791f-207">På snabbfliken **förutsättningar** väljer du **redigera**.</span><span class="sxs-lookup"><span data-stu-id="b791f-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="b791f-208">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b791f-208">Select **New**.</span></span>
    7. <span data-ttu-id="b791f-209">Välj **konfiguration** i fältet **förutsättningskomponenttyp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="b791f-210">Välj konfiguration av **metadata för utländsk handel**.</span><span class="sxs-lookup"><span data-stu-id="b791f-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="b791f-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b791f-211">Select **Save**.</span></span> <span data-ttu-id="b791f-212">Observera att referensen läggs till version 1 av konfigurationen **metadata för utländsk handel**.</span><span class="sxs-lookup"><span data-stu-id="b791f-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="b791f-213">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="b791f-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="b791f-214">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b791f-214">Close the page.</span></span>
    11. <span data-ttu-id="b791f-215">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="b791f-216">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="b791f-217">I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="b791f-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="b791f-218">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="b791f-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="b791f-219">Skriv **Dokument** i fältet **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b791f-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="b791f-220">Välj tabellregister **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b791f-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="b791f-221">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b791f-222">Endast två tabeller erbjöds eftersom de enda två tabellerna lades till i uppsättningen metadata som används.</span><span class="sxs-lookup"><span data-stu-id="b791f-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="b791f-223">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="b791f-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="b791f-224">I trädet väljer du **Intrastat \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="b791f-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="b791f-225">I trädet väljer du **Transaktion = Intrastat \> Fakturerat belopp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="b791f-226">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="b791f-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="b791f-227">I trädet väljer du **Intrastat \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="b791f-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="b791f-228">I trädet väljer du **Transaktion = Intrastat \> Datum**.</span><span class="sxs-lookup"><span data-stu-id="b791f-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="b791f-229">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="b791f-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="b791f-230">I trädet väljerdu **Intrastat \> \>Relationer \> IntrastatCommodity \> Kod**.</span><span class="sxs-lookup"><span data-stu-id="b791f-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="b791f-231">I trädet väljer du **Transaktion = Intrastat \> Artikelkod**.</span><span class="sxs-lookup"><span data-stu-id="b791f-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="b791f-232">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="b791f-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="b791f-233">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="b791f-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b791f-234">När valideringen är slutförd har du bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om programdata från den ER-metadatakonfiguration som refereras till.</span><span class="sxs-lookup"><span data-stu-id="b791f-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="b791f-235">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b791f-235">Select **Save**.</span></span>

<span data-ttu-id="b791f-236">När du behöver utöka den befintliga uppsättningen metadata kan du göra det i programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-236">As you require, you can extend the existing set of metadata in the application.</span></span> <span data-ttu-id="b791f-237">Sedan kan du exportera den nya slutförda versionen av konfigurationen för ER-metadata från, importera den till RCS och uppdatera förutsättningarna för den konfigurerade modellmappningskonfigurationen som hänvisar till en ny version av importerad metadatakonfiguration.</span><span class="sxs-lookup"><span data-stu-id="b791f-237">You can then export the new completed version of the ER metadata configuration, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="b791f-238">Det här sättet att hämta information om programdata det enda som är tillgängligt för lokalt distribuerade program (när lokala affärsdata \[LBD\] eller lokalt, distributionsmodell används för programmet).</span><span class="sxs-lookup"><span data-stu-id="b791f-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for the application).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="b791f-239">Få åtkomst till programmets metadata med hjälp av anslutna program</span><span class="sxs-lookup"><span data-stu-id="b791f-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="b791f-240">Följande procedur visar hur en RCS.användare som har rollen **Systemadministratör** eller **Utvecklare av elektronisk rapportering** kan designa en ny ER-modellmappning genom att använda metadata från programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the application.</span></span> <span data-ttu-id="b791f-241">Programdata kan nås online genom att använda det RCS-anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="b791f-242">Exempel på ER-modellmappning kommer att konfigureras för åtkomst till utländska handelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="b791f-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="b791f-243">För att slutföra den här proceduren måste du först slutföra stegen i proceduren [ER Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md) i RCS.</span><span class="sxs-lookup"><span data-stu-id="b791f-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="b791f-244">Om du inte har slutfört proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](#access-application-metadata-by-using-an-er-configuration), gå till sidan [Elektroniska rapporteringsguider för Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) för att hämta och spara följande ER-konfigurationsfiler i förväg och spara dem lokalt; **Utländsk handel metadata.xml**, **Utländsk handel model.xml**; **Utländsk handel mapping.xml** och slutför sedan stegen i proceduren.</span><span class="sxs-lookup"><span data-stu-id="b791f-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="b791f-245">Skapa nödvändiga ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="b791f-245">Get required ER configurations</span></span>

<span data-ttu-id="b791f-246">Om du redan har slutfört proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](#access-application-metadata-by-using-an-er-configuration) tidigare i det här ämnet har du redan alla ER-konfigurationer som krävs (metadata för utländsk handel, modell- och mappningskonfiguration) i den aktuella RCS-instansresursen.</span><span class="sxs-lookup"><span data-stu-id="b791f-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="b791f-247">I så fall kan du hoppa över den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="b791f-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="b791f-248">Gå till **Alla arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b791f-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="b791f-249">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="b791f-250">Läs in konfigurationsfilerna **metadata för utländsk handel.xml**, **utländsk handelsmodell.xml** och **mappning till utländsk handel.xml** som upprepar följande steg för var och en av dem:</span><span class="sxs-lookup"><span data-stu-id="b791f-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="b791f-251">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="b791f-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="b791f-252">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="b791f-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="b791f-253">välj **Bläddra** och välj en fil.</span><span class="sxs-lookup"><span data-stu-id="b791f-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="b791f-254">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791f-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-the-application"></a><span data-ttu-id="b791f-255">Registrera anslutningen till programmet</span><span class="sxs-lookup"><span data-stu-id="b791f-255">Register the connection with the application</span></span>

1. <span data-ttu-id="b791f-256">Gå till **Alla arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b791f-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="b791f-257">Välj **anslutna program**.</span><span class="sxs-lookup"><span data-stu-id="b791f-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="b791f-258">Kontrollera att det konfigurerade programmet är baserat på Microsoft Azure och att det är tillgängligt i allmänhet för att RCS-användare.</span><span class="sxs-lookup"><span data-stu-id="b791f-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="b791f-259">Den aktuella RCS-användaren måste ha åtkomst till det konfigurerade programmet och registrerats som en användare av det här programmet som ger honom eller henne behörighet att komma åt programmets metadata.</span><span class="sxs-lookup"><span data-stu-id="b791f-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="b791f-260">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b791f-260">Select **New**.</span></span>
5. <span data-ttu-id="b791f-261">Ange **MyConnectedApp** som namnet på det kopplade programmet i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b791f-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="b791f-262">Ange URL för programmet i fältet **Program**.</span><span class="sxs-lookup"><span data-stu-id="b791f-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="b791f-263">Ange leverantör för programmet i fältet **Klientorganisation**.</span><span class="sxs-lookup"><span data-stu-id="b791f-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="b791f-264">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b791f-264">Select **Save**.</span></span> 
9. <span data-ttu-id="b791f-265">När du kontrollerar anslutningen till ett konfigurerat program klickar du på sidan **Anslut till fjärrprogram**, välj länken **Välj här för att ansluta till valt fjärrprogram**.</span><span class="sxs-lookup"><span data-stu-id="b791f-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="b791f-266">Välj **kontrollera anslutningen** för att verifiera åtkomst till det konfigurerade programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="b791f-267">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="b791f-267">Select **Close**.</span></span>

<span data-ttu-id="b791f-268">När du har avslutat proceduren och anslutningsvalideringen är klar uppdateras informationen om version och klientorganisation för det konfigurerade programmet i det aktuella rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b791f-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="b791f-269">Granska befintlig konfiguration för mappning</span><span class="sxs-lookup"><span data-stu-id="b791f-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="b791f-270">Gå till **Alla arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b791f-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="b791f-271">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="b791f-272">I trädet väljer du **Utländsk handelsmodell \> Utländsk handelsmappning**.</span><span class="sxs-lookup"><span data-stu-id="b791f-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="b791f-273">Välj snabbfliken **förutsättningar**.</span><span class="sxs-lookup"><span data-stu-id="b791f-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-274">Denna mappning refererar till konfigurationen för metadata.</span><span class="sxs-lookup"><span data-stu-id="b791f-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="b791f-275">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="b791f-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="b791f-276">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-276">Select **Designer**.</span></span>
5. <span data-ttu-id="b791f-277">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-277">Select **Designer**.</span></span>
6. <span data-ttu-id="b791f-278">I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="b791f-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="b791f-279">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="b791f-279">Select **Add root**.</span></span>
8. <span data-ttu-id="b791f-280">Ange eller välj ett värde i fältet **Register**.</span><span class="sxs-lookup"><span data-stu-id="b791f-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-281">Denna mappning refererar till konfigurationen för metadata.</span><span class="sxs-lookup"><span data-stu-id="b791f-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="b791f-282">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="b791f-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="b791f-283">Välj **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="b791f-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="b791f-284">Tilldela kopplat program till modellmappning</span><span class="sxs-lookup"><span data-stu-id="b791f-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="b791f-285">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b791f-285">Select **Edit**.</span></span>
2. <span data-ttu-id="b791f-286">I **fältet kopplat program** väljer du programmet **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="b791f-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-287">Denna mappning refererar till metadata för det markerade anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="b791f-288">Om en mappning refererar till metadatakonfigurationen och det anslutna programmet samtidigt, används metadata för det anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="b791f-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="b791f-289">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-289">Select **Designer**.</span></span>
4. <span data-ttu-id="b791f-290">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b791f-290">Select **Designer**.</span></span>
5. <span data-ttu-id="b791f-291">I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="b791f-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="b791f-292">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="b791f-292">Select **Add root**.</span></span>
7. <span data-ttu-id="b791f-293">Ange eller välj ett värde i fältet **Register**.</span><span class="sxs-lookup"><span data-stu-id="b791f-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b791f-294">Nu erbjuds mer än två programtabeller eftersom mappningen använder alla metadata för det anslutna program som har tilldelats för det.</span><span class="sxs-lookup"><span data-stu-id="b791f-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="b791f-295">Välj **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="b791f-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="b791f-296">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="b791f-296">Select **Validate**.</span></span>

<span data-ttu-id="b791f-297">Du har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om metadata för det anslutna program som har tilldelats den här mappningen.</span><span class="sxs-lookup"><span data-stu-id="b791f-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="b791f-298">När du behöver utvärdera den här modellmappningen med hjälp av metadata i ett annat versionsprogram, registrerar du ett annat anslutet program, tilldelar det till den här modellmappningen och validerar det mot nya metadata.</span><span class="sxs-lookup"><span data-stu-id="b791f-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b791f-299">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b791f-299">Additional resources</span></span>

<span data-ttu-id="b791f-300">Du kan också spela upp uppgiftsguiden **förbereda programmetadata som kan användas i RCS** i programmet och uppgiftsguiderna **Få åtkomst till programmets metadata med hjälp av en ER-konfiguration** och **Få åtkomst till programmetadata med hjälp av kopplade program** i RCS.</span><span class="sxs-lookup"><span data-stu-id="b791f-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in the application as as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="b791f-301">De här uppgiftsguiderna kan hämtas på sidan [uppgiftsguiden elektronisk rapportering för Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="b791f-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>
