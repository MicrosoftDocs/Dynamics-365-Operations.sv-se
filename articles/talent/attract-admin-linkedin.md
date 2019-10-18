---
title: Konfigurera integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract
description: I det här avsnittet beskrivs hur du konfigurerar LinkedIn-integration för Microsoft Dynamics 365 Talent - Attract så att du enkelt kan publicera jobb till LinkedIn från Attract och så att dina rekryterare kan synkronisera sina rekryteringsuppgifter med en kandidats LinkedIn-profil.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 6b86cafdf364f2de051f3d8ceab7413c2c13c3a5
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009980"
---
# <a name="set-up-linkedin-integration"></a>Ställ in LinkedIn-integration

[!include[banner](../includes/banner.md)]

Hjälpa dina rekryterare och personalchefer att locka talanger genom att konfigurera LinkedIn-integration med Microsoft Dynamics 365 Talent: Attract. Attract låter dig publicera jobb direkt till LinkedIn, det största professionella nätverket online.

Jobb som du publicerar på LinkedIn via Attract är begränsade listor och tillhandahålls utan extra kostnader i ditt företag. Dessa listor är endast tillgängliga via LinkedIn-programpartners, t.ex. Attract. De visas inte på panelen **karriärer** på ditt företags LinkedIn-sida eftersom bara betalda listor visas där. De visas emellertid när potentiella kandidater visar alla tillgängliga jobb. Begränsade listor visas också på LinkedIn-jobbsökningar.

Attract erbjuder två sätt att integrera med LinkedIn för att hjälpa dig att källkandidater från den här populära karriärplatsen:

- Publicera från Attract till LinkedIn
- Hitta kandidater från LinkedIn från Attract.

Du konfigurerar båda alternativen på fliken **LinkedIn-integration** i Administrationscenter. Öppna administrationscenter genom att gå till <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> För att använda LinkedIn Recruiter-integration med Attract, behöver du [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) och [LinkedIn Recruiter-licenser](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Mer information finns i [vilken version av Attract?](./attract-comprehensive-hiring.md).

Om du har problem med att publicera jobb till LinkedIn, se [Felsöka integration med LinkedIn](./attract-troubleshoot-linkedin.md).

Mer information om andra sätt att publicera jobb på LinkedIn finns i [Vanliga frågor om LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Konfigurera jobbpublicering till LinkedIn

Innan du kan publicera jobb från Attract till LinkedIn behöver du ett [LinkedIn företags-ID](https://aka.ms/findID). Ditt LinkedIn företags-ID är en sträng med nummer som unikt identifierar ditt företag i LinkedIn. För mer information, se [associera ditt LinkedIn företags-ID med LinkedIn jobbtavla - Vanliga frågor](https://aka.ms/findID).

Attract skickar en feed av dina jobbpubliceringar till LinkedIn, och LinkedIn söker efter feed ungefär en gång per dag. Det kan ta upp till 48 timmar innan dina jobb publiceras på siten.

Jobb som har publicerats på LinkedIn visas på den publicerade LinkedIn-webbplatsen. LinkedIn har inte testmiljö för att publicera jobb. Se därför till att du inte publicerar några testjobb av misstag. 

1. I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationscenter**. Du kan också gå till <https://attract.talent.dynamics.com/adminsettings>.
2. Välj fliken **LinkedIn-integration**.
3. Under **företagsnamn** anger du namnet på ditt företag och anger ditt **företags-ID** anger du LinkedIn företags-ID. Kontrollera att företagsnamnet matchar namnet som visas på ditt företags LinkedIn-sida. För mer information om LinkedIn företags-ID:n, se [associera ditt LinkedIn företags-ID med LinkedIn jobbtavla - Vanliga frågor](https://www.linkedin.com/help/linkedin/answer/98972).

    Om du behöver ändra någon information för organisationen läser [Ändra organisationens adress, teknisk kontakt med mera](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Om du fortfarande har problem,kontakta [LinkedIn-support](https://www.linkedin.com/help/linkedin).

4. Välj **Spara**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Ställa in LinkedIn Recruiter med Attract 

Om du vill tillåta rekryterare att hitta jobb via LinkedIn Recruiter måste du konfigurera integrationen med LinkedIn Recruiter i Attract. För att slutföra konfigurationsprocessen måste du samarbeta med användare är en administratör i organisationens LinkedIn Recruiter-kontrakt.

1. I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationscenter**. Du kan också gå till <https://attract.talent.dynamics.com/adminsettings>.
2. Välj fliken **LinkedIn-integration**.

    [![Attract Admin-vy för att starta LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Välj **Anslut** för att starta installationen. Du kommer att guidas genom LinkedIn-inloggningsprocesserna.
4. Om du har platser på flera LinkedIn-kontrakt markerar du kontraktet som du vill ansluta till Attract-systemet. Om du har en plats i ett enda LinkedIn-kontrakt kan du hoppa över det här steget.
5. Under **Recruiter System Connect (RSC)**, väljer du **begära**.

    [![Attract Admin-vy för att begära LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. Inställningen **Recruiter System Connect (RSC)** ska nu visas som **partnerklar**. Om du vill se **meddela partner** vänta några sekunder på den här sidan, klicka på **meddela partner** och uppdatera sedan sidan. Inställningen ska nu visas som **partnerklar**.

    [![Attract Admin-vy om du vill visa att Attract-sidan av begäranden har slutförts](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Du måste slutföra följande steg, du måste ha administratörsbehörigheter i ditt LinkedIn Recruiter-kontrakt.

    1. Logga in på LinkedIn genom att använda ditt administratörskonto och välj **LinkedIn Recruiter**sedan i det övre högra hörnet. 
    2. På sidan **mer** längst upp på skärmen, väljer du **administrationsinställningar**, och klickar sedan på fliken **ATS**.
    3. Om du vill aktivera exporten för ett enda kontrakt ska du aktivera **åtkomst på kontraktsnivå för varje klient i det här kontraktet**. Aktivera det för hela företaget genom att aktivera åtkomst på **företagsnivå för varje kontrakt i företaget**.

    [![Aktivera Attract-integration från LinkedIn Recruiter Admin-vy](./media/EnableRSC.png)](./media/EnableRSC.png)

8. I administrationscentret för Attract väljer du fliken **LinkedIn-integration**. Inställningen **Recruiter System Connect (RSC)** bör nu visas som **aktiverad**.

    [![LinkedIn Recruiter integration slutförd](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Ställ in Ansök med LinkedIn i Attract

Du kan tillåta kandidater att ansök dina jobb genom att använda deras LinkedIn-profiler. Mer information om hur du Ansök med LinkedIn finns i [Styrkan med LinkedIn överallt: ansök med LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Den här funktionen är för närvarande i förhandsgranskning. Innan du följer de här stegen ska du se till att ansök med LinkedIn är aktiverat. För information om hur du aktiverar funktioner för förhandsgranskning finns i [Få åtkomst till förhandsfunktioner i Talent](./access-preview-feature.md).

1. I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationscenter**. Du kan också gå till <https://attract.talent.dynamics.com/adminsettings>.
2. Välj fliken **LinkedIn-integration**.

    [![Attract Admin-vy för att starta LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Bredvid to **Ansök med LinkedIn**, välj **Anslut** för att starta installationen. Du kommer att guidas genom resten av processen med LinkedIn.

## <a name="see-also"></a>Se även

[Vanliga frågor LinkedIn](./attract-linkedin-faq.md)

[Publicera jobb från Attract på externa webbplatser](./posting-jobs-external.md)

[Hitta kandidater med LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Skapa jobb](./creating-jobs-attract.md)

[Felsöka integration med LinkedIn](./attract-troubleshoot-linkedin.md)
