---
title: Reservera Talent
description: "I det här avsnittet får du veta hur du skapar en ny miljö för Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 2fc4119f3b33aa583274f4d823e296752cdde41d
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="provision-talent"></a>Reservera Talent

[!include [banner](includes/banner.md)]

I det här avsnittet får du veta hur du skapar en ny produktionsmiljö för Microsoft Dynamics 365 for Talent. Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Microsoft Dynamics 365-licens som redan innehåller tjänsteplanen for Talent och du inte kan utföra stegen i det här avsnittet, kontakta då supporten.

För att komma igång måste en global administratör logga in på [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) och skapa ett nytt projekt for Talent. Såvida inte ett licensieringsproblem hindrar dig från att tillhandahålla Talent krävs ingen hjälp från supporten eller Dynamics Service Engineering (DSE)-representanter.

## <a name="create-an-lcs-project"></a>Skapa ett LCS-projekt
För att hantera dina Talent-miljöer med LCS måste först skapa ett LCS-projekt.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index) med det konto som du använder för din Talent-prenumeration.
2. Klicka på plustecknet (**+**) för att skapa ett projekt.
3. Välj **Microsoft Dynamics 365 for Talent** som produktversion och produktnamn.
4. Välj metoden **Dynamics 365 for Talent**.
5. Markera **Skapa**.

Mer information om hur du kommer igång med Talent finns i metoden för **Talent** som du skapade i det nya projektet. När du har skapat projektet slutför du stegen nedan för att skapa din Talent-miljö.

## <a name="provision-a-talent-project"></a>Skapa ett Talent-projekt
När du har skapat ett LCS-projekt kan du införa Talent i en miljö.

1. I LCS-projektet väljer du fliken **App-hantering for Talent**.
2. Talent etableras alltid i en Microsoft PowerApps-miljö, detta i syfte att möjliggöra PowerApps-integrering och -utbyggnad. Läs avsnittet ”Välja en PowerApps-miljö” i det här ämnet innan du fortsätter. 
3. Om du inte redan har en PowerApps-miljö, följ då stegen i avsnittet ”Skapa en ny PowerApps-miljö (vid behov)” i det här avsnittet innan du fortsätter.

    > [!NOTE]
    > Om du vill visa befintliga miljöer eller skapa nya miljöer måste den innehavaradministratören som tillhandahåller Talent inneha en PowerApps P2-licens. Om din organisation inte har en licens för PowerApps P2 kan du skaffa en från din CSP eller [Prissättningssidan för PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Välj **Lägg till** och välj sedan den miljö du vill etablera Talent i.
5. Markera alternativet ”Inkludera demodata" om du vill att din miljö med samma demodatauppsättning används i Talent testkörning.  Detta är praktiskt för långsiktig demonstrations- och utbildningsmiljöer och ska aldrig användas i produktionsmiljöer.  Observera att du måste välja det här alternativet vid den första implementeringen och det går inte att uppdatera en befintlig distribution senare.
6. Välj **Ja** för att acceptera villkoren och börja implementeringen.

    Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt bara några minuter. Om försörjningprocessen misslyckas måste du kontakta Support.

7. Välj **Logga in på Talent** för att använda den nya miljön.

> [!NOTE]
> Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Talent i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

> [!NOTE]
> Eftersom bara två LCS-miljöer tillåts tillsammans med Talent-abonnemanget kan du även försöka utnyttja den kostnadsfria 60-dagars [utvärderingsmiljön för Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Även om utvärderingsmiljön ägs av den användare som har begärt den, kan andra användare bjudas in via systemets administrationserfarenhet för personalfrågor. Utvärderingsmiljöer innehåller fiktiva data som kan användas för att utforska programmet på ett säkert sätt. De är inte avsedda att användas som produktionsmiljöer. Observera att alla data i miljön tas bort och kan inte återställas när utvärderingstiden upphör att gälla efter 60 dagar. Du kan registrera dig för en ny utvärderingsmiljö när den befintliga miljön har gått ut.

## <a name="select-a-powerapps-environment"></a>Välj en PowerApps-miljö

Integreringen mellan Talent och PowerApps-miljöer låter dig integrera och utöka användningen av Talent-data med verktyg för PowerApps. Att förstå syftet med PowerApps-miljöer kan inte bara hjälpa dig att skapa appar för att utöka Talent, utan kan även hjälpa dig att välja rätt miljö vid tillhandahållande av Talent. Mer information om PowerApps-miljöer, såsom omfattning, åtkomst och att skapa och välja miljö finns i [Vi presenterar PowerApps-miljöer](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Använd följande riktlinjer när du bestämmer vilka PowerApps-miljöer som ska användas för att distribuera Talent: 
1. I LCS, välj Hantera miljöer eller gå direkt till PowerApps Administratörscenter, där du kan visa befintliga miljöer och skapa nya miljöer.
2. En enskild Talent-miljö mappas till en enda PowerApps-miljö.
3. En PowerApps-miljö "innehåller" Talent-programmet tillsammans med motsvarande PowerApps, Flow och CDS-program. Om PowerApps-miljön tas bort tas även apparna bort.
4. Dataintegration och teststrategier ska beaktas, till exempel: begränsat läge, UAT, produktion. Därför rekommenderar vi att du noggrant överväger de olika konsekvenserna för distribution, eftersom det inte är lätt att senare ändra vilken Talent-miljö som är mappad till en PowerApps-miljö.
5. Följande PowerApps-miljöer kan inte användas för Talent och filtreras i urvalslistan i LCS:
 
    **CDS 2.0-miljöer** CDS 2.0 görs offentligt tillgänglig 21 mars 2018, Talent stöder ännu inte CDS 2.0. Du kan visa och skapa CDS 2.0-databaser i PowerApps administratörscenter, men de kan inte användas i Talent. Alternativet att använda CDS 2.0-miljöer i Talent-distributioner kan användas vid en senare tidpunkt.
   
   > [!Note]
   > För att särskilja mellan CDS 1.0- och 2.0-miljöer i administrationsportalen, välj en miljö och leta efter **Uppgifter**. CDS 2.0-miljöer refererar till faktum att ”du kan hantera dessa inställningar i Dynamics 365 administrationscenter” pekar på en instansversion och har ingen flik som för Databas. 
 
   **Standardinställda PowerApps- miljöer** Även om varje innehavare konfigureras automatiskt med en standardmiljö för PowerApps, rekommenderar vi inte att använda dem med Talent eftersom alla innehavare har tillgång till PowerApps-miljön och kanske oavsiktligt förstör produktionsdata när de testar och utforskar integrering med PowerApps eller Flow.
   
   <strong>Testkörningsmiljöer</strong> Miljöer med ett namn som ”TestDrive- alias@domain" skapas med en 60 dagars förfalloperiod och upphör att gälla efter den tiden vilket kan orsaka att miljön tas bort automatiskt.
   
   **Regioner som inte stöds** För närvarande stöds bara Talent i följande regioner: USA, Europa och Australien.
  
6. Det finns inga specifika åtgärder som ska vidtas när du har fastställt den korrekta miljön att använda. Fortsätt försörjningsprocessen. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Skapa en ny PowerApps-miljö (vid behov)

Kör ett PowerShell-skript om du vill skapa en ny PowerApps-miljö för Talent inom ramen för innehavaradministrationen som har PowerApps Plan 2-licens. Skriptet automatiserar följande steg:


 + Skapande av en PowerApps-miljö
 + Skapandet av en CDS 1.0-databas
 + Avmarkera alla exempeldata i CDS 1.0-databasen


Slutför följande instruktioner för att köra skriptet:

1. Hämta filen ProvisionCDSEnvironment.zip från följande plats: [ProvisionCDSEnvironment-skript](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Från din hämtningsmapp högerklickar du på filen ProvisionCDSEnvironment.zip precis hämtade och markera **egenskaper**.  Om det finns ett säkerhetsmeddelande längst ned i dialogrutan som visar ”den här filen kommer från en annan dator och kan ha blockerats för att skydda datorn”, markera kryssrutan om du vill **Avblockera**, klicka på **Använd** och sedan **OK**.

3. Packa upp hela innehållet av filen ProvisionCDSEnviroinment.zip i en annan mapp än din rotmapp.

4. Kör programmet Windows PowerShell eller Windows PowerShell ISE som administratör.

   Besök avsnittet [Ange körningspolicyn](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) om du vill veta mer om hur du anger körningspolicy så att skript ska kunna köras. Vi föreslår att du använder följande ”Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process”, men kom ihåg att följa ditt företags säkerhetsprinciper och stäng PowerShell-fönstret när du är klar. 
  
5. Navigera inom PowerShell till mappen där du packade upp filen och kör följande kommando och ersätt värden enligt anvisningarna nedan:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **MyNewEnvironment** bör ersättas med ditt namn på miljön. Detta namn visas i LCS och kommer att visas när användare väljer vilken Talent-miljö som ska användas. 

   **YourLocation** ska ersättas med någon av regionerna som stöds för Talent: USA, Europa, Australien. 

   **– Utförligt** är valfri och ger detaljerad information för att skicka till support om det uppstår problem.

6. Fortsätt försörjningsprocessen.
 

## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.
Som standard har den globala administratör som skapade miljön åtkomst till den. Ytterligare användare måste beviljas explicit åtkomst. För att bevilja åtkomst lägger du [till användare](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) och [tilldela dem lämpliga roller](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles) i bas-miljön för HR. Global administratör som har distribuerat Talent måste också starta både Attract- och Onboard-programmen för att slutföra initieringen och aktivera åtkomst för andra innehavare.  Tills detta inträffar kan andra användare inte komma åt Onboard- och Attract-programmen och får åtkomstfel.


