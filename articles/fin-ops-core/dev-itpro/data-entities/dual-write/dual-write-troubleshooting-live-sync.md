---
title: Felsöka problem med direkt synkronisering
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med direkt synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b40b71eb45ae5a95a732c9554356afcddecb750e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566823"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="b9c29-103">Felsöka problem med direkt synkronisering</span><span class="sxs-lookup"><span data-stu-id="b9c29-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="b9c29-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b9c29-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="b9c29-105">Särskilt ger den information som kan hjälpa dig att åtgärda problem med direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="b9c29-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9c29-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="b9c29-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="b9c29-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="b9c29-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="b9c29-108">En direkt synkronisering returnerar felet 403-förbud när du skapar en rad i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="b9c29-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="b9c29-109">Följande felmeddelande kan visas när du skapar i en rad i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="b9c29-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="b9c29-110">*\[{\\"fel\\":{\\"kod\\":\\"0x80072560\\",\\"meddelande\\":\\"Användaren är inte en medlem av organisationen.\\"}}\], Fjärrservern returnerade ett fel: (403) förbjudet."}}".*</span><span class="sxs-lookup"><span data-stu-id="b9c29-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="b9c29-111">Om du vill åtgärda problemet följer du stegen i [Systemkrav och förutsättningar](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="b9c29-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="b9c29-112">För att kunna utföra dessa steg måste användare av apen med dubbelriktad skrivning som skapas i Dataverse ha rollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b9c29-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="b9c29-113">Teamet för standardägargrupp måste också ha rollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b9c29-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="b9c29-114">En direkt synkronisering någon tabell ger konsekvent ett liknande fel när du skapar en rad i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="b9c29-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="b9c29-115">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="b9c29-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="b9c29-116">Ett felmeddelande kan visas som följande varje gång du försöker spara tabelldata i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="b9c29-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="b9c29-117">*Det går inte att spara ändringarna i databasen. Arbetsenheten kan inte genomföra transaktionen. Det gick inte att skriva data till entitets-uoms. Skrivningar till UnitOfMeasureEntity misslyckades med felmeddelandet Det gick inte att synkronisera med entitets-uoms.*</span><span class="sxs-lookup"><span data-stu-id="b9c29-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="b9c29-118">För att lösa problemet måste du se till att de förutsatta referensdata finns i både Finance and Operations-appen och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b9c29-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="b9c29-119">Till exempel om kunden du är i Finance and Operations-appen tillhör en viss kundgrupp, se till att den kundgruppen finns i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b9c29-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="b9c29-120">Om det finns data på båda sidor och du har bekräftat att problemet inte är datarelaterat följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b9c29-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="b9c29-121">Stoppa den relaterade tabellen.</span><span class="sxs-lookup"><span data-stu-id="b9c29-121">Stop the related table.</span></span>
2. <span data-ttu-id="b9c29-122">Logga in på Finance and Operations-appen och se till att det finns rader för den felaktiga tabellen i tabellerna DualWriteProjectConfiguration och DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b9c29-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="b9c29-123">Här ser till exempel frågan ut som om tabellen **Kunder** misslyckas.</span><span class="sxs-lookup"><span data-stu-id="b9c29-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="b9c29-124">Om det finns rader för den felaktiga tabellen även efter att du har stoppat entitetsmappningen tar du bort de poster som är relaterade till den felaktiga tabellen.</span><span class="sxs-lookup"><span data-stu-id="b9c29-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="b9c29-125">Anteckna kolumnen **projektnamn** i tabellen DualWriteProjectConfiguration och hämta posten i raden DualWriteProjectFieldConfiguration med hjälp av projektnamnet för att radera raden.</span><span class="sxs-lookup"><span data-stu-id="b9c29-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="b9c29-126">Starta tabellmappningen.</span><span class="sxs-lookup"><span data-stu-id="b9c29-126">Start the table mapping.</span></span> <span data-ttu-id="b9c29-127">Verifiera om data synkroniseras utan problem.</span><span class="sxs-lookup"><span data-stu-id="b9c29-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="b9c29-128">Hantera läs- eller skrivbehörighetsfel när du skapar data i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="b9c29-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="b9c29-129">Felmeddelandet "Felaktig begäran" kan visas som liknar följande exempel när du skapar data i en Finance and Operations-app.</span><span class="sxs-lookup"><span data-stu-id="b9c29-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exempel på felmeddelandet Felaktig begäran](media/error_record_id_source.png)

<span data-ttu-id="b9c29-131">För att åtgärda problemet måste du tilldela rätt säkerhetsroll till teamet för den mappade affärsenheten Dynamics 365 Sales eller Dynamics 365 Customer Service för att aktivera den saknade behörigheten.</span><span class="sxs-lookup"><span data-stu-id="b9c29-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="b9c29-132">I Finance and Operations-appen, leta reda på den affärsenhet som är mappad till anslutningsuppsättningen för dataintegration.</span><span class="sxs-lookup"><span data-stu-id="b9c29-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Organisationsmappning](media/mapped_business_unit.png)

2. <span data-ttu-id="b9c29-134">Logga in på miljön i den modellstyrda appen i Dynamics 365, gå till **Inställningar \> Säkerhet** och hitta teamet för den mappade affärsenheten.</span><span class="sxs-lookup"><span data-stu-id="b9c29-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Team av den mappade affärsenheten](media/setting_security_page.png)

3. <span data-ttu-id="b9c29-136">Öppna sidan för teamet som ska redigeras och välj sedan **Hantera Roller** för att öppna dialogrutan **Hantera teamroller**.</span><span class="sxs-lookup"><span data-stu-id="b9c29-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Knappen Hantera roller](media/manage_team_roles.png)

4. <span data-ttu-id="b9c29-138">Tilldela rollen som har läs-/skrivbehörighet för de relevanta tabellerna och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9c29-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="b9c29-139">Åtgärda synkroniseringsproblem i en miljö som har en nyligen ändrad Dataverse-miljö</span><span class="sxs-lookup"><span data-stu-id="b9c29-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="b9c29-140">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="b9c29-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="b9c29-141">Följande felmeddelande kan visas när du skapar data i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="b9c29-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="b9c29-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Det gick inte att generera nyttolast för entiteten CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Skapande av nyttolast misslyckades med fel URI: URI är tom."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="b9c29-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="b9c29-143">Så här ser felet ut i den modellstyrda appen i Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="b9c29-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="b9c29-144">*Ett oväntat fel uppstod från ISV-koden. (ErrorType = ClientError) Oväntat undantag från plugin-programmet (kör): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: misslyckades att bearbeta ett entitetskonto - (Ett anslutningsförsök misslyckades eftersom den anslutna parten inte svarade ordentligt efter en tidsperiod, eller upprättad anslutning misslyckades eftersom ansluten värd inte har svarat*</span><span class="sxs-lookup"><span data-stu-id="b9c29-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="b9c29-145">Det här felet uppstår när Dataverse miljön återställs felaktigt samtidigt som du försöker skapa data i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="b9c29-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="b9c29-146">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="b9c29-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="b9c29-147">Logga in på Finance and Operations virtuell dator (VM), öppna SQL Server Management Studio (SSMS) och leta efter rader i tabellen DUALWRITEPROJECTCONFIGURATIONENTITY där **internalentityname** är lika med **Kunder V3** och **externalentityname** är lika med **Konton**.</span><span class="sxs-lookup"><span data-stu-id="b9c29-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="b9c29-148">Så här ser frågan ut.</span><span class="sxs-lookup"><span data-stu-id="b9c29-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="b9c29-149">Använd projektnamnet från resultatet av föregående fråga för att köra följande fråga.</span><span class="sxs-lookup"><span data-stu-id="b9c29-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="b9c29-150">Kontrollera att kolumnen **externalenvironmentURL** har korrekt Dataverse eller app URL.</span><span class="sxs-lookup"><span data-stu-id="b9c29-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="b9c29-151">Radera alla dubblettrader som pekar på fel Dataverse URL.</span><span class="sxs-lookup"><span data-stu-id="b9c29-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="b9c29-152">Ta bort motsvarande rader i tabellerna DUALWRITEPROJECTFIELDCONFIGURATION och DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="b9c29-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="b9c29-153">Stoppa tabellmappningen och starta sedan om den</span><span class="sxs-lookup"><span data-stu-id="b9c29-153">Stop the table mapping, and then restart it</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]