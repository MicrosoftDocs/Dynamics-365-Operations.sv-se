---
title: Felsöka problem med direkt synkronisering
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med direkt synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 60839bbd1b3ae642cdd419c7df2388292776a461
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172747"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="fb85f-103">Felsöka problem med direkt synkronisering</span><span class="sxs-lookup"><span data-stu-id="fb85f-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="fb85f-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fb85f-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="fb85f-105">Särskilt ger den information som kan hjälpa dig att åtgärda problem med direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="fb85f-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb85f-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="fb85f-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="fb85f-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="fb85f-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="fb85f-108">En direkt synkronisering returnerar felet 403 förbud mot att skapa en post i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="fb85f-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="fb85f-109">Följande felmeddelande kan visas när du skapar i en post i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="fb85f-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="fb85f-110">*\[{\\"fel\\":{\\"kod\\":\\"0x80072560\\",\\"meddelande\\":\\"Användaren är inte en medlem av organisationen.\\"}}\], Fjärrservern returnerade ett fel: (403) förbjudet."}}".*</span><span class="sxs-lookup"><span data-stu-id="fb85f-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="fb85f-111">Om du vill åtgärda problemet följer du stegen i [Systemkrav och förutsättningar](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="fb85f-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="fb85f-112">För att kunna utföra dessa steg måste användare av apen med dubbelriktad skrivning som skapas i Common Data Service ha rollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fb85f-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="fb85f-113">Teamet för standardägargrupp måste också ha rollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fb85f-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="fb85f-114">En direkt synkronisering någon entitet ger konsekvent ett liknande fel när du skapar en post i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="fb85f-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="fb85f-115">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="fb85f-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="fb85f-116">Ett felmeddelande kan visas som följande varje gång du försöker spara entitetsdata i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="fb85f-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="fb85f-117">*Det går inte att spara ändringarna i databasen. Arbetsenheten kan inte genomföra transaktionen. Det gick inte att skriva data till entitets-uoms. Skrivningar till UnitOfMeasureEntity misslyckades med felmeddelandet Det gick inte att synkronisera med entitets-uoms.*</span><span class="sxs-lookup"><span data-stu-id="fb85f-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="fb85f-118">För att lösa problemet måste du se till att de förutsatta referensdata finns i både Finance and Operations-appen och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fb85f-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="fb85f-119">Till exempel om kunden du är i Finance and Operations-appen tillhör en viss kundgrupp, se till att den kundgruppen finns i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fb85f-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="fb85f-120">Om det finns data på båda sidor och du har bekräftat att problemet inte är datarelaterat följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="fb85f-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="fb85f-121">Stoppa den relaterade entiteten.</span><span class="sxs-lookup"><span data-stu-id="fb85f-121">Stop the related entity.</span></span>
2. <span data-ttu-id="fb85f-122">Logga in på Finance and Operations-appen och se till att det finns poster för den felaktiga entiteten i tabellerna DualWriteProjectConfiguration och DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fb85f-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="fb85f-123">Här ser till exempel frågan ut som om entiteten **Kunder** misslyckas.</span><span class="sxs-lookup"><span data-stu-id="fb85f-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="fb85f-124">Om det finns poster för den felaktiga entiteten även efter att du har stoppat entitetsmappningen tar du bort de poster som är relaterade till den felaktiga entiteten.</span><span class="sxs-lookup"><span data-stu-id="fb85f-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="fb85f-125">Anteckna kolumnen **projektnamn** i tabellen DualWriteProjectConfiguration och hämta posten i tabellen DualWriteProjectFieldConfiguration med hjälp av projektnamnet för att ta bort posten.</span><span class="sxs-lookup"><span data-stu-id="fb85f-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="fb85f-126">Starta entitetsmappningen.</span><span class="sxs-lookup"><span data-stu-id="fb85f-126">Start the entity mapping.</span></span> <span data-ttu-id="fb85f-127">Verifiera om data synkroniseras utan problem.</span><span class="sxs-lookup"><span data-stu-id="fb85f-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="fb85f-128">Hantera läs- eller skrivbehörighetsfel när du skapar data i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="fb85f-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="fb85f-129">Felmeddelandet "Felaktig begäran" kan visas som liknar följande exempel när du skapar data i en Finance and Operations-app.</span><span class="sxs-lookup"><span data-stu-id="fb85f-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exempel på felmeddelandet Felaktig begäran](media/error_record_id_source.png)

<span data-ttu-id="fb85f-131">För att åtgärda problemet måste du tilldela rätt säkerhetsroll till teamet för den mappade affärsenheten Dynamics 365 Sales eller Dynamics 365 Customer Service för att aktivera den saknade behörigheten.</span><span class="sxs-lookup"><span data-stu-id="fb85f-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="fb85f-132">I Finance and Operations-appen, leta reda på den affärsenhet som är mappad till anslutningsuppsättningen för dataintegration.</span><span class="sxs-lookup"><span data-stu-id="fb85f-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Organisationsmappning](media/mapped_business_unit.png)

2. <span data-ttu-id="fb85f-134">Logga in på miljön i den modellstyrda appen i Dynamics 365, gå till **Inställningar \> Säkerhet** och hitta teamet för den mappade affärsenheten.</span><span class="sxs-lookup"><span data-stu-id="fb85f-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Team av den mappade affärsenheten](media/setting_security_page.png)

3. <span data-ttu-id="fb85f-136">Öppna sidan för teamet som ska redigeras och välj sedan **Hantera Roller** för att öppna dialogrutan **Hantera teamroller**.</span><span class="sxs-lookup"><span data-stu-id="fb85f-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Knappen Hantera roller](media/manage_team_roles.png)

4. <span data-ttu-id="fb85f-138">Tilldela rollen som har läs-/skrivbehörigheten för e relevanta entiteterna och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb85f-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="fb85f-139">Åtgärda synkroniseringsproblem i en miljö som har en nyligen ändrad Common Data Service-miljö</span><span class="sxs-lookup"><span data-stu-id="fb85f-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="fb85f-140">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="fb85f-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="fb85f-141">Följande felmeddelande kan visas när du skapar data i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="fb85f-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="fb85f-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Det gick inte att generera nyttolast för entiteten CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Skapande av nyttolast misslyckades med fel URI: URI är tom."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="fb85f-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="fb85f-143">Så här ser felet ut i den modellstyrda appen i Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="fb85f-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="fb85f-144">*Ett oväntat fel uppstod från ISV-koden. (ErrorType = ClientError) Oväntat undantag från plugin-programmet (kör): Microsoft.Dynamics.Integrator.CrmPlugins.Plugin: System.Exception: misslyckades att bearbeta ett entitetskonto - (Ett anslutningsförsök misslyckades eftersom den anslutna parten inte svarade ordentligt efter en tidsperiod, eller upprättad anslutning misslyckades eftersom ansluten värd inte har svarat*</span><span class="sxs-lookup"><span data-stu-id="fb85f-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.CrmPlugins.Plugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="fb85f-145">Det här felet uppstår när Common Data Service miljön återställs felaktigt samtidigt som du försöker skapa data i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="fb85f-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="fb85f-146">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="fb85f-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="fb85f-147">Logga in på Finance and Operations virtuell dator (VM), öppna SQL Server Management Studio (SSMS) och leta efter poster i registret DUALWRITEPROJECTCONFIGURATIONENTITY där **internalentityname** är lika med **Customers V3** och **externalentityname** lika med **konton**.</span><span class="sxs-lookup"><span data-stu-id="fb85f-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="fb85f-148">Så här ser frågan ut.</span><span class="sxs-lookup"><span data-stu-id="fb85f-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="fb85f-149">Använd projektnamnet från resultatet av föregående fråga för att köra följande fråga.</span><span class="sxs-lookup"><span data-stu-id="fb85f-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="fb85f-150">Kontrollera att kolumnen **externalenvironmentURL** har korrekt Common Data Service eller app URL.</span><span class="sxs-lookup"><span data-stu-id="fb85f-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="fb85f-151">Ta bort alla dubblettposter som pekar på fel Common Data Service URL.</span><span class="sxs-lookup"><span data-stu-id="fb85f-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="fb85f-152">Ta bort motsvarande poster i registren DUALWRITEPROJECTFIELDCONFIGURATION och DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="fb85f-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="fb85f-153">Stoppa entitetsmappningen och starta sedan om den</span><span class="sxs-lookup"><span data-stu-id="fb85f-153">Stop the entity mapping, and then restart it</span></span>
