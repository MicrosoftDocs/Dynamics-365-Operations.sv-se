---
title: Hantering av förmåner – översikt
description: I denna artikel finns en översikt över funktionen för förmånshantering i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f008c273a3088353c33ae8c4b0b3cbc6b274fbcf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901159"
---
# <a name="benefits-management-overview"></a>Hantering av förmåner – översikt


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda. Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder. Med förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ. Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.

- Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer. Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.
- Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.
- Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.
- En anmälan online av förmåner är en enkel upplevelse för dina anställda.
- Kvalificerad bearbetning av livshändelse stöder framtida livshändelser.

Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.

> [!NOTE]
> Du kan nu anpassa sidorna för förmånshantering. Anpassade fält relaterade till som hör till disponeringssatser kan läggas till på sidan **Disponeringsalternativ** för förmånsplaner. Mer information om arbete med anpassade fält finns i [Anpassade fält](hr-developer-custom-fields.md).
>
> ![Anpassade fält för förmånshantering](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Aktivera hantering av förmåner

Den här artikeln beskriver hur du aktiverar funktionerna i personal. Det förklarar också vilka befintliga funktioner i Personal som ersätts av Förmånshantering och vilka som inaktiveras när du har aktiverat förmånshanteringen.

> [!IMPORTANT]
> När du har aktiverat hantering av förmåner i miljön **produktion** kan du inte inaktivera den. Vi rekommenderar att du aktiverar och testar förmånshantering i en miljö med **begränsat läge** innan du aktiverar den i en miljö för **produktion**. Det finns betydande skillnader mellan den tidigare förmånsfunktionen och nya fördelar för hanteringsfunktioner som kräver ytterligare inställningar och bör testas innan de kan placeras i produktionen.

Mer information finns i [Hantera funktioner](hr-admin-manage-features.md).

## <a name="process-overview"></a>Processöversikt

När du konfigurerar förmåner måste du utföra följande uppgifter:

1.  Ange obligatorisk förmånsinformation.
2.  Ange valfri förmånsinformation.
3.  Ställa in förmånsplaner.
4.  Ställa in flexkreditprogram (valfri).
5.  Konfigurera obligatorisk medarbetarinformation.
6.  Konfigurera valfri medarbetarinformation.
7.  Bearbeta medarbetare för att fastställa kvalifikationer.
8.  Medarbetare väljer planer via medarbetarnas självbetjäning (valfritt).
9.  Bekräfta val av medarbetarplan.
10. Bearbetning av livshändelse (valfri).
11. Kursuppdateringar (valfritt).

## <a name="set-up-required-benefit-information"></a>Ange obligatorisk förmånsinformation

Innan medarbetare kan anmälas till planerna måste flera komponenter ställas in:

- **Parametrar för förmånshantering** – De här inställningarna delas av alla företag. Du kan ställa in standardkoder, aktivera alternativet **Årlig inkomst av förmåner** ange en standardbetalningsfrekvens för nyanställningar och aktivera händelser för livslängd. Mer information finns i [Ställa in parametrar för förmånshantering](hr-benefits-setup-parameters.md).
- **Berättigandealternativ för personlig kontakt** – Personliga kontakter är de personer som antingen är beroende eller mottagare av de planer som upprättas. Vanligtvis är de underordnade, make/maka eller förtroendeorganisationer. För mer information, se [Konfigurera berättigandealternativ för personlig kontakt](hr-benefits-setup-contact-eligibility-options.md).
- **Disponeringsalternativ** – Ange vilka typer av disponering som ska vara tillgängliga för en plan. Definiera specifikt vem som ska omfattas eller hur mycket disponering som är tillgänglig. Mer information finns i [Skapa disponeringsalternativ](hr-benefits-setup-coverage-options.md).
- **Plantyper** – Ställ in vilka typer av planer som kommer att vara tillgängliga när du skapar en förmånsplan. Några exempel på plantyper omfattar **Tandvård**, **Vision** och **Besparingar**. Vissa viktiga inställningar för plantypen bestämmer vilka inställningar som finns tillgängliga i förmånsplanen. Mer information finns i [Skapa plantyper](hr-benefits-setup-plan-types.md).
- **Berättiganderegler** – berättiganderegler används för att fastställa om en medarbetare är berättigad till en plan. Minst en berättiganderegel måste kopplas till varje förmånsplan. För mer information, se [Konfigurera regler och alternativ för berättigande](hr-benefits-setup-eligibility-rules.md).
- **Betalningsfrekvenser** – Betalningsfrekvenser krävs när förmånssatser konfigureras. Betalningsfrekvensen som används med en sats gör det lättare att identifiera det belopp som medarbetaren och/eller arbetsgivaren är skyldig, varje vecka, månad eller år. Mer information finns i [Ställa in betalningsfrekvenser](hr-benefits-setup-payment-frequencies.md).
- **Tariffer** – Tariffer anger hur mycket en förmån kommer att kosta, antingen medarbetaren eller arbetsgivaren. Om pengar ska fördelas tillbaka till en medarbetare (till exempel en kredit mot ett gymkort) anges ett negativt tal. Mer information finns i [Konfigurera tariffer](hr-benefits-setup-rates.md).
- **Nivåpriser** – Nivåpriser används när en tariff måste ändras baserat på vissa kriterier. Den vanligaste nivåpriser är en enskild tariff som baseras på ålder. Dock kan dubbla nivåpriser också ställas in, där tariffen kan ändras baserat på kön, ålder eller andra kriterier.
- **Avdrag** – Avdragen är i princip rubrikinformation/koder som kommer att skickas vidare till lönesystemet för att identifiera avdraget för förmånen. Du måste ställa in dessa avdrag eftersom de krävs i förmånsplanen. Mer information finns i [Konfigurera avdrag](hr-benefits-setup-deductions.md).
- **Förmånsperioder** – En förmånstid är den period då anställda kommer att ha förmånstäckning. Det kallas också för ett planår. De öppna anmälningsperioderna ställs också in här.

## <a name="set-up-optional-benefit-information"></a>Ange valfri förmånsinformation

Följande komponenter behöver inte ställas in för att du ska kunna skapa en förmånsplan:

- **Program** – Ett program är en uppsättning förmåner som gäller för samma berättiganderegler. Alla på försäljningsavdelningen kanske till exempel får en mobiltelefon.
- **Buntar** – En bunt är en grupp fördelar, där en plan måste väljas innan alternativet att välja ytterligare planer är tillgängligt. En hög avdragsgill medicinsk plan kan till exempel buntas ihop med ett hälsosparkonto (HSA).
- **Livscykeltyper** – Livscykelhändelser är händelser som gör det möjligt att ändra en medarbetares täckning. Händelsetyper för livslängd är kopplade till en plantyp. En typ av medicinsk plan kan till exempel tillåta ändringar i planer på grund av födsel eller kön, eller på grund av en förändring i civilståndet. En försäkringsplanstyp kanske inte tillåter ändringar på grund av livstidshändelser. Mer information finns i [konfigurera livshändelsetyper](hr-benefits-setup-life-event-types.md).
- **Väntedagar och väntetider** – En täcknings väntetid kan fastställas på en förmånsplan. En nyanställd medarbetare kanske till exempel bara kan anmäla sig till en 401(k) efter tre månaders anställning. I detta fall är väntetiden tre månader. Väntetider används i väntetiden om nya anmälningar bara kan bearbetas och skickas till leverantören på en viss dag i månaden. Om t.ex. 401(k) anmälan endast kan behandlas den femtonde i månaden, efter tre månaders anställning, är den inställda perioden tre månader och väntetiden är den femtonde. Mer information finns i [Konfigurera väntetider](hr-benefits-setup-waiting-days.md) och [Konfigurera vänteperioder](hr-benefits-setup-waiting-periods.md).
- **Orsakskoder** – Motiveringskoder används för att förklara varför en förmån kan förändras för en anställd. Mer information finns i [Ange orsakskoder](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Ställa in förmånsplaner

När du ställer in en förmånsplan måste du utföra följande steg innan medarbetare kan anmälas:

- Tilldela en förmånsperiod.
- Bifoga täckningsalternativ.
- Ange ett giltigt från- och giltigt till-datum på fliken **Allmänt**.
- Tilldela minst en berättiganderegel.
- Ställ in fältet **Tillåt/fortsätt anmälan** på fliken **Inställningar**.

Mer information om hur du ställer in förmånsplaner hittar du på [Ställ in förmånsplaner](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Ställa in flexkreditprogram (valfri)

Du kan använda flexkreditprogram för att registrera anställda i förmåner enligt ett förutbestämt antal flexsaldon. Medarbetarna kan välja hur de vill fördela sina flexkredit. Om till exempel medarbetare redan omfattas av make/makans hälsoförsäkringsplan, behöver de inte använda sina krediter för hälsotäckning. Därför kanske de vill använda dem för andra förmåner istället. Mer information om flexkreditprogram finns i [Ställa in flexkreditprogram](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Konfigurera obligatorisk medarbetarinformation

Innan du kan registrera medarbetare i förmåner måste du ange den information som krävs för dem. 

Medarbetaren måste ha en **Befattning** tilldelad. En **befattning** kan tilldelas medarbetaren på sidorna **arbetare** eller **befattning** genom att uppdatera **arbetstilldelningen**.  

Sedan måste medarbetaren anmälas till en fast kompensationsplan på startdatumet eller också måste de ha ett **lönebelopp för årslönen.** Innan en medarbetare tilldelas **fast kompensation** måste en **befattning** tilldelas. 

> [!NOTE] 
> **Startdatumet för den fasta kompensationen** kan inte in vara före **tilldelningsdatumet för befattningen**.

Om du har en medarbetare som tar emot kompletterande kompensation som provisioner kan du lägga till ett belopp för **årslön** från medarbetarposten. Personal kommer att använda beloppet **Årslön vid fastställande av täckningsbelopp**, istället för det **årliga beloppet för fast ersättning**. Den **Årslönen** måste vara giltig för medarbetarens startdatum eller början av förmånsperioden, beroende på vilket som är senaste. En befattning krävs dock inte för att tilldela **Årlig inkomst av förmåner**. Aktivera funktionen **Årlig inkomst** av förmåner genom att gå till sidan **delade Human Resources-parametrar** på fliken **Förmåner**. Funktionen är som standard avstängd.

> [!IMPORTANT]
> Om både en **fast kompensation** och **bestämda årslönsbelopp** registreras för en medarbetare, kommer den **bestämda årslönen** att användas vid fast ställande av täckningsbelopp. Dessutom, i avsnittet **Anställningsinformation** på sidan **Arbetare** måste du välja ett värde i fältet **Förmånslönefrekvens**.

## <a name="configure-optional-employee-information"></a>Konfigurera valfri medarbetarinformation
När du skapar en förmånsplan som bygger på kön eller ålder måste du ange ett födelsedatum och kön för medarbetaren för att beräkna förmånskostnaden.

## <a name="process-employees-to-determine-eligibility"></a>Bearbeta medarbetare för att fastställa kvalifikationer
Innan medarbetare kan anmälas till planer körs bearbetning av berättigande för att fastställa vilka planer de är berättigade till. Du kan visa resultatet av berättigandeprocessen i **visningsprogrammet för processresultat**. Mer information finns i [Bearbeta anmälningsberättigande](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Medarbetare väljer planer via **medarbetarnas självbetjäning** (valfritt)

När öppen anmälan inträffar är medarbetare nyanställen, eller så uppstår en livstidshändelse, kan medarbetarna välja eller uppdatera sina förmåner via **medarbetarnas självbetjäning**. Mer information finns i [Konfigurera självbetjäning för medarbetare](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Bekräfta val av medarbetarplan

Förmånerna som medarbetarna väljer måste bekräftas innan medarbetarna anses vara registrerade i dem. Förmåner kan också väljas för en medarbetares räkning. Välj eller bekräfta förmåner på sidan **Medarbetare** på fliken **Förmåner** genom att välja **Arbetsförmånersplaner**.  Om du vill välja eller bekräfta förmåner för flera medarbetare använder du sidan **Uppdatering av gruppuppdatering för arbetsförmånersplaner**. 

## <a name="life-event-processing-optional"></a>Bearbetning av livshändelse (valfri)

Under medarbetarens livscykel kanske varje medarbetare upplever olika händelser i livslängden, till exempel förändringar av anställningen, förändringar av beroende eller arbetstillstånd. Om du vill använda livscykelhändelser måste du aktivera dem på sidan **Delade Human Resources-parametrar**. Ställ in alternativ för livscykelhändelsetyper och livscykelhändelse för plantyper.

Innan du kan bearbeta livshändelser måste du redan ha kört öppna registreringar minst en gång under en anställningstidsram. I USA är det vanligt att öppna anmälningen en gång per år. Utanför USA kan öppen registrering utföras vid anställningstiden. Bearbetning av livscykeln kräver inte att medarbetare väljer en förmånsplan. Arbetarna måste dock ha inkluderats i öppen bearbetning av anmälan. Mer information finns i följande avsnitt:

- [Bearbeta livshändelser](hr-benefits-process-life-events.md)
- [Bearbeta ändringar av livshändelser](hr-benefits-process-life-event-changes.md)
- [Bearbeta livshändelseberättigande](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>Kursuppdateringar (valfritt)

Ibland ändras satsen för en förmån under planperioden. Om du vill uppdatera satserna för medarbetare som redan är registrerade i planen måste du bearbeta kursens ändringar. Mer information finns i [Bearbeta ändringar av sats](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
