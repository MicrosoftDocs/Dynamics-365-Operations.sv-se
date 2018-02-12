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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: sv-se
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Reservera Microsoft Dynamics 365 for Talent
I det här avsnittet får du veta hur du skapar en ny miljö för Microsoft Dynamics 365 for Talent. Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Microsoft Dynamics 365-licens som redan innehåller tjänsteplanen for Talent och du inte kan utföra stegen i det här avsnittet, kontakta då supporten.

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

    Den nya miljön visas i listan över miljöer i navigeringsfönstret till vänster. Du kan emellertid inte börja att använda miljön förrän objektets implementeringsstatus uppdateras till **Implementera**. Den här processen tar normalt bara några minuter. Du måste kontakta supporten om implementeringen misslyckas.

6. Välj **Logga in på Talent** för att använda den nya miljön.

> [!NOTE]
> Om du ännu inte har uppfyllt de slutgiltiga kraven kan du implementera en testinstans av Talent i projektet. Du kan sedan använda den här instansen för att testa din lösning tills du loggar ut. Om du använder den nya miljön för testning måste du upprepa denna procedur för att skapa en produktionsmiljö.

## <a name="create-a-new-powerapps-environment-if-required"></a>Skapa en ny PowerApps-miljö (vid behov)
1. Välj **Hantera miljöer** i LCS. Du förflyttas till [PowerApps administratörscenter](https://preview.admin.powerapps.com/environments), där du kan visa befintliga miljöer och skapa nya miljöer.
2. Välj knappen (**+**) **Ny miljö**.
3. Ange ett unikt namn för miljön och välj den plats du vill implementera på.

    > [!NOTE]
    > Talent är inte tillgängligt överallt. Därför bör du kontrollera tillgängligheten innan du väljer platsen för din miljö.

4. När du tillfrågas om du vill skapa en databas, markera **Skapa databas** för att skapa databasen Common Data Service (CDS) där delar av dina Talent-data kommer att lagras. Genom att skapa en databas kan du också integrera PowerApps-program i Talent.
5. Du tillfrågas om den åtkomstnivå som du vill använda för databasen. Vi rekommenderar att du väljer **Begränsa åtkomst** eftersom detta alternativ hindrar Talent-användare från att få direkt tillgång till känsliga data genom att använda ett PowerApps-program.
6. CDS-databasen som skapas innehåller demonstrationsdata. Dessa demonstrationsdata är användbara eftersom du kan använda demonstrationsföretaget för tester eller för att skapa uppgiftsinspelningar eller uppgiftsguider. Demonstrationsdatan tillför emellertid inaktiva anställda och fiktiva adresser (bland annat) i din produktionsmiljö. För att ta bort demonstrationsdatan, följ dessa steg när du är klar med CDS-databasen:

    > [!IMPORTANT]
    > Om du tidigare skapat en CDS-databas och angett någon form av företagets produktionsdata i denna, notera då att dessa steg tar bort **alla** data i den valda databasen, även uppgifter om företagets produktion.

    1. Logga in i [PowerApps](https://preview.web.powerapps.com/home) och gå till den miljö som du skapade i steg 2.
    2. Välj **Enheter**. Markera ellipsknapen till höger på sidan (**...**) och välj sedan **Rensa alla data**.
    3. Välj **Ta bort data** för att bekräfta att du vill ta bort dina data. Denna åtgärd tar bort alla demodata som ingår i CDS som standard. Den tar också bort alla andra data som har angetts i den valda databasen.

Du kan nu använda den nya miljön.

