---
title: Hantera funktioner
description: Läs mer om hur du aktiverar och inaktiverar nya funktioner i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010569"
---
# <a name="manage-features"></a>Hantera funktioner

Som en del av vår kontinuerliga distribution av ny funktioner för Microsoft Dynamics 365 Human Resources, vill vi att kunder får nya funktioner så snart som möjligt. Vi tillhandahåller förhandsfunktioner som snart är allmänt tillgänglig och har genomgått omfattande testning. Vi söker bara en slutlig runda av feedback från kunder och validering innan vi gör dem allmänt tillgångliga.

Mer information om nya funktioner i Personal, se [Nyheter och ändringar i Personal](hr-admin-whats-new.md) och [Viktig information om Dynamics 365 och Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

Arbetsytan **Funktionshantering** ger en lista med funktioner som levereras i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem. Mer information om hur du aktiverar Funktionshantering finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan **Funktionshantering** kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.

När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan **funktionshantering** anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

## <a name="enable-or-disable-preview-features"></a>Aktivera eller inaktivera funktioner för förhandsgranskning

För att du ska kunna använda funktionerna för förhandsgranskning måste du först aktivera dem i miljön. Aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.

> [!IMPORTANT]
> Funktionerna för förhandsgranskning är endast tillgängliga i **begränsade** miljöer När du aktiverar förhandsgranskningsfunktioner kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö. När du inaktiverar förhandsgranskningsfunktioner, inaktiverar du den och gör dem otillgängliga för användarna. Förhandsgranskningsfunktioner har begränsad funktionalitet i Personal. De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Personal servicenivåavtal (SLA). Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.

1. I Personal, välj **Systemadministration**.

2. Välj panelen **funktionshantering**.

3. Aktivera en förhandsgranskningsfunktion genom att markera den i listan och sedan välja **Aktivera**. Inaktivera en förhandsgranskningsfunktion genom att markera den i listan och sedan välja **inaktivera**.

## <a name="preview-feature-benefits-management"></a>Förhandsgranskningsfunktion: Hantering av förmåner

Hantering av förmåner får du en flexibel lösning som stöder en mängd olika förmånsalternativ, tillsammans med en lättanvänd medarbetares erfarenhet som visar dina erbjudanden. Mer information om hur du konfigurerar och använder en förmånshantering finn si [Översikt över förmånshantering](hr-benefits-management-overview.md).

Förmånshantering ersätter funktioner i arbetsytan **förmåner**. När du aktiverar funktionen för förhandsgranskning av förmånshantering kan du inte längre komma åt följande formulär på arbetsytan **förmåner**:

- **Förmåner**
- **Förmånselement**
- **Tariffer för lönetilläggsberäkning**
- **Resultat från förmånsanmälan**
- **Förmåner som upphör och resulterande förlängningar**
- **Policyregeltyper för förmånsberättigande**
- **Policyer för förmånsberättigande**
- **Berättigandehändelser**

Du kan visa informationen i dessa formulär i skrivskyddat läge. Om du vill redigera informationen måste du först inaktivera förhandsgranskningsfunktioner för förmånshantering.

### <a name="benefits-management-known-issues"></a>Kända problem med förmånshantering

#### <a name="life-events"></a>Livshändelser

När du bearbetar livshändelser får användaren ett felmeddelande:

Täckningens startdatum måste ligga mellan *början av planperioden* och *slutet av planperioden*. 

Livshändelsen fortsätter att bearbetas som förväntat.

#### <a name="eligibility-processing"></a>Bearbetning av berättigande

När du kör berättigande till förmåner som använder en 1-5X lön, % av lönen och fast belopp för försäkringsbeloppet måste datum för förmånsinformation måste ställas in på anställdas startdatum i **Anställningshistorik**, med arbetade timmar, lönefrekvens och årlig inkomst av förmånen. Om det finns en fast kompensation för arbetaren anger du under de timmar som arbetas tillsammans med lönefrekvensen och årlig inkomst av förmånen kommer att beräknas. Om medarbetaren har lön behöver du inte ange arbetade timmar. Vi rekommenderar att du först anger fast kompensation när du skapar nya medarbetare. Om du vill uppdatera informationen om förmånsposter, gå till **Arbetare > Arbetarhistorik > Information om anställning**. Justera datumet till arbetarens startdatum.

#### <a name="employee-self-service"></a>Självbetjäning för medarbetare

Medarbetare kan välja en plan som de inte är kvalificerade för och checka ut. En arbetare har till exempel inga beroenden, men har tillåtelse att välja en sjukvårdsplan med ett alternativ för föräldraledighet.

Medarbetarbelopp beräknas inte när täckningsbeloppet uppdateras för livförsäkring. När en medarbetare till exempel erbjuds en livförsäkringsplan kan han eller hon välja upp för att $ 50 000 för täckning till en kostnad av $ 0,36 per $ 1 000 av täckning.  När medarbetaren uppdaterar täckningsbeloppet finns medarbetarens kopplade kostnad kvar på noll.

För en förmånsplan som bara tillåter ett enda urval av den aktuella plantypen får användaren ett fel om de försöker att avstå från en plan efter att ha valt en plan. En användare väljer till exempel en sjukvårdsplan och placerar den i vagnen. Användaren väljer sedan **Avstå** för en annan sjukvårdsplan. Användaren får ett felmeddelande.

## <a name="preview-features-in-leave-and-absence"></a>Funktioner för förhandsgranskning av tjänstledighet och frånvaro

Funktioner för förhandsgranskning av tjänstledighet och frånvaro inkluderar:

- **Tjänstledighets- och frånvaro-kalender** - tjänstledighets- och frånvaroparametrar flyttas från **personalparametrar** till en ny skärm som kallas **tjänstledighets- och frånvaroparametrar**. Den nya skärmen innehåller ny flik för **kalender**. Den här förhandsgranskningen aktiverar bara en del av parametrarna. Du når den nya skärmen från fliken **Länkar** i arbetsytan **ledighet och frånvaro**. Kalendern innehåller:
  - **Företagskalender** - visar alla förfrågningar om medarbetarledighet. Personer med rollen **Personal** har åtkomst till den här kalendern från fliken **länkar** i arbetsytan **tjänstledighet och frånvaro**.
  - **Chef teamkalender** - visar alla direktrapporters ledighetsbegäran. Chefer får åtkomst till kalendern från fliken **mitt team** i självbetjäning för medarbetare under **tjänstledighet och frånvaro**. 

- **Semesterkalender för tjänstledighet och frånvaro** - tjänstledighetstyper inkluderar ett nytt alternativ för **helgdag** som används tillsammans med arbetstidskalendern. Dagar som definieras i semestrar och stängningar betecknas nu som **helgdag** när arbetsdagar skapas. När periodiseringar bearbetas görs justeringar av medarbetare som har tilldelats till kalendern för att redovisa helgdagar på en arbetsdag.

- **Granskning av periodisering av tjänstledighet** - en ny skärm gör det möjligt att granska när periodiseringen har bearbetats och raderats, både av alla medarbetare och enskilda medarbetare. Du når den nya skärmen från fliken **Länkar** i arbetsytan **ledighet och frånvaro**.

- **Ta bort periodisering av tjänstledighet** - du kan nu ta bort periodiseringar för specifika tjänstledighetsplaner. Du når detta nya alternativ från fliken **Länkar** i arbetsytan **ledighet och frånvaro**. För enskilda medarbetare visas det här alternativet i grupperingen **tjänstledighet och frånvaro** i medarbetarprofilen. 

- **Avrundning av periodisering av tjänstledighet** - Nya alternativ för **tjänstledighetstyp** definiera vilken typ av avrundning som ska användas, plus decimalens precision för avrundningen under periodiseringsprocessen. När periodiseringar bearbetas tillämpas avrundningen och precisionen på posterna i periodiseringen. 

- **Konfigurera flera tjänstledighetstyper på en enda tjänstledighetsplan** - en ny kolumn i det periodiseringsschemat för tjänstledighet där du kan definiera flera tjänstledighetstyper i en tjänstledighets- och frånvaroplan med olika periodiseringsscheman. Tidigare fältet **tjänstledighetstyp** tas bort. På medarbetarens registrering visas saldona för tjänstledighetstyperna i en tabell i stället för längst upp på skärmen.

  > [!IMPORTANT]
  > Du kan inte stänga av den här funktionen när du har aktiverat den.

- **Använd en medarbetares heltidslön (FTE) för periodisering** - en ny kolumn i periodiseringsschemat för tjänstledighet gör det möjligt att använda en FTE för periodisering. När periodiseringar bearbetas använder programmet medarbetarens primära befattning och den heltid som definierats för att bestämma det proportionella periodiserade beloppet.

  > [!NOTE]
  > Den här funktionen är bara tillgänglig om du aktiverar **Konfigurera flera ledighetstyper per ledighetsplan**. 

## <a name="feedback"></a>Feedback

Vi vill gärna höra om din erfarenhet av dessa förhandsfunktioner. Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.

- [Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.
- Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tycker att vi ska göra av befintliga funktioner. Föreslå produktidéer om [personalidéer](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
Inkludera inte personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen. Insamlad information kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning. Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Se även

- [Nyheter i Personal](hr-admin-whats-new.md)
- [Utgivningsplan för Dynamics 365 och Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)