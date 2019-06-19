---
title: Få åtkomst till förhandsfunktioner i Microsoft Dynamics 365 for Talent
description: Det här avsnittet beskriver hur en administratör kan aktivera funktionen förhandsgranska i Microsoft Dynamics 365 for Talent och visar funktionerna som är aktiverade för förhandsgranskning.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 2858451435c358380503c8edc5cb162e6834894a
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620606"
---
# <a name="access-preview-features-in-talent"></a>Få åtkomst till förhandsfunktioner i Talent

[!include[banner](../includes/banner.md)]

Som en del av vår kontinuerliga distribution av HR-hanteringsfunktioner (HCM) för Microsoft Dynamics 365 for Talent, vill vi att kunder får nya funktioner så snart som möjligt. Administratörer kan se och använda funktioner för förhandsgranskning i datormiljön. Dessa funktioner kan snart allmänt tillgänglig och har genomgått omfattande testning. Vi söker bara en slutlig runda av feedback från kunder och validering innan vi gör dem allmänt tillgångliga.

Det här avsnittet beskriver hur du kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning. Den här listan uppdateras funktioner släpps till normala tillgänglighet och nya funktioner som ges ut om du vill förhandsgranska. Ingen anmälan görs när nya funktioner publiceras för att förhandsgranska. Användare börjar bara se funktionerna. Mer information om nya funktioner i Talent, se [Nyheter och ändringar in Dynamics 365 for Talent](./whats-new.md) och [Viktig information om Dynamics 365 och Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Aktivera eller inaktivera funktioner för förhandsgranskning

För att du ska kunna använda funktionerna för förhandsgranskning måste du först aktivera dem i miljön. Aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.

> [!IMPORTANT]
> När du aktiverar inställningen **förhandsgranskningsfunktioner** kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö. När du inaktiverar inställningen, inaktiveras förhandsgranskningsfunktioner och gör dem otillgängliga för användarna. Förhandsgranskningsfunktioner har begränsad funktionalitet i Talent. De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Talent servicenivåavtal (SLA). Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.

### <a name="attract"></a>Attrahera

1. Logga in på Microsoft Dynamics 365 for Talent: Attract.
2. I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationscenter**.
3. På fliken **Funktionshantering** väljer du alternativet bredvid **Förhandsgranskningsfunktioner** så att det blir blått och visar **På**.

    ![Aktivera förhandsfunktioner i Attract](./media/attract-enable-preview-features.png)

4. Välj eller avbryt valet av enskilda förhandsgranskningsfunktioner. Om du inte gör någonting aktiveras alla tillgängliga funktioner för förhandsgranskning.
5. Uppdatera webbläsaren för att starta och se de nya funktionerna. Användare som redan har loggat in ser funktionerna nästa gång de loggar in och de kan uppdatera webbläsaren om du vill se funktionerna direkt.

> [!NOTE]
> Vissa förhandsgranskningsfunktioner kan kräva ytterligare konfiguration. Slutför inställningarna genom att följa länkarna bredvid förhandsgranskningsfunktionen.

### <a name="core-hr"></a>Grundläggande personal

1. Logga in på Talent.
2. Välj **systemadministration** och välj sedan fliken **länkar**.
3. På sidan **Systemadministration** under **Inställningar**, välj **Systemparametrar**.
4. På sidan **systemparametrar** väljer du fliken **Förhandsfunktioner**.
5. Ange alternativet **aktivera förhandsgranskningsläge för alla** till **Ja** om du vill göra förhandsgranskningar tillgängliga.

    ![Aktivera förhandsfunktioner i Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> För att inaktivera förhandsfunktionen använder du samma steg men anger alternativet **aktivera förhandsgranskningsläge för alla** till **Nej**. När du inaktiverar förhandsgranskningsfunktioner blir de otillgängliga för användarna och fel kan inträffa i processer som är associerade med funktionerna.

### <a name="onboard"></a>Integrera

Inga förhandsfunktioner är för närvarande tillgängliga för Microsoft Dynamics 365 for Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Funktioner som är i förhandsgranskning nu.

### <a name="attract"></a>Attrahera

- [Kandidatrekommendation](./intelligent-recommendations.md#candidate-recommendations) – om det finns fler än tio kandidater kandidater som har meritförteckningar eller fullständiga profiler kommer de kandidater som bäst uppfyller jobbkraven att visas i avsnittet **Sökande att beakta** på det jobbets sida.
- [Jobbrekommendation](./intelligent-recommendations.md#job-recommendations) – om fler än tio jobb publiceras på din karriärwebbplats ger Attract jobbrekommendationer till potentiella kunder.
- [Broadbean-integration](./posting-jobs-external.md#post-jobs-to-broadbean) – du kan publicera jobb från Attract till Broadbean, en extern webbplats för jobbpublicering. När du har aktiverat den här förhandsfunktionen måste du slutföra installationen genom att ange ditt Broadbean användarnamn, klient-ID och krypteringstoken.
- [Analys](./analytic-reports.md) – I analysnavet kan anställningsgrupper visa nyckelmått för ett enskilt jobb plus aggregerade mått genom ala jobb.
- [EEO](./activities-attract.md) – nya aktivitetstyper möjliggör användning av ett fördefinierat formulär för anmälan om diskriminering (EEO) och diskrimineringsombudsmannens data (OFCCP) av sökande. Det fördefinierade formuläret kan inte redigeras
- [Rekommendation av potentiell kandidat](./intelligent-recommendations.md#prospect-recommendations) – Attract granskar tidigare sökande och aktuella kandidater för att tillhandahålla en lista med potentiella kandidater som är en bra matchning för ditt jobb.
- [Relevanssökning](./attract-talent-pools.md#search-and-view-candidate-profiles) – du kan söka i hela kandidatdatabasen efter specifika kunskaper, namn eller utbildningsbakgrunder. Attract söker hela profilen och markerar alla matchningar som den hittar. Attract söker även alla dokument som är tillgängliga för en kandidat och rangordnar intelligent sökresultaten.
- [Aktivitetsgrupp](./whats-new-talent-march-20.md#setting-the-audience-on-activities) – du kan ställa in gruppen för aktiviteter (t.ex. intervju, schema eller feedback) till **alla kandidater**, **interna kandidater** eller **externa kandidater**. u kan leverera anpassade aktiviteter, till exempel YouTube videoklipp, webbinnehåll och Microsoft Forms till alla kandidater, endast interna kandidater, endast externa kandidater eller anställningsteamet.
- [Ansök med LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) – du kan ställa in ett alternativ på Attract karriärwebbplatsen så att jobbkandidater kan söka med LinkedIn. Den här funktionen effektiviserar ansökningsprocessen för dina kandidater genom att de använder sin LinkedIn-profil för att automatiskt fylla i sina ansökningar på karriärwebbplatsen.
- [Källspårning](./source-tracking.md) – Attract spårar källan till kandidatansökningar för att ge värdefull information som kan hjälpa dig att rikta dina rekryteringsansträngningar. Du kan också välja en ansökningskälla när du lägger till en kandidat till ett jobb eller en talangpool.
- [Silvermedaljör](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) – om några kandidater är mycket lämpliga för din organisation, men du inte kan ge ett erbjudande till dem för din nuvarande befattning, kan du ange dem som silvermedaljör. Med hjälp av den här funktionen kan du förkorta tiden till att anställa nästa gång du har en liknande tjänst tillgänglig.

### <a name="core-hr"></a>Grundläggande personal

- [Validera hierdata för befattningshierarki](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) – du kan validera ledarskapshierarkin för de cirkulära referenser som av misstag har importerats.
- [Ange orsakskoder för tjänstledighetstyper](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) – du kan ange orsakskoder för tjänstledighetstyper.
- [Kräv orsaks koder för ledighets ansökningar](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) – förutom att ange orsaks koder för tjänstledighets typer kan du kräva orsaks koder för förfrågningar om ledighet.
- [Skapa en tjänstledighets- och frånvarotransaktionslista för HR](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) – du kan visa en lista över tjänstledighets- och frånvarotransaktioner som hjälper till att tillhandahålla insikter i ledighetssaldon.

### <a name="onboard"></a>Integrera

Inga förhandsfunktioner är för närvarande tillgängliga för Onboard.

## <a name="feedback"></a>Feedback

Vi vill gärna höra om din erfarenhet av dessa förhandsfunktioner. Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.

- [Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.
- Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tycker att vi ska göra av befintliga funktioner. Föreslå produktidéer på följande webbplatser:

    - [Attract idéer](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR idéer](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Onboard idéer](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Se till att inte inkludera personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen. Insamlad information kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning. Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Sätt ett bokmärke i detta ämne och gå tillbaka ofta för att hålla dig uppdaterad om nya funktioner för förhandsgranskning som vi släpper.

## <a name="see-also"></a>Se även

- [Prova eller köp Talent-appar](https://dynamics.microsoft.com/talent/overview/)
- [Nyheter](./whats-new.md)
- [Viktig information](https://docs.microsoft.com/business-applications-release-notes/index)
- [Få support för Talent](./talent-support.md)
