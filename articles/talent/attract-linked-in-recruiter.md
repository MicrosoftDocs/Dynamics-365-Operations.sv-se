---
title: Anskaffning med LinkedIn-rekryterare
description: "Det här avsnittet innehåller information om hur du använder maskininlärning för att få rekommendationer om jobb och jobbkandidater."
author: josaw
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 9bb323728923ff3b09ff0bfba3849f3c5d84eb34
ms.contentlocale: sv-se
ms.lasthandoff: 12/07/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a>Anskaffning med LinkedIn-rekryterare
[!include[banner](../includes/banner.md)]

LinkedIn är världens största talangdatabasen och ofta det primära systemet som rekryterare använder för att hitta, kommunicera med och anskaffa kandidater till de jobb som rekryterarna vill fylla. Integration av LinkedIn-rekryterare med Dynamics 365 for Talent: Attract gör det enklare för användarna att anställa och synkronisera data mellan de två systemen.

> [!NOTE]
> Du behöver tillägg för omfattande anställning och LinkedIn-rekryterarplatser för att kunna använda integration av LinkedIn-rekryteraren med Attract.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Ställ in LinkedIn-rekryteraren med Attract 

Innan du kan använda funktionerna i LinkedIn-rekryteraren måste du konfigurera åtkomst på kontrakt- eller företagetsnivå med din Attract-instans. För att slutföra konfigurationsprocessen måste du samarbeta med användare är en administratör i ditt LinkedIn-rekryterarkontrakt. Gör följande steg om du vill konfigurera LinkedIn-rekryteraren med Attract.

1.  Logga in på Attract som en administratör och gå till **administrationsinställningar**.

2.  I vänster fönster klickar du på fliken **LinkedIn-integration**.

[![Attract Admin-vy för att starta integration med LinkedIn-rekryteraren](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Klicka på **Anslut** för att starta installation och få vägledning genom LinkedIn-inloggningsprocessen.

4.  Om du har platser på flera LinkedIn-kontrakt markerar du kontraktet som du vill ansluta till Attract-systemet. Om du har en plats i ett enda LinkedIn-kontrakt behövs inte det här steget.

5.  LinkedIn-widgeten laddas nu i Admin-inställningarna med en lista över integrationer. Under **Recruiter System Connect**, klickar du på **begära**.

[![Attract Admin-vy för att begära integration med LinkedIn-rekryteraren](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  När integrationen begärs från Attract visas den som **Partner-klar** och kan aktiveras från **Rekryterarens administratörsinställningar**. Om du vill se **meddela partner** vänta några sekunder på den här sidan, klicka på **meddela partner** och uppdatera sedan sidan. Den ska nu visa **Partner-klar**.

[![Attract Admin-vy om du vill visa att Attract-sidan av begäranden har slutförts](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Du måste ha behörigheten Admin i LinkedIn-rekryterarens kontrakt för att slutföra nästa steg.

7.  Logga in på LinkedIn med administratörskontot och gå till LinkedIn-rekryteraren längst upp till höger. 

8. I menyn **mer** längst upp på skärmen, klickar du på **administrationsinställningar**, och klickar sedan på fliken **ATS**.

Attract-systemet visas med två olika alternativ som kan aktiveras.

9. Om du vill aktivera endast 1 - klicka på exportera för **I ATS-indikatorn** och **I ATS-profilwidget**, markera **åtkomst på företagsnivå**. Välj om du vill aktivera alla funktioner för åtkomst på företagsnivå plus åtkomst för InMail-historik, anteckningshistorik och InMail stub-profil, välj **Åtkomst på kontraktnivå**.

10. Aktivera önskad åtkomstnivå från din LinkedIn-rekryterarens **Admin ATS**-inställningar.

[![Aktivera Attract-integration från LinkedIn-rekryterarens Admin-vy](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Gå tillbaka till Attract administrationsinställningar som en AttractAdmin och välj fliken **LinkedIn-integration**. Du bör se LinkedIn-widgeten som visar **aktiverad** med den valda åtkomstnivån aktiverad.

[![Integrering av LinkedIn-rekryterare klar](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Använda funktionerna för LinkedIn-rekryterare

När LinkedIn-rekryterarens funktioner har aktiverats av Attract Admin är den tillgänglig för anställande chefer och rekryterare. Om du vill använda de här funktionerna anslut ditt LinkedIn-konto under **användarinställningar**. Flera funktioner blir tillgängliga när både administratör och användare har anslutits.

### <a name="in-ats-profile-widget"></a>Profilwidget för I-ATS

Du kan visa kandidatens LinkedIn-profil i Attract. LinkedIn-widgeten visar kandidatens profil när ATS-informationen matchar LinkedIn-information för användarna.

Om du vill visa en profil, gå till kandidatens profil från ett jobb eller talangpool. I kandidatprofilen väljer du fliken **LinkedIn** och profilwidgeten läses in. Du kan också spara kandidaten till dina LinkedIn-rekryterarprojekt på den här sidan.
1. Den sökandes profil visas om LinkedIn hittar en match baserat på e-post och LinkedIn medlems-ID (exakt träff). Användaren har fortfarande ett alternativ för att länka/ta bort länk till profilen.

2. Om LinkedIn inte hittar kandidaten baserat på deras e-post eller medlems-ID, visas en lista över möjliga kandidatmatchningar baserat på sökande och användaren kan välja en av dem och länka profilen.  

3. Om LinkedIn inte hittar dem utifrån namnet kommer den returnera att ingen matchning hittades.

### <a name="1-click-export"></a>1-klick exportera 

Vid anskaffning av kandidater i LinkedIn kan 1-klick exportera kandidaten till jobb som för närvarande är öppna. Gör följande steg för en 1-klick export. Innan du utför de här stegen ska du kontrollera att har tilldelats rollen anställande chef eller rekryterare för jobbet och att jobbet har fasen **potentiell kandidat**.

1.  Skapa jobbet, tilldela lämpliga roller och aktivera jobbet.

2.  Navigera till LinkedIn-rekryteraren när jobbet har aktiverats.

3.  Hitta den kandidat som du söker efter och gå till deras profil.

4.  Använd jobbsökrutan i kontaktkortet, hitta jobbet med titeln eller jobb-id som aktiverades i Attract. Om du inte hittar jobbet klickar du på **ändra ATS** för att hitta rätt Attract-instans.

5. När jobbet är markerat klickar du på **exportera**. Kandidaten hämtas nu av Attract.

6.  Gå till Attract och öppna respektive jobb. Du hittar kandidaten som du just har exporterat i fasen **potentiella kandidater** för jobbet.

### <a name="in-ats-indicator"></a>Indikatorn I-ATS 

Genom att använda LinkedIn-rekryterare kan du följa upp om en kandidat har sökt andra jobb i organisationen, titta på när de är i olika faser i jobbansökningar och visa feedback och kommentarer från Attract i LinkedIn-rekryteraren.

1.  Öppna LinkedIn-rekryteraren och leta reda på kandidatprofilen som du söker efter.

2.  Bläddra nedåt i avsnittet **I-ATS** i kandidatens profil.

3.  Du kan använda denna widgeten för att visa all information om kandidaten som finns i Attract från LinkedIn-rekryterarens vy.

4.  Välj fliken **jobb och status** för att se jobb som de är en del av, senaste status och hur de har flyttat mot varje jobb.

5.  Välj fliken **intervjufeedback** för att se feedback som intervjuare har lämnat i Attract.

6.  Välj fliken **anteckningar** för att visa anteckningar som har hämtats för sökanden i Attract.

> [!NOTE]
> Kandidater och programdata synkroniseras inte med LinkedIn Recruiter om kandidaten inte har flyttats från fasen potentiell kandidat.

### <a name="inmail-history"></a>InMail-historik

LinkedIn InMail-historik finns i åtkomst på kontraktnivå med LinkedIn-rekryteraren. Om den är aktiverad måste visa hela InMail-historiken med kandidaten. Du kan också se vilka andra från din organisation som har utbytt InMail med kandidaten, men du inte kan visa meddelanden mellan dem..

För att historik för InMail, gå till kandidatens profil, gå till fliken **LinkedIn** och bläddra till slutet på sidan för att visa historik. Du kan visa InMail-historik om du har haft en diskussion med kandidaten. Meddelanden från InMail synkroniseras med Attract varannan timme.

### <a name="notes-history"></a>Anteckningshistorik 

LinkedIn anteckningshistorik finns i åtkomst på kontraktnivå med LinkedIn-rekryteraren. När den är aktiverad kan du visa anteckningar som har gjorts om kandidaten av olika rekryterare från organisationen.

För att historik för anteckningar, gå till kandidatens profil, gå till fliken **LinkedIn** och bläddra till slutet på sidan för att visa historik. Du kan visa alla anteckningar om kandidaten från LinkedIn-rekryteraren.

### <a name="inmail-stub-profile"></a>InMail stub-profil

LinkedIn InMail stub-historik finns i åtkomst på kontraktnivå med LinkedIn-rekryteraren. Om kandidater enas om att deras LinkedIn-profiler delas med alla användare i organisationen, kan du spåra kandidater i Attract och en ny kandidatpost skapas för varje kandidat. Du kan visa kandidatens e-postadress om kandidaten redan finns i systemet med en e-postadress eller delat adressen med rekryteraren.

Om du vill visa listan med kandidater, gå till **talangpooler** för att se en systemskapad LinkedIn talangpool. Den här talangpoolen innehåller listan av kandidater och deras stub-profiler som fås från LinkedIn och som visar kandidatens förnamn och efternamn. Kandidatens e-post-ID visas om kandidaten har delat sin e-postadress.

