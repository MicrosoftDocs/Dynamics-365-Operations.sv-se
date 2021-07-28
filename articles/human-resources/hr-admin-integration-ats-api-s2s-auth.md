---
title: Autentisering mellan servrar för API:t för ATS-integrering
description: Detta ämne beskriver hur du ställer in autentisering mellan servrar för integreringar mot Dynamics 365 Human Resources-API:t för sökandespårningssystem (ATS).
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ed76d22ab6b917c931220f3ba462f4f14cae207
ms.sourcegitcommit: bd684c9eb6de718573e6be5479e1832fe614d919
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "6373071"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Autentisering mellan servrar för API:t för ATS-integrering

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver hur du konfigurerar autentisering mellan servrar för programintegreringar mot Dynamics 365 Human Resources-API:t för sökandespårningssystem (ATS). Det finns ett par säkerhetsskikt som måste hanteras för att tjänstens huvudman ska kunna få åtkomst till den virtuella Microsoft Dataverse-tabellen och tillhörande data. Användaren måste beviljas åtkomst till den virtuella Dataverse-tabellen i Microsoft Power Platform samt till datan i Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Aktivera åtkomst till virtuella Dataverse-tabeller i Power Platform

Det första steget till att ge åtkomst till de virtuella Dataverse-tabellerna i Power Platform är att konfigurera ditt program i Power Platform för autentisering mot slutpunkter i virtuella Dataverse-tabeller. Stegen för detta beskrivs i [Microsoft Dataverse-utvecklarguiden](/powerapps/developer/data-platform).

  - För appregistreringar med en enda innehavare: [Använd autentisering mellan servrar för en enda användare](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - För appregistreringar med flera innehavare: [Använd autentisering mellan servrar för flera användare](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Skapa en säkerhetsroll för ATS-integreringar

Ett av stegen efter att programanvändaren har skapat detta är att tilldela användaren en säkerhetsroll som definierar programmets åtkomst till slutpunkterna. Detta är steg 7 i [Skapa programanvändare](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) för appregistreringar för en enda användare samt [Skapa en säkerhetsroll för programanvändaren](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) för registreringar med flera klientorganisationer. 

Den roll som du tilldelar programanvändaren ska ha åtkomst till de dataenheter som används för din ATS-integration. Denna finns inte vid leverans, varför en ny säkerhetsroll skapas måste. Den nya rollen kan skapas enligt stegen som anges i [Skapa en säkerhetsroll](/power-platform/admin/create-edit-security-role#create-a-security-role).

För den nya rollen måste du åtminstone tilldela lämplig åtkomst till följande entiteter på fliken **Anpassade enheter** för den nya rollen. Observera att det kan finnas ytterligare entiteter som du kan behöva lägga till om integreringen använder mer omfattande programdata. När den nya rollen har skapats kan den tilldelas till programanvändaren.

  - Basmedarbetare (mshr)
  - Kandidat att anställa (mshr)
  - Certifikatskompetens (mshr)
  - Certifikattyp (mshr)
  - Företag
  - Kompensationsjobbfunktion (mshr)
  - Kompensationsjobbtyp (mshr)
  - Land/regioner (mshr)
  - Avdelning (mshr)
  - Utbildningskompetens (mshr)
  - Examina (mshr)
  - Utbildningsdiscipliner (mshr)
  - Utbildningsmässiga krav (mshr)
  - Identifiering (mshr)
  - Identifieringstyp (mshr)
  - Institution (mshr)
  - Utfärdande organ (mshr)
  - Jobbkompensation (mshr)
  - Jobb (mshr)
  - Utbildningsnivå (mshr)
  - Partens kontakter (mshr)
  - Personer (mshr)
  - Privata adresser (mshr)
  - Personkontroll (mshr)
  - Befattningstyp (mshr)
  - Befattningar V2 (mshr)
  - Yrkeserfarenhetskompetens (mshr)
  - Bedömningsnivå (mshr)
  - Bedömningsmodeller (mshr)
  - Orsakskoder (mshr)
  - Rekryteringsbegäran (mshr)
  - Plats för rekryteringsbegäran (mshr)
  - Befattning för rekryteringsbegäran (mshr)
  - Färdigheter för rekryteringsbegäran (mshr)
  - Kontrolltyp (mshr)
  - Färdighetskompetens (mshr)
  - Färdigheter (mshr)
  - Titlar (mshr)
  - Veteranstatus (mshr)
  - Medarbetare (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Bevilja programbehörighet för personaldata

Syftet med det andra steget är att säkerställa att programmet beviljas rätt behörighet till data i Personal genom att koppla det till en användare i programmet Personal. För en programanvändare görs anropen från server till server via virtuella Dataverse-tabeller i kontexten för användarens identitet (app) i Dataverse som genererat åtgärden. Den virtuella tabelladaptertjänsten söker sedan upp den associerade användaren i Personal och kör frågan i samband med användaren. Detta innebär att en användare måste skapas i Personal med de korrekta rollerna tilldelade för att ge åtkomst till de data som integrationsprogrammet behöver.

Personalanvändaren måste också tilldelas rätt behörighet till data i Personal. Rollen **Rekryteringsprogram** (HcmRecruitingIntegrator) finns tillgänglig med privilegier till de primära entiteter som krävs för integrering med rekryteringsdata. Denna rollen kan tilldelas programanvändaren på sidan **Användare** i syfte att bevilja lämplig åtkomst till datan. Mer information om säkerhetsroller för Personal finns i [Rollbaserad säkerhet](/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Ställ in den nya användaren med lämpliga behörigheter

Följ dessa steg för att konfigurera den nya användaren med lämpliga behörigheter:

  1. Öppna sidan **Användare** i Personal och välj **Ny**.
  2. Ange ett **Användar-ID** och ett **Användarnamn** för den nya programanvändaren. Du kan till exempel ange "Rekryteringsintegrering".

      > [!NOTE]
      > Om programmet inte har något Microsoft Azure Active Directory (Azure AD)-användarkonto eller tillhörande e-postadress kan du ange exempelvis "RecruitingApp" i användarfälten för e-postadress och leverantör.

  3. På snabbfliken **Användarens roller** väljer du åtgärden **Tilldela roller**.
  4. I fönstret **Tilldela roller till användare** väljer du **Rekryteringsansökan** och sedan **OK**.
  5. Spara den nya användarposten.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Koppla den nya Personal-användaren till programmet

När användaren har skapats måste en post skapas för programmet i formuläret **Azure Active Directory-program** om du vill koppla programmet till Personalanvändaren.

  1. Öppna formuläret **Azure Active Directory-program** och välj **Ny**.
  2. I fältet **Klient-ID** anger du klient-ID för den programanvändare som skapats för programmet.
  3. I fältet **Namn** anger du namnet på integreringsprogrammet.
  4. I fältet **Användar-ID** väljer du den nya Personalanvändare som skapats för rekryteringsintegreringen.
  5. Spara den nya posten.

Programmet får då tillgång till Personaldata, som endast begränsas till den information som krävs för rekrytering av programintegreringar.

## <a name="see-also"></a>Se även

[Rekrytera jobbkandidater](hr-personnel-recruit.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Använd webb-API för Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Skapa och uppdatera alternativuppsättningar med hjälp av webb-API:t](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
