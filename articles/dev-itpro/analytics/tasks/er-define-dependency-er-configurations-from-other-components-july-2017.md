--- 
title: "Definiera beroendet av konfigurationer från andra komponenter för elektronisk rapportering (ER)"
description: "För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden ER Hantera modellmappningskonfigurationer, och ha åtkomst till Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/23/2017
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 1a627e2261c4c9c854b68262d7ce316ab6d40dd4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-the-dependency-of-configurations-from-othcomponents-for-electronic-reporting-er"></a><span data-ttu-id="11eae-103">Definiera beroendet av konfigurationer från andra komponenter för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="11eae-103">Define the dependency of configurations from othcomponents for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="11eae-104">För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden ER Hantera modellmappningskonfigurationer, och ha åtkomst till Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="11eae-104">To complete these steps, you must first complete the steps in the task guide, ER Manage model mapping configurations, and you must have access to Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="11eae-105">I den här proceduren beskrivs hur du skapar en konfiguration för elektronisk rapportering (ER) och anger beroendet från andra programvarukomponenter, så att du kan garantera att konfigurationen hämtas korrekt till en viss version av Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="11eae-105">This procedure shows how to design an Electronic reporting (ER) configuration and specify its dependency from other software components, so that you can help guarantee that the configuration is correctly downloaded to a specific version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="11eae-106">I det här exemplet ska du skapa erforderliga ER-konfigurationer för exempelföretaget Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="11eae-106">In this example, you will create required ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="11eae-107">Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="11eae-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="11eae-108">Dessa steg kan utföras i alla företag, eftersom ER-konfigurationer delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="11eae-108">The steps can be performed in any company, because ER configurations are shared among companies.</span></span> 

1. <span data-ttu-id="11eae-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="11eae-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
    * <span data-ttu-id="11eae-110">Kontrollera att konfigurationsträdet innehåller konfigurationen Sample data model och underordnade objekt.</span><span class="sxs-lookup"><span data-stu-id="11eae-110">Make sure that the configurations tree contains the ‘Sample data model’ configuration and subordinate items.</span></span> <span data-ttu-id="11eae-111">I annat fall genomför du stegen i uppgiftsguiden ER Hantera modellmappningskonfigurationer och startar den här guiden igen.</span><span class="sxs-lookup"><span data-stu-id="11eae-111">Otherwise, complete the steps in the task guide, ER Manage model mapping configurations, and then start this guide again.</span></span>   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a><span data-ttu-id="11eae-112">Definiera beroendet av ER-konfigurationer från andra komponenter</span><span class="sxs-lookup"><span data-stu-id="11eae-112">Define the dependency of ER configurations from other components</span></span>
1. <span data-ttu-id="11eae-113">Expandera Sample data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-113">In the tree, expand 'Sample data model'.</span></span>
2. <span data-ttu-id="11eae-114">Välj Sample data model\Sample mapping i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-114">In the tree, select 'Sample data model\Sample mapping'.</span></span>
    * <span data-ttu-id="11eae-115">Vi har valt utkastversionen av modellmappningskonfigurationen Sample mapping.</span><span class="sxs-lookup"><span data-stu-id="11eae-115">We selected the draft version of the ‘Sample mapping’ model mapping configuration.</span></span> <span data-ttu-id="11eae-116">Vi ska nu definiera beroendet från andra programvarukomponenter.</span><span class="sxs-lookup"><span data-stu-id="11eae-116">We will now define its dependency from other software components.</span></span> <span data-ttu-id="11eae-117">Det här steget anses vara en förutsättning för att styra hämtningen av den här konfigurationens version från en ER- databas och ytterligare användning av den här versionen.</span><span class="sxs-lookup"><span data-stu-id="11eae-117">This step is considered a prerequisite for controlling the download of this configuration’s version from an ER repository and any further use of this version.</span></span>   
3. <span data-ttu-id="11eae-118">Expandera avsnittet Förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="11eae-118">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="11eae-119">Observera att gruppen för implementeringsförutsättningar har lagts till automatiskt i det stadiet.</span><span class="sxs-lookup"><span data-stu-id="11eae-119">Note that the ‘Implementations’ prerequisites group has been added automatically at this stage.</span></span> <span data-ttu-id="11eae-120">Den här gruppen innehåller den nödvändiga komponent som refererar till den datamodellkonfigurationen och har flaggan Implementering aktiverad.</span><span class="sxs-lookup"><span data-stu-id="11eae-120">This group contains the prerequisite component that refers to the data model configuration and has the Implementation flag turned on.</span></span> <span data-ttu-id="11eae-121">Den här flaggan innebär modellmappningskonfigurationen Sample mapping tar hänsyn till implementeringen av datamodellen Sample data model.</span><span class="sxs-lookup"><span data-stu-id="11eae-121">This flag indicates that the ‘Sample mapping’ mapping configuration is considered the implementation of the ‘Sample data model’ data model.</span></span> <span data-ttu-id="11eae-122">Den här komponenten tvingar ER att hämta mappningskonfigurationen Sample mapping från en ER-databas när modellkonfigurationen Sample data model hämtas.</span><span class="sxs-lookup"><span data-stu-id="11eae-122">This component will force ER to download the ‘Sample mapping’ mapping configuration from an ER repository whenever the ‘Sample data model’ model configuration is downloaded.</span></span>   
4. <span data-ttu-id="11eae-123">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="11eae-123">Click Edit.</span></span>
    * <span data-ttu-id="11eae-124">Du kan ange ett enstaka beroende av den aktuella versionen av en konfiguration från en programvarukomponent med definitionen för komponenttypen, och antingen versionen av komponenten eller flera olika versioner av komponenten.</span><span class="sxs-lookup"><span data-stu-id="11eae-124">A single dependency of the current version of a configuration from a software component can be specified by using the definition of the component’s type, and either the component version or a range of component versions.</span></span>  
    * <span data-ttu-id="11eae-125">Önskade beroenden kan grupperas.</span><span class="sxs-lookup"><span data-stu-id="11eae-125">Desired dependencies can be grouped together.</span></span> <span data-ttu-id="11eae-126">När grupptypen Alla väljs, anses beroendevillkoret för den här gruppen vara uppfyllt när varje beroendevillkor från den här gruppen och den underordnade gruppen uppfylls.</span><span class="sxs-lookup"><span data-stu-id="11eae-126">When the ‘All of’ grouping type is selected, the dependency condition of this group is considered satisfied when each dependency condition from this group and subordinate group is satisfied.</span></span> <span data-ttu-id="11eae-127">När grupptypen En väljs, anses beroendevillkoret för den här gruppen vara uppfyllt när minst ett beroendevillkor från den här gruppen uppfylls.</span><span class="sxs-lookup"><span data-stu-id="11eae-127">When the ‘One of’ grouping type is selected, the dependency condition of this group is considered satisfied when at least one dependency condition from this group is satisfied.</span></span>   
5. <span data-ttu-id="11eae-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="11eae-128">Click New.</span></span>
6. <span data-ttu-id="11eae-129">Välj produktförutsättningskomponenten.</span><span class="sxs-lookup"><span data-stu-id="11eae-129">Select Product prerequisite component.</span></span>
7. <span data-ttu-id="11eae-130">Välj Microsoft Dynamics 365 for Operations (1611).</span><span class="sxs-lookup"><span data-stu-id="11eae-130">Select Microsoft Dynamics 365 for Operations (1611).</span></span>
8. <span data-ttu-id="11eae-131">Skriv "[7.1.1541.3036,8)" i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="11eae-131">In the Version field, type '[7.1.1541.3036,8)'.</span></span>
    * <span data-ttu-id="11eae-132">[7.1.1541.3036,8)</span><span class="sxs-lookup"><span data-stu-id="11eae-132">[7.1.1541.3036,8)</span></span>  
    * <span data-ttu-id="11eae-133">När den här konfigurationen har hämtats från en ER-databas utvärderas de beroenden som du anger.</span><span class="sxs-lookup"><span data-stu-id="11eae-133">Dependencies that you enter will be evaluated when this configuration is downloaded from any ER repository.</span></span> <span data-ttu-id="11eae-134">Den här konfigurationsversionen hämtas från ER-databasen när version 1 av konfigurationen Sample data redan finns på plats eller har hämtats i förväg.</span><span class="sxs-lookup"><span data-stu-id="11eae-134">This configuration version will be downloaded from the ER repository when version 1 of the ‘Sample data model’ configuration is either already in place or downloaded in advance.</span></span> <span data-ttu-id="11eae-135">Om den hämtas i förväg måste detta genomföras i Finance and Operations, versionen måste vara 7.1.1541.3036 eller senare och den får inte vara senare än huvudversion 8.</span><span class="sxs-lookup"><span data-stu-id="11eae-135">If it’s downloaded in advance, it must be completed in Finance and Operations, the version of which must be 7.1.1541.3036 or later, but must not exceed major version 8.</span></span>   
9. <span data-ttu-id="11eae-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="11eae-136">Click Save.</span></span>
10. <span data-ttu-id="11eae-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-137">Close the page.</span></span>
11. <span data-ttu-id="11eae-138">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="11eae-138">Click Change status.</span></span>
12. <span data-ttu-id="11eae-139">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="11eae-139">Click Complete.</span></span>
13. <span data-ttu-id="11eae-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-140">Click OK.</span></span>
14. <span data-ttu-id="11eae-141">Välj Sample data model\Sample mapping (alternative) i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-141">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
15. <span data-ttu-id="11eae-142">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="11eae-142">Click Edit.</span></span>
16. <span data-ttu-id="11eae-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="11eae-143">Click New.</span></span>
17. <span data-ttu-id="11eae-144">Välj produktförutsättningskomponenten.</span><span class="sxs-lookup"><span data-stu-id="11eae-144">Select Product prerequisite component.</span></span>
18. <span data-ttu-id="11eae-145">Välj Microsoft Dynamics AX 7.0 RTW.</span><span class="sxs-lookup"><span data-stu-id="11eae-145">Select Microsoft Dynamics AX 7.0 RTW.</span></span>
19. <span data-ttu-id="11eae-146">Skriv "[7.0.1265.3015,7.1)" i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="11eae-146">In the Version field, type '[7.0.1265.3015,7.1)'.</span></span>
    * <span data-ttu-id="11eae-147">[7.0.1265.3015,7.1)</span><span class="sxs-lookup"><span data-stu-id="11eae-147">[7.0.1265.3015,7.1)</span></span>  
    * <span data-ttu-id="11eae-148">Beroendena utvärderas när den här konfigurationen har hämtats från en ER-databas.</span><span class="sxs-lookup"><span data-stu-id="11eae-148">Dependencies will be evaluated when the configuration is downloaded from any ER repository.</span></span> <span data-ttu-id="11eae-149">Den här konfigurationsversionen hämtas från ER-databasen när version 1 av konfigurationen Sample data redan finns på plats eller har hämtats i förväg.</span><span class="sxs-lookup"><span data-stu-id="11eae-149">This configuration version will be downloaded from the ER repository when version 1 of the ‘Sample data model’ configuration is either already in place or downloaded in advance.</span></span> <span data-ttu-id="11eae-150">Om den hämtas i förväg måste detta genomföras i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, versionen måste vara 7.0.1265.3015 eller senare och den får inte vara senare än delversion 1. </span><span class="sxs-lookup"><span data-stu-id="11eae-150">If it’s downloaded in advance, it must be completed in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, the version of which must be 7.0.1265.3015 or later, but must not exceed minor version 1.</span></span>   
20. <span data-ttu-id="11eae-151">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="11eae-151">Click Save.</span></span>
21. <span data-ttu-id="11eae-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-152">Close the page.</span></span>
22. <span data-ttu-id="11eae-153">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="11eae-153">Click Change status.</span></span>
23. <span data-ttu-id="11eae-154">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="11eae-154">Click Complete.</span></span>
24. <span data-ttu-id="11eae-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-155">Click OK.</span></span>

## <a name="configure-the-er-repository"></a><span data-ttu-id="11eae-156">Konfigurera ER-databasen</span><span class="sxs-lookup"><span data-stu-id="11eae-156">Configure the ER repository</span></span>
1. <span data-ttu-id="11eae-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-157">Close the page.</span></span>
2. <span data-ttu-id="11eae-158">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="11eae-158">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="11eae-159">Öppna listan över ER-databaser den aktuella ER-leverantören, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="11eae-159">Open the list of ER repositories for the current ER provider, Litware, Inc.</span></span>  
3. <span data-ttu-id="11eae-160">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="11eae-160">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="11eae-161">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="11eae-161">Click Repositories.</span></span>
5. <span data-ttu-id="11eae-162">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="11eae-162">Click Show filters.</span></span>
6. <span data-ttu-id="11eae-163">Ange filtervärdet "LCS" i fältet "Typnamn" med filteroperatorn "innehåller".</span><span class="sxs-lookup"><span data-stu-id="11eae-163">Enter a filter value of "LCS" on the "Type name" field using the "contains" filter operator.</span></span>
    * <span data-ttu-id="11eae-164">Om LCS-databasen redan är registrerad för den aktuella ER-leverantören du kan hoppa över resten av stegen i den här underaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="11eae-164">If the LCS repository is already registered for the current ER provider, you can skip the remaining steps in this sub-task.</span></span> <span data-ttu-id="11eae-165">Om LCS-databasen inte redan är registrerad ska du utföra resten av stegen.</span><span class="sxs-lookup"><span data-stu-id="11eae-165">If the LCS repository isn’t already registered, complete the remaining steps.</span></span>   
7. <span data-ttu-id="11eae-166">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="11eae-166">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="11eae-167">Skriv "LCS" i fältet Typ av konfigurationsdatabas.</span><span class="sxs-lookup"><span data-stu-id="11eae-167">In the Configuration repository type field, enter 'LCS'.</span></span>
9. <span data-ttu-id="11eae-168">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="11eae-168">Click Create repository.</span></span>
10. <span data-ttu-id="11eae-169">Ange eller välj ett värde i fältet Projekt.</span><span class="sxs-lookup"><span data-stu-id="11eae-169">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="11eae-170">Välj önskat LCS-projekt från sökningen i fältet Projekt.</span><span class="sxs-lookup"><span data-stu-id="11eae-170">Select the desired LCS project from the lookup of the ‘Project’ field.</span></span>  
11. <span data-ttu-id="11eae-171">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-171">Click OK.</span></span>
12. <span data-ttu-id="11eae-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-172">Close the page.</span></span>

## <a name="upload-configurations-to-lcs"></a><span data-ttu-id="11eae-173">Överför konfigurationer till LCS</span><span class="sxs-lookup"><span data-stu-id="11eae-173">Upload configurations to LCS</span></span>
1. <span data-ttu-id="11eae-174">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="11eae-174">Click Reporting configurations.</span></span>
2. <span data-ttu-id="11eae-175">Välj "Sample data model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-175">In the tree, select 'Sample data model'.</span></span>
3. <span data-ttu-id="11eae-176">Välj den slutförda versionen av den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="11eae-176">Select the completed version of this configuration.</span></span>
4. <span data-ttu-id="11eae-177">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="11eae-177">Click Change status.</span></span>
5. <span data-ttu-id="11eae-178">Klicka Dela.</span><span class="sxs-lookup"><span data-stu-id="11eae-178">Click Share.</span></span>
6. <span data-ttu-id="11eae-179">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-179">Click OK.</span></span>
    * <span data-ttu-id="11eae-180">Version 1 av denna modellkonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.</span><span class="sxs-lookup"><span data-stu-id="11eae-180">Version 1 of this model configuration has been uploaded to LCS by using the LCS project for the ER repository that was previously configured.</span></span>   
7. <span data-ttu-id="11eae-181">Expandera Sample data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-181">In the tree, expand 'Sample data model'.</span></span>
8. <span data-ttu-id="11eae-182">Välj Sample data model\Sample mapping i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-182">In the tree, select 'Sample data model\Sample mapping'.</span></span>
9. <span data-ttu-id="11eae-183">Välj den slutförda versionen av den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="11eae-183">Select the completed version of this configuration.</span></span>
10. <span data-ttu-id="11eae-184">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="11eae-184">Click Change status.</span></span>
11. <span data-ttu-id="11eae-185">Klicka Dela.</span><span class="sxs-lookup"><span data-stu-id="11eae-185">Click Share.</span></span>
12. <span data-ttu-id="11eae-186">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-186">Click OK.</span></span>
    * <span data-ttu-id="11eae-187">Version 1.1 av denna modellmappningskonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.</span><span class="sxs-lookup"><span data-stu-id="11eae-187">Version 1.1 of this model mapping configuration has been uploaded to LCS by using the LCS project for the ER repository that was previously configured.</span></span>   
13. <span data-ttu-id="11eae-188">Välj Sample data model\Sample mapping (alternative) i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-188">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
14. <span data-ttu-id="11eae-189">Välj den slutförda versionen av den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="11eae-189">Select the completed version of this configuration.</span></span>
15. <span data-ttu-id="11eae-190">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="11eae-190">Click Change status.</span></span>
16. <span data-ttu-id="11eae-191">Klicka Dela.</span><span class="sxs-lookup"><span data-stu-id="11eae-191">Click Share.</span></span>
17. <span data-ttu-id="11eae-192">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11eae-192">Click OK.</span></span>
    * <span data-ttu-id="11eae-193">Version 1.1 av denna modellmappningskonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.</span><span class="sxs-lookup"><span data-stu-id="11eae-193">Version 1.1 of this model mapping configuration has been uploaded to LCS by using the LCS project for the ER repository that was previously configured.</span></span>   

## <a name="evaluate-er-configuration-dependencies"></a><span data-ttu-id="11eae-194">Utvärdera beroenden för ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="11eae-194">Evaluate ER configuration dependencies</span></span>
    * <span data-ttu-id="11eae-195">Vi ska ta bort de skapade konfigurationerna från systemet och hämta tillbaka dem från LCS-databasen.</span><span class="sxs-lookup"><span data-stu-id="11eae-195">We will delete created configurations from the system and download them back from the LCS repository.</span></span>  
1. <span data-ttu-id="11eae-196">Välj Sample data model\Sample mapping i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-196">In the tree, select 'Sample data model\Sample mapping'.</span></span>
2. <span data-ttu-id="11eae-197">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="11eae-197">Click Delete.</span></span>
3. <span data-ttu-id="11eae-198">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="11eae-198">Click Yes.</span></span>
4. <span data-ttu-id="11eae-199">Välj Sample data model\Sample mapping (alternative) i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-199">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
5. <span data-ttu-id="11eae-200">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="11eae-200">Click Delete.</span></span>
6. <span data-ttu-id="11eae-201">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="11eae-201">Click Yes.</span></span>
7. <span data-ttu-id="11eae-202">Välj Sample data model\Sample format i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-202">In the tree, select 'Sample data model\Sample format'.</span></span>
8. <span data-ttu-id="11eae-203">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="11eae-203">Click Delete.</span></span>
9. <span data-ttu-id="11eae-204">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="11eae-204">Click Yes.</span></span>
10. <span data-ttu-id="11eae-205">Välj "Sample data model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-205">In the tree, select 'Sample data model'.</span></span>
11. <span data-ttu-id="11eae-206">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="11eae-206">Click Delete.</span></span>
12. <span data-ttu-id="11eae-207">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="11eae-207">Click Yes.</span></span>
13. <span data-ttu-id="11eae-208">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-208">Close the page.</span></span>
    * <span data-ttu-id="11eae-209">Öppna listan över ER-databaser den aktuella ER-leverantören, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="11eae-209">Open the list of ER repositories for the current ER provider, Litware, Inc.</span></span>  
14. <span data-ttu-id="11eae-210">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="11eae-210">Click Repositories.</span></span>
15. <span data-ttu-id="11eae-211">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="11eae-211">Click Show filters.</span></span>
16. <span data-ttu-id="11eae-212">Ange filtervärdet "LCS" i fältet "Typnamn" med filteroperatorn "innehåller".</span><span class="sxs-lookup"><span data-stu-id="11eae-212">Enter a filter value of "LCS" on the "Type name" field using the "contains" filter operator.</span></span>
17. <span data-ttu-id="11eae-213">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="11eae-213">Click Open.</span></span>
18. <span data-ttu-id="11eae-214">Välj "Sample data model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-214">In the tree, select 'Sample data model'.</span></span>
    * <span data-ttu-id="11eae-215">Observera att du kan visa en utvärdering av om nödvändiga villkor är uppfyllda för varje version av ER-konfigurationerna för den aktuella databasen.</span><span class="sxs-lookup"><span data-stu-id="11eae-215">Note that you can view an evaluation of whether prerequisite conditions have been satisfied for each version of the ER configurations for the current repository.</span></span> <span data-ttu-id="11eae-216">Visa utvärderingen genom att klicka på Kontrollera förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="11eae-216">To view this evaluation, click Check prerequisites.</span></span>   
19. <span data-ttu-id="11eae-217">Klicka på Kontrollera förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="11eae-217">Click Check prerequisites.</span></span>
20. <span data-ttu-id="11eae-218">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="11eae-218">Click Import.</span></span>
21. <span data-ttu-id="11eae-219">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="11eae-219">Click Yes.</span></span>
22. <span data-ttu-id="11eae-220">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-220">Close the page.</span></span>
23. <span data-ttu-id="11eae-221">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-221">Close the page.</span></span>
24. <span data-ttu-id="11eae-222">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="11eae-222">Close the page.</span></span>
25. <span data-ttu-id="11eae-223">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="11eae-223">Go to Organization administration > Electronic reporting > Configurations.</span></span>
26. <span data-ttu-id="11eae-224">Expandera Sample data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="11eae-224">In the tree, expand 'Sample data model'.</span></span>
    * <span data-ttu-id="11eae-225">Observera att modellkonfigurationen Sample mapping har hämtats tillsammans med den valda datamodellkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="11eae-225">Note that the model ‘Sample mapping’ mapping configuration has been downloaded together with the selected data model configuration.</span></span> <span data-ttu-id="11eae-226">De två filerna hämtas tillsammans eftersom Sample mapping har definierats till att implementera den valda datamodellen, och eftersom den gäller för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11eae-226">The two files are downloaded together because ‘Sample mapping’ has been defined as implementing the selected data model, and because it’s applicable for Finance and Operations.</span></span> <span data-ttu-id="11eae-227">Konfigurationen Sample mapping (alternative) har inte hämtats eftersom villkoret för programversionen inte är uppfyllt.</span><span class="sxs-lookup"><span data-stu-id="11eae-227">The ‘Sample mapping (alternative)’ configuration hasn’t been downloaded because the condition for the required application version isn’t satisfied.</span></span>   
    * <span data-ttu-id="11eae-228">Om du loggar in till Dynamics 365 for Finance and Operations, Enterprise Edition, registrerar samma leverantör, öppnar LCS-projektet och hämtar samma datamodellkonfiguration, hämtas konfigurationen Sample mapping (alternative) medan konfigurationen Sample mapping hoppas över.</span><span class="sxs-lookup"><span data-stu-id="11eae-228">If you sign in to Dynamics 365 for Finance and Operations, Enterprise edition, register the same provider, access the same LCS project, and download the same data model configuration, the ‘Sample mapping (alternative)’ configuration will download, whereas the ‘Sample mapping’ configuration will be skipped.</span></span>  

