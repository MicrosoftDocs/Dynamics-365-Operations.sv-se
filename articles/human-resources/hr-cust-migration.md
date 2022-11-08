---
title: Dynamics 365 Human Resources kundmigrering till infrastrukturen för ekonomi och drift
description: Den här artikeln beskriver kundmigrering av Microsoft Dynamics 365 Human Resources till ekonomi- och driftsinfrastrukturen.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63b08a8493702cf319aa078ef6aa787e2094be87
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733464"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Dynamics 365 Human Resources kundmigrering

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

Kundmigrering är en "Lift and Shift-migrering" (rörelse) för en kunddatabas till den infrastruktur som används för ekonomi och drift. Automatiserad migreringsverktyg används för den. Resultatet är en ny ekonomi- och driftmiljö som använder kundens Personal-databas.

## <a name="prerequisites"></a>Förutsättningar

### <a name="user-access-and-permissions"></a>Användaråtkomst och behörighet

- Microsoft Dynamics Lifecycle Services-användaren ska ha rollen **Organisationsadministration**.
- Användaren ska kunna [skapa Azure DevOps-projekt](/azure/devops/organizations/projects/create-project) eller använda befintlig Azure DevOps-projekt.
- Användaren ska ha åtkomst till att [skapa en Azure DevOps säkerhetstoken för personlig åtkomst](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) eller ha en token som är tillgänglig för användning.

### <a name="dataverse-environment-backup-sandbox"></a>Dataverse-miljö säkerhetskopia (Sandbox)

1. Valfri men rekommenderad: Uppdatera den befintliga sandbox-miljön för Personal med hjälp av en kopia av personalproduktionsmiljön.
2. [Skapa en ny Dataverse-miljö](/power-platform/admin/create-environment#create-an-environment-with-a-database) genom att ändra Power Platform administrationscentret.

    > [!NOTE]
    > När du lägger till en databas måste alternativet **Aktivera Dynamics 365-program** vara inställt på **Ja**.

3. [Kopiera den befintliga Dataverse-miljön](/power-platform/admin/copy-environment), som är länkad till det fristående programmet Personal, till den miljö du skapade i det föregående steget.

### <a name="dataverse-capacity"></a>Dataverse-kapacitet

1. Använd sidan **Sammanfattning** i Power Platform administrationscenter för att kontrollera att [Dataverse lagringen](/power-platform/admin/finance-operations-storage-capacity) har tillräckligt med tillgänglig kapacitet för miljökopian.
2. Om det inte finns tillräcklig tillgänglig kapacitet bör du använda [riktlinjer för att frigöra lagringsutrymme](/power-platform/admin/free-storage-space) för att minska den övergripande förbrukningen. Kunderna kan också [lägga till ytterligare lagringskapacitet](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Kundmigreringsprocess

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Skapa ett Lifecycle Services-projekt för Personal-migrering

Det första steget är att skapa ett nytt ekonomi- och driftimplementeringsprojekt i Lifecycle Services. Kunden kommer att ha ett befintligt Lifecycle Services-projekt för Personal. Den befintliga Personal-miljön kommer att migreras till nytt implementeringsprojekt för ekonomi och drift.

Om du vill skapa ett nytt projekt, följ dessa steg:

1. Logga in som global administratör i Lifecycle Services eller på den angivna tjänstekontoanvändaren.
2. På startsidan Lifecycle Services väljer du **Skapa/ny (+)**.
3. Välj appar för ekonomi och drift som produkt.
4. I fältet **Projektsyfte**, välj **Implementering**.
5. Ange ett projektnamn och en beskrivning.
6. På fältet **Anpassad projekttyp**, välj **Microsoft Dynamics 365 Human Resources-migrering**.
7. Markera kryssrutan om du vill acceptera villkoren.
8. Markera **Skapa**.

När du har skapat en ny Lifecycle Services-projekt följer du dessa steg och konfigurerar den.

1. Välj **Projektregistrering** för att slutföra projektregistreringen. Mer information finns i [Projektregistrering](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Välj samma region som dina aktuella miljöer. Det här valet påverkar inte migrering.
    - För äldre system väljer du **Övrigt**.

2. Slutför projektinställningarna. Som en del av det här steget ska du konfigurera SharePoint onlinebiblioteket, Azure DevOps och Azure-anslutningar om så krävs. Mer information finns i [Lifecycle Services (LCS) användarguide](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> Kunder kan använda ett befintligt Azure DevOps-projekt och den associerade säkerhetstoken för personlig åtkomst. Om ett befintligt projekt används blir de konfigurationer som hör till projektet tillgängliga automatiskt och kan granskas så att de är korrekta.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migrera en sandbox-miljö för Personal

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Förbered för att migrera sandbox-miljön

När ett nytt Lifecycle Services-projekt har skapats och projektets registreringsprocess har slutförts är du redo att migrera den första miljön. Innan du startar den här processen rekommenderar vi att du uppdaterar sandbox-miljön som du vill migrera från din produktionsmiljö på den fristående infrastrukturen.

#### <a name="prepare-a-power-platform-environment"></a>Förbered en Power Platform-miljö

> [!NOTE]
> Det här steget används bara för migrering av sandbox-miljöer. När du migrerar produktionsmiljön, den befintliga Power Platform-miljön i administrationscentret som är kopplad till produktionsmiljön kommer att föras vidare.

- I administrationscentret för Power Platform [skapa en Power Platform-miljö](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center) att använda för sandbox-migrering, eller välj en befintlig miljö.
- [Kopiera en miljö](/power-platform/admin/copy-environment) för att uppdatera den Power Platform-miljö som används för mappning.

#### <a name="migrate-the-sandbox-environment"></a>Migrera sandbox-miljön

1. Logga in som global administratör i Lifecycle Services eller på den angivna tjänstekontoanvändaren.

    > [!NOTE]
    > Vi rekommenderar att du använder ett namngivet användarkonto. Den inloggade användaren måste ha säkerhetsrollen **Projektägare** eller **Miljöchef** i det fristående Lifecycle Services-projektet för Personal.

2. Öppna det nya migreringsprojektet Personal.
3. Granska och slutför lämpliga faser för migreringsmetodiken och projektets registrering.
4. I instrumentpanelen för projekt, i rutan **Standard: Standardgodkännandetest**, välj **Migrera HR**.
5. I rutan **Välj miljö att migrera**, välj lämpligt Lifecycle Services-projekt och den ursprungliga Personal-miljön (från ditt fristående personalprogram).
6. Aktivera **Mappning till ny Power Platform-miljö** och välj lämplig Power Platform-miljö. Välj sedan **Nästa**.
7. Slutför guiden **Distributionsinställningar (ekonomi och drift – sandbox)** för att bekräfta detaljer och kundens signering och välj sedan **Distribuera**.

Miljöstatus visar förloppet. Status ändras från **Läser in** till **Distribuerar** till **Distribuerad**.

> [!NOTE]
> Produktionsfönstret är inte tillgängligt förrän beredskapskontroll för projekt som är klara för publicering har slutförts. Mer information finns i [Förbered publicering](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Beaktanden och antaganden

Det finns en personalmiljö i ett Lifecycle Services-projekt hos den innehavare som har följande egenskaper:

- Den sandbox-miljö för personal som inte är kopplad till en befintlig sammanslagen miljö. Endast en migrering i taget kan pågår för en viss Personalmiljö.
- Antalet sandbox-miljöer som är tillåtna när som helst baseras på licenserna för Personal. Om tillräckligt många licenser har köpts för klientorganisationen kommer ytterligare sandbox-miljöer att anges i rutan **Miljöer** för projektet.
- Migreringar måste göras i miljöer av samma typ. Det innebär med andra ord att enbart migreringar mellan sandbox och sandbox kan utföras.

    > [!NOTE]
    > Det är endast miljötyper för Personal som beaktas när status för sandbox eller produktionen bestäms. Om miljöerna kategoriseras felaktigt (det vill säga om en produktionsmiljö markeras som en sandbox-miljö, eller om en sandbox-miljö är märkt som en produktionsmiljö) kontaktar du supporten.

- Om migreringen inte fungerar visas ett felmeddelande om fel och knappen **Ta bort** blir tillgänglig. Använd den här knappen när du vill ta bort den misslyckade migreringen. Du kan sedan ommigrera miljön.

#### <a name="validate-the-sandbox-migration"></a>Validera sandbox-migreringen

När sandbox-migreringsprocessen är klar skapar du en detaljerad testplan för att verifiera och underteckna alla affärsprocesser.

Innan du börjar testa ska du validera följande information:

- Bekräfta att den migrerade miljön är tillgänglig via URL-adressen som skapas.
- Bekräfta att användarna har åtkomst till den migrerade sandbox.
- Bekräfta att Dataverse-miljön som är kopplad till den migrerade sandbox-miljön är tillgänglig.
- Kontrollera olika data för att bekräfta att det mest aktuella data finns tillgängligt.
- Slutför de kritiska affärsprocesserna för validering.
- Bekräfta att dina säkerhetspolicyer gäller.
- Bekräfta att batchjobb har utlösts som förväntat.

Du kommer inte att ha åtkomst till fjärrskrivbord till den migrerade sandbox. Du kan använda självbetjäningsfunktioner och -verktyg när du utför följande åtgärder för dina nivå 2+ sandbox-miljöer:

- Öppna [Azure SQL-databasen](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Kom åt [loggfiler](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Använd [perfmon-verktyg](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- Slå [underhållsläge på/av](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Starta om [tjänster](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Konfigurera [Regression Suite Automation Tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Mer information finns i [Vanliga frågor för självbetjäningsdistribution](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migrera en produktionsmiljö för Personal

När du är klar med migrering och validering av en sandbox-miljö, följer du dessa steg för att flytta produktionsmiljön.

#### <a name="prerequisites"></a>Förutsättningar

- Prenumerationsberäkning bör vara slutförd.
- Go-live [beredskapsbedömning](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) ska ha slutförts.

#### <a name="migrate-the-production-environment"></a>Migrera produktionsmiljön

1. Logga in som global administratör i Lifecycle Services eller på den angivna tjänstekontoanvändaren.

    > [!NOTE]
    > Vi rekommenderar att du använder ett namngivet användarkonto. Den inloggade användaren måste ha säkerhetsrollen **Projektägare** eller **Miljöchef** i Lifecycle Services-projektet.

2. Öppna det nya migreringsprojektet Personal.
3. Granska och slutför lämpliga faser för migreringsmetodiken och projektets registrering.
4. I instrumentpanelen för projekt, i rutan **Produktion**, välj **Migrera HR**.
5. I rutan **Välj miljö att migrera**, välj lämpligt Lifecycle Services-projekt och den ursprungliga Personal-miljön (från ditt fristående personalprogram). Välj sedan **Nästa**.
6. Slutför guiden **Distributionsinställningar (ekonomi och drift – sandbox)** för att bekräfta detaljer och kundens signering och välj sedan **Distribuera**.

Miljöstatus visar distributionsförloppet. Status ändras från **Läser in** till **Distribuerar** till **Distribuerad**.

#### <a name="post-migration-considerations"></a>Hänsyn efter migrering

- Använd den senaste [kvalitetsuppdateringen](/fin-ops-core/fin-ops/get-started/quality-updates) för dina miljöer.
- Om du använder [virtuella tabeller](hr-admin-integration-common-data-service-virtual-entities.md), måste du omkonfigurera slutpunkterna.
- Konfigurera om integrering av dubbel skrivning. Utvärdera vilka enheter som måste vara aktiverade.
- Överväg att använda virtuella tabeller för att ersätta dubbel skrivning för integration.

#### <a name="dual-write-integration"></a>Integration med dubbelriktad skrivning

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Konfigurera Microsoft Power Platform integrering av dubbel skrivning

1. Gå till Power Platform administrationscenter och välj **Miljöer** i den vänstra navigeringen.
2. Välj den miljö som kopierats/uppdaterats tidigare och bekräfta att statusen är **Klar**.
3. Gå till Lifecycle Services och bekräfta att statusen för migreringsprojektet har **distribuerats**.
4. Välj under den migrerade miljön **Fullständig information** för att granska ytterligare detaljer och [ställa in ett program för dubbel skrivning](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. I rutan **Konfiguration av app för dubbelriktad skrivning** markera kryssrutan för att godkänna mappning och synkronisering av data mellan databaser och välj sedan **Konfigurera**.
6. När en meddelanderuta meddelar dig om att konfiguration för dubbelriktad skrivning lyckades, väljer du **OK**.
7. Du kan övervaka konfigurationens förlopp i detalj.
8. När konfigurationen är klar väljer du **Länk till Power Platform-miljö** för att synkronisera tillgängliga dataenheter.
9. När statusen visar att miljön har länkats, går du till administratörscentret för Power Platform och granskar och väljer lämpliga dataenheter.
10. I vänstra fönstret, välj **Dynamics 365-appar \> Resurser**.
11. Bekräfta att statusvärdet för programmet Personal är **Aktiverat**.
12. Välj dubbelriktad skrivning programmet Personal välj sedan **Installera**.
13. I fönstret **Installera dubbelriktad skrivning Dynamics 365 Human Resources-appen**, välj lämplig miljö att installera paketet i.
14. Markera kryssrutan om du vill acceptera servicevillkoren och välj **Installera**.
15. I programmiljön Dynamics 365 är statusen **Installation** medan installationen pågår. Det uppdateras till **Installerat** när installationen är slutförd.

##### <a name="review-and-apply-a-dual-write-solution"></a>Granska och tillämpa en lösning för dubbel skrivning

1. I den nya miljön för ekonomi och drift, gå till **Datahantering \> Dubbelriktad skrivning**.
2. Välj **Tillämpa lösning**.
3. I rutan, välj **Dynamics installerade lösningar**, **Entitetsmappningar för dubbelriktade appar** och **Dynamics 365 Human Resources mappningar**. Välj sedan **Tillämpa**. Ett meddelande bekräftar att lösningen används. När lösningen har tillämpats visas alla tillgängliga registermappningar.
4. Gå igenom tillgängliga registermappningar för att välja och köra integrationen genom att använda dubbel skrivning.
5. När du kör den här integrationsprocessen för dubbel skrivning första gången för registermappningar markerar du kryssrutan **Inledande synkronisering**. Om det finns en befintlig integration från källmiljön Personal behöver du inte markera kryssrutan **Initial synkronisering** när du kör integrationen för registermappningar.

#### <a name="recommended-practices"></a>Rekommenderade metoder

Det här avsnittet innehåller rekommendationer för att migrera från den fristående infrastruktur till den ekonomi- och driftinfrastrukturen.

- Vi rekommenderar starkt att du arbetar med din Microsoft Dynamics partner för att få hjälp med migrering av Personal-miljön.
- Planera lämplig tid för att testa användarens godkännande (UAT) på den migrerade sandbox-miljön.
- Planera och dokumentera de detaljerade stegen för att migrera integrationer till den migrerade miljön.
- Skapa en detaljerad checklista för att beskriva omställningsprocessen för din migrering.
- Planera ett lämpligt antal driftstopp för verksamheten medan du migrerar.
- Vi rekommenderar starkt att FastTrack-kvalificerade kunder arbetar med sin FastTrack-lösning för att få hjälp med att övervaka migreringsprocessen.
- Vi rekommenderar starkt att du uppdaterar din arbetsmiljö i den fristående infrastruktur innan du gör den första migreringen. Den här uppdateringen ska inkludera din Dataverse-miljö som är ansluten till den sandbox-miljö som du planerar att flytta till.
- Vi rekommenderar starkt att du använder ett servicekonto när du distribuerar, migrerar och skapar ett Lifecycle Services-projekt.
- Planera att uppgradera miljön för UAT-validering i den senaste versionen av allmänt tillgänglig version (GA). Mer information finns i [beaktanden](hr-infrastructure-merge.md#considerations).
