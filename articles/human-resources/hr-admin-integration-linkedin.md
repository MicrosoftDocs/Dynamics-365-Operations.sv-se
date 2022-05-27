---
title: Integration med LinkedIn Talent Hub
description: Det här avsnittet beskriver hur du ställer in integreringen mellan Microsoft Dynamics 365 Human Resources och LinkedIn Talent Hub.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d14a8cb1973e0ed55ef10ddb43415eba80eb5c1b
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717123"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integration med LinkedIn Talent Hub

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!IMPORTANT]
> Integrationen mellan och Dynamics 365 Human Resources och LinkedIn Talent Hub som beskrivs i det här avsnittet drogs tillbaka den 31 december 2021. Integrationstjänsten är inte längre tillgänglig efter det här datumet. Organisationer som inte redan använder integrationstjänsten kan inte implementera tjänsten innan den dras tillbaka.

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) är en plattform för sökningsspårningssystem (ATS). Med den kan du anskaffa, hantera och anställa medarbetare på samma ställe. Genom att integrera Microsoft Dynamics 365 Human Resources med LinkedIn Talent Hub kan du enkelt skapa medarbetarposter i Personal för de sökande som har anställts för en befattning.

## <a name="setup"></a>Ställ in

En systemadministratör måste slutföra installationsåtgärderna för att kunna integrera med LinkedIn Talent Hub. Först i Power Apps-miljön måste du ställa in en användar- och säkerhetsroll för att ge LinkedIn Talent Hub rätt behörighet att skriva data till Personal.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Länka din miljö till LinkedIn Talent Hub

1. Öppna [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. På listmenyn för användare väljer du **produktinställningar**.

3. I det vänstra navigeringsfönstret i avsnittet **Avancerat** välj **Integreringar**.

4. Välj **auktorisera** för Microsoft Dynamics 365 Human Resources-integrationen.

5. På sidan **Dynamics 365 Human Resources**, välj den miljö du vill länka LinkedIn Talent Hub till och välj sedan **Länka**.

    ![LinkedIn Talent Hub-registrering.](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Du kan bara länka till miljöer där ditt användarkonto har administratörsåtkomst till både Personal-miljön och den associerade Power Apps-miljön. Om det inte finns några miljöer på sidan Personal-länkar ser du till att du har licensierade Personal-miljöer på klientorganisationen och att användaren som du har loggat in på länksidan som har administratörsbehörighet för både Personal-miljön och Power Apps-miljön.

### <a name="create-a-power-apps-security-role"></a>Skapa en Power Apps säkerhetsroll

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer** väljer du den miljö som är kopplad till Personal-miljön som du vill länka din instans av LinkedIn Talent Hub till.

3. Välj **inställningar**.

4. Expandera noden **användare + behörigheter** och välj sedan **säkerhetsroller**.

5. På sidan **säkerhetsroller** i verktygsfältet, välj **Ny roll**.

6. På fliken **Detaljer** anger du ett namn på rollen, t.ex. **LinkedIn Talent Hub HRIS-integration**.

7. På fliken **Anpassning** väljer du behörighet **Läs** på organisationsnivå för följande entiteter:

    - Enhet
    - Fält
    - Förhållande

8. Spara och stäng säkerhetsrollen.

### <a name="create-a-power-apps-application-user"></a>Skapa en Power Apps appanvändare

En program användare måste skapas för LinkedIn Talent Hub för att bevilja behörighet till adaptern att skriva kandidatposter till Power Apps-miljön.

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer** väljer du den miljö som är kopplad till Personal-miljön som du vill länka din instans av LinkedIn Talent Hub till.

3. Välj **inställningar**.

4. Expandera noden **användare + behörigheter** och välj sedan **användare**.

5. Välj **Hantera användare i Dynamics 365**.

6. Använd den nedrullningsbara menyn ovanför listan för att ändra visningen av vyn standardinställda **användare** för **appanvändare**.

    ![Vyn Programanvändare.](./media/hr-admin-integration-power-apps-application-users.jpg)

7. I verktygsfältet klickar du på **Nytt**.

8. Gå till sidan **Ny användare** och följ dessa steg:

    1. Ändra värdet för fältet **Användartyp** till **Appanvändare**.
    2. Ange fältet **användarnamn** till **Dynamics365 HR LinkedIn HRIS-integration**.
    3. Ange fältet **App-ID** till **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Ange valfritt värde i fälten **Förnamn**, **Efternamn** och **Primär e-post**.
    5. I verktygsfältet, välj **Spara \& Stäng**.

### <a name="assign-a-security-role-to-the-new-user"></a>Tilldela den nya användaren en säkerhetsroll

När du har sparat och stängt den nya appanvändaren i föregående avsnitt, kommer du tillbaka till sidan **användarlista**.

1. På sidan **Användarlista** ändra vyn till **appanvändare**.

2. Välj den appanvändare som du skapade i det föregående avsnittet.

3. Välj **hantera roller** i verktygsfältet.

4. Välj den säkerhetsroll som du skapade tidigare för integrationen.

5. Välj **OK**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Lägg till en Azure Active Directory-app i Personal

1. I Dynamics 365 Human Resources, öppna sidan **Azure Active Directory-appar**.
2. Lägg till en ny post till listan och ange följande fält:

    - **Klient-ID**: ange **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Namn**: Ange namnet på den Power Apps säkerhetsroll som du skapade tidigare, t.ex. **LinkedIn Talent Hub HRIS-integration**.
    - **Användar-ID**: Välj en användare som har behörighet att skriva data i personalhantering.

### <a name="create-the-table-in-dataverse"></a>Skapa tabellen i Dataverse

> [!IMPORTANT]
> Integreringen med LinkedIn Talent Hub vilar på virtuella register i Dataverse för Personal. Som en förutsättning för det här steget i konfigurationen måste du konfigurera virtuella register. Mer information om hur du konfigurerar virtuella register finns i [Konfigurera virtuella Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md).

1. I Personal öppnar du sidan **Dataverse-integrering**.

2. Välj fliken **Virtuella register**.

3. Filtrera enhetslistan efter enhetsetikett för att hitta **LinkedIn-exporterad kandidat**.

4. Välj den entiteten och välj sedan **generera/uppdatera**.

## <a name="exporting-candidate-records"></a>Exportera kandidatposter

När installationen är klar kan rekryterare och HR-personal använda funktionen **Exportera till HRIS** i LinkedIn Talent Hub för att exportera anställda sökandeposter från LinkedIn Talent Hub till Personal.

### <a name="export-records-from-linkedin-talent-hub"></a>Exportera poster från LinkedIn Talent Hub

När en kandidat har gått igenom rekryteringsprocessen och har anställts kan du exportera kandidatposten från LinkedIn Talent Hub till Personal.

1. På LinkedIn Talent Hub öppnar du projektet som du har anställt den nya medarbetaren för.

2. Välj en kandidatpost.

3. Välj **Ändra fas** och välj sedan **Anställd**.

4. På ellips-menyn (**...**) för kandidaten väljer du **Exportera till HRIS**.

5. I fönstret **Exportera till HRIS** ange informationen som måste exporteras:

    - I fältet **HRIS-leverantör** väljer du **Microsoft Dynamics 365 Human Resources**.
    - I fältet **startdatum** välj ett värde för den nya anställda.
    - I fältet **jobbtitel**, ange en jobbtitel för den nya medarbetarens jobb.
    - I fältet **plats** anger du den plats där medarbetaren ska baseras.
    - Ange eller verifiera medarbetarens e-postadress.

![Exportera till HRIS-fönstret i LinkedIn Talent Hub.](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Slutföra registrering i Personal

Kandidatposter som exporteras från LinkedIn Talent Hub till Personal visas i avsnittet **kandidater att anställa** på sidan **personalhantering**.

1. I Personal, öppna listsidan **personalhantering**.

2. I avsnittet **kandidater att anställa** väljer du **anställa** för den valda kandidaten.

3. I dialogrutan **Anställ ny medarbetare** granskar du posten och lägger till nödvändig information. Du kan också välja positionsnumret som kandidaten har anställts för.

När den information som krävs har angetts kan du fortsätta med dina standardprocesser för att skapa medarbetarposter och registrera medarbetare.

Följande information importeras och inkluderas i den nya medarbetarposten:

- Förnamn
- Efternamn
- Startdatum för anställning
- E-postadress
- Telefonnummer

## <a name="see-also"></a>Se även

[Konfigurera virtuella Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
