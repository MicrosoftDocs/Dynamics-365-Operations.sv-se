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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 82bdcc71196c22689cc65601f98187aaa9e5e9d6
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997312"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Felsöka problem med direkt synkronisering

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Särskilt ger den information som kan hjälpa dig att åtgärda problem med direkt synkronisering.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>En direkt synkronisering returnerar felet 403 förbud mot att skapa en post i en Finance and Operations-app

Följande felmeddelande kan visas när du skapar i en post i en Finance and Operations-app:

*\[{\\"fel\\":{\\"kod\\":\\"0x80072560\\",\\"meddelande\\":\\"Användaren är inte en medlem av organisationen.\\"}}\], Fjärrservern returnerade ett fel: (403) förbjudet."}}".*

Om du vill åtgärda problemet följer du stegen i [Systemkrav och förutsättningar](requirements-and-prerequisites.md). För att kunna utföra dessa steg måste användare av apen med dubbelriktad skrivning som skapas i Common Data Service ha rollen systemadministratör. Teamet för standardägargrupp måste också ha rollen systemadministratör.

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>En direkt synkronisering någon entitet ger konsekvent ett liknande fel när du skapar en post i en Finance and Operations-app

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Ett felmeddelande kan visas som följande varje gång du försöker spara entitetsdata i en Finance and Operations-app:

*Det går inte att spara ändringarna i databasen. Arbetsenheten kan inte genomföra transaktionen. Det gick inte att skriva data till entitets-uoms. Skrivningar till UnitOfMeasureEntity misslyckades med felmeddelandet Det gick inte att synkronisera med entitets-uoms.*

För att lösa problemet måste du se till att de förutsatta referensdata finns i både Finance and Operations-appen och Common Data Service. Till exempel om kunden du är i Finance and Operations-appen tillhör en viss kundgrupp, se till att den kundgruppen finns i Common Data Service.

Om det finns data på båda sidor och du har bekräftat att problemet inte är datarelaterat följer du dessa steg.

1. Stoppa den relaterade entiteten.
2. Logga in på Finance and Operations-appen och se till att det finns poster för den felaktiga entiteten i tabellerna DualWriteProjectConfiguration och DualWriteProjectFieldConfiguration. Här ser till exempel frågan ut som om entiteten **Kunder** misslyckas.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Om det finns poster för den felaktiga entiteten även efter att du har stoppat entitetsmappningen tar du bort de poster som är relaterade till den felaktiga entiteten. Anteckna kolumnen **projektnamn** i tabellen DualWriteProjectConfiguration och hämta posten i tabellen DualWriteProjectFieldConfiguration med hjälp av projektnamnet för att ta bort posten.
4. Starta entitetsmappningen. Verifiera om data synkroniseras utan problem.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Hantera läs- eller skrivbehörighetsfel när du skapar data i en Finance and Operations-app

Felmeddelandet "Felaktig begäran" kan visas som liknar följande exempel när du skapar data i en Finance and Operations-app.

![Exempel på felmeddelandet Felaktig begäran](media/error_record_id_source.png)

För att åtgärda problemet måste du tilldela rätt säkerhetsroll till teamet för den mappade affärsenheten Dynamics 365 Sales eller Dynamics 365 Customer Service för att aktivera den saknade behörigheten.

1. I Finance and Operations-appen, leta reda på den affärsenhet som är mappad till anslutningsuppsättningen för dataintegration.

    ![Organisationsmappning](media/mapped_business_unit.png)

2. Logga in på miljön i den modellstyrda appen i Dynamics 365, gå till **Inställningar \> Säkerhet** och hitta teamet för den mappade affärsenheten.

    ![Team av den mappade affärsenheten](media/setting_security_page.png)

3. Öppna sidan för teamet som ska redigeras och välj sedan **Hantera Roller** för att öppna dialogrutan **Hantera teamroller**.

    ![Knappen Hantera roller](media/manage_team_roles.png)

4. Tilldela rollen som har läs-/skrivbehörigheten för e relevanta entiteterna och välj sedan **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a>Åtgärda synkroniseringsproblem i en miljö som har en nyligen ändrad Common Data Service-miljö

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du skapar data i en Finance and Operations-app:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":" **Det gick inte att generera nyttolast för entiteten CustCustomerV3Entity** ","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Skapande av nyttolast misslyckades med fel URI: URI är tom."}\],"isErrorCountUpdated":true}*

Så här ser felet ut i den modellstyrda appen i Dynamics 365:

*Ett oväntat fel uppstod från ISV-koden. (ErrorType = ClientError) Oväntat undantag från plugin-programmet (kör): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: misslyckades att bearbeta ett entitetskonto - (Ett anslutningsförsök misslyckades eftersom den anslutna parten inte svarade ordentligt efter en tidsperiod, eller upprättad anslutning misslyckades eftersom ansluten värd inte har svarat*

Det här felet uppstår när Common Data Service miljön återställs felaktigt samtidigt som du försöker skapa data i Finance and Operations-appen.

Gör så här om du vill åtgärda problemet.

1. Logga in på Finance and Operations virtuell dator (VM), öppna SQL Server Management Studio (SSMS) och leta efter poster i registret DUALWRITEPROJECTCONFIGURATIONENTITY där **internalentityname** är lika med **Customers V3** och **externalentityname** lika med **konton**. Så här ser frågan ut.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Använd projektnamnet från resultatet av föregående fråga för att köra följande fråga.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Kontrollera att kolumnen **externalenvironmentURL** har korrekt Common Data Service eller app URL. Ta bort alla dubblettposter som pekar på fel Common Data Service URL. Ta bort motsvarande poster i registren DUALWRITEPROJECTFIELDCONFIGURATION och DUALWRITEPROJECTCONFIGURATION.
4. Stoppa entitetsmappningen och starta sedan om den
