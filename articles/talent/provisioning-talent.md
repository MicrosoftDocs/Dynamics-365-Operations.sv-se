---
title: Reservera Talent
description: I det här avsnittet får du veta hur du skapar en ny miljö för Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
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
ms.openlocfilehash: 5bcdb50475fb341a538211cb122eb7c13067d86a
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527228"
---
# <a name="provision-talent"></a>Etablera Talent

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I det här avsnittet får du veta hur du skapar en ny produktionsmiljö för Microsoft Dynamics 365 Talent. Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Microsoft Dynamics 365-licens som redan innehåller tjänsteplanen for Talent och du inte kan utföra stegen i det här avsnittet, kontakta då supporten.

För att komma igång måste en global administratör logga in på [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) och skapa ett nytt projekt for Talent. Såvida inte ett licensieringsproblem hindrar dig från att tillhandahålla Talent krävs ingen hjälp från supporten eller Dynamics Service Engineering (DSE)-representanter.

## <a name="create-an-lcs-project"></a>Skapa ett LCS-projekt
För att hantera dina Talent-miljöer med LCS måste först skapa ett LCS-projekt.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index) med det konto som du använder för din Talent-prenumeration.

2. Klicka på plustecknet (**+**) för att skapa ett projekt.

3. Välj **Microsoft Dynamics 365 Talent** som produktversion och produktnamn.

4. Välj **Dynamics 365 Talent**-metoden.

5. Markera **Skapa**. 

Mer information om hur du kommer igång med Talent finns i metoden för **Talent** som du skapade i det nya projektet. När du har skapat projektet slutför du stegen nedan för att skapa din Talent-miljö.

## <a name="provision-a-talent-project"></a>Skapa ett Talent-projekt

När du har skapat ett LCS-projekt kan du införa Talent i en miljö.

1. I LCS-projektet väljer du fliken **App-hantering for Talent**.

2. Ange om detta är ett begränsat läge eller produktionsinstans av Talent. Funktionerna för förhandsgranskning kan finnas tillgängliga i begränsade instanser för att möjliggöra tidig återrapportering och testning. 

    > [!NOTE]
    > Det går inte att ändra Talent-instanstypen när den har angetts. Kontrollera att rätt instanstyp har valts innan du fortsätter.

    > [!NOTE]
    > Instanstypen Talent är separat från instanstypen för Microsoft Power Apps-miljön, som du anger i Power Apps-administrationscentret.

3. Markera alternativet **Inkludera demodata** om du vill att din miljö med samma demodatauppsättning används i Talent testkörning. Detta är praktiskt för långsiktig demonstrations- och utbildningsmiljöer och ska aldrig användas i produktionsmiljöer.  Observera att du måste välja det här alternativet vid den första implementeringen. Du kan inte uppdatera en befintlig distribution senare.

4. Talent etableras alltid i en Microsoft Power Apps-miljö, detta i syfte att möjliggöra Power Apps-integrering och utbyggnad. Läs avsnittet ”Välja en Power Apps-miljö” i det här ämnet innan du fortsätter. Om du inte redan har en Power Apps-miljö, välj hantera miljöer i LCS eller gå till Power Apps administrationscenter. Följ stegen för att [skapa en Power Apps-miljö](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Välj den miljö som du vill konfigurera Talent på.

6. Välj **Ja** för att acceptera villkoren och börja implementeringen.

    Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt några minuter. Om försörjningprocessen misslyckas måste du kontakta Support.

7. Välj **Logga in på Talent** för att använda den nya miljön.

    > [!NOTE]
    > Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Talent i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

    > Eftersom bara två LCS-miljöer tillåts tillsammans med Talent-abonnemanget kan du även försöka utnyttja den kostnadsfria 60-dagars [utvärderingsmiljön för Talent](https://dynamics.microsoft.com/talent/overview/). Även om utvärderingsmiljön ägs av den användare som har begärt den, kan andra användare bjudas in via systemets administrationserfarenhet för Personal. Utvärderingsmiljöer innehåller fiktiva data som kan användas för att utforska programmet på ett säkert sätt. De är inte avsedda att användas som produktionsmiljöer. Observera att alla data i miljön tas bort och kan inte återställas när utvärderingstiden upphör att gälla efter 60 dagar. Du kan registrera dig för en ny utvärderingsmiljö när den befintliga miljön har gått ut.

## <a name="select-a-power-apps-environment"></a>Välj en Power Apps-miljö

Integreringen mellan Talent och Power Apps-miljöer låter dig integrera och utöka användningen av Talent-data med verktyg för Power Apps. Att förstå syftet med Power Apps-miljöer kan inte bara hjälpa dig att skapa appar för att utöka Talent, utan kommer även hjälpa dig att välja rätt miljö vid tillhandahållande av Talent. Mer information om Power Apps-miljöer, såsom omfattning, åtkomst och att skapa och välja miljö finns i [Vi presenterar Power Apps-miljöer](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Använd följande riktlinjer när du bestämmer vilka Power Apps-miljöer som ska användas för att distribuera Talent: 

1. I LCS, välj **Hantera miljöer** eller gå direkt till Power Apps Administratörscenter, där du kan visa befintliga miljöer och skapa nya miljöer.

2. En enskild Talent-miljö mappas till en enda Power Apps-miljö.

3. En Power Apps-miljö "innehåller" Talent-programmet tillsammans med motsvarande Power Apps, Power Automate och Common Data Service-program. Om Power Apps-miljön tas bort tas även apparna bort. Vid tillhandahållande av en Talent-miljö kan du tillhandahålla antingen en **Utvärderingsversion**- eller **Produktion**-miljö. Välj typ av miljö baserat på hur miljön kommer att användas. 

4. Dataintegration och teststrategier ska beaktas, till exempel: begränsat läge, UAT, produktion. Vi rekommenderar att du noggrant överväger de olika konsekvenserna för distribution, eftersom det inte är lätt att senare ändra vilken Talent-miljö som är mappad till en Power Apps-miljö.

5. Följande Power Apps-miljöer kan inte användas för Talent och filtreras i urvalslistan i LCS:
 
    - **Standardinställda Power Apps-miljöer** - Även om varje innehavare konfigureras automatiskt med en standardmiljö för Power Apps, rekommenderar vi inte att använda dem med Talent eftersom alla innehavare har tillgång till Power Apps-miljön och kanske oavsiktligt förstör produktionsdata när de testar och utforskar integrering med Power Apps eller Power Automate.
   
    - **Testmiljöer** Dessa miljöer skapas med ett förfallodatum och upphör att gälla efter den tiden vilket kan orsaka att miljön och alla Talent-instanser som den innehåller tas bort automatiskt.
   
    - **Regioner som inte stöds** För närvarande stöds bara Talent i följande regioner: USA, Europa, Storbritannien, Australien, Kanada och Asien.
  
6. När du har kontrollerat den korrekta miljön kan du fortsätta med etableringsprocessen. 
 
## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.

Som standard har den globala administratör som skapade miljön åtkomst till den. Ytterligare användare måste beviljas explicit åtkomst. För att bevilja åtkomst måste du lägga till användare och tilldela dem lämpliga roller i Personal-miljön. Global administratör som har distribuerat Talent måste också starta både Attract och Onboard för att slutföra initieringen och aktivera åtkomst för andra innehavare.  Tills detta inträffar kan andra användare inte komma åt Onboard och Attract och får åtkomstfel. Mer information finns i [skapa nya användare](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) och [tilldela användare till säkerhetsroller](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
