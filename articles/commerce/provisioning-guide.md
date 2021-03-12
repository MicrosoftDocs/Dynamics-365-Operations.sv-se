---
title: Etablera en bedömningsmiljön för Dynamics 365 Commerce
description: Det här avsnittet förklarar hur du etablerar en bedömningsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8cda79a6be1aca7ad3826b9409e110524e6560e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969911"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Etablera en bedömningsmiljön för Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Det här avsnittet förklarar hur du etablerar en bedömningsmiljö för Microsoft Dynamics 365 Commerce.

Innan du börjar rekommenderar vi att du tar en snabbgenomgång genom det här avsnittet för att få en uppfattning om vad processen kräver.

> [!NOTE]
> Commerce bedömningsmiljöer är i allmänhet inte tillgängliga och ges till partners och kunder för varje enskild begäran. För mer information, kontakta din Microsoft-partnerkontakt.

## <a name="overview"></a>Översikt

För att kunna etablera din bedömningsmiljö för Commerce måste du skapa ett projekt som har ett specifikt produktnamn och en viss typ. Miljön och Commerce Scale Unit (CSU) har även del specifika parametrar som du måste använda för att kunna förvänta dig att etablera näthandel senare. Instruktionerna i det här avsnittet beskriver alla nödvändiga steg för att slutföra etablering och de parametrar som du måste använda.

När du har tillhandahållit din bedömningsmiljö för Commerce måste du slutföra några steg efter etablering för att förbereda den. Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera. Du kan alltid slutföra de valfria stegen senare.

Information om hur du konfigurerar bedömningsmiljö för Commerce efter att du har konfigurerat den finns i [Konfigurera en bedömningsmiljö för Commerce](cpe-post-provisioning.md). Information om hur du konfigurerar valfria funktioner för din Commerce bedömningsmiljö finns i [Konfigurera valfria funktioner för bedömningsmiljö för Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara på plats innan du kan etablera din bedömningsmiljö för Commerce:

- Du har tagit med i bedömningsprogrammet och beviljats kapacitet för en bedömningsmiljö.
- Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).
- Du är en befintlig Microsoft Dynamics 365-partner eller kund och kan skapa ett Dynamics 365 Commerce-projekt.
- Du har administratörsåtkomst till din Microsoft Azure prenumeration, eller så har du kontakt med en prenumerationsadministratör som kan hjälpa dig om det behövs.
- Du har ditt Azure Active Directory (Azure AD) innehavar-ID tillgängligt.
- Du har skapat en Azure AD-säkerhetsgrupp som kan användas som en systemadministratörsgrupp för näthandel och du har dess ID tillgängligt.
- Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt. (Den här säkerhetsgruppen kan vara samma som administratörsgruppen för näthandelssystem.)

Observera att listan inte är uttömmande. Om du har problem kontakta din Microsoft-partnerkontakt för hjälp.

## <a name="provision-your-commerce-evaluation-environment"></a>Etablera en bedömningsmiljö för Commerce

Dessa procedurer förklarar hur du etablerar en bedömningsmiljö för Commerce. När du har slutfört dem kommer bedömningsmiljö för Commerce att vara redo för konfigurering. Alla aktiviteter som beskrivs här utförs i LCS-portalen.

### <a name="create-a-new-project"></a>Skapa ett nytt projekt

Om du vill skapa ett nytt projekt i LCS, följ dessa steg:

1. På LCS-startsidan väljer du plustecknet (**+**) för att skapa ett projekt.
1. I den högra rutan följer du något av följande steg:

    - Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.
    - Om du är kund väljer du **Potentiella försäljningar**.

1. Ange ett namn, beskrivning och bransch.
1. I fältet **Produktnamn** välj **Dynamics 365 Commerce**.
1. I fältet **Produktversion** välj **Dynamics 365 Commerce**.
1. Fältet **Metod**, välj **Dynamics Retail implementeringsmetod**.
1. Valfritt: Du kan importera roller och användare från ett befintligt projekt.
1. Markera **Skapa**. Projektvyn visas.

### <a name="add-the-azure-connector"></a>Lägg till Azure-koppling

Om du vill lägga till Azure-anslutaren i LCS-projektet följer du stegen i [slutföra registreringsprocessen för Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).

### <a name="deploy-the-environment"></a>Distribuera miljö

Följ dessa steg för att distribuera miljön.

> [!NOTE]
> Du kanske inte behöver slutföra steg 6, 7 och/eller 8, eftersom sidor som har ett enda alternativ hoppas över. När du är i vyn **Miljöparametrar** bekräfta att texten **Dynamics 365 Commerce – Demo (10.0.* x* med plattformsuppdatering *xx*)** visas direkt ovan fältet **Miljönamn**. För mer information, se illustrationen som visas efter steg 8.

1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Klicka på **Lägg till** om du vill lägga till en miljö.
1. I fältet **Programversion** väljer du den mest aktuella versionen. Om du har ett specifikt behov av att välja en annan programversion än den senaste versionen ska du inte välja en version före **10.0.14**.
1. I fältet **plattformsversion** använder du den plattformsversion som väljs automatiskt för den valda programversionen. 

    ![Välj program- och plattformsversioner](./media/project1.png)

1. Välj **Nästa**.
1. Välj **Demo** som miljötopologi.

    ![Välja miljötopologi 1](./media/project2.png)

1. Ange ett **miljönamn** på sidan distribuera miljö. Lämna Avancerade inställningar som de är.

    ![Sidan Distribuera miljö](./media/project4.png)

1. Justera VM-storlek som krävs. (Vi rekommenderar VM lagerhållningsenhet \[SKU\]**D13 v2**.)
1. Granska prissättnings- och licensvillkoren och markera sedan kryssrutan för att ange att du godkänner dem.
1. Välj **Nästa**.
1. På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**. Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.

    Den begärda miljön visas som en kö och distribueras sedan. Miljöarbetsflödena kommer att ta lite tid att slutföras. Kontrollera därför tillbaka efter ungefär sex till nio timmar.

1. Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Initiera Commerce Scale Unit (moln)

Gör så här om du vill initiera CSU:n.

1. Välj din miljö i listan **Molnstyrda miljöer**.
1. Välj i miljövyn till höger **Fullständig information**. Vyn miljöinformation visas.
1. Under **Miljöfunktioner**, välj **hantera**.
1. På fliken **Commerce**, välj **Initiera**. Parametervyn CSU-initiering visas.
1. I fältet **Region** väljer du den region som är densamma eller nära den region som du har distribuerat miljön till.
1. Lämna fältet **Version** tomt.
1. Välj **initiera**.
1. På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**. Vyn **Hantering av handel** visas igen, där fliken **Commerce** väljs. Din CSU har ställts i kö för etablering.
1. Innan du fortsätter bör du kontrollera att status för din CSU är **Lyckades**. Initieringen tar ungefär två till fem timmar.

Om du inte hittar länken **hantera** i vyn miljödetaljer kontaktar du din Microsoft-kontakt för att få hjälp.

Följande felmeddelande kan visas under distributionsprocessen:

> Bedömnings(demo-/test)miljöer måste registrera anslutningsprogrammet för skalningsenhet \<application ID\> i administrationen.

Om CSU-initialiseringen misslyckas och du får det här felmeddelandet, noterar du program-ID:t (som är en global unik identifierare, GUID) och följer sedan stegen i nästa avsnitt om du vill registrera CSU-distribueringsprogrammet i Commerce-administrationen.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Registrera CSU-distribueringsprogrammet i Commerce-administrationen (vid behov)

Följ dessa steg om du vill registrera CSU-distribueringsprogrammet i Commerce-administrationen.

1. I Commerce-administrationen går du till **Systemadministration \> Inställningar \> Azure Active Directory-program**.
1. I kolumnen **Klient-ID** anger du program-ID:t från det CSU-initieringsfelmeddelande som du har fått.
1. Ange eventuell beskrivande text i kolumnen **Namn** (t. ex. **CSU Eval**).
1. I kolumnen **Användar-ID** anger du **RetailServiceAccount**.
1. Försök att initiera CSU igen och distribuera från LCS.

### <a name="initialize-e-commerce"></a>Initiera näthandelsplattform

Gör så här om du vill initiera näthandel.

1. Granska medgivande för utvärdering på fliken **näthandel** och välj sedan **inställningar**.
1. I fältet **miljönamn för näthandel**, ange ett namn. Tänk på att det här namnet kommer att visas i några av webbadresserna som pekar mot din näthandelsinstans.
1. I fältet **Namn på Commerce Scale Unit** välj din CSU i listan. (Listan bör bara ha ett alternativ.)

    Fältet **geografi för näthandel** ställs in automatiskt.

1. Klicka på **Nästa** när du vill fortsätta.
1. I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.
1. I fältet **AAD-säkerhetsgruppen för systemadministratör**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten. Välj korrekt säkerhetsgrupp i listan.
1.  I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten. Välj korrekt säkerhetsgrupp i listan.
1. Lämna alternativet **tjänsten aktivera klassificering och granska** till **Ja**.
1. Välj **initiera**. Vyn **Hantering av handel** visas igen, där fliken **näthandel** väljs. Initieringen av näthandel har påbörjats.
1. Innan du fortsätter väntar du tills initieringsstatus för näthandel är **initialisering har slutförts**.
1. Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:

    * **näthandelssajt** – länken till roten på din näthandelssajt.
    * **Commerce webbplatsskaparen** – länken till webbplatshanteringsverktyget.

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen med att tillhandahålla och konfigurera din bedömningsmiljö för Commerce, se [Konfigurera en bedömningsmiljö för Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Konfigurera en Dynamics 365 Commerce bedömningsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)

[Dynamics 365 Commerce bedömningsmiljö – vanliga frågor](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (moln)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)
