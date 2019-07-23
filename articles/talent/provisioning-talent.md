---
title: Reservera Talent
description: I det här avsnittet får du veta hur du skapar en ny miljö för Microsoft Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 05/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: c249df697553cd42eccd59d3f2c3f5f083ead1cb
ms.sourcegitcommit: 15154b0aa86110ce5fad6f63e6763103a676a1d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2019
ms.locfileid: "1624617"
---
# <a name="provision-talent"></a>Etablera Talent

[!include [banner](includes/banner.md)]

I det här avsnittet får du veta hur du skapar en ny produktionsmiljö för Microsoft Dynamics 365 for Talent. Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Microsoft Dynamics 365-licens som redan innehåller tjänsteplanen for Talent och du inte kan utföra stegen i det här avsnittet, kontakta då supporten.

För att komma igång måste en global administratör logga in på [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) och skapa ett nytt projekt for Talent. Såvida inte ett licensieringsproblem hindrar dig från att tillhandahålla Talent krävs ingen hjälp från supporten eller Dynamics Service Engineering (DSE)-representanter.

## <a name="create-an-lcs-project"></a>Skapa ett LCS-projekt
För att hantera dina Talent-miljöer med LCS måste först skapa ett LCS-projekt.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index) med det konto som du använder för din Talent-prenumeration.
2. Klicka på plustecknet (**+**) för att skapa ett projekt.
3. Välj **Microsoft Dynamics 365 for Talent** som produktversion och produktnamn.
4. Välj **Dynamics 365 for Talent**-metoden.
5. Markera **Skapa**.

Mer information om hur du kommer igång med Talent finns i metoden för **Talent** som du skapade i det nya projektet. När du har skapat projektet slutför du stegen nedan för att skapa din Talent-miljö.

## <a name="provision-a-talent-project"></a>Skapa ett Talent-projekt
När du har skapat ett LCS-projekt kan du införa Talent i en miljö.

1. I LCS-projektet väljer du fliken **App-hantering for Talent**.
2. Ange om detta är ett begränsat läge eller produktionsinstans av Talent. Funktionerna för förhandsgranskning kan finnas tillgängliga i begränsade instanser för att möjliggöra tidig återrapportering och testning. 
    > [!NOTE]
    > Instanstypen Talent är separat från instanstypen för PowerApps-miljön, som du anger i PowerApps-administrationscentret.
3. Markera alternativet **Inkludera demodata** om du vill att din miljö med samma demodatauppsättning används i Talent testkörning. Detta är praktiskt för långsiktig demonstrations- och utbildningsmiljöer och ska aldrig användas i produktionsmiljöer.  Observera att du måste välja det här alternativet vid den första implementeringen. Du kan inte uppdatera en befintlig distribution senare.
4. Talent etableras alltid i en Microsoft PowerApps-miljö, detta i syfte att möjliggöra PowerApps-integrering och -utbyggnad. Läs avsnittet ”Välja en PowerApps-miljö” i det här ämnet innan du fortsätter. Om du inte redan har en PowerApps-miljö, välj hantera miljöer i LCS eller gå till PowerApps administrationscenter. Följ stegen för att [skapa en miljö med PowerApps](https://docs.microsoft.com/en-us/powerapps/administrator/create-environment).

    > [!NOTE]
    > Om du vill visa befintliga miljöer eller skapa nya miljöer måste den innehavaradministratören som tillhandahåller Talent inneha en PowerApps P2-licens. Om din organisation inte har en licens för PowerApps P2 kan du skaffa en från din CSP eller [Prissättningssidan för PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

5. Välj den miljö som du vill konfigurera Talent på.
6. Välj **Ja** för att acceptera villkoren och börja implementeringen.

    Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt några minuter. Om försörjningprocessen misslyckas måste du kontakta Support.

7. Välj **Logga in på Talent** för att använda den nya miljön.

    > [!NOTE]
    > Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Talent i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

    > Eftersom bara två LCS-miljöer tillåts tillsammans med Talent-abonnemanget kan du även försöka utnyttja den kostnadsfria 60-dagars [utvärderingsmiljön för Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Även om utvärderingsmiljön ägs av den användare som har begärt den, kan andra användare bjudas in via systemets administrationserfarenhet för personalfrågor. Utvärderingsmiljöer innehåller fiktiva data som kan användas för att utforska programmet på ett säkert sätt. De är inte avsedda att användas som produktionsmiljöer. Observera att alla data i miljön tas bort och kan inte återställas när utvärderingstiden upphör att gälla efter 60 dagar. Du kan registrera dig för en ny utvärderingsmiljö när den befintliga miljön har gått ut.

## <a name="select-a-powerapps-environment"></a>Välj en PowerApps-miljö

Integreringen mellan Talent och PowerApps-miljöer låter dig integrera och utöka användningen av Talent-data med verktyg för PowerApps. Att förstå syftet med PowerApps-miljöer kan inte bara hjälpa dig att skapa appar för att utöka Talent, utan kommer även hjälpa dig att välja rätt miljö vid tillhandahållande av Talent. Mer information om PowerApps-miljöer, såsom omfattning, åtkomst och att skapa och välja miljö finns i [Vi presenterar PowerApps-miljöer](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Använd följande riktlinjer när du bestämmer vilka PowerApps-miljöer som ska användas för att distribuera Talent: 

1. I LCS, välj **Hantera miljöer** eller gå direkt till PowerApps Administratörscenter, där du kan visa befintliga miljöer och skapa nya miljöer.
2. En enskild Talent-miljö mappas till en enda PowerApps-miljö.
3. En PowerApps-miljö "innehåller" Talent-programmet tillsammans med motsvarande PowerApps, Flow och Common Data Service-program. Om PowerApps-miljön tas bort tas även apparna bort. Vid tillhandahållande av en Talent-miljö konfigureras antingen ”Utvärderingsversion” eller ”Produktion”. Välj typ av miljö baserat på hur miljön kommer att användas. 
4. Dataintegration och teststrategier ska beaktas, till exempel: begränsat läge, UAT, produktion. Vi rekommenderar att du noggrant överväger de olika konsekvenserna för distribution, eftersom det inte är lätt att senare ändra vilken Talent-miljö som är mappad till en PowerApps-miljö.
5. Följande PowerApps-miljöer kan inte användas för Talent och filtreras i urvalslistan i LCS:
 
    - **Standardinställda PowerApps- miljöer** Även om varje innehavare konfigureras automatiskt med en standardmiljö för PowerApps, rekommenderar vi inte att använda dem med Talent eftersom alla innehavare har tillgång till PowerApps-miljön och kanske oavsiktligt förstör produktionsdata när de testar och utforskar integrering med PowerApps eller Flow.
   
    - **Testmiljöer** Dessa miljöer skapas med ett förfallodatum och upphör att gälla efter den tiden vilket kan orsaka att miljön och alla Talent-instanser som den innehåller tas bort automatiskt.
   
    - **Regioner som inte stöds** För närvarande stöds bara Talent i följande regioner: USA, Europa, Storbritannien och Australien.
  
6. När du har kontrollerat den korrekta miljön kan du fortsätta med etableringsprocessen. 
 
## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.
Som standard har den globala administratör som skapade miljön åtkomst till den. Ytterligare användare måste beviljas explicit åtkomst. För att bevilja åtkomst måste du lägga till användare och tilldela dem lämpliga roller i Core HR-miljön. Global administratör som har distribuerat Talent måste också starta både Attract- och Onboard-programmen för att slutföra initieringen och aktivera åtkomst för andra innehavare.  Tills detta inträffar kan andra användare inte komma åt Onboard- och Attract-programmen och får åtkomstfel. Mer information finns i [skapa nya användare](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) och [tilldela användare till säkerhetsroller](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
