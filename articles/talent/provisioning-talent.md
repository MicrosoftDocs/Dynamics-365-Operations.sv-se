---
title: Reservera Microsoft Dynamics 365 for Talent
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
ms.sourcegitcommit: 1be4b41f63dd03a1d853d344fcde05e8962424e2
ms.openlocfilehash: e6266ef5890b5caaf33db76eeccfc8a7a6888a11
ms.contentlocale: sv-se
ms.lasthandoff: 03/17/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Reservera Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

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
2. Talent etableras alltid i en Microsoft PowerApps-miljö, detta i syfte att möjliggöra PowerApps-integrering och -utbyggnad. Om du inte redan har en PowerApps-miljö, följ då stegen i avsnittet ”Skapa en ny PowerApps-miljö (vid behov)” i det här avsnittet innan du fortsätter.

    > [!NOTE]
    > Om du vill visa befintliga miljöer eller skapa nya miljöer måste den innehavaradministratören som tillhandahåller Talent inneha en PowerApps P2-licens. Om din organisation inte har en licens för PowerApps P2 kan du skaffa en från din CSP eller [Prissättningssidan för PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Välj **Lägg till** och välj sedan den miljö du vill etablera Talent i.
4. Välj **Ja** för att acceptera villkoren och börja implementeringen.

    Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt bara några minuter. Om försörjningprocessen misslyckas måste du kontakta Support.

6. Välj **Logga in på Talent** för att använda den nya miljön.

> [!NOTE]
> Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Talent i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

> [!NOTE]
> Miljöer som etableras i Talent genom LCS innehåller inte demodata som är konfigurerade för personaluppgifter (HR) eller som är specifika för Talent. Om du behöver en miljö som innehåller demodata rekommenderar vi att du registrerar dig för den kostnadsfria 60-dagars [utvärderingsmiljön för Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Även om utvärderingsmiljön ägs av den användare som har begärt den, kan andra användare bjudas in via systemets administrationserfarenhet för personalfrågor. Utvärderingsmiljöer innehåller fiktiva data som kan användas för att utforska programmet på ett säkert sätt. De är inte avsedda att användas som produktionsmiljöer. Observera att alla data i miljön tas bort och kan inte återställas när utvärderingstiden upphör att gälla efter 60 dagar. Du kan registrera dig för en ny utvärderingsmiljö när den befintliga miljön har gått ut.

## <a name="create-a-new-powerapps-environment-if-required"></a>Skapa en ny PowerApps-miljö (vid behov)
Integreringen mellan Talent och PowerApps-miljöer låter dig integrera och utöka användningen av Talent-data med verktyg för PowerApps. Att förstå syftet med PowerApps-miljöer hjälper dig skapa appar som uppfyller de krav har du för att utöka Talent. Mer information om PowerApps-miljöer, såsom omfattning, åtkomst och att skapa och välja miljö finns i [Vi presenterar PowerApps-miljöer](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). När varje innehavare automatiskt skapas i en standardmiljö för PowerApps är kanske inte detta den bästa miljön för distribution av Talent. Dataintegration och strategitester bör beaktas i det här skedet, varför vi rekommenderar att du överväger olika konsekvenser för distribution, eftersom det är svårt att ändra senare. 

Även om varje innehavare automatiskt skapas i en standardmiljö för PowerApps är kanske inte detta den bästa miljön för distribution av Talent. Dataintegration och teststrategier bör beaktas under det här steget. Därför rekommenderar vi att du noggrant överväger de olika konsekvenserna för distribution, eftersom det inte är lätt att senare ändra PowerApps-miljö.

1. I LCS välj **Hantera miljöer**. Du förflyttas till [PowerApps administratörscenter](https://preview.admin.powerapps.com/environments), där du kan visa befintliga miljöer och skapa nya miljöer.
2. Välj **ny miljö**.
3. Ange ett unikt namn för miljön och välj den plats du vill implementera på.

    > [!NOTE]
    > Talent är inte tillgängligt överallt. Därför bör du kontrollera tillgängligheten innan du väljer platsen för din miljö.

4. När du tillfrågas om du vill skapa en databas, markera **Skapa databas** för att skapa databasen Common Data Service (CDS) där delar av dina Talent-data kommer att lagras. Genom att skapa en databas kan du också integrera PowerApps-program i Talent.
5. Du tillfrågas om vilken åtkomstnivå du vill använda för databasen. Vi rekommenderar att du väljer **Begränsa åtkomst** eftersom detta alternativ hindrar Talent-användare från att få direkt tillgång till känsliga data genom att använda ett PowerApps-program.
6. Den CDS-databas som skapas innehåller demonstrationsdata som tillför inaktiva anställda och fiktiva adresser (bland annat) i din produktionsmiljö. För att ta bort demonstrationsdatan, följ dessa steg när du är klar med CDS-databasen:

    > [!IMPORTANT]
    > Om du tidigare skapat en CDS-databas och angett något av företagets produktionsdata i denna, kommer dessa steg att ta bort **alla** data i den valda databasen, även uppgifter om företagets produktion.

    1. Logga in på [PowerApps](https://preview.web.powerapps.com/home).
    2. Välj den miljö som du skapade i steg 2 i rullgardinsmenyn i det övre högra hörnet.
    3. Expandera **Common Data Service** i det vänstra navigeringsfönstret och välj sedan **enheter**.
    4. Markera ellipsknapen till höger på sidan (**...**) och välj sedan **Rensa alla data**.
    5. Välj **Ta bort data** för att bekräfta att du vill ta bort dina data. Denna åtgärd tar bort alla demodata som ingår i CDS som standard. Den tar också bort alla andra data som har angetts i den valda databasen.

Du kan nu använda den nya miljön.

## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.
Som standard har den globala administratör som skapade miljön åtkomst till den. Ytterligare användare måste beviljas explicit åtkomst. För att bevilja åtkomst lägger du [till användare](../dev-itpro/sysadmin/tasks/create-new-users.md) och [tilldela dem lämpliga roller](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) i bas-miljön för HR. Du måste också lägga till dessa användare i PowerApps-miljön så att de kan komma åt Attract- och Onboard-program. Proceduren beskrivs här. Om du behöver hjälp att slutföra stegen läs [introduktion till PowerApps administratörscenter ](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/), som är ett blogginlägg.

Den här proceduren slutförs av den globala administratören som distribuerat Talent-miljön.

1. Öppna [PowerApps Admin center](https://preview.admin.powerapps.com/environments).
2. Markera de relevanta miljöerna.
3. Tilldela berörda användare rollen **Environment Maker** i fliken **Säkerhet**.

Observera att det sista steget, där du manuellt lägger till användare i en PowerApps-miljö är tillfälligt. Så småningom infogas det automatiskt när du lägger till användare i basprogrammet för personal (Core HR).

