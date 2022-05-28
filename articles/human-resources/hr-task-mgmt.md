---
title: Uppgiftshantering
description: I det här avsnittet beskrivs de funktioner för uppgiftshantering som finns i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae453bd57217f272038decc7e40ed373f618ae03
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710234"
---
# <a name="task-management"></a>Uppgiftshantering

[!INCLUDE [PEAP](../includes/peap-1.md)]

Med Uppgiftshantering kan du skapa uppgifter som måste slutföras för att anställa (registrera), säga upp (avregistrera) och överföra (övergång) medarbetare. Uppgiftshanteringen använder begreppet checklistor. En checklista innehåller en lista med registrerings-, registrerings- eller övergångsuppgifter. I Uppgiftshantering används checklistor för att gruppera uppgifter tillsammans och tilldelar dem till personer eller grupper. Checklistans funktion för registrering, avregistrering och övergångar liknar varandra.

## <a name="checklist-overview"></a>Checklista – översikt

En checklista är en grupp med uppgifter. Checklistor ger dig ett flexibelt sätt att gruppera uppgifter och de kan återanvändas (till exempel när du anställer ytterligare medarbetare). Du kan skapa så många checklistor som du behöver och du kan tilldela samma uppgifter till flera checklistor.

### <a name="examples"></a>Exempel

Följande exempel visar hur checklistor kan användas i processen för registrering. Eftersom checklistefunktionen för registrering, avregistrering och övergångar liknar varandra, gäller den även för övergångsprocesser och avregistreringsprocesser.

Som en del av registreringsprocessen kan personal (HR) skapa uppgifter som spårar registreringsprocessen för inkommande och nyligen anställda medarbetare. Eftersom registreringsprocessen kan variera, beroende på medarbetarens befattning eller geografiska plats, kan du skapa flera checklistor för registrering för att hantera olika anställningssituationer.

**Exempel 1**

Alla medarbetare som anställs i USA måste utföra uppgifter som att t.ex. fylla i skattekällsformulär. Uppgifter som till exempel att tilldela en företagsbil kanske bara gäller för personal på chefsnivå. I det här fallet kan två introduktionschecklistor skapas: **USA-baserade medarbetare** och **endast chefer**. När sedan en chef på mellannivå anställs i USA, väljs checklistan **USA-baserade medarbetare**. När en chef anställs i USA väljs dock båda checklistorna för att säkerställa att alla nödvändiga registreringsuppgifter är slutförda.

**Exempel 2**

Ett företag har både säsongsanställda och ordinarie heltidsanställda. Även om vissa uppgifter (som att verifiera ankomsttiden för den nya medarbetaren) gäller anställda av båda typerna, gäller vissa ytterligare uppgifter endast för vanliga heltidsanställda. I det här fallet kan du skapa två checklistor. Båda checklistorna inkluderar de uppgifter som gäller för både säsongs- och heltidsanställda, men bara en checklista innehåller de uppgifter som är specifika för heltidsanställda.

## <a name="task-management-workspace"></a>Arbetsyta för uppgiftshantering

I arbetsytan för **Uppgiftshantering** visas alla uppgifter som enskilda personer har tilldelats vid registrerings-, avregistrerings- och övergångsprocesser. Om du vill visa uppgifterna för en process väljer du lämplig flik i det övre vänstra hörnet: **Registrering**, **Avregistrering** eller **Övergångar**. Som standard har endast personalansvariga åtkomst till **arbetsytan för uppgiftshantering**.

Fliken **registrering** innehåller en lista för **startar snart** som visar inkommande medarbetare och en lista över **nyanställda** som nyanställda har. I båda listorna kan du bara välja en medarbetare. När du väljer en medarbetare visas alla uppgifter som är relaterade till medarbetarens registrering på sidans högra sida. Fliken **Registrering** innehåller också en lista med **Alla uppgifter** som visar alla uppgifter för alla inkommande eller nyligen anställda. Slutligen innehåller den en lista över förfallna uppgifter och en lista över uppgifter som har tilldelats den aktuella användaren.

Fliken **avregistrering** innehåller en lista över medarbetare som lämnar företaget och en lista över medarbetare som redan har lämnat företaget. I båda listorna kan du bara välja en medarbetare. När du väljer en medarbetare visas alla uppgifter som är relaterade till medarbetarens avregistrering. Fliken **Avregistrering** innehåller också en lista med **Alla uppgifter** som visar alla uppgifter för alla medarbetare som säger upp sig eller är uppsagda. Slutligen innehåller den en lista över förfallna uppgifter och en lista över uppgifter som har tilldelats den aktuella användaren.

Fliken **Övergångar** innehåller en lista med **Alla uppgifter** som visar alla uppgifter för alla medarbetare som ska byta befattningar eller som nyligen ändrade befattningar. Det finns också en lista över förfallna uppgifter och en lista över uppgifter som har tilldelats den aktuella användaren.

På alla tre flikar kan personalmedhjälpare och chefer utföra följande aktiviteter:
- Använd en checklista för en medarbetare
- Uppdatera status för en uppgift
- Tilldela om en uppgift
- Uppdatera en uppgifts förfallodatum

> [!NOTE]
> Som standard visar fliken **Registrering** medarbetare som anställts de senaste sju dagarna. Om du vill ändra denna inställning, på sidan **Personalparametrar** på fliken **Allmänt** i fältet **Nyanställda** anger du en tidsram. Informationen i listan **Nyanställda** kan visas under ett specifikt antal dagar, månader eller år. Om du till exempel vill visa listan med medarbetare som anställdes under de senaste 14 dagarna anger du fältet **Period** som **14** och fältet **Enhet** som **Dagar**.
> På sidan **Personalparametrar** kan du även uppdatera datumintervallet för listorna över utsända och utsända medarbetare som visas på fliken **Avregistrering**. Inställningarna gäller även arbetsytan **Personalhantering**.

## <a name="setting-up-tasks"></a>Ställa in uppgifter

Du kan skapa uppgifter individuellt och sedan återanvända dem i flera checklistor. Du skapar en uppgift på sidan **Inställning av registrering** på fliken **Uppgifter** välj **Ny**.

Du kan också lägga till uppgifter direkt i en checklista. Om du vill lägga till en uppgift i en checklista, på sidan **Inställning av registrering** på fliken **Checklista**, antingen skapa en ny checklista för att lägga till uppgiften eller lägg till uppgiften i en befintlig checklista.

> [!NOTE]
> Om du lägger till en uppgift direkt i en checklista kan du inte återanvända den i andra checklistor.

I följande tabell beskrivs de fält som är tillgängliga när du skapar en uppgift med någon av dessa metoder.

| Fält           | Beskrivning |
|-----------------|-------------|
| Uppgift            | Ange namnet på uppgiften. |
| Beskrivning     | Ange en beskrivning av uppgift. |
| Valfritt        | Ange om uppgiften är valfri och endast till för information. |
| Uppgiftslänk       | Ange URL för en extern webbsida eller en särskild sida i programmet där användaren ska utföra uppgiften. Mer information finns i avsnittet [Uppgiftslänkar](#task-links). |
| Tilldelningstyp | Uppgifter kan tilldelas en viss arbetare, befattning eller befattningsgrupp, chef för den medarbetare som påverkas (det vill säga den medarbetare som ingår i processen vid arbete, utanför företaget eller övergångsprocessen) eller den medarbetare som påverkas. Välj typ av tilldelning. Mer information finns i avsnittet [tilldelningstyper](#assignment-types). |
| Har tilldelats     | Välj särskild arbetare, befattning eller befattningsgrupp som uppgiften ska tilldelas. |
| Kontaktperson  | Ange den person som ska kontaktas om det finns frågor om uppgiften. |
| Förfallodatum förskjutning | Ange hur många dagar före eller efter det introduktions-, uppsägnings- eller övergångsdatum som uppgiften har förfaller. Mer information finns i avsnittet [Förfallodatum för uppgift och fältet Förfallodatum för förskjutning](#task-due-dates-and-the-due-date-offset-field). |
| Instruktioner    | Ange instruktioner för att utföra uppgiften. Mer information finns i avsnittet [ instruktioner](#instructions). |

### <a name="task-links"></a>Uppgiftslänkar

En uppgiftslänk innehåller en länk till en extern webbsida eller en sida i programmet Dynamics 365. Du kan ange en uppgiftslänk om personen som har tilldelats en uppgift ska gå till en särskild webbsida eller en särskild sida i programmet Dynamics 365 för att slutföra uppgiften. När du skapar en uppgiftslänk kan du välja något av följande alternativ:

- **Menyalternativ** – Om du väljer det här alternativet visas en lista med alla sidor i programmet Dynamics 365. Välj en sida i listan.
- **URL** – Om du väljer det här alternativet anger du webbadressen till webbsidan som du vill att personen som är tilldelad uppgiften ska gå till. Den angivna sidan kan vara en sida som inte ingår i programmet Dynamics 365.
- **Arbetarinformation** – Om du väljer det här alternativet ska du välja ett av följande alternativ:

    - **Självbetjäningsåtgärder** för medarbetare – I det här alternativet visas en lista över sidor som är tillgängliga i **Självbetjäning för medarbetare**. Använd den om uppgiften som tilldelades den anställda måste ha utförts i **självbetjäning för medarbetare**. Om du till exempel vill att medarbetaren ska ange sin personliga kontaktinformation väljer du **Självbetjäningsåtgärder för medarbetaren** och väljer sedan **Personuppgifter&gt;Personuppgifter**.
    - **Åtgärder för arbetarhantering** – Det här alternativet visar en lista med sidor som är relaterade till arbetarens post, men som inte är tillgängliga för medarbetaren. Om du till exempel vill att uppgiftsägaren ska ange information som är specifik för en anställd arbetare, såsom kompensationsinformation, väljer du **Åtgärder för arbetarhantering**  och väljer sedan **Kompensation&gt;Fast kompensation**.

### <a name="assignment-types"></a>Tilldelningstyper

När en medarbetare anställs, sägs upp eller överförs, kan en eller flera checklistor väljas. När en checklista har markerats och anställnings-, uppsägnings- eller överföringsprocessen har slutförts, skapas uppgifter som tilldelas användarna för att spåra framsteg.

När en uppgift skapas tilldelas den till en viss användare. Vilken användare som en uppgift har tilldelats beror på vilken tilldelningstyp som valts för uppgiften. Följande värden är tillgängliga i fältet **Tilldelningstyp**: 

- **Arbetare** – Tilldela uppgiften till en viss arbetare. När du har valt det här värdet väljer du arbetaren i fältet **Tilldelad till**.
- **Befattning** – Tilldela uppgiften till en viss befattning. När du har valt det här värdet väljer du position i fältet **Tilldelad till**.

    En IT-tekniker kommer till exempel alltid att ansvara för att förbereda en bärbar dator för en ny medarbetare. I det här fallet, när du skapar konfigurationsuppgiften för den bärbara datorn, välj **Befattning** som tilldelningstyp och välj sedan **IT-tekniker** som befattning. När en medarbetare anställs och checklistan har tilldelats tilldelas konfigurationsuppgiften för datorn till den person som har den anställdas IT-tekniker vid den tidpunkt då anställningsåtgärden registreras.

- **Grupp** – Tilldela uppgiften till en grupp med befattningar (tilldelningsgrupp). När du har valt det här värdet väljer du gruppen i fältet **Tilldelad till**. Mer information finns i avsnittet [Skapa uppdragsgrupper (valfritt)](#setting-up-assignment-groups-optional).
- **Chef** – Tilldela uppgiften till chefen för den medarbetare som är anställda, uppsagda eller överförda.

    > [!IMPORTANT]
    > När en checklista tillämpas kan chefen inte fastställas om ingen befattning har tilldelats till den anställda, uppsagda eller överförda medarbetaren. I detta fall tilldelas uppgiften checklistas ägare. Mer information finns i avsnittet [Konfigurera checklista](#setting-up-checklists).

- **Medarbetare** – Tilldela den medarbetare som är anställda, uppsagda eller överförda.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Förfallodatum för uppgift och fältet Förfaller till förfallodatum

Uppgiftens förfallodatum baseras på anställningens startdatum, uppsägningsdatum eller övergångsdatum. Vissa uppgifter måste slutföras före medarbetarens startdatum, medan andra uppgifter kan slutföras efter. När du definierar en uppgift ställer du in fältet **förfallodatum för förskjutning** för att ange ett förfallodatum som är relativt startdatumet, uppsägningsdatumet eller övergångsdatumet. En IT-tekniker måste till exempel förbereda en bärbar dator för en ny medarbetare två dagar före medarbetarens startdatum. I det här fallet, när du skapar konfigurationsuppgiften för den bärbara datorn, ställ in fältet till **förfallodatum för förskjutning** till **-2**. Om medarbetarens startdatum är 5 maj, förfaller uppgiften sedan till den 3 maj.

> [!NOTE]
> Förfallodatum kan justeras efter att uppgiften har skapats.

Förfallodatumen beräknas utifrån den kalender som är associerad med checklistan. Mer information finns i avsnittet [Konfigurera checklista](#setting-up-checklists).

### <a name="instructions"></a>Instruktioner

Komplicerade uppgifter kanske kräver flera steg eller kräver att personen som utför uppgifter tillhandahåller ytterligare information. I fältet **Instruktioner** kan du ange instruktioner eller ytterligare information för att hjälpa den person som är tilldelad uppgiften att slutföra den.

## <a name="setting-up-checklists"></a>Ställa in checklistor

En checklista är en grupp med uppgifter. Du kan skapa så många checklistor som du behöver och du kan tilldela samma uppgifter till flera checklistor. När du skapar en checklista anger du en ägare och en kalender.

Om fältet **Tilldelningstyp** för en uppgift har ställts in som **Befattning**, **Chef** eller **Grupp**, men ingen specifik individ kan härledas från uppdragstypen, uppgiften kommer att tilldelas checklistans ägare. Här följer några exempel på situationer där uppgifter tilldelas till ägaren av checklistan:

- Ingen befattning tilldelas den anställde som anställs eller sägs upp. Eftersom medarbetaren inte har någon befattningstilldelning kan chefen inte fastställas.
- Fältet **Tilldelningstyp** anges till **Befattning**, men ingen medarbetare tilldelas befattningen vid den tidpunkt då uppgiften skapas. Till exempel uppgiften **Ställ in bärbar dator** tilldelas till befattningsnummer 000876 (**Teknisk supportspecialist**). När en medarbetare anställs tilldelas ingen medarbetare befattning 000876. Därför skapas en uppgift för checklisteägare.
- Fältet **Tilldelningstyp** anges till **Grupp**, men ingen medarbetare tilldelas befattningarna i gruppen vid den tidpunkt då uppgiften skapas.

Den kalender som har angetts för en checklista används för att beräkna förfallodatumet för uppgifter som ingår i checklistan. Arbetsdagar och ej arbetsdagar definieras i kalenderinställningarna. Arbetsdagar inkluderas när förfallodatumet för uppgifter beräknas, och ej arbetsdagar exkluderas. Ej arbetsdagar inkluderar helger och semestrar. 

När en kalender har ställts in associeras den med en checklistemall. På så sätt beräknas förfallodatumet för alla uppgifter i checklistan på samma sätt. Du kan ställa in flera kalendrar, men bara en kalender kan kopplas till varje checklista.

## <a name="setting-up-assignment-groups-optional"></a>Ställa in tilldelningsgrupper (valfritt)

Ibland är en grupp personer ansvarig för en uppgift. En grupp av IT-arbetare kanske till exempel ansvarar för att förbereda datorer för nyanställning.

Följ dessa steg för att skapa en tilldelningsgrupp.

1. Välj **Nytt** på sidan **Grupptilldelning**.
1. Ange ett namn (till exempel **IT bärbar dator**) och en beskrivning av gruppen.
1. Välj **Spara**.
1. På snabbfliken **Medlemmar** väljer du **Lägg till**.
1. Markera alla befattningar som ansvarar för uppgiften i fältet **Befattningar**.

När en tilldelningsgrupp har skapats kan den väljas när en uppgift skapas. Om du vill välja en specifik grupp för en uppgift måste du välja **Grupp** i **Tilldelningstypen**. Gruppen som du skapar kan sedan väljas i fältet **Tilldelad**.

> [!IMPORTANT]
> Om en uppgift tilldelas en grupp markeras uppgiften som **Slutförd** när en person i gruppen slutför den. Uppgifterna skapas vid tiden för anställning, uppsägning eller övergång. De skapas för de användare som tilldelas befattningarna som ingår i gruppen.

## <a name="setting-up-task-groups-optional"></a>Ställa in uppgiftsgrupper (valfritt)

En registrerings-, avregistrerings- eller övergångsperiod kan innefatta många olika uppgifter. För att göra det enklare att tilldela alla nödvändiga uppgifter till en checklista kan du skapa valfria uppgiftsgrupper för att kategorisera relaterade uppgifter. Till exempel personal-, IT- och löneavdelningarna måste alla slutföra specifika uppgifter för att anställa en ny medarbetare. Därför skapar du följande uppgiftsgrupper: **Personal**, **IT** och **Lön**. När du sedan skapar en uppgift kan du koppla en av dessa uppgiftsgrupper till den.

När du vill lägga till en uppgift i en checklista, kan du filtrera listan med uppgifter efter den uppgiftsgrupp som önskad uppgift har tilldelats till. När du skapar en checklistemall kan du till exempel filtrera listan så att bara de IT-uppgifter som har tilldelats till **IT**-uppgiftsgruppen visas. Därför kan du säkerställa att endast de relevanta IT-uppgifterna väljs.

## <a name="using-checklists"></a>Använda checklistor

När en medarbetare anställs, sägs upp eller överförs, kan en eller flera checklistor väljas. Förfallodatum för uppgifter och arbetstilldelningar skapas efter att anställnings-, uppsägnings- eller övergångsperioden har slutförts. När du till exempel väljer knappen **Anställ** eller **Anställ och lägger till detaljer**, skapas uppgifter för enskilda personer baserat på tilldelningstypen.

Varje uppgift tilldelas ett förfallodatum genom att man adderar eller subtraherar förfallodatum förskjutningen från medarbetarens startdatum. Mer information finns i avsnittet [Förfallodatum för uppgift och fältet Förfallodatum för förskjutning](#task-due-dates-and-the-due-date-offset-field).

Om du använder personalåtgärder skapas uppgifterna när knappen **Slutför** har valts eller åtgärden har godkänts.

I arbetsytan i **Uppgiftshantering** kan du tillämpa en checklista på en medarbetare genom att markera medarbetaren på den enkla listsidan eller detaljsidan och sedan välja **Tillämpa checklista**. Värdet i fältet **Måldatum** används vid beräkning av uppgifternas förfallodatum. Vanligtvis ska måldatumet matcha medarbetarens anställnings-, uppsägnings- eller övergångsdatum.

Du kan också tillämpa en checklista för en medarbetare genom att öppna sidan **Arbetare** och välja **Checklistor** på menyn.

## <a name="completing-tasks"></a>Slutföra uppgifter

På sidan **Självbetjäning för medarbetare** kan en medarbetare visa alla uppgifter som är tilldelade till dem. För varje tilldelad uppgift visas **uppgift**, **beskrivning**, **instruktioner** och **kontaktpersonens** värden. Dessutom kan medarbetaren öppna den associerade externa webbsidan eller den associerade sidan i programmet Dynamics 365 för varje uppgift.

Uppgifter kan också visas på standardinstrumentpanelen. Gör så här om du vill visa uppgifter på standardinstrumentpanelen:
1. Gå till **Användaralternativ – Inställningar – Uppgiftshantering** 
2. Välj **Visa uppgifter på standardinstrumentpanel** till **På**.  

>[!Note] 
>Funktionen **Uppgiftshantering** måste vara aktiverad i **Funktionshantering** för att alternativet ska visas i **Användaralternativ**.

Uppgifter kan markeras som **pågår**, **annullerad** eller **slutförd**. Om en uppgift tilldelas en grupp markeras den som **Slutförd** när en person i gruppen slutför den.

Uppgifter kan också tilldelas om.
