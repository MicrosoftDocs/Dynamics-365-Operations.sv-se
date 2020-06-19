---
title: Etablera en Dynamics 365 Commerce förhandsversionsmiljö
description: Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 06/02/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c109c2326cf01739255b49587c15aa34ad884f6a
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426475"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Etablera en Dynamics 365 Commerce förhandsversionsmiljö


[!include [banner](includes/banner.md)]

Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Dynamics 365 Commerce.

Innan du börjar rekommenderar vi att du tar en snabbgenomgång genom det här avsnittet för att få en uppfattning om vad processen kräver.

> [!NOTE]
> Om du inte har beviljats åtkomst till förhandsgranskning för Dynamics 365 Commerce kan du begära förhandsgranskningsåtkomst från [Dynamics 365 Commerce webbplats](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Översikt

För att kunna etablera din förhandsversionsmiljö för Commerce måste du skapa ett projekt som har ett specifikt produktnamn och en viss typ. Miljön och Commerce Scale Unit (CSU) har även del specifika parametrar som du måste använda för att kunna etablera e-handel senare. Instruktionerna i det här avsnittet beskriver alla nödvändiga steg för att slutföra etablering och de parametrar som du måste använda.

När du har tillhandahållit din förhandsversionsmiljö för Commerce måste du slutföra några steg efter etablering för att förbereda den. Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera. Du kan alltid slutföra de valfria stegen senare.

Information om hur du konfigurerar förhandsversionsmiljö för Commerce efter att du har konfigurerat den finns i [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md). Information om hur du konfigurerar valfria funktioner för Commerce efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för förhandsversionsmiljö för Commerce](cpe-optional-features.md).

Om du har frågor om etableringsstegen eller om du stöter på problem ska du tala om för Microsoft i [Microsoft Dynamics 365 Commerce förhandsgranskning Yammer-grupp](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara på plats innan du kan etablera din förhandsversionsmiljö för Commerce:

- Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).
- Du är en befintlig Microsoft Dynamics 365-partner eller kund och kan skapa ett Dynamics 365 Commerce-projekt.
- Du har accepterats i Dynamics 365 Commerce förhandsgranskningsprogrammet.
- Du har de behörigheter som krävs för att skapa ett projekt för **Migrera, skapa lösningar och lär dig**.
- Du är rollen **Miljöhanterare** eller **Projektägare** i projektet där du ska etablera miljön
- Du har administratörsåtkomst till din Microsoft Azure-prenumeration eller kontakta en prenumerationsadministratör som kan slutföra de två steg som kräver administratörsbehörighet för din räkning
- Du har ditt Azure Active Directory (Azure AD) innehavar-ID tillgängligt.
- Du har skapat en Azure AD-säkerhetsgrupp som kan användas som en systemadministratörsgrupp för e-handel och du har dess ID tillgängligt.
- Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt. (Den här säkerhetsgruppen kan vara samma som administratörsgruppen för e-handelssystem.)

## <a name="provision-your-commerce-preview-environment"></a>Etablera en förhandsversionsmiljö för Commerce

Dessa procedurer förklarar hur du etablerar en förhandsversionsmiljö för Commerce. När du har slutfört dem kommer förhandsversionsmiljö för Commerce att vara redo för konfigurering. Alla aktiviteter som beskrivs här utförs i LCS-portalen.

> [!IMPORTANT]
> Förhandsgranskningsåtkomsten är knuten till LCS-kontot och organisationen som du angav i förhandsgranskningsprogrammet för Handel. Du måste använda samma konto för att etablera förhandsversionsmiljö för Commerce. Om du måste använda ett annat LCS-konto eller en innehavare för förhandsversionsmiljö för Commerce måste du ange dessa uppgifter för Microsoft. Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare i det här ämnet.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS

För att bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS.

1. Logga in på [LCS-portalen](https://lcs.dynamics.com) med hjälp av samma LCS-konto som du använde för att begära åtkomst till förhandsgranskningen.
1. Rulla hela vägen till höger på LCS-startsida och klicka på panelen för **Hantering av förhandsgranskningsfunktioner**.

    ![Panel för förhandsgranskningsfunktion](./media/preview1.png)

1. Rulla ned till **Privata förhandsgranskningsfunktioner** och se till att följande funktioner är tillgängliga och aktiverade:

    - Utvärdering av e-handel
    - Miljöer för förhandsgranskningsprogram

    ![Privata förhandsgranskningsfunktioner](./media/preview2.png)

1. Om dessa funktioner inte visas i listan kan du kontakta Microsoft och ange din e-postadress för arbete, LCS-konto och klientinformation. Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare.

### <a name="create-a-new-project"></a>Skapa ett nytt projekt

Om du vill skapa ett nytt projekt i LCS, följ dessa steg:

1. På LCS-startsidan väljer du plustecknet (**+**) för att skapa ett projekt.
1. I den högra rutan följer du något av följande steg:

    - Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.
    - Om du är kund väljer du **Potentiella försäljningar**.

1. Ange ett namn, beskrivning och bransch.
1. I fältet **Produktnamn** välj **Dynamics 365 Retail**.
1. I fältet **Produktversion** välj **Dynamics 365 Retail**.
1. Fältet **Metod**, välj **Dynamics Retail implementeringsmetod**.
1. Valfritt: Du kan importera roller och användare från ett befintligt projekt.
1. Markera **Skapa**. Projektvyn visas.

### <a name="add-the-azure-connector"></a>Lägg till Azure-koppling

Så här lägger du till Azure Connector i ditt LCS-projekt.

1. Gör något av följande:

    - Om du är en partner väljer du panelen **Projektinställningar** längst till höger.
    - Om du är kund väljer du **projektinställningar** på huvudmenyn.

1. Välj **Azure-kopplingar**.
1. Klicka på **+ Lägg till** om du vill lägga till Azure-koppling.
1. Ange ett namn.
1. Ange ditt Azure prenumerations-ID.
1. Aktivera alternativet **Konfigurera för att använda Azure Resource Manager (ARM)**.
1. Kontrollera att värdet **Azure-abonnemangets AAD-innehavardomän (eller ID)** är korrekt. Kontakta din Azure abonnemangsadministratör om det behövs.
1. Välj **Nästa**.
1. Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration. Kontakta din Azure abonnemangsadministratör om det behövs.

    1. Logga in på [Azure-portal](https://portal.azure.com/).
    1. Kontrollera att rätt katalog är markerad och välj sedan **prenumerationer** på menyn till vänster.
    1. Leta rätt på den korrekta prenumerationen i listan och markera den. Använd sökfunktionen efter behov.
    1. Välj **åtkomstkontroll (IAM)** på menyn.
    1. Till höger under **Lägg till** välj **Lägg till**. Fönstret **Lägg till rolltilldelning** visas.
    1. I fältet **Roll**, välj **Deltagare**.
    1. I fältet **Tilldela åtkomst till**, lämna standardvärdet **Azure AD användare, grupp eller Service Principals**.
    1. Under **Välj**, anger du **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Välj **Dynamics distributionstjänst \[wsfed-enabled\]** i listan.
    1. Välj **Spara**.

1. Välj **Nästa**.
1. Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration. Kontakta din Azure abonnemangsadministratör om det behövs.
1. Välj **Nästa**.
1. I fältet **Azure-region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.
1. Välj **Anslut**. Din Azure-koppling ska visas i listan.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importera Commerce-förhandsgranskning demo bastillägg

Så här importerar du Commerce-förhandsgranskning demo bastillägg till ditt projekt.

1. Öppna projektets startsida genom att välja projektnamnet överst.
1. Gör något av följande:

    - Om du är en partner väljer du panelen **Tillgångsbibliotek** längst till höger.
    - Om du är kund väljer du **Tillgångsbibliotek** på huvudmenyn.

1. I listan till vänster, välj **Distribuerbart programpaket**.
1. Välj **Importera**.
1. Under **Delat tillgångsbibliotek**, välj **Commerce-förhandsgranskning demo bastillägg** från listan med tillgångar.
1. Välj **Plocka**. Du kommer att returneras till tillgångsbiblioteket och du bör se filnamnstillägget i listan.

Följande illustration visar de åtgärder som måste vidtas på sidan LCS **tillgångsbibliotek**.

![Importera Commerce-förhandsgranskning demo bastillägg](./media/import.png)

### <a name="deploy-the-environment"></a>Distribuera miljö

Följ dessa steg för att distribuera miljön.

> [!NOTE]
> Du kanske inte behöver slutföra steg 6, 7 och/eller 8, eftersom sidor som har ett enda alternativ hoppas över. När du är i vyn **Miljöparametrar** bekräfta att texten **Dynamics 365 Commerce - Demo (10.0.* x* med plattformsuppdatering *xx*)** visas direkt ovan fältet **Miljönamn**. För mer information, se illustrationen som visas efter steg 8.

1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Klicka på **Lägg till** om du vill lägga till en miljö.
1. I fältet **Programversion** väljer du den mest aktuella versionen. Om du har ett specifikt behov av att välja en annan programversion än den senaste versionen ska du inte välja en version före **10.0.8**.
1. I fältet **plattformsversion** använder du den plattformsversion som väljs automatiskt för den valda programversionen. 

    ![Välj program- och plattformsversioner](./media/project1.png)

1. Välj **Nästa**.
1. Välj **Demo** som miljötopologi.

    ![Välja miljötopologi 1](./media/project2.png)

1. Välj **Dynamics 365 Commerce - Demo** som miljötopologi. Om du konfigurerade en enda Azure-koppling tidigare kommer den att användas i den här miljön. Om du har konfigurerat flera Azure-kopplingar kan du välja vilken koppling som: **Östra USA**, **Östra USA 2**, **Västra USA** eller **Västra USA 2**. (För bästa slutpunkt till slutpunkt-prestanda rekommenderar vi att du väljer **Västra USA 2**.)

    ![Välja miljötopologi 2](./media/project3.png)

1. Ange ett **miljönamn** på sidan distribuera miljö. Lämna Avancerade inställningar som de är.

    ![Sidan Distribuera miljö](./media/project4.png)

1. Justera VM-storlek som krävs. (Vi rekommenderar VM lagerhållningsenhet \[SKU\]**D13 v2**.)
1. Granska prissättnings- och licensvillkoren och markera sedan kryssrutan för att ange att du godkänner dem.
1. Välj **Nästa**.
1. På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**. Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.

    Den begärda miljön visas som en kö och distribueras sedan. Miljöarbetsflödena kommer att ta lite tid att slutföras. Kontrollera därför tillbaka efter ungefär sex till nio timmar.

1. Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Initiera Commerce Scale Unit (moln)

Gör så här om du vill initiera en CSU.

1. Välj din miljö i listan **Molnstyrda miljöer**.
1. Välj i miljövyn till höger **Fullständig information**. Vyn miljöinformation visas.
1. Under **Miljöfunktioner**, välj **hantera**.
1. På fliken **Handel**, välj **Initiera**. Parametervyn CSU-initiering visas.
1. I fältet **Region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.
1. I fältet **version** väljer du **ange en version** i listan och anger sedan **9.18.20014.4** i fältet som visas. Var noga med att ange den exakta versionen som anges här. I annat fall måste du uppdatera RCSU till rätt version senare.
1. Aktivera alternativet **Använd tillägg**.
1. Från listan över tillägg, välj **Handelsförhandsgranskning demobastillägg**.
1. Välj **initiera**.
1. På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**. Vyn **Hantering av handel** visas igen, där fliken **Handel** väljs. Din CSU har ställts i kö för etablering.
1. Innan du fortsätter bör du kontrollera att status för din CSU är **Lyckades**. Initieringen tar ungefär två till fem timmar.

### <a name="initialize-e-commerce"></a>Initiera e-handelsplattform

Gör så här om du vill initiera e-handel.

1. Granska medgivande för förhandsversion på fliken **e-handel** och välj sedan **inställningar**.
1. I fältet **E-handelsinnehavarens namn**, ange ett namn. Tänk dock på att det här namnet kommer att visas i några av webbadresserna som pekar på din e-handelsinstans.
1. I fältet **Namn på Commerce Scale Unit** välj din CSU i listan. (Listan bör bara ha ett alternativ.)

    Fältet **e-handelsgeografi** ställs in automatiskt och värdet kan inte ändras.

1. Klicka på **Nästa** när du vill fortsätta.
1. I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.
1.  I fältet **AAD säkerhetsgrupp för systemadministration**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda. Välj ikonen förstoringsglas för att visa sökresultaten. Välj korrekt säkerhetsgrupp i listan.
2.  I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda. Välj ikonen förstoringsglas för att visa sökresultaten. Välj korrekt säkerhetsgrupp i listan.
1. Lämna alternativet **tjänsten aktivera klassificering** aktiverat.
1. Välj **initiera**. Vyn **Hantering av handel** visas igen, där fliken **e-handel** väljs. Initieringen av e-handel har påbörjats.
1. Innan du fortsätter väntar du tills initieringsstatus för e-handel är **initialisering har slutförts**.
1. Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:

    * **e-handelsplats** – länken till roten på din e-handelsplats.
    * **e-handelsplats hanteringsverktyg** – länken till webbplatshanteringsverktyget.

## <a name="commerce-preview-environment-support"></a>Support för förhandsversionsmiljö för Commerce

Om du får problem när du slutför etableringsstegen kan du gå till [Microsoft Dynamics 365 Commerce förhandsversion Yammer-gruppen](https://aka.ms/Dynamics365CommercePreviewYammer) och be om hjälp.

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen med att tillhandahålla och konfigurera din förhandsgranskningsmiljö för Commerce, se [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce förhandsversionsmiljö – översikt](cpe-overview.md)

[Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurera valfria funktioner för en förhandsversionsmiljö för Dynamics 365 Commerce](cpe-optional-features.md)

[Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (moln)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)

