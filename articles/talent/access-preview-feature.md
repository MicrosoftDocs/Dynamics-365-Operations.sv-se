---
title: "Åtkomst till förhandsfunktioner i Dynamics 365 for Talent"
description: "Det här avsnittet beskriver hur en administratör kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning."
author: rschloma
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2e5dd8f852ac1a6c2997a50a60f03db6adfd218c
ms.openlocfilehash: 5500bfc1cdd1949d301ae82fad5506dfdbeb59f3
ms.contentlocale: sv-se
ms.lasthandoff: 05/01/2018

---

# <a name="access-preview-features-in-dynamics-365-for-talent"></a>Åtkomst till förhandsfunktioner i Dynamics 365 for Talent 

[!include[banner](../includes/banner.md)]

Som en del av vår kontinuerliga distribution av produktens funktioner, vill vi att kunder får nya funktioner så snart som möjligt. Administratörer kan se och använda funktioner för förhandsgranskning i datormiljön. Dessa funktioner kan snart allmänt tillgänglig och har genomgått omfattande testning. Vi söker bara en slutlig runda av feedback från kunder och validering innan vi vanligtvis frigörs.

Det här avsnittet beskriver hur en administratör kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning. Den här listan uppdateras funktioner släpps till normala tillgänglighet och nya funktioner som ges ut om du vill förhandsgranska. Ingen anmälan görs när nya funktioner publiceras för att förhandsgranska. Användare börjar bara se funktionerna.

## <a name="enable-or-disable-preview-features"></a>Aktivera eller inaktivera funktioner för förhandsgranskning

Du kan använda inställningrn **förhandsgranskningsfunktioner** i administratörscenter för Microsoft Dynamics 365 for Talent för att aktivera eller inaktivera funktioner för förhandsgranskning. Inställningen är avstängd som standard. Åtgärden att aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.

> [!IMPORTANT]
> Genom att aktivera inställningen **förhandsgranskningsfunktioner** kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö. Genom att inaktivera inställningen, inaktiveras förhandsgranskningsfunktioner och gör dem otillgängliga för användarna. Förhandsgranskningsfunktioner har begränsad funktionalitet i Talent. De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Talent servicenivåavtal. Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Aktivera eller inaktivera funktioner för förhandsgranskning för organisationen

#### <a name="attract"></a>Attract

1. Logga in på Microsoft Dynamics 365 for Talent: Attract
2. I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationsinställningar**.
3. På fliken **Funktionshantering** väljer du alternativet bredvid **Förhandsgranskningsfunktioner** så att det blir blått.
4. Uppdatera webbläsaren för att starta och se de nya funktionerna. (Användare som redan har loggat in ser funktionerna nästa gång de loggar in och de kan uppdatera webbläsaren om du vill se funktionerna direkt.)

#### <a name="core-hr"></a>Grundläggande personal

1. Logga in på Talent. Arbetsytan för grundläggande personal öppnas, som du utför resten av stegen från. 
2. Välj **Systemadministration \> Länkar systemparametrar**.
3. På sidan **systemparametrar**på fliken **Förhandsgranskningsfunktioner** anger du **aktivera förhandsgranskningsläget för alla användare** till **Ja** för att göra förhandsgranskningsfunktionerna tillgängliga.

> [!NOTE]
> Inaktivera förhandsgranskningsfunktioner med samma grundläggande steg. När du inaktiverar förhandsgranskningsfunktioner blir de otillgängliga för användarna och fel kan inträffa i processer som är associerade med funktionerna.

## <a name="features-that-are-currently-in-preview"></a>Funktioner som är i förhandsgranskning nu.

### <a name="attract"></a>Attract

- **Jobbmallar** – nu kan du skapa mallar för anställningsprocesser. Användare kan redan anpassa anställningsprocessen för ett specifikt jobb. De kan nu skapa mallar för den processen och välja lämplig mall när ett visst jobb skapas. Därför hjälper den här funktionen till att effektivisera jobbinställningsprocessen.
- **Karriärplats** – aktuell version av karriärplats visar bara en lista över alla lediga jobb. Dock läggs mer kapacitet till webbplatsen i framtiden. Jobb kan markeras som antingen interna eller externa. Interna användare som loggar in på webbplatsen ser både interna projekt och externa jobb. Men icke interna användare och användare som inte är inloggade ser endast externa jobb.
- **Jobbpublicering** – nu kan du publicera jobb på karriärwebbplatsen.
- **LinkedIn jobbpublicering** – nu kan du publicera jobb på LinkedIn.

    > [!NOTE]
    > Jobb som har publicerats visas bara för kunder som prenumererar på en eller flera LinkedIn-jobblistor. Annars ser kunder endast ett jobb om de uttryckligen söker efter det. Det uppstår en fördröjning när jobb publiceras på LinkedIn. Ett jobb kan ta flera timmar visas när det har publiceras från Attract.

- **Kandidatsökning** – både interna och externa kandidater kan nu söka direkt från jobbsidan på karriärwebbplatsen.
- **Bedömningar** – som en del av den konfigurerbara anställningsprocessen för ett visst jobb eller när en jobbmall används har nu användarna tillgång till en ny aktivitetstyp för **bedömning**. De kan sedan använda projektet: ”Gauge” appen i Talent för att skapa grundläggande bedömningar som du kan skicka till sökande. Projekt: ”Gauge” är också i förhandsversion. Ytterligare providers läggs till i framtiden.
- **Projekt: ”Gauge”** – projekt: ”Gauge” är ett program i Talent där användarna kan skapa enkla bedömningar och undersökningar.
- **Erbjudandehantering** – användarna kan nu skapa erbjudanden från mallar som inkluderar platshållare. När ansökande avancerar framåt till erbjudandefasen, kan rekryterare och anställande chefer använda erbjudandeverktyget för att förbereda ansökandes formella erbjudande via mallar, skicka erbjudande för internt godkännande och slutligen skicka erbjudandet till ansökande för underskrift. Många nya funktioner läggs till erbjudandeverktyget med tiden och förhandsgranskningsfunktionen uppdateras med de här funktionerna när vi är klara att släppas för att förhandsgranska.

### <a name="core-hr"></a>Grundläggande personal

- **Öppna anmälan** – Öppna anmälan ger anställda en enkel, egen erfarenhet för val av förmånerna. Personaladministratörer kan konfigurera förmåner i den öppna anmälningsprocessen för organisationen och anmälningsupplevelse för medarbetare med hjälp av en enkel guidad lösning.

## <a name="feedback"></a>Feedback

Oavsett om feedback är positiv eller negativ vill vi gärna höra från dig om hur du använder funktionerna för förhandsgranskning. Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.

- [Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.
- Använd följande webbplatser för att komma med förslag om produkter. Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tror ska göras av befintliga funktioner.

    - [Ge dig idéer](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Grundläggande personal](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

Inkludera inte personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen. Information som samlas in kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning. Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/en-us/privacystatement).

> [!TIP]
> Sätt ett bokmärke i detta ämne och gå tillbaka ofta för att hålla dig uppdaterad om nya funktioner för förhandsgranskning som vi släpper.

