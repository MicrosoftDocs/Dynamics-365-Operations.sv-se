---
title: Etablera Human Resources
description: I detta ämne får du veta hur du skapar en ny produktionsmiljö för Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c856bca32c3dee44469c098961d85b4d8cb70a6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060448"
---
# <a name="provision-human-resources"></a>Etablera Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



I detta ämne får du veta hur du skapar en ny produktionsmiljö för Microsoft Dynamics 365 Human Resources. 

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara på plats innan du kan etablera en ny produktionsmiljö:

- Du har köpt Personal via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Microsoft Dynamics 365-licens som redan innehåller tjänsteplanen for Personal och du inte kan utföra stegen i detta ämne kontaktar du supporten.

- Den globala administratören har loggat in på [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) och skapat ett nytt projekt for Personal. 

## <a name="provision-a-human-resources-trial-environment"></a>Skapa en utvärderingsmiljö för Personal

Innan du provisioner din första resurs eller produktionsmiljö kan du använda en [utvärderingsmiljö för Personal](https://go.microsoft.com/fwlink/p/?LinkId=2115962) för att validera personalfunktioner. Bedömningsmiljöer innehåller fiktiva data som kan användas för att utforska programmet på ett säkert sätt. Även om bedömningsmiljön ägs av den användare som har begärt den, kan andra användare bjudas in via systemets administrationserfarenhet för Personal. 

Med utvärderingsmiljöer kan du utvärdera personalfunktioner för personer som inte redan har tillgång till en personalmiljö. Om du inför en utvärderingsmiljö och den autentiserade användaren redan har tillgång till en eller flera befintliga personalmiljöer, omdirigeras användaren till den befintliga miljön eller listan över miljöer.

Testmiljöer är inte avsedda att användas som produktionsmiljöer. De är begränsade till en 30-dagars försöksperiod. När utvärderingsperioden löper ut är miljön och all data inte raderas och kan inte återställas. Miljön kan inte konverteras till en produktions- eller tillverkningsmiljö. Du kan registrera dig för en ny bedömningsmiljö när den befintliga miljön har gått ut.

När du skapar en Human Resources-utvärderingsmiljö skapas också en Power Apps-utvärderingsmiljö i klientorganisationen och kopplas till Human Resources-miljön. Power Apps-miljön, med namnet "TestDrive", har samma utvärderingsperiod som Human Resources-miljön.

> [!NOTE]
> Om den autentiserade användaren inte har behörighet att skapa Power Apps-utvärderingsmiljöer kommer det inte att gå att etablera en Human Resources-utvärderingsmiljö. Användaren måste inkluderas i den användargrupp som kan skapa utvärderingsmiljöer i Power Platform-administratörscenter. Mer information finns i [Kontrollera vem som kan skapa och hantera miljöer i Power Platform-administratörscenter](/power-platform/admin/control-environment-creation).

## <a name="plan-human-resources-environments"></a>Planera Personal-miljöer

Innan du skapar din första Personal-miljö bör du noggrant planera miljöbehoven för ditt projekt. Ett basabonnemang på Personal innehåller två miljöer: en produktionsmiljö och en sandbox-miljö. Beroende på hur komplext ditt projekt är, kanske du måste köpa in ytterligare sandbox-miljöer för att kunna stödja projektaktiviteter. 

Att tänka på vid ytterligare miljöer:

- **Datamigrering**: Du kan komma att behöva överväga en ytterligare miljö för datamigreringsaktiviteter så att din sandbox-miljö kan användas i testsyfte under hela projektets gångf. Om det finns ytterligare en miljö kan datamigreringsaktiviteter fortsätta samtidigt som tester och konfigurationsaktiviteter sker i en annan miljö.
- **Integrering**: Du kanske måste överväga att skapa ytterligare en miljö för att konfigurera och testa integreringer. Detta kan innefatta inbyggda integreringer som Ceridian Dayforce LinkedIn Talent Hub-integreringar eller anpassade integreringar som exempelvis för löne-, sökandespårningssystem eller förmånssystem och leverantörer.
- **Utbildning**: Du kan behöva en separat miljö som är konfigurerad med en uppsättning utbildningsdata för att utbilda dina medarbetare i användningen av det nya systemet. 
- **Flerprojektfas**: Du kan behöva ytterligare en miljö för att stödja konfiguration, datamigrering, testning eller andra aktiviteter i en projektfas som planeras efter projektets ursprungliga start.

 > [!IMPORTANT]
 > När det gäller din miljö rekommenderar vi följande:
 > - Använd din produktionsmiljö i hela projektet som din konfigurationsmiljö GULD. Detta är viktigt eftersom du inte kan kopiera en sandbox-miljö till en produktionsmiljö. När du går live nu är därför GULD-miljö din produktionsmiljö, och du utför dina övergångsaktiviteter i den här miljön.</br></br>
 > - Använd din sandbox- eller någon annan miljö för att utföra en testomställning innan du lanserar. Detta gör du genom att uppdatera produktionsmiljön med din GULD-konfiguration i din sandbox-miljö.</br></br>
 > - Upprätta en detaljerad övergångschecklista som inkluderar varje datapaket som krävs för att migrera den slutgiltiga datan till produktionsmiljön i samband med lanseringsövergången.</br></br>
 > - Använd din produktionsmiljö i hela projektet som din konfigurationsmiljö TEST. Om du behöver fler miljöer kan organisationen köpa dem för en extra kostnad.</br></br>

## <a name="create-an-lcs-project"></a>Skapa ett LCS-projekt

För att hantera dina Personal-miljöer med LCS måste först skapa ett LCS-projekt.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index) med det konto som du använder för din Personal-prenumeration.

   > [!NOTE]
   > För att säkerställa ett lyckat tillhandahållande måste det konto som du använder för att tillhandahålla Personal-miljön tilldelas antingen rollen **Systemadministratör** eller rollen **Systemanpassare** i den Power Apps-miljö som är kopplad till Personal-miljön. Mer information om att tilldela säkerhetsroller till användare i Power Platform finns i [Konfigurera användarsäkerhet för resurser](/power-platform/admin/database-security).

2. Klicka på plustecknet (**+**) för att skapa ett projekt.

3. Välj **Microsoft Dynamics 365 Human Resources** som produktversion och produktnamn.

4. Välj **Dynamics 365 Human Resources**-metoden.

5. Markera **Skapa**.

Mer information om hur du kommer igång med Personal finns i metoden för **Personal** som du skapade i det nya projektet. När du har skapat projektet slutför du stegen nedan för att skapa din Personal-miljö.

## <a name="provision-a-human-resources-project"></a>Etablera Personal-projekt

När du har skapat ett LCS-projekt kan du införa Personal i en miljö.

1. I LCS-projektet väljer du fliken **-hantering for Personal**.

2. Ange om denna miljö är ett begränsat läge eller produktionsinstans av Personal. Funktionerna för förhandsgranskning kan finnas tillgängliga i begränsade instanser för att möjliggöra tidig återrapportering och testning.
   
    > [!NOTE]
    > Det går inte att ändra Personal-instanstypen när den har angetts. Kontrollera att rätt instanstyp har valts innan du fortsätter.</br></br>
    > Instanstypen Personal är separat från instanstypen för Microsoft Power Apps-miljön, som du anger i Power Apps-administrationscentret.
    
3. Markera alternativet **Inkludera demodata** om du vill att din miljö med samma demodatauppsättning används i utvärderingsmiljön för Personal. Demodata är praktiskt för långsiktig demonstrations- och utbildningsmiljöer och ska aldrig användas i produktionsmiljöer. Du måste välja det här alternativet vid den första implementeringen. Du kan inte uppdatera en befintlig distribution senare.

4. Personal etableras alltid i en Microsoft Power Apps-miljö, detta i syfte att möjliggöra Power Apps-integrering och utbyggnad. Läs avsnittet ”Välja en Power Apps-miljö” i det här ämnet innan du fortsätter. Om du inte redan har en Power Apps-miljö, välj hantera miljöer i LCS eller gå till Power Apps administrationscenter. Följ stegen för att [skapa en Power Apps-miljö](/powerapps/administrator/create-environment).

5. Välj den miljö som du vill konfigurera Personal på.

6. Välj **Ja** för att acceptera villkoren och börja implementeringen.

   Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt några minuter. Om försörjningprocessen misslyckas måste du kontakta Support.

7. Välj **Logga in på Personal** för att använda den nya miljön.

    > [!NOTE]
    > Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Personal i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

## <a name="select-a-power-apps-environment"></a>Välj en Power Apps-miljö

Du kan integrera och utöka användningen av personaldata med hjälp Power Apps-verktyg. Mer information om Power Apps-miljöer, såsom omfattning, åtkomst och att skapa och välja miljö finns i [Vi presenterar Power Apps-miljöer](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Använd följande riktlinjer när du bestämmer vilka Power Apps-miljöer som ska användas för att distribuera Personal: 

1. I LCS välj **Hantera miljöer**. Du kan också gå direkt till administratörscenter för Power Apps där du kan visa befintliga miljöer och skapa nya.

2. En enskild Personal-miljö mappas till en enda Power Apps-miljö.

3. En Power Apps-miljö "innehåller" Personal-programmet tillsammans med motsvarande Power Apps, Power Automate och Dataverse-program. Om Power Apps-miljön tas bort tas även apparna bort. Vid tillhandahållande av en Personal-miljö kan du tillhandahålla antingen en **Bedömningsversion**- eller **Produktion**-miljö. Välj typ av miljö baserat på hur miljön kommer att användas. 

4. Dataintegrering och teststrategier ska beaktas, till exempel: begränsat läge, UAT, produktion. Överväg noggrant de olika konsekvenserna för distribution, eftersom det inte är lätt att ändra vilken Personal-miljö som är mappad till en Power Apps-miljö.

5. Följande Power Apps-miljöer kan inte användas för Personal. De filtreras från urvalslistan i LCS:
 
    - **Standard Power Apps-miljöer** – Medan varje klientorganisation automatiskt etableras med en standard Power Apps-miljö rekommenderar vi inte att du använder dem med personal. Alla användare av klientorganisation kan komma åt Power Apps-miljön och oavsiktligt skada produktionsdata när de testar och utforskar med Power Apps eller Power Automate integreras.
   
    - **Testmiljöer** – dessa miljöer skapas med ett utgångsdatum. Efter förfallodatum kommer din miljö och alla personalinstanser som finns i den att tas bort automatiskt.
   
    - **Ej stödda områden** - Miljön måste finnas i ett geografiskt område som stöds. Mer information finns i [Områden som stöds](hr-admin-setup-provision.md#supported-geographies).

6. Dubbla skrivfunktioner för att integrera Personal-data med miljön Power Apps kan bara användas om alternativet **Aktivera Dynamics 365-appar** har valts för miljön. Se [sidan Dubbelriktad skrivning](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md) för mer information för dubbelriktad skrivning.

    > [!NOTE]
    > Alternativet **Aktivera Dynamics 365-appar** måste väljas när Power Apps skapas. Om alternativet inte är valt vid administreringstillfället kommer du inte att kunna använda dubbelriktad skrivning för att integrera data mellan Dynamics 365 Human Resources och Power Apps miljön eller installera Dynamics 365-appar som Dynamics 365 Sales och Field Service i miljön. Det här alternativet kan inte ångras. Mer information finns i [Några viktiga överväganden när du skapar en ny miljö](//power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment) på Power Platform dokumentationssplatsen.

7. När du har kontrollerat den korrekta miljön kan du fortsätta med etableringsprocessen. 

### <a name="supported-geographies"></a>Områden som stöds

Personal har för närvarande stöd för följande områden:

- USA
- Europa
- Storbritannien
- Australien
- Kanada
- Asien 

När du skapar en Personal-miljö väljer du en Power Apps-miljö att koppla till Personal-miljön. Personal-miljön tillhandahålls sedan i samma Azure-område som den valda Power Apps-miljön. Du kan välja var Personal-miljön och -databasen finns rent fysiskt genom att välja område när du skapar den Power Apps-miljö som ska associeras med Personal-miljön.

Du kan välja det Azure-*område* där miljön tillhandahålls, men du kan inte välja den specifika Azure-*-regionen*. Vid automation fastställs den specifika region inom den område där miljön skapas i syfte att optimera belastningsutjämning och prestanda. Du hittar information om Azure-områden och -regioner i dokumentationen om [Azure-områden](https://azure.microsoft.com/global-infrastructure/geographies).

Datan för Personal-miljön finns alltid i det Azure-område som den skapas i. Den finns dock inte alltid inom samma Azure-region. I haveriberedskapssyfte replikeras datan både i den primära Azure-regionen och i en sekundär redundansregion inom området.

 > [!NOTE]
 > Migrering av Personal-miljöer från en Azure-region till en annan stöds inte.

## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.

Som standard har den globala administratör som skapade miljön åtkomst till den. Du måste uttryckligen bevilja åtkomst till ytterligare appanvändare. Du måste lägga till användare och tilldela dem lämpliga roller i Personal-miljön. Mer information finns i [skapa nya användare](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) och [tilldela användare till säkerhetsroller](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
