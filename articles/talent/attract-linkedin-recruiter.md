---
title: Skaffa kandidater med LinkedIn Recruiter i Attract
description: Använd den LinkedIn-integration som ges av Microsoft Dynamics 365 Talent - Attract för att hitta jobbkandidater via LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528279"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a>Skaffa kandidater med LinkedIn Recruiter i Attract

[!include [banner](includes/banner.md)]

LinkedIn är världens största online professionella nätverk, vilket ger dig till gång till världens främsta talanger. Microsoft Dynamics 365 Talent: Attract gör att du kan hitta kandidater direkt från LinkedIn. Därför är det enklare än någonsin att hitta talanger som du behöver för att fylla dina öppna befattningar. När du har ställt in din anslutning med LinkedIn genom Attract kan du visa potentiella LinkedIn-kandidater för dina befattningar och exportera dem till Attract med bara ett klick.

Om du inte verkar ha den här funktionen kontaktar du din administratör. Innan du kan dra nytta av LinkedIn Recruiter från Attract måste din administratör [ställa in integration med LinkedIn](./attract-admin-linkedin.md). Du kan sedan konfigurera din anslutning med LinkedIn Recruiter och börja hitta kandidater.

>[!IMPORTANT]
>Från och med den 1 juli 2020 har LinkedIn inte längre stöd för Internet Explorer 11. Användare kan fortfarande komma åt LinkedIn med Internet Explorer 11, men kommer att uppmanas att uppgradera eller använda en annan webbläsare. Mer information finns i [Webbläsare som stöds för LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Konfigurera anslutningen med LinkedIn Recruiter

Innan du kan börja arbeta med LinkedIn Recruiter via Attract måste du ställa in anslutningen med LinkedIn Recruiter. För det här steget ska du använda dina autentiseringsuppgifter för LinkedIn Recruiter.

1. Klicka på knappen **Inställningar** (kugghjulsikonen) längst upp till höger på sidan.
2. Välj **Användarinställningar**.
3. Välj **Anslutningar**, välj **Anslut** bredvid **LinkedIn**. Följ instruktionerna som finns på LinkedIn.

    ![[Konfigurera anslutning till LinkedIn Recruiter från Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Visa LinkedIn-kandidater i Attract

När du är ansluten till LinkedIn Recruiter kan du visa kandidaters LinkedIn-profiler i Attract.

>[!NOTE]
>Om du har tilldelats en plats som Rekryterare kan du se kandidatens fullständiga information.<br><br>
>Om du har tilldelats en plats som Anställande chef eller ingen plats alls måste du logga ut från LinkedIn eller LinkedIn Recruiter innan du går till fliken LinkedIn för en kandidat i Attract. Du kan se kandidatens grundläggande offentliga profil, som för- och efternamn.

1. I Attract, välj **Jobb** eller **Talangpooler** till vänster och välj sedan en sökande.

    ![[Visa LinkedIn-kandidater i Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. I kandidatens profil väljer du fliken **LinkedIn**. Du kan visa kandidatens profil samt InMail-historik.

   ![Visa en kandidats LinkedIn-information](./media/attract-candidate-linkedin-tab.png)

Härifrån kan du sedan utföra följande åtgärder:

- Välj fliken **Rekryteringsaktiviteter** för att visa följande:
   
   - Rekryteringsanteckningar (både offentliga och privata). Som standard är anteckningarna privata och endast synliga för anteckningens ägare.
   - InMail-aktivitet (men inte InMail-innehållet). Rulla längst ned på sidan om du vill visa InMail-utbytet med din potentiella kund och visa andra användare i organisationen som interagerar med din potentiella kund.
   - Avvisande av kandidat

- Välj **Skicka InMail** för att skicka InMail utan att behöva lämna Attract.

- Välj **Spara till ett jobb** om du vill spara jobbet utan att lämna Attract.

> [!NOTE]
> En kandidats LinkedIn-profil visas i Attract när kandidatens Attract-information matchar LinkedIn-informationen. Följande matchningsregler används:
> 
> 1. Om e-postadressen och medlems-ID för LinkedIn matchar Attract och LinkedIn visas kandidatens profil. Kandidater har fortfarande möjlighet att koppla eller ta bort kopplingen till LinkedIn-profilen från Attract.
> 2. Om e-postadressen eller medlems-ID för LinkedIn inte matchar visas en lista över möjliga kandidater. Du kan sedan välja en kandidat i listan och länka profilen.
> 3. Om det inte finns några bra matchningar meddelas du om att ingen matchning hittades.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Exportera LinkedIn-kandidater till Attract med ett klick

När du granskar kandidater i LinkedIn Recruiter kan du exportera dem till jobb som du för närvarande har öppet i Attract. För det här steget behöver du behörigheterna Rekryterare eller Anställande chef i Attract. Mer information om roller i Attract finns i [Säkerhets- och rollhantering i Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

Du måste också kontrollera att jobbet har fasen potentiell kandidat. Mer information i [Aktivitet för potentiell kandidat](./activities-attract.md#prospect-activity).

1. I Attract, skapa ett jobb, tilldela lämpliga roller och aktivera jobbet.
2. I LinkedIn Recruiter hittar du en bra kandidat för jobbet och går till kandidatens profil.
3. I jobbsökrutan i kontaktkortet, hitta jobbet med titeln eller jobb-id som aktiverades i Attract. Om du inte hittar jobbet klickar du på **ändra ATS** för att hitta rätt Attract-instans.
4. Markera jobbet och välj **Exportera**.
5. Öppna jobbet i Attract. Den exporterade kandidaten visas på fliken **potentiell kandidat** i jobbet.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Visa Attract-information i LinkedIn Recruiter

I LinkedIn Recruiter kan du följa upp om en kandidat har sökt andra jobb i organisationen, titta på när kandidaten är i olika faser i jobbansökningar och visa feedback och kommentarer från Attract.

1. Öppna LinkedIn Recruiter och välj en kandidatprofil.
2. Hovra över **I ATS**.
3. Välj något av följande alternativ för att visa kandidatinformationen som är lagrad i Attract:

    - **Jobb och status** – se de jobb som kandidaten är en del av, den senaste statusen och hur kandidaten fortskrider för varje jobb.
    - **Intervjufeedback** – Se feedback som intervjuare har lämnat i Attract.
    - **Anteckningar** – Se alla noteringar som har angetts för den här kandidaten i Attract.

    ![[Visa Attract-information från LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> Kandidater och programdata synkroniseras inte med LinkedIn Recruiter om kandidaten inte har flyttats från fasen potentiell kandidat.

## <a name="view-linkedin-talent-pools"></a>Visa LinkedIn talangpooler

Om kandidater är överens om att dela sin LinkedIn-profil med en användare i din organisation, skapas en ny kandidatpost i Attract. Dessa kandidater visas sedan i en systemskapad LinkedIn talangpool.

1. I Attract, välj **Talangpooler** till vänster.
2. Välj LinkedIn talangpool. En lista med kandidater och deras stub-profiler visas på LinkedIn. Stub-profiler innehåller kandidatens förnamn och efternamn och e-postadress, om kandidaten väljer att dela den.

## <a name="see-also"></a>Se även

[Vanliga frågor Attract-integration med LinkedIn](./attract-linkedin-faq.md)

[Konfigurera integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Skapa, godkänna och bokföra jobb i Attract](./creating-jobs-attract.md)

[Publicera jobb på LinkedIn från Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Felsöka integrering med LinkedIn och Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]