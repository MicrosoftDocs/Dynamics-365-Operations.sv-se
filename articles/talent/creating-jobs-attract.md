---
title: Skapa ett jobb i Attract
description: Det här avsnittet beskriver delarna av ett jobb i Attract. Här förklaras också hur du skapar ett jobb.
author: hasrivas
manager: AnnBe
ms.date: 07/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 95bc75596f6f014b58160022f41ae86a825c5afc
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527276"
---
# <a name="create-a-job-in-attract"></a>Skapa ett jobb i Attract

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet beskriver delarna av ett jobb i Dynamics 365 Talent: Attract. Här förklaras också hur du skapar ett jobb.

## <a name="job-creation"></a>Skapa jobb

Administratörer, rekryterare och anställningschefer kan skapa jobb. När du skapar ett jobb kan du uppmanas att ange din roll i processen: anställande chef eller rekryterare. När du väljer en roll uppmanas du att välja en processmall. Om du väljer **hoppa över**, används standardmallen. Mer information om processmallar finns i [Skapa en processmall i Attract](./process-templates-attract.md).

Ett jobb i Attract har jobbinformation, ett anställningsteam, jobbpubliceringar och analys.

## <a name="job-details"></a>Jobbdetaljer

Fliken **Jobbdetaljer** innehåller information om jobbets ansvarsområden och attribut. Fälten för jobbtitel, jobbbeskrivning och plats för jobbet krävs. De andra fälten är valfria.

Som standard anges fältet **antal lediga jobb** till **1**. Du kan dock ändra värdet. När ett erbjudande har tagits fram för ett jobb, minskar värdet i fältet **antal tillgängliga lediga jobb**.

Om befattningshantering är aktiverat på administratörscenter är **uppdatera befattningar** tillgängligt. Den här sökningen läser entiteten JobPosition i Common Data Service och returnerar en lista över befattningar som kan väljas för jobbet. Om antalet befattningar som du väljer överskrider antalet lediga befattningar, visas ett varningsmeddelande. Du får också en varning om en befattning används i flera jobb.

> [!NOTE]
> Befattningshantering finns i tillägget omfattande anställning.

Beroende på inställningarna i anställningsprocessens erbjudandeaktivitet, kan ett befattningsnummer användas två gånger i ett erbjudande. Mer information finns i [Aktiviteter i anställningsprocesser](./activities-attract.md).

Attract innehåller en standarduppsättning med **Kompetenser**. Dessa kompetenser visas som förslag medan du skriver. Du kan lägga till flera kompetenser genom att ange den nya kompetenstexten i fältet och tryck på Retur.

Attract innehåller en standarduppsättning med **Jobbfunktioner**. Du kan lägga till upp till tre fler jobbfunktioner genom att ange en ny jobbfunktion i fältet och trycka på retur.

Attract innehåller en standarduppsättning med **Företagets bransch**. Du kan lägga till upp till tre fler företagets branscher genom att ange en ny företagets bransch i fältet och trycka på retur.

## <a name="hiring-team"></a>Anställningsteam

Fliken **anställningsteam** innehåller en lista över personer som ingår i jobbet. När en användare läggs till ett anställningsteam måste de tilldelas en roll för anställningsteamet. Rollen bestämmer de data som användarna har tillgång till och meddelanden som de tar emot. Rollerna som kan väljas är **Rekryterare**, **Anställande chef**, **Ombud** och **Intervjuare**. Mer information om rollprivilegier finns i dokumentet ”rollhantering”. Rekryterare och anställande chefer kan utse en eller flera ombud att arbeta för deras räkning. Mer information om ombud finns i [Säkerhets- och rollhantering i Attract](./security-attract.md).

Anställningsteamet kan uppdateras när jobbet har aktiverats.

## <a name="process"></a>Process

Standardinformation om anställningsprocessen baseras på processmallen som valdes när jobbet skapades. Om en specifik mall inte markerades vid den tiden används standardmallen. När du definierar anställningsprocessen kan du lägga till eller ta bort olika faser utom faserna potentiell kandidat, ansökning och erbjudande. Även om fasen potentiell kandidat inte kan tas bort, kan den vara avstängd. Inom varje fas kan du lägga till eller ta bort en eller flera fördefinierade aktiviteter.

Mer information om aktiviteter som kan läggas till i anställningsprocessen finns i [Aktiviteter i anställningsprocesser](./activities-attract.md).

> [!NOTE]
> Processen för anställning kan inte uppdateras när jobbet har aktiverats.

## <a name="postings"></a>Bokföringar

När ett jobb har aktiverats kan det publiceras. Endast rekryterare och administratörer kan publicera jobb. Jobbet kan publiceras antingen till Talent Careers (en karriärwebbplats för Dynamics 365 Talent) eller LinkedIn. Attract-teamet arbetar kontinuerligt med att samarbeta med en sammanslutning av arbetstavlor. Listan utvidgas över tiden. När ett jobb har publicerats som endast internt behöver kandidater ett AAD-konto för att visa och ansöka om jobbet. Om jobbet är offentlig kan sökanden visa och ansöka om jobb med alla autentiseringsalternativ. 

Mer information om jobbpubliceringar finns i [Ställa in din karriärwebbplats i Microsoft Dynamics 365 Talent - Attract](career-site.md).

> [!NOTE]
> Funktionen jobbpublicering är bara tillgänglig för tillägget omfattande anställning. för Attract.

## <a name="activate"></a>Aktivera

När ett jobb har aktiverats kan det publiceras och potentiella kandidater och sökanden kan läggas till. Alternativet att lägga till potentiella kandidater till ett jobb anges i aktiviteten potentiell kandidat i anställningsprocessen.

> [!NOTE]
> Processen för anställning kan inte uppdateras när jobbet har aktiverats.

## <a name="prospects-and-applicants"></a>Potentiella kandidater och sökande

Alternativet att lägga till potentiella kandidater till ett jobb anges i [Aktiviteter i anställningsprocesser](./activities-attract.md#prospect-activity) i anställningsprocessen. Det här alternativet ska ställas in innan du aktiverar jobbet. När ett jobb har aktiverats kan potentiella kandidater och sökanden läggas till.

## <a name="approvals"></a>Godkännanden

Attract-jobb kan skickas för godkännande. Inte alla jobb kräver godkännande. Behovet anges på mallnivån. Som standard stängs godkännanden av på mallen. För att ställa in godkännanden går du till en processmall och ställer in fältet **godkännande** till standard. Välj sedan den mallen när du skapar jobbet.

När ett jobb sparas skickas den för godkännande. I följande tabell visas statusen för ett dokument som använder godkännanden.

| Status   | Stat                                                               |
|----------|---------------------------------------------------------------------|
| Utkast    | Jobbet har sparats, men det har inte skickats till ett arbetsflöde. |
| Väntande  | Jobbet har skickats till godkännare.                            |
| Godkänt | Jobbet har godkänts, men har inte aktiverats.            |
| Avvisat | Jobbet har avvisats och kan inte aktiveras.               |
| Aktiva   | Jobbet har godkänts och aktiverats.                            |

I jobblistan kan du filtrera på jobbstatus.

Godkännanden kan skickas till Microsoft Azure Active Directory (Azure AD)-användare i företaget. Godkännanden skickas parallellt till alla personer som är angivna som godkännare. Alla godkännare måste godkänna jobbet innan det kan fortsätta. Om en godkännare avvisar jobbet, visar projektet statusen **Avvisat**. När ett jobb har godkänts kan det aktiveras.

Om en användare redigerar jobbet när det är godkänt, men inte aktiverat återställs jobbstatus till **utkast** och jobbet måste skickas in igen för godkännande. När ett godkänt jobb har aktiverats kan du inte redigera det.

Personer som är angivna som godkännare meddelas i Attract och ett e-postmeddelande för att informera dem om att de har en artikel att godkänna.  I e-postmeddelandet kan godkännare klicka på länken för att öppna jobbet, granska informationen och antingen godkänna eller avvisa. När projektets status anges som **godkänd** eller **avvisad** meddelas avsändaren i Attract och de tar emot ett e-postmeddelande. Dessutom får godkännare ett e-postmeddelande med påminnelse om de inte har svarat på en begäran om godkännande inom 24 timmar.

> [!NOTE]
> Du kan skapa anpassade e-postmallar för e-post för godkännande. Mer information [Skapa och hantera e-postmallar](https://docs.microsoft.com/dynamics365/unified-operations/talent/email-templates).

## <a name="create-a-job"></a>Skapa ett jobb

Följ dessa steg för att skapa ett jobb.

1. Gå till **Jobb**.
2. Välj **Ny**.
3. I fältet **Jobbtitel**, ange jobbtiteln. I fältet **Roll** anger du din roll.
4. I fältet **Mall** anger du en mall. Du kan också välja **Hoppa över**. Om du väljer **hoppa över** används mallen som har markerats som standardmall.

    Om dokumentet ska gå igenom någon godkännandeprocess, markera en mall där fältet **godkännandeprocess** har tilldelats **standard**.

5. På fliken **Detaljer** anger du detaljerna för jobbet. Fälten **Titel**, **Jobbeskrivning** och **Plats** krävs.
6. Välj **Spara**.
7. På fliken **Anställningsteam** lägger du till en anställande chef, rekryterare eller intervjuare.
8. Välj **Spara**.
9. På fliken **Process** lägger du till eller tar bort faser som du vill:

    - Lägg till en fas genom att markera **+ Ny fas**.
    - Om du vill ta bort en fas, för pekaren över fasen som ska tas bort och välj knappen för papperskorgen som visas.

        > [!NOTE]
        > Faserna potentiell kandidat, ansökan och erbjudanden kan inte tas bort.

10. Lägg till eller ta bort aktiviteter som du vill:

    - Om du vill lägga till en aktivitet, drar du den från listan till höger till lämplig fas. Du kan också dubbelklicka på aktiviteten och sedan välja fasen som den ska läggas till i.
    - Om du vill ta bort en aktivitet, expandera den och välj sedan knappen för papperskorgen i aktivitetshuvudet.

11. Välj **Spara**.
12. Om du väljer att använda en godkännandeprocess gör du så här:

    1. Välj **+ Lägg till godkännare** och ange en användare som har ett konto på Azure AD. Du kan lägga till flera godkännare.
    2. Välj **Skicka till godkännare**.

    Fältet **Jobbstatusjobb** för jobbet har tilldelats **väntande**. Efter att värdet för fältet **Jobbstatus** ändras till **Godkänt** kan jobbet aktiveras.

13. Aktivera jobbet genom att välja **Aktivera**.
14. Om du vill publicera jobbet går du till **Publiceringar** och väljer sedan **Publicera nu** under Talent karriärwebbplats eller LinkedIn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]