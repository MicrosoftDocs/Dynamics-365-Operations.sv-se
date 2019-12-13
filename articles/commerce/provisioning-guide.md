---
title: Konfigurera en utvärderingsmiljö för e-handel
description: Den här guiden innehåller steg-för-steg-instruktioner om hur du etablerar och konfigurerar din Microsoft Dynamics 365 Commerce förhandsgranskningsmiljö.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771690"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Konfigurera en utvärderingsmiljö för e-handel

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Den här guiden innehåller steg-för-steg-instruktioner om hur du etablerar och konfigurerar din Microsoft Dynamics 365 Commerce förhandsgranskningsmiljö. Innan du börjar rekommenderar vi att du åtminstone läser igenom dokumentationen för att få en uppfattning om vad processen medför och vad guiden innehåller.

*Obs! Om du inte har beviljats åtkomst till Microsoft Dynamics 365 Commerce förhandsgranskning ännu kan du begära förhandsgranskningsåtkomst [E-handelswebbplats](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Sammanfattning
För att du ska kunna konfigurera miljön måste projektet skapas med ett specifikt produktnamn och en specifik typ. Miljön och Retail Cloud Scale Unit har även del specifika parametrar som du måste använda för att kunna starta näthandelsetableringen senare. Instruktionerna i den här handboken innehåller alla nödvändiga steg som du måste vidta och parametrar som du behöver använda.

När etableringen har slutförts finns det några efter etableringssteg som du måste vidta för att förbereda förhandsgranskningmiljön. Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera. Om du senare ändrar dig kan du alltid köra de valfria stegen senare.

Om du har frågor om etableringsstegen eller om du stöter på problem ska du tala om för oss vad [Microsoft Dynamics 365 Commerce förhandsgranskning Yammer-grupp](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Förutsättningar
Följande förutsättningar måste uppfyllas för att du ska kunna etablera din Dynamics 365 förhandsgranskningsmiljö:
* Du har åtkomst till portalen **Lifecycle Services-portal (LCS)**
* Du har **accepterats i Dynamics 365 Commerce förhandsgranskningsprogrammet**
* Du har de behörigheter som krävs för att skapa ett **projekt för potentiell försäljning** eller **migrera, skapa lösningar och lära dig**
* Du är rollen **Miljöhanterare** eller **Projektägare** i projektet där du ska etablera miljön
* Du har administratörsåtkomst till din Azure-prenumeration eller kontakta en prenumerationsadministratör som kan utföra de två steg som kräver administratörsbehörighet för din räkning
* Du har ditt **AAD-klient-ID** tillgängligt
* Du har skapat en **AAD-säkerhetsgrupp** som ska användas som **gruppen E-handelssystemadministratörer** och du har tillgång till ID:t
* Du har skapat en **AAD-säkerhetsgrupp** som ska användas som **gruppen Klassificering- och granska moderator** och du har dess ID-tillgänglig (kan vara samma SG som gruppen systemadministratör ovan)
## <a name="provisioning-preview-environment"></a>Etablerar förhandsgranskningsmiljö
De här instruktionerna täcker hur du etablerar en Microsoft Dynamics 365 Commerce förhandsgranskning. När du har slutfört de här stegen har du en förhandsgranskningsmiljö som kan konfigureras. Alla aktiviteter som beskrivs här utförs i LCS-portalen.

*Observera att förhandsgranskningsåtkomsten är associerad till LCS-kontot och organisationen som du angav i förhandsversionsprogrammet. Du måste använda samma konto för etableringen. Om du måste använda olika LCS-konton eller innehavare för förhandsversionsmiljön måste du förse oss med dessa uppgifter. Mer information om kontakter finns i "ytterligare resurser" nedan.*
### <a name="before-starting"></a>Innan du startar
##### <a name="grant-access-to-e-commerce-applications"></a>Bevilja åtkomst till e-handelsprogram

*Obs! **Den person som loggar in måste vara AAD-administratör**. Utan att slutföra det här steget kommer resten av etableringsstegen att misslyckas.*

1. För det här steget behöver du ditt **ID för AAD-innehavare**. Du måste auktorisera e-handelsprogram för att komma åt din Azure-prenumeration. Det enklaste sättet att åstadkomma detta är att sätta samman en URL så här:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Klicka inte på URL:en direkt**, kopiera den i stället och klistra in den i webbläsaren eller textredigeraren och **\{AAD_TENANT_ID\}** med din **ID för AAD-innehavare** innan du navigerar till URL:en.
3. Du visas i inloggningsdialogrutan för Microsoft AAD där du bekräftar att du vill bevilja "Dynamics 365 Commerce (förhandsgranskning)"-åtkomst till din prenumeration.
4. Du kommer att skickas till en sida som bekräftar om åtgärden har lyckats.

##### <a name="log-in-to-the-lcs"></a>Logga in i LCS
1. Logga in i LCS-portal: https://lcs.dynamics.com
1. Se till att du är inloggad med samma LCS-konto som du använde när du begärde åtkomst till förhandsgranskning.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Bekräfta att förhandsgranskningsfunktionerna är tillgängliga och aktiverade
1. Rulla hela vägen till höger på LCS framsida och klicka på panelen för **Hantering av förhandsgranskningsfunktioner**.
1. Rulla ned till "PRIVATA FÖRHANDSGRANSKNINGSFUNKTIONER" och se till att följande funktioner är tillgängliga och aktiverade:
    1. **Utvärdering av e-handel**
    1. **Miljöer för förhandsgranskningsprogram**
1. Om du inte kan se funktionerna i listan kontaktar du oss med din e-postadress till arbetet, LCS-konto och innehavarinformation. Se **ytterligare resurser** för mer information om hur kontaktar oss.

![Panel för förhandsgranskningsfunktion](./media/preview1.png)

![Förhandsfunktioner](./media/preview2.png)
### <a name="create-project"></a>Skapa projekt
##### <a name="creating-new-project"></a>Skapa ett nytt projekt
1. Klicka på **+** om du vill skapa ett nytt projekt.
1. Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.
1. Om du är kund väljer du **Potentiella försäljningar**.
1. Ange namn, beskrivning och bransch när du ser anpassa.
1. För **produktnamn**, välj **Dynamics 365 Retail**.
1. För **produktversion**, välj **Dynamics 365 Retail**.
1. För **Metod**, välj **Dynamics Retail implementeringsmetod**.
1. Du kan importera roller och användare från ett befintligt projekt om det behövs.
1. Klicka på **Skapa**.
1. Du skickas till projektvyn.
##### <a name="add-azure-connector"></a>Lägg till Azure-koppling
1. Om du är en partner klickar du på **projektinställningar** från panelerna verktyg längst till höger.
1. Om du är kund väljer du **projektinställningar** på huvudmenyn.
1. Välj **Azure-kopplingar**.
1. Klicka på **+ Lägg till** om du vill lägga till Azure-koppling.
1. Ange ett namn.
1. Ange ditt **Azure prenumerations-ID**.
1. Aktivera **Konfigurera för att använda Azure Resource Manager (ARM)**.
1. Kontrollera att **Azure-abonnemangets AAD-innehavardomän (eller ID)** är korrekt. Kontakta din Azure abonnemangsadministratör om det behövs.
1. Klicka på **Nästa**.
1. Följ instruktionerna på skärmen och ge de program som krävs åtkomst till din prenumeration. Kontakta din Azure abonnemangsadministratör om det behövs:
    1. Logga in i Azure-portal: https://portal.azure.com/
    1. Kontrollera att du har valt rätt katalog.
    1. Klicka på **Abonnemang** på menyn till vänster.
    1. Leta rätt på den korrekta prenumerationen i listan och markera den. Använd sökning om det behövs.
    1. Välj **åtkomstkontroll (IAM)** på menyn.
    1. Klicka på **Lägg till** under **Lägg till en rolltilldelning** på höger sida. Fönstret **Lägg till rolltilldelning** öppnas.
    1. För **Roll**, välj **Deltagare**.
    1. För **Tilldela åtkomst till**, lämna som **Azure AD användare, grupp eller Service Principals**.
    1. Under **Välj**, anger du **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Välj **Dynamics distributionstjänst [wsfed-enabled]** från listan.
    1. Klicka på **Spara**.
1. Klicka på **Nästa**.
1. Följ instruktionerna på skärmen och ge de program som krävs åtkomst till din prenumeration. Kontakta din Azure abonnemangsadministratör om det behövs.
1. Klicka på **Nästa**.
1. För **Azure-region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.
1. Klicka på **anslut**.
1. Din Azure-koppling ska visas i listan.
### <a name="import-extension"></a>Importera tillägg
1. Navigera tillbaka till projektets förgrundssida genom att klicka på projektnamnet överst.
1. Om du är en partner klickar du på **Tillgångsbibliotek** från panelerna verktyg längst till höger.
1. Om du är kund väljer du **Tillgångsbibliotek** på huvudmenyn.
1. Välj **Distribuerbart programpaket** från listan till vänster.
1. Klicka på **IMPORTERA** i åtgärdsfönstret.
1. Välj **Commerce-förhandsgranskning demo bastillägg** från listan med tillgångar under **DELAT TILLGÅNGSBIBLIOTEK**.
1. Klicka på **Hämta**.
1. Du kommer att returneras till tillgångsbiblioteket och du bör se filnamnstillägget i listan.

![Skapa projekt - versioner](./media/import.png)
### <a name="deploy-environment"></a>Distribuera miljö

*Obs! det är möjligt att steg 6, 7 och/eller 8 inte visas, eftersom skärmar med ett enda alternativ hoppas över. När du befinner dig i vyn **miljöparametrar** bekräftar du att du har texten "Dynamics 365 Commerce (förhandsgranskning) - Demo (10.0.6 med plattformsuppdatering 30)" direkt ovan fältet **Miljönamn**. Se bilden nedan.*

1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Klicka på **+ Lägg till** om du vill lägga till en miljö.
1. För **Programversion**, välj **10.0.6**.
1. För **plattformsversion**, väljer du **plattformsuppdatering 30**.
1. Klicka på **Nästa**.
1. För miljötopologi, välj **DEMO**.
1. För miljötopologi, välj **Dynamics 365 Commerce (förhandsgranska) - Demo**.
1. Om du konfigurerade en enda Azure-koppling tidigare kommer den att användas i den här miljön. Om du har konfigurerat flera Azure-kopplingar kan du välja vilken anslutning du vill använda: **östra US**, **östra US 2**, **västra US** eller **västra US 2** (rekommenderas för bästa resultat från slutpunkt till slutpunkt)
1. Ange ett **miljönamn**.
1. Justera VM-storleken så att den passar. (Vi rekommenderar VM SKU **D13 v2**.)
1. Lämna **Avancerade inställningar** som de är.
1. När du har granskat prissättningen och licensieringsvillkoren på skärmen markerar du rutan för att ange avtal.
1. Klicka på **Nästa**.
1. På skärmen för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**.
1. Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.
1. Den begärda miljön visas som en kö och distribueras sedan. Det tar lite tid för alla miljöarbetsflöden att slutföras, så kom tillbaka efter några timmar (ungefär 6 – 9 timmar).
1. Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.

![Skapa projekt - versioner](./media/project1.png)

![Skapa projekt - topologi 1](./media/project2.png)

![Skapa projekt - topologi 2](./media/project3.png)

![Skapa projekt - miljöparametrar](./media/project4.png)
### <a name="initialize-rcsu"></a>Initiera RCSU
1. Välj din miljö i listan **Molnstyrda miljöer**.
1. Klicka på miljövyn på höger sida av skärmen **Fullständig information**. Vyn miljöinformation visas.
1. Under **MILJÖFUNKTIONER**, klicka på **hantera**.
1. Från fliken **Butik** klicka på **initiera**. Parametervyn RCSU-initiering visas.
1. För **REGION**, väljer du **östra US**, **östra US 2**, **västra US** eller **västra US 2**.
1. För **VERSION** väljer du först **Ange en version** i listrutan och ange **9.16.19262.5** i textfältet som visas nedan. *Obs! var noga med att **ange den exakta versionen** som anges här för att undvika att behöva uppdatera RCSU senare till korrekt version.*
1. Tillämpa **Tillämpa tillägg**.
1. Från listan över tillägg, välj **Handelsförhandsgranskning demobastillägg**.
1. Klicka på **Initiera**.
1. På skärmen för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**.
1. Du återgår till vyn **Butikshantering** med fliken **Butik** aktiverad. Din RCSU har ställts i kö för etablering.
1. Vänta tills din RCSU-status är **KLAR** innan du fortsätter (cirka 2-5 timmar).
### <a name="initialize-e-commerce"></a>Initiera e-handelsplattform
1. Växla till fliken **e-handel (förhandsgranskning)**.
1. När du har granskat förhandsgranskningen klickar du på **inställningar**.
1. Ange ett namn för **E-handelsinnehavarens namn**. Observera dock att detta kan visas i vissa av de URL:er som pekar på din e-handelsinstans.
1. För **Namn på Retail Cloud Scale Unit**, välj RCSU från listan (listan ska bara innehålla ett alternativ).
1. **E-handelsgeografi** fylls i automatiskt och kan inte ändras.
1. Klicka på **Nästa** när du vill fortsätta.
1. För **Värdnamn som stöds**, ange giltig domän (t.ex. www.fabrikam.com).
1. För **AAD-säkerhetsgruppen för systemadministratör**, anger du det AAD SG-ID som du vill använda som systemadministratörsgrupp för e-handel.
1. För **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange det AAD SG-ID som du vill använda för gruppen moderator för omdömen och recensioner.
1. Lämna **B2C**-värden tomma (7 fält som börjar med B2C).
1. Lämna **Aktivera klassificering och granska tjänsten** aktiverad.
1. Klicka på **Initiera**.
1. Du återgår till vyn **Butikshantering** med fliken **e-handel (förhandsgranskning)** aktiverad. Initieringen av e-handel har påbörjats.
1. Innan du fortsätter väntar du tills initieringsstatus för e-handel är **INITIALISERING HAR SLUTFÖRTS**.
1. Under **LÄNKAR** längst ned till höger.
    * Anteckna länken **näthandelsplats**. Det här är länken till roten för C2-platsen.
    * Anteckna länken **Hanteringsverktyg för näthandelsplats**. Det här är länken till platshanteringsverktyget (C1-utvecklingsverktyget).
## <a name="post-provisioning-steps"></a>Steg efter etableringsstegen
I den här fasen har miljön etablerats för slutpunkt till slutpunkt, men det finns fortfarande konfigurationssteg som måste vidtas innan du kan börja utvärdera miljön.
### <a name="before-starting"></a>Innan du startar
1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Klicka **Fullständig information** från miljöinformationen till höger.
1. Klicka på **Logga in** för att öppna en meny, välj **Logga in på miljön**.

Kontrollera att **USRT** juridisk person har valts (övre högra hörnet).

### <a name="configure-pos"></a>Konfigurera POS
##### <a name="associate-worker-with-your-identity"></a>Associera arbetare med din identitet
1. Från menyn till vänster går du till **moduler > butik > anställda > arbetare**.
1. Hitta och markera önskad post **000713 - Andrew Collette** i listan.
1. Klicka på **Butik** i åtgärdsfönstret.
1. Klicka på **Associera befintlig identitet**
1. I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.
1. Klicka på **Sök**.
1. Markera posten med ditt namn.
1. Klicka på **OK**.
1. Klicka på **Spara**.
##### <a name="activate-cloud-pos"></a>Aktivera molnbaserad kassa
1. Logga in i LCS-portal:.
1. Navigera till ditt projekt.
1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Klicka **Fullständig information** från miljöinformationen till höger.
1. Klicka på **Logga in** för att öppna en meny, välj **Logga in på en molnbaserad kassa**, kassan bör läsas in.
1. Klicka på **Nästa**.
1. Logga in med ditt AAD-konto.
1. Under **Butiksnamn**, välj **San Francisco**.
1. Klicka på **Nästa**.
1. Under **Register och enhet**, välj **SANFRAN-1**.
1. Klicka på **Aktivera**.
1. Du bör loggas ut och hamna på kassainloggningsskärmen.
1. Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.
### <a name="site-setup"></a>Inställning av webbplats
1. Logga in på **platshanteringsverktyget** med den URL du noterade tidigare. 
1. Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.
1. För domän väljer du den domän du angav tidigare när e-handel initierades.
1. För standardkanal väljer du **Fabrikam utökade online-butik**. *Obs! se till att välja den **utökade** onlinebutiken*
1. För standardspråk väljer du **sv-SE**.
1. Lämna **sökvägen** som den är.
1. Klicka på **OK**.
1. Du kommer att skickas till listan över sidor på webbplatsen.
### <a name="enable-jobs"></a>Aktivera jobb
1. Logga in på miljön (HQ).
1. Gå till menyn till vänster **Butik > Förfrågningar och rapporter > Batch-jobb**.
1. Utför följande steg för varje jobb i listan nedan:
    * **Bearbeta butikorders e-postmeddelande**.
    * **Produkttillgänglighet**.
    * **P-0001**.
    * **Synkronisera orderjobb**.
1. Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn (visas ovan).
1. Utför följande steg om status för jobbet är **Undanhåll**:
    1. Välj posten.
    1. Från åtgärdsfönstret, öppna **Batch-jobb** och klicka på **Ändra status**.
    1. Välj **Väntar** och klicka på **OK**.
### <a name="run-full-data-sync"></a>Kör fullständig datasynkronisering
1. Med hjälp av menyn till vänster, gå till **Moduler > Butik > Administrationsinställning > Butiksschemaläggare > Kanaldatabas**.
1. **Standard** kanalen väljs i listan till vänster. *Välj en annan tillgänglig kanal (namngiven **scXXXXXXXXX**)*.
1. Klicka på **Fullständig datasynkronisering** i åtgärdsfönstret.
1. Ange **9999** som distributionsschema.
1. Klicka på **OK**.
1. Klicka på **OK**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Efter dessa åtgärder kan du börja utvärdera din förhandsgranskningsmiljö!
Använd URL för **Hanteringsverktyg för näthandelsplats** för att navigera till C1-redigeringsmiljön och URL för **näthandelsplats** URL för att navigera till C2-redigeringsmiljön.

## <a name="additional-resources"></a>Ytterligare resurser
### <a name="how-to-find-your-aad-tenant-id"></a>Så här hittar du ditt AAD-klient-ID
AAD-klient-ID är ett GUID och ser ut så här: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Från Azure-portalen
1. Logga in i Azure-portal: https://portal.azure.com/
1. Kontrollera att du har valt rätt katalog.
1. Klicka på **Azure Active Directory** på menyn till vänster.
1. Välj **egenskaper** under **hantera**.
1. AAD-klient-ID visas under **katalog-ID**.
##### <a name="from-openid-connect-metadata"></a>Ansluta metadata från OpenID
Skapa **OpenID-URL** genom att ersätta **\{YOUR_DOMAIN\}** med din domän, t.ex. microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration skulle bli https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Navigera till **OpenID-URL** : med din domän i den.
1. AAD-klient-ID kan visas i flera egenskapsvärden.
1. Sök efter **authorization_endpoint** och extrahera GUID direkt efter **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Så här hittar du ID för din AAD-säkerhetsgrupp
AAD-säkerhetsgrupp-ID är ett GUID och ser ut så här: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Det här steget förutsätter att användaren är medlem i den grupp som de försöker hitta ID för.
1. Navigera till diagramutforskaren: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Klicka på **Logga in med Microsoft** och logga in med dina autentiseringsuppgifter.
1. När du har loggat klickar du på **visa fler exempel** från vänster.
1. Aktivera **grupper** från högra fönstret.
1. Stäng den högra rutan.
1. Klicka på **Alla grupper jag tillhör**.
1. Leta reda på gruppen i textrutan **Förhandsgranskning av svar**.
1. ID för säkerhetsgrupp anges under egenskapens **ID**.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Testa kreditkortsinformation för att utföra testinköp
För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:

Kortnummer: 4111-1111-1111-1111, Utgång: 10/20, CVV: 737

*Obs! Du bör inte försöka använda äkta kreditkortsinformation på testwebbplatsen under några omständigheter!*
### <a name="useful-links"></a>Användbara länkar
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Microsoft Azure-portal](https://azure.microsoft.com/en-us/features/azure-portal)
* [Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)
* [Hjälpresurser för Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Microsoft Dynamics 365 Commerce förhandsversion support
Om du får problem när du utför etableringsstegen kan du gå till [Microsoft Dynamics 365 Commerce förhandsversion Yammer-gruppen](https://aka.ms/Dynamics365CommercePreviewYammer) och be om hjälp. 

Om du har problem med att komma åt Yammer-gruppen kan du även nå oss via e-post på **Dynamics365Commerce@microsoft.com**. Den här e-postadressen övervakas inte aktivt så förvänta dig fördröjda svar.
***
## <a name="prerequisites-for-optional-features"></a>Förutsättningar för valfria funktioner
Följande förutsättningar måste uppfyllas om du vill utvärdera e-postfunktionerna för transaktion:
* Du har en e-postserver tillgänglig (SMTP-server) som kan användas från den Azure-prenumeration där du tillhandahåller förhandsversionsmiljön.
* Du har tillgång till serverns FQDN-/IP-nummer, SMTP-portnummer och autentiseringsinformation.

Om du vill utvärdera funktioner för digital tillgångshantering, särskilt intag av nya flerkanalsbilder, måste följande krav uppfyllas:
* Du måste ha ditt **CMS-innehavarnamn** tillgängligt. Anvisningar för hur du hittar namnet finns nedan.
### <a name="configure-image-backend-optional"></a>Konfigurera bildserver (valfritt)
##### <a name="finding-your-media-base-url"></a>Hitta din mediebas-URL
*Obs! innan du kan slutföra det här steget måste du slutföra **konfiguration av webbplatsen**.*
1. Logga in på platshanteringsverktyget med den URL du noterade tidigare.
1. Öppna webbplatsen **Fabrikam**.
1. Välj **Tillgångar** på menyn till vänster.
1. Markera en enskild bildtillgång.
1. Hitta **offentlig URL** från egenskapspanelen till höger. Den har en URL i sig.
    * Exempel-URL: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Ersätt den sista identifieraren i URL:en (MA1nQC i exempel-URL ovan) med följande sträng: **search?fileName=**
    * Exempel-URL efter ersättning: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Det här är **Mediebas-URL** - gör en anteckning av den.
##### <a name="updating-the-media-base-url"></a>Uppdatera mediebas-URL
1. Logga in på miljön (HQ).
1. Med hjälp av menyn till vänster, gå till **Moduler > Butik > Kanalinställning > Butiksschemaläggare > Kanalprofiler**.
1. Klicka på **Redigera**.
1. Från **Profilegenskaper**, ersätt egenskapsvärdet för **Medieserverbas-URL** med den **Mediebas-URL** du skapade tidigare.
1. Välj den andra kanalen i listan till vänster under **standard** kanal.
1. Under **Profilegenskaper**, klicka på **+ Lägg till**.
1. För den egenskap som valdes, välj **medieserverbas-URL** som egenskapsnyckel och för egenskapsvärde väljer du den **mediebas-URL** du skapade tidigare.
1. Klicka på **Spara**.

### <a name="configure-email-server-optional"></a>Konfigurera e-postserver (valfritt)
Observera att SMTP-servern eller e-posttjänsten som du anger här måste vara tillgänglig från den Azure-prenumeration du använder för miljön.
1. Logga in på miljön (HQ).
1. Med hjälp av menyn till vänster, gå till **Moduler > Butik > Administrationsinställning > Parametrar > E-postparametrar**.
1. Klicka på fliken **SMTP-inställningar**.
1. I **fältet utgående e-postserver**, skriv den FQDN eller IP-adress för din SMTP-server eller e-posttjänst.
1. I fältet **SMTP-portnummer** ange portnummer (standard är 25 när du inte använder SSL).
1. I fältet **Användarnamn** ange ett värde (om autentisering krävs).
1. I fältet **Lösenord** ange ett värde (om autentisering krävs).
1. Klicka på **Spara**.
1. Klicka på **Uppdatera**.
1. Klicka på fliken **Testa e-post**.
1. I fältet e-postleverantör, välj **SMTP**.
1. I fältet **Skicka till** ange e-postadressen där du vill att testmeddelandet ska levereras.
1. Klicka på **Skicka testmeddelande**.
### <a name="configure-email-templates-optional"></a>Konfigurera e-postmallar (valfritt)
E-postmallen för varje transaktionshändelse som du vill skicka e-postmeddelanden för måste uppdateras med en giltig e-postadress för avsändaren.
1. Med hjälp av menyn till vänster, gå till **Moduler > Organisationsadministration > Inställning > E-postmall för organisation**.
1. Klicka på **Visa lista**.
1. För var och en av mallarna i listan:
    1. Ange avsändarens e-postadress för e-postmallen i fältet **e-postadress för avsändaren**.
    1. (Valfritt) I fältet **avsändarensnamn** anger du ett namn som ska användas som avsändare för den här e-postmallen.
1. Klicka på **Spara**.
### <a name="customizing-email-templates-optional"></a>Anpassa e-postmallar (valfritt)
Du kanske vill anpassa e-postmallarna så att de använder olika bilder eller uppdatera länkarna i mallen om du vill länka tillbaka till förhandsversionsmiljön. I stegen nedan beskrivs hur du hämtar standardmallarna, anpassar dem och uppdaterar mallarna i systemet.
1. Med hjälp av en webbläsare, hämta [Microsoft Dynamics 365 Commerce förhandsversion av standard e-postmallar .zip-fil](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) med följande HTML-dokument till den lokala datorn.
    1. Orderbekräftelsemall
    1. Utfärda presentkortsmall
    1. Ny ordermall
    1. Förpackningsordermall
    1. Hämta förpackningsordermall
1. Anpassa mallarna med hjälp av en text- eller HTML-redigerare. Se en lista med token som stöds nedan.
1. Logga in på miljön (HQ).
1. Med hjälp av menyn till vänster, gå till **Moduler > Butik > Administrationsinställning > Parametrar > Organisationens e-postmallar**.
1. Expandera listan till vänster om du vill se alla mallar.
1. Utför följande steg för varje mall som du vill anpassa:
    1. Välj mallen i listan.
    1. Under **Innehåll i e-postmeddelande**, välj lämplig språkversion från listan (standard **sv-SE**).
    1. Under **Innehåll i e-postmeddelande**, klicka på **Redigera**, bör du se fönstret **Överför e-postmall** öppnas.
    1. Klicka på **Bläddra** och leta upp HTML-filen med det anpassade innehållet.
    1. Klicka på **Överför**, mallen överförs till systemet och en förhandsversion visas.
    1. Klicka på **OK**.
    1. Valfritt Anpassa egenskapen **ämne** för mallen.
    1. Klicka på **Spara**.

#### <a name="supported-tokens-in-the-email-template"></a>Variabler som stöds i e-postmallen
Dessa token ersätts med e-postrenderingstid med de faktiska värden som gäller för kunden och deras order.

**Försäljningsorder** - följande token gäller för den övergripande försäljningsordern.

|Namn på token|Token |
|---|---|
|Ordernummer|%salesid%|
|Kundnamn|%customername%|
|Leveransadress|%deliveryaddress%|
|Faktureringsadress|%customeraddress%|
|Orderdatum|%shipdate%|
|Leveransläge|%modeofdelivery%|
|Rabatt|%discount%|
|Moms|%tax%|
|Ordersumma|%total%|

**Försäljningsrad** - följande token fylls i för varje produkt i ordern.

*Obs! Placera token **Produktlista - start** och **Produktlista - slut** i början och slutet av HTML-block som upprepas för varje produkt.*

|Namn på token|Token |
|---|---|
|Produktlista - start|\<!--%tablebegin.salesline% -->|
|Produktlista - slut|\<!--%tableend.salesline%-->|
|Produktnamn|%lineproductname%|
|Beskrivning|%lineproductdescription%|
|Antal|%linequantity%|
|Pris för radenhet|%lineprice% (verifiera)|
|totalbelopp för radartikel|%linenetamount%|
|radrabatt|%linediscount%|
|Transportdatum|%lineshipdate%|
|Anskaffningsmetod|%linedeliverymode%|
|leveransadress|%linedeliveryaddress%|
|Försäljningsenhet för raden|%lineunit%|

