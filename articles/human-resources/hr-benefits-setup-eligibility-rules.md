---
title: Konfigurera berättiganderegler och alternativ
description: Ange berättiganderegler och optioner för hantering av förmåner i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3aae50b8f7fac6991f187ced44f7d122eb7ed40824bd2d53265fa06bfa87dd6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756134"
---
# <a name="configure-eligibility-rules-and-options"></a>Konfigurera regler och alternativ för berättigande 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

När du har konfigurerat de nödvändiga parametrarna för förmånshantering kan du skapa berättiganderegler, buntar, perioder och program som du vill associera med dina förmånsplaner.

Berättiganderegler används för att fastställa om en medarbetare är berättigad till en plan. Medarbetare måste uppfylla villkoret om minst en regel för att kunna anses vara berättigade till förmånen. Du har till exempel två regler för en plan. Den första regeln (rad 1) anger att medarbetartypen måste vara **medarbetare**. Den andra regeln (rad 2) anger att medarbetartypen måste vara heltidsanställd. Därför är medarbetare som uppfyller regel 1 berättigade även om de bara är deltid anställda.

Du kan dock skapa en enda regel som har flera villkor. I detta fall måste anställda uppfylla alla villkor i regeln för att anses vara berättigade till förmånen Du har till exempel en regel som kallas **Heltidsanställd**. Den här regeln anger att medarbetartypen **Medarbetare** *och* medarbetaren måste vara anställd heltid. Därför måste medarbetarna uppfylla båda villkoren i regeln för att vara berättigade.

> [!IMPORTANT]
> Minst en berättiganderegel måste kopplas till varje förmånsplan. Du kan associera flera regler med en förmån.

## <a name="create-an-eligibility-rule"></a>Skapa en berättiganderegel

Berättiganderegler definierar vilka medarbetare som kan registrera varje förmånsplan. När du har definierat berättiganderegler tilldelar du dem till förmånsplaner. Sedan kan du bearbeta anmälan av berättigade för att se vilka medarbetare som är berättigade till respektive plan. 

Medarbetarna kan välja förmånsplaner under den öppna anmälan. Om de är olämplig för en förmånsplan baserat på berättiganderegler efter att de redan har registrerats avregistreras de inte automatiskt. När en livshändelse inträffar som påverkar planberättigande initieras vanligtvis en anmälningsperiod för medarbetaren för att välja vilka planer de är berättigade till. 

1. I arbetsytan **olämplig** under **inställningar**, välj **Förmånsberättiganderegler och alternativ**.

2. På fliken **berättiganderegler** väljer **Ny** för att skapa en berättiganderegel. Om du vill se planer som associeras med en stödberättigande regel, välj **Kopplade planer**.

3. Ange värden för de följande fälten.

   | Fält | beskrivning |
   | --- | --- |
   | **Berättiganderegel** | En unik identifierare för berättiganderegeln. |
   | **Beskrivning** | En beskrivning för berättiganderegeln. |
   | **Giltig från datum och tid** | Startdatum för berättiganderegeln. | 
   | **Giltig till datum och tid** | Slutdatum för berättiganderegeln. |
   | **Användare medarbetartyp** | Anger om medarbetarens medarbetartyp av förmånsberättiganderegel. |
   | **Typ av arbetare** | Typen av arbetare om växla för **Använd medarbetartyp** är inställd på **ja**. |
   | **Använd medarbetarstatus** | Anger om medarbetarens medarbetarens anställningsstatus i förmånsberättiganderegel. |
   | **Status** | Typen av medarbetarstatus om växla för **Använd medarbetarstatus** är inställd på **ja**. Om **Använd medarbetarstatus** är inställd på **Nej** används inte fältet. |
   | **Använd anställningskategori** | Anger om medarbetarens värde **Anställningskategori** som en del av förmånsberättiganderegeln. | 
   | **Anställningskategori** | Medarbetarens anställningskategori om växlingsknappen **Använd anställningskategori** är inställd på **Ja**. |
   | **Använd ny anställningsregel** | Anger om en ny anställnings värde för ny anställningsperiod ska användas som en del av regeln för förmånsberättigande. |
   | **Anmälningsperiod** | Tidsperiod då den nya anställningsanmälan är tillåten. Om du även ställer in detta i parametrar har inställningen för parametrar företräde framför denna. |
   | **Använd tidigare anställningsstatus** | Anger om en anställds tidigare anställningsstatus ska användas som en del av reglerna för förmånsberättigande. Till exempel kan du ange en behörighetsregel som avstår från en täckningsväntetid för alla anställda som har övergått från status **Slutat** till status **anställd** inom 90 dagar efter sin tidigare anställning. |

4. Under **ytterligare villkor** väljer du följande alternativ och lägger till information efter behov.

   | Alternativ | beskrivning |
   | --- | --- |
   | **Berättigad ålder** | Anger åldersintervall eller de intervall som krävs för att uppfylla villkorsregeln. |
   | **Berättigad avdelning** | Anger avdelningen eller avdelningarna som en medarbetare måste vara i att uppfylla berättiganderegeln. |
   | **Berättigad anställningstyp** | Anger anställningstyp eller typer som en medarbetare måste kategoriseras till för att uppfylla berättiganderegeln. Till exempel heltid eller deltid. |
   | **Berättigat jobb** | Anger det jobb eller de jobb som uppfyller berättiganderegeln. Jobben är kopplade till befattningar och befattningar fylls i av medarbetare. |
   | **Berättigad jobbfunktion** | Anger den jobbfunktion eller de jobbfunktioner som uppfyller berättiganderegeln. Till exempel försäljningsarbetare eller tekniker. |
   | **Berättigad jobbtyp** | Anger den jobbtyp eller de jobbtyper som uppfyller berättiganderegeln. Till exempel tjänstemän eller chefer. |
   | **Berättigad juridisk person** | Anger den juridiska personen eller de juridiska personer som är giltiga för berättiganderegeln. Till exempel Contoso Entertainment System USA. |
   | **Region för berättigad kompensation** | Anger den medarbetarplats som uppfyller berättiganderegeln. Till exempel centrala USA. |
   | **Berättigad befattning** | Anger den befattning eller de befattningar som uppfyller berättiganderegeln. Till exempel personalmedarbetare eller anställande chef. |
   | **Berättigad befattningstyp** | Anger den befattningstyp eller de befattningstyper som uppfyller berättiganderegeln. Till exempel heltid. |
   | **Berättigad delstat** | Anger de stater eller provinser som uppfyller berättiganderegeln. Till exempel North Dakota USA eller British Columbia, Kanada. |
   | **Berättigande anställningsvillkor** | Anger de anställningsvillkor som uppfyller berättiganderegeln. Till exempel provanställning eller gruppavtal. |
   | **Berättigad fackförening** | Anger det fackföreningsmedlemskap som uppfyller berättiganderegeln. Till exempel gaffeltruckförare i USA.</br></br>När du använder en fackföreningsbaserad berättiganderegel måste medarbetarens fackföreningspost ha slutdatumet ifyllt. Du kan inte lämna det tomt. |
   | **Berättigat postnummer** | Anger de postnummer som uppfyller berättiganderegeln. Exempelvis 58104. |

5. Under **ytterligare detaljer** kan du visa följande ytterligare information.

   | Fält | beskrivning |
   | --- | --- |
   | **Fältet Berättigad användare** | Anger ytterligare berättiganderegler baserat på kunddefinierade fält. |
   | **Berättigandetyp** | Anger den kriteriekategori du valde under **ytterligare villkor**. |
   | **Berättigande referens** | Anger de värden du valde under **ytterligare villkor**. |
   | **Beskrivning** | Den beskrivning du valde under **ytterligare villkor**. |

6. Välj **Spara**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Använda anpassade fält i berättiganderegler

[Anpassade fält](hr-developer-custom-fields.md) kan skapas i Human Resources för att spåra ytterligare information. Dessa fält kan läggas till direkt i användargränssnittet och en kolumn läggs dynamiskt till i det underliggande registret.  

Anpassade fält kan användas i berättigandeprocessen. Berättiganderegler kan använda ett eller flera anpassade fältvärden för att bestämma en medarbetares berättigande.  Om du vill lägga till ett anpassat fält i en befintlig regel eller skapa en ny regel går du till **Förmånshantering > Länkar > Inställningar > Berättiganderegler > Berättigande av anpassat fält**. På den här sidan kan du skapa en regel som använder ett eller flera anpassade fält, och du kan definiera flera värden för varje anpassat fält för att fastställa berättigande.

Följande register har stöd för anpassade fält som kan användas vid berättigandebearbetning:

- Arbetare (HcmWorker)  
- Jobb (HcmJob)  
- Befattning (HcmPosition)  
- Befattningsdetaljer (HcmPositionDetail)  
- Befattningstilldelning för arbetare  
- Anställning (HcmEmployment)  
- EmploymentDetails (HcmEmploymentDetails)  
- Jobbdetaljer (HcmJobDetails)  

Följande anpassade fälttyper stöds vid berättigandebearbetning:

- Text  
- Plocklista  
- Antal  
- Decimal  
- Kryssruta  

I följande tabell visas anpassad information om berättigandeformulär för fält.

| Fält  | beskrivning |
|--------|-------------|
| Namn | Namn på kriteriet som skapas. |
| Tabellnamn | Registernamnet som innehåller det anpassade fält som används för berättiganderegeln. |
| Fältnamn | Det fält som ska användas för berättiganderegeln. |
| Typ av operator | Visar operatorn som används i den anpassade berättigandekonfigurationen för fält. |
| Värde | Visar värdet som används i den anpassade berättigandekonfigurationen för fält. |

## <a name="eligibility-logic"></a>Berättigandelogik

I följande avsnitt beskrivs hur du beskriver hur du berättigar till förmåner.

### <a name="rules-assigned-to-a-plan"></a>Regler som tilldelats en plan 
När flera berättiganderegler har tilldelats till en förmånsplan måste en medarbetare uppfylla minst en regel för att vara berättigad att registrera sig i förmånsplanen.  I följande exempel måste medarbetaren antingen uppfylla kraven i regeln för **jobbtyp** eller regeln för **aktiva medarbetare**.

![Medarbetaren måste antingen uppfylla kraven i regeln för jobbtyp eller regeln för aktiva medarbetare.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Kriterier inom en berättiganderegel 
I en regel definierar du de kriterier som utgör regeln. I ovanstående exempel är kriterierna för regeln om **jobbtyp** var Jobbtyp = Chefer. Medarbetaren måste därför vara en VD för att kunna vara berättigad. Detta är en regel där det bara finns ett kriterium i regeln.

Du kan definiera regler som har flera kriterier. När du definierar flera kriterier i en berättiganderegel måste en medarbetare uppfylla alla kriterier i regeln för att kunna välja förmånsplanen. 

Regeln för **aktiva medarbetare** ovan består till exempel av följande kriterier. För att medarbetaren ska vara behörig enligt regeln **Aktiva medarbetare** måste medarbetaren vara anställd i den juridiska personen USMF *och* ha befattningstypen heltid.  

![Kriterier inom en berättiganderegel.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Flera villkor inom kriterier

Regler kan utvidgas ytterligare om du vill använda flera villkor inom ett enda kriterium. Medarbetaren måste uppfylla minst ett villkor för att vara behörig. Regeln för **aktiva medarbetare** kan utökas ytterligare för att inkludera medarbetare som också är deltidsanställda, baserat på exemplet ovan. Följden blir att medarbetaren nu måste vara en medarbetare i USMF *och* antingen heltids- eller deltids medarbetare.  

![Flera villkor inom kriterier.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Berättigandevillkor inom ett anpassat fältkriterium 
På liknande sätt kan anpassade fält användas när du skapar berättiganderegler och arbetar på samma sätt. Du kanske till exempel vill erbjuda återbetalning på Internet till de Fargo- och Köpenhamn-medarbetare som arbetar hem, eftersom Internetkostnaderna är högre på dessa platser. Det gör du genom att skapa två anpassade fält: **Kontorsplats** (plocklista) och **Arbeta hemifrån** (kryssruta). Skapa sedan en regel som kallas **WFH-medarbetare**. Kriteriet för regeln är var **Kontorsplats = Fargo** eller **Köpenhamn** *och* där **Arbeta hemifrån = Ja**.

De anpassade berättigandereglerna måste ställas in på det sätt som visas i bilden nedan. 

![Berättigandevillkor inom ett anpassat fältkriterium.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Konfigurera buntar

Buntar är en uppsättning relaterade förmånsplaner. Du kan använda förmånsbuntar för att gruppera förmånsplaner som en medarbetare måste välja för att kunna registrera vissa förmånsplaner som kan vara beroende av andra anmälningar till förmånsplaner. Exempel på när du kan vilja använda en bunt är:

- En hälsoplanbunt som innehåller avdragsgill sjukförsäkring med ett tillhörande hälsosparandekonto (HSA).

- En livförsäkringsplan med en obligatorisk medarbetares försäkringsplan buntad med en livsberoendeplan. Det innebär att en medarbetare inte kan välja en beroende livstäckning utan att registrera den anställdes täckning.

1. I arbetsytan **olämplig** under **inställningar**, välj **Förmånsberättiganderegler och alternativ**.

2. På fliken **buntar** väljer du **ny** för att skapa en bunt. Om du vill se planer som associeras med en bunt, välj **Kopplade planer**.

3. Ange värden för de följande fälten.

   | Fält | beskrivning |
   | --- | --- |
   | **Bunt** | En unik identifierare för bunten. |
   | **Beskrivning** | En beskrivning av bunten. |
   | **Rubrik** | Anger om ett av planerna i bunten måste markeras som huvudplan. Huvudplanen måste väljas under öppen registrering som en del av bunten innan förmånsadministratören kan bekräfta val av medarbetarens förmåner. |
   | **Giltig från datum och tid** | Det datum och tid då bunten blir aktiv. |
   | **Giltig till** | Det datum då bunten går ut. Standard är 12/31/2154, vilket betyder aldrig. |

4. Välj **Spara**.

## <a name="configure-periods"></a>Konfigurera perioder

Perioder anger när förmåner ska gälla och när medarbetare tillåts registrera sig. Du kan skapa hur många perioder du vill för att hålla öppna anmälan och förmånens omfattningsperioder. Förmånsplanens åt kanske eller inte följer ett kalenderår. 

1. I arbetsytan **olämplig** under **inställningar**, välj **Förmånsberättiganderegler och alternativ**.

2. På fliken **Perioder** väljer du **ny** för att skapa en period. Om du vill köra en process som kopplar alla giltiga aktiva förmånsplaner till förmånsperioden väljer du **koppla planer**. Om du vill se planer som associeras med en bunt, välj **Kopplade planer**. 

3. Ange värden för de följande fälten.

   | Fält | beskrivning |
   | --- | --- |
   | **Period** | En unik identifierare för perioden. |
   | **Giltig från datum och tid** | Startdatum och tid då förmånsperioden är aktiv. |
   | **Giltig till datum och tid** | Datum och tid då förmånsperioden är inaktiv. |
   | **Start för anmälan** | Startdatum för öppen registrering. Öppen registrering är när en medarbetare kan göra förmånsval i självbetjäningsförmåner. |
   | **Anmälningsperiodens slut** | Slutdatum för öppen registrering. |
   | **Ledig** | Anger om perioden är öppen baserat på systemdatumet och giltighet från och till datum och tider. | 
   | **Föregående period** | Anger förmånsperioden som föregår de valda förmånsperioderna. Den här informationen används under anmälan av förmånsberättigande för att tilldela planer, omfattningsalternativ och tilldelningar från föregående år. |
 
4. Välj **Spara**.

## <a name="use-a-flex-credit-program"></a>Använd ett flexkreditprogram

Du kan använda flexkreditprogram för att registrera anställda i förmåner enligt ett förutbestämt antal flexsaldon. Medarbetarna kan välja hur de vill fördela sina flexkredit. Om t.ex. en medarbetare täcks av sin makes sjukförsäkringsplan kan de vilja använda de krediter de annars skulle ha använt för hälsoskydd mot andra förmåner.

1. I arbetsytan **olämplig** under **inställningar**, välj **Förmånsberättiganderegler och alternativ**.

2. På fliken **Perioder** välj **Flexkreditprogram**.

3. Välj ett flexkreditprogram som ska användas. Fältet innehåller följande information.

   | Fält | beskrivning |
   | --- | --- |
   | ID för förmånens kredit | Det unika ID:t för flexkreditprogrammet. |
   | Beskrivning | En beskrivning av flexkreditprogrammet. | 
   | Från-datum | Det datum då flexkreditprogrammet blir aktivt. |
   | Till-datum | Slutdatumet för flexkreditprogrammet. Du kan lämna standardvärdet (12/31/2154) för att ange att flexkreditprogrammet inte har ett förfallet förfallodatum. |
   | Totalt kreditvärde | Det antal tillgodohavanden som varje medarbetare måste använda för sina förmåner. |
   | Regel för proportionell fördelning | Den regel som ska användas för att allokera flexkrediter när en medarbetare anställs i mitten av den flexkreditperioden. </br></br><ul><li>**Ingen** – medarbetaren får inga flexkrediter om de anställs efter att flexprogramperioden har inletts.</li><li>**Fullständig kredit** – medarbetaren får hela beloppet för flexsaldon, oavsett när de anställs.</li><li>**Proportionell fördelning** – medarbetaren får ett proportionellt antal flexsaldon baserat på startdatumet.</li></ul> |
   | Formel för proportionell fördelning av flexkredit | Den regel som ska användas för att allokera flexkrediter för medarbetare som anställs i mitten av flexkreditperiodens förmånsperiod. Proportionell fördelning baseras på anställningens startdatum. Detta fält används endast om du väljer **Proportionell fördelning** i fältet **Regel för proportionell fördelning**. </br></br><ul><li>**Dagligen** – Proportionell fördelning av antalet flexsaldon som en medarbetare får på dagnivå. Det totala antalet flexsaldon divideras med antalet dagar i perioden. Om till exempel din förmånsperiod är 400 dagar delas det totala antalet flexsaldon med 400 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per dag.</li><li>**Aktuell månad** – Proportionell fördelning av antalet flexsaldon som en medarbetare får från månadsnivån, avrundad till aktuell månad. Det totala antalet flexsaldon divideras med antalet månader i perioden. Om till exempel din förmånsperiod är 15 månader delas det totala antalet flexsaldon med 15 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per månad.</li><li>**Följande månad** – Proportionell fördelning av antalet flexsaldon som en medarbetare får från månadsnivån, avrundad till nästa månad. Det totala antalet flexsaldon divideras med antalet månader i perioden. Om till exempel din förmånsperiod är 15 månader delas det totala antalet flexsaldon med 15 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per månad.</li></ul> |
   
   Kontrollera att varje förmånsplan endast är anmäld för ett flexkreditprogram per förmånsperiod. I annat fall vet inte systemet vilket flexkreditprogram som ska användas för att bevilja flexsaldon och du kommer att stöta på problem. 

## <a name="configure-programs"></a>Konfigurera program

Program är en uppsättning förmånsplaner som delar en gemensam uppsättning regler för berättigande. Du kan definiera berättiganderegler för hela programmet i stället för varje enskild plan. Till exempel ett Contoso Kanada FTE-program eller ett Contoso Europa program på verkställande nivå. 

1. I arbetsytan **olämplig** under **inställningar**, välj **Förmånsberättiganderegler och alternativ**.

2. På fliken **Program** väljer du **ny** för att skapa ett program. Om du vill göra undantag för medarbetare som inte uppfyller kraven för berättiganderegler väljer du **Åsidosätt berättiganderegel**. Om du vill se planer som associeras med ett program, välj **Kopplade planer**.

3. Ange värden för de följande fälten.

   | Fält | beskrivning |
   | --- | --- |
   | **Program** | En unik identifierare för programmet. |
   | **Beskrivning** | En beskrivning av programmet. | 
   | **Giltig från datum och tid** | Det datum och tid då programmet blir aktivt. |
   | **Giltig till datum och tid** | Det datum och tid då programmet går ut. Standard är 12/31/2154, vilket betyder aldrig. |
   | **Vänteperiod för försäkringen** | Den period en medarbetare måste vänta innan den börjar gälla för förmånsprogrammet. |
   | **Vänteperiod för avdrag** | Den period en medarbetare väntar innan avdragen börjar gälla för förmånsprogrammet. |
   | **Berättiganderegler** | Välj de berättiganderegler som ska användas för förmånsprogrammet. Du definierar reglerna för berättigande på fliken **berättiganderegler** på den här sidan. |
   
4. Välj **Spara**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
