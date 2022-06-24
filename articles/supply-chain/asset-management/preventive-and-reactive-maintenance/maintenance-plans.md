---
title: Underhållsplaner
description: I denna artikel beskrivs underhållsplaner i Tillgångshantering.
author: johanhoffmann
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectType, EntAssetCounterType, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1f8a6de85f68a924a8d285d8cdd306ab774661fb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897818"
---
# <a name="maintenance-plans"></a>Underhållsplaner

[!include [banner](../../includes/banner.md)]

En underhållsplan definierar när ett tidigare planerat förebyggande underhållsjobb ska utföras på en tillgång. Underhållsplaner kan relateras till tillgångar, tillgångstyper, funktionsplatser eller funktionsplatstyper, men först skapas de underhållsplaner som ska användas i företaget.

En underhållsplan kan ha flera underhållsplanrader. Typ och intervall för underhållsjobb anges på underhållsplanraden. Det finns två typer av underhållsplanrader:

- Tid
- Räknare

Underhållsplanrader av typen "Tid" används för återkommande planerat underhåll baserat på ett fast tidsintervall. Underhållsplanrader av typen "Räknare" används för planerat underhåll eller reaktivt underhåll baserat på tillgångsräknarregistreringar. En underhållsplan kan innehålla flera underhållsplanrader av båda typerna.

>[!NOTE]
>Om inga räknarvärden har registrerats för en räknartyp för en tillgång, utelämnas underhållsplanensrader.

Först skapar du de underhållsplaner du behöver för dina förebyggande underhållsjobb och väljer de tillgångstyper, tillgångar, funktionsplatstyper och de funktionsplatser som ska vara relaterade till varje underhållsplan. Efteråt kan du även lägga till underhållsplaner till en tillgång eller en funktionsplats, vilket görs i **Alla tillgångar** \> välj tillgång \> snabbfliken **Underhållsplan för tillgång** eller **Alla funktionsplatser** \> välj en funktionsplats \> snabbfliken **Underhållsplaner**.

Om du lägger till en underhållsplan för tillgångstyper eller funktionsplatstyper, innebär det att när du skapar nya till gångar eller funktionsplatser med dessa tillgångstyper eller funktionsplatstyper läggs tillgången eller funktionsplatsen automatiskt till i underhållsplanen. Startdatum för relationen till en underhållsplan blir det aktuella datumet, vilket kan behöva justeras.

## <a name="set-up-maintenance-plans"></a>Ställ in underhållsplaner

I det här avsnittet beskrivs hur du konfigurerar underhållsplanrader och ger exempel på hur de kan användas.

1. Gå till **Tillgångshantering \> Inställning \> Förebyggande underhåll \> Underhållsplaner**.

1. Skapa en ny sekvens genom att välja **Nytt**.

1. Infoga ett ID i fältet **Underhållssekvens** och ett namn i fältet **Namn**.

1. I fältet **Plandatum** anger du det startdatum från vilket planering kan utföras för underhållsplanen. Observera att tidsbaserade underhållsplanrader kan ha andra plandatum.

1. Välj "Ja" i den växlingsknappen **Aktiv** om du vill aktivera underhållsplanen.

    >[!NOTE]
    >Om du inaktiverar en underhållsplan skapas inga schemaposter i underhållsplanen när du kör ett schemalagt underhållsplanjobb.

1. Fälten **Tolerans dagar före** och **Tolerans dagar efter** är relaterade till underhållsplansrader för vilka kryssrutan **Undertryck överlappande underhållsjobb** har markerats (se steg 17). Fälten "Tolerans" används för att utöka intervallet i dagar då, om flera underhållsplaner överlappar, det mest omfattande/största jobbet skapas som en underhållsplaneringsrad under planering av underhållsplan, medan mer frekventa, överlappande jobb utelämnas vid planering av underhållsplanen. Infoga antal dagar i fältet **Tolerans dagar före**, till exempel "2".

1. Om du har infogat ett värde i **Tolerans dagar före** ska du även infoga antalet dagar i fältet **Tolerans dagar efter**, till exempel "2".

    >[!NOTE]
    >Exemplet som beskrivs i detta och föregående steg innebär att om flera underhållsplanrader överlappar och **Undertryck överlappande underhållsjobb** har valts för en eller flera rader, utökas perioden för att utelämna underhållsschemarader till sammanlagt fem dagar (förväntat startdatum på underhållsschemaraden *och* två dagar före *och* två dagar efter detta datum).

1. Fälten i gruppen **Detaljer** på snabbfliken **Detaljer** visar det antal underhållsplanrader som har ställts in i underhållsplanen samt antalet tillgångar och funktionsplatser som är relaterade till underhållsplanen.

1. På snabbfliken **Rader** klickar du på **Lägg till tidsrad** eller **Lägg till räknarrad** om du vill skapa en ny underhållsplanrad.

1. Infoga en beskrivning för raden i fältet **Arbetsorderbeskrivning**. Beskrivningen överförs till relaterade arbetsorder.

1. Välj jobbtypen som underhållsplanraden är relaterad till i fältet **Underhållsjobbtyp**.

1. I fälten **Variant av underhållsjobbtyp** och **Yrkesgren** väljer varianten av underhållsjobbtypen och en yrkesgren för underhållsjobbtypen.

1. I fälten **Slutför inom dagar** och **Slutför inom timmar** kan du infoga förväntat slutdatum i dagar eller timmar. Det förväntade slutdatumet infogas i förhållande till det förväntade startdatumet, som beräknas när underhållsplanrader skapas. Du kan till exempel infoga "7" i fältet **Slutför inom dagar** för att ange att det relaterade jobbet ska slutföras inom en vecka från det förväntade startdatumet.

1. I fältet **Intervalltyp** väljer du den typ av intervall som ska användas på underhållsplanraden, till exempel "Upprepat..." eller "En gång...". Se tabellen [Översikt över intervalltyper](#interval-types) nedan om du vill se en beskrivning av relationen mellan intervalltyper och radtyper.

1. Fältet **Period** relaterar bara till tidsbaserade radtyper. Välj periodtypen som är relaterad till periodfrekvensen.

1. I fältet **Periodfrekvens** anger du hur många gånger raden ska användas för att planera förebyggande underhållsjobb. Exempel: Om du har skapat en rad av typen "Räknare", och räknaren är produktionskvantitet och du infogar siffran "20 000" i det här fältet, skapas nya underhållsserierader under förebyggande underhållsplanering varje gång du förväntar dig att producera 20 000 fler artiklar.

1. Kryssrutan **Undertryck överlappande underhållsjobb** avser både tidsbaserade och räknarbaserade radtyper. Markera kryssrutan om du vill ta bort poster för underhållsplaner som skapas för samma datum. Detta är relevant om du t ex. har skapat en 1-månads inspektionsrad, en 6-månaders inspektionsrad och en 1-års inspektionsrad. För den 1-åriga inspektionen vill du bara att inspektionen skall utföras, inte de två andra inspektionerna som också skulle passa inom tidsramen. För att du ska kunna konfigurera det här exemplet korrekt ställer du in en 1-års inspektionsrad som den första raden, 6-månadersraden som den andra raden och 1-månadsraden som den tredje raden, och markerar kryssrutan **Undertryck överlappande underhållsjobb** för 1-månads- och 6-månadersraderna. På så sätt ser du till att inspektionerna för en månad och sex månader utelämnas när du når 1-årsmarkeringen och att en underhållsschemarad endast skapas för 1-årsinspektionsraden.

    >[!NOTE]
    >Exemplet som beskrivs i det här steget visar att det mest omfattande jobbet, som innehåller det största antalet uppgifter och som inte utförs så ofta, alltid ska infogas som den första raden. De vanligaste jobben infogas som separata rader i frekvensordning, där det vanligaste jobbet placeras längst ned i listan.

1. Fältet **Räknare** relaterar bara till räknarbaserade radtyper. Välj den räknartyp som ska användas på raden. Om en räknartyp inte är aktiv för en relaterad tillgång utelämnas underhållsplanraden.

1. Fältet **Gräns för tillgångsräknartid i dagar** är bara relaterad till räknarbaserade radtyper. Infoga ett nummer som definierar hur många dagar bakåt räknaregistreringarna kontrolleras när underhållsplaneringen utförs. Detta innebär hur långt tillbaka används data (befintliga räknarregistreringar) för att beräkna trenden som bestämmer hur många underhållsschemarader som skapas.

    >*Exempel:* Om räknarregistreringar förväntas göras en gång i månaden kan du infoga siffran 365 i det här fältet eftersom underhållsplaneringen alltid kommer att baseras på de senaste 12 månaderna och därför skapa underhållsschemarader baserat på trenden för det senaste året. Om du däremot infogar siffran 10 i det här fältet förväntar du att räknarregistreringarna ska göras oftare, till exempel dagligen. Det innebär att när du planerar underhållsplanen används räknarregistreringar för de senaste 10 dagarna som grund för planeringen av underhållsschemarader.

1. Fältet **Plandatum** relaterar bara till tidsbaserade radtyper. Om underhållsplanraden har ett annat planeringsdatum än hela underhållsplanen väljer du ett datum i fältet **Plandatum** på raden.

1. I fältet **Servicenivå** kan du välja en servicenivå för arbetsorder som en ytterligare avgränsning på underhållsplanraden som ska användas som servicenivå på arbetsorder.

1. Markera kryssrutan **Autoskapa** om du vill att en arbetsorder automatiskt ska skapas enligt den valda underhållsplanraden när du planerar underhållsplaner.

1. Om du har markerat kryssrutan **Autoskapa** kan du välja en arbetsordertyp för den automatiskt skapade arbetsordern i fältet **Arbetsordertyp**. Om du har markerat kryssrutan **Autoskapa** och inte väljer någon arbetsordertyp i det här fältet, används arbetsordertypen som valts i **Tillgångshantering \> Inställning \> Parametrar för Tillgångshantering \> Arbetsorder** länk \> **Förebyggande arbetsorder**.

1. Använd fälten **Från säsong** och **Till säsong** för att skapa en upprepad tidsbaserad underhållsplanrad inom en 12-månadersperiod. *Exempel:* Utrustning som används för att underhålla grönområden måste få service varje vår inom en fördefinierad period. Infoga startdatumet för den period som ska upprepas i fältet **Säsong från**.

1. Infoga slutdatumet för den period som ska upprepas i fältet **Säsong till**.

1. I fältet **Resulterande period** visas den aktuella perioden som ska upprepas. När den aktuella perioden har passerat, och du startar ett nytt år, kommer perioden som visas i det här fältet att uppdateras för att återspegla nästa period i upprepningssekvensen.

1. På snabbfliken **Tillgångar** väljer du de tillgångar som ska relateras till underhållsplanen.

1. På snabbfliken **Tillgångstyper** väljer du de tillgångstyper som ska relateras till underhållsplanen.

1. På snabbfliken **Funktionsplatser** väljer du de funktionsplatser som ska relateras till underhållsplanen. Om det behövs kan du göra inställningarna mer specifika genom att välja en relaterad tillgångstyp, tillverkare och modell.

1. På snabbfliken **Funktionsplatstyper** väljer du de funktionsplatstyper som ska relateras till underhållsplanen.

>[!NOTE]
>När arbetsorder skapas manuellt på tillgångar som täcks av en leverantörsgaranti visas en dialogruta som gör användaren medveten om garantin. Skapandet av arbetsordern kan sedan annulleras. Kontrollen av en garantirelation utelämnas för arbetsorder som skapas automatiskt.

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>Översikt över intervalltyper

| Intervalltyp och beskrivning | Radtyp: Tid | Radtyp: Räknare |
|---|---|---|
| **Intervalltyp: upprepande från plandatum** antalet startar från det planerade datum som används. När du planerar underhållsplaner skapas en underhållsplanrad när intervallet nås. | **Plandatumet** på underhållsplanraden används. Om inget plandatum har valts på raden används **Plandatumet** för underhållsplanen. Exempel: Om siffran 3 infogas i fältet **Periodfrekvens** och "År" har valts i fältet **Period** skapas en ny underhållsschemarad en gång vart tredje år. | **Plandatumet** för underhållsplanen används. Om räknaren har ersatts används det senaste ersättningsdatumet som plandatum. |
| **Intervalltyp: Upprepat från startdatum** Räkningen börjar från startdatumet på tillgångsrelationen. Datumet väljs i detaljvyn **Alla tillgångar** snabbfliken \> **Underhållsplaner för tillgångar** fältet \> **Startdatum** eller i detaljvyn **Alla funktionsplatser** snabbfliken \> **Underhållsplaner** fältet \> **Startdatum**. När du planerar underhållsplaner skapas en underhållsplanrad när intervallet nås. | Startdatum för underhållsplanraden på tillgången eller funktionsplatsen används. Om det fältet är tomt används **Plandatumet** för underhållsplanen. | Startdatum för underhållsplanraden på tillgången eller funktionsplatsen används. Om det fältet är tomt används **Plandatumet** för underhållsplanen. |
| Intervalltyp: **Upprepat från senaste arbetsorder** Antalet startar från det faktiska slutdatumet och tiden för den senaste arbetsordern som slutfördes på tillgången med den specifika underhållsjobbstypen/variant av underhållsjobbtyp/yrkesgren. Datumet och tiden visas i fältet **Faktiskt slut** i detaljvyn **Alla arbetsorder**. | Faktiskt slutdatum och faktisk sluttid för arbetsordern som har slutförts på tillgången med den specifika typen av underhållsjobbtyp/variant av underhållsjobbtyp/yrkesgren Om ingen slutförd arbetsorder hittas används i stället ett av de datum som anges i intervalltypen "Upprepat från startdatum" som beskrivs ovan. | Faktiskt slutdatum och faktisk sluttid för arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren används. Om slutdatum och sluttid lämnades tomt på arbetsordern används i stället ett av de datum som anges i intervalltypen "Upprepat från startdatum" som beskrivs ovan. |
| **Intervalltyp: En gång från plandatum** Se beskrivningen för intervalltypen "Upprepat från plandatum" ovan. Den enda skillnaden är att denna intervalltyp bara ska användas en gång. | Se beskrivning för intervalltypen "Upprepat från plandatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. | Se beskrivning för intervalltypen "Upprepat från plandatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. **Anmärkning 1:** Den här intervalltypen är bara relevant om räknaren ersätts varje gång du utför ett underhållsjobb eller servicejobb. Om en räknare av någon anledning har ersatts före slutet av det planerade intervallet, beräknas en ny tid för jobbet från tidpunkten för bytet av räknaren. **Anmärkning 2:** Om räknaren ersätts när underhålls- eller servicejobbet slutförs, fungerar denna intervalltyp som intervalltypen "Upprepat från plandatum" ovan. |
| **Intervalltyp: En gång från startdatum** Se beskrivningen för intervalltypen "Upprepat från startdatum" ovan. Den enda skillnaden är att denna intervalltyp bara ska användas en gång. | Se beskrivning för intervalltypen "Upprepat från startdatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. | Se beskrivning för intervalltypen "Upprepat från startdatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. **Anmärkning 1** ovan gäller även för den här intervalltypen. **Anmärkning 3:** Om räknaren ersätts när underhålls- eller servicejobbet slutförs, fungerar denna intervalltyp som intervalltypen "Upprepat från startdatum" ovan. |
| **Intervalltyp: När övre nås** Den här intervalltypen gäller endast räknare och används för att indikera en övre gräns som ställts in på underhållsplanraden. Underhållsschemaposter får det förväntade startdatumet och tidpunkten för räknarregistreringen, vilket innebär att dessa poster skapas med ett förväntat startdatum som är lika med eller tidigare än systemdatumet. | Inte aktuellt | Räknarintervallet indikerar en övre gräns. Om denna gräns överskrids när du skapar en räknarregistrering skapas en underhållsschemarad när du planerar förebyggande underhåll. |
| **Intervalltyp: När nedre nås** Den här intervalltypen gäller endast räknare och används för att indikera en nedre gräns som ställts in på underhållsplanraden. Underhållsschemaposter får det förväntade startdatumet och tidpunkten för räknarregistreringen, vilket innebär att dessa poster skapas med ett förväntat startdatum som är lika med eller tidigare än systemdatumet. | Inte aktuellt | Räknarintervallet indikerar en nedre gräns. Om denna gräns passeras när du skapar en räknarregistrering skapas en underhållsschemarad när du planerar förebyggande underhåll. |
| **Intervalltyp: länkad från startdatum** Den här intervalltypen skapar bara en underhållsschemarad en gång. En underhållsplan kan innehålla flera underhållsplanrader med den här intervalltypen och dessa rader är kopplade till varandra. Vanligtvis skapar du en underhållsplan som innehåller enbart rader med den här intervalltypen. Underhållsschemarader skapas genom identifiering av den underhållsplanrad som har det första förväntade startdatumet och tiden. | Se beskrivning för intervalltypen "En gång från startdatum" ovan. Exempel: Du skapar två rader i en underhållsplan för ett servicejobb på en bil: en tidsbaserad rad med en 1-årsperiod och en räknarbaserad rad med en 25 000 km-gräns. En underhållsschemarad skapas för den gräns som först uppnås. För den här radtypen skapar du raden med 1-årsperioden. | Se beskrivning för intervalltypen "En gång från startdatum" ovan. Exempel: Du skapar två rader i en underhållsplan för ett servicejobb på en bil: en tidsbaserad rad med en 1-årsperiod och en räknarbaserad rad med en 25 000 km-gräns. En underhållsschemarad skapas för den gräns som först uppnås. För den här radtypen skapar du raden med 25 000 km-gränsen. Exempel för att skapa två räknarrader: Du kan också konfigurera en underhållsplan med två länkade, räknarbaserade rader där den första raden har en gräns på 10 000 producerade artiklar och den andra raden gäller den maskin eller resurs som kräver service efter att ha körts 3 000 timmar. |
| **Intervalltyp: länkat från senaste arbetsorder** denna intervalltyp skapar nya underhållsplaneringsrader efter varje slutförd arbetsorder. En underhållsplan kan innehålla flera rader med den här intervalltypen och dessa rader är kopplade till varandra. Vanligtvis skapar du en underhållsplan som innehåller enbart underhållsplanrader med den här intervalltypen. Underhållsschemarader skapas genom identifiering av den underhållsplanrad som har det första förväntade startdatumet och tiden. | Den här intervalltypen fungerar på ett och samma sätt som "Länkat från startdatum", som beskrivs ovan. Den enda skillnaden är det datum som intervalltypen baseras på. Datumet som används är det faktiska datumet och tiden för den senaste arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren. | Den här intervalltypen fungerar på ett och samma sätt som "Länkat från startdatum", som beskrivs ovan. Den enda skillnaden är det datum som intervalltypen baseras på. Datumet som används är det faktiska datumet och tiden för den senaste arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren. |
| **Intervalltyp: Upprepat på aggregerat värde (endast räknare)** När underhållsplanen körs skapas en tidsplanerad underhållsrad varje gång det ackumulerade värdet för en tillgångsräknare når periodfrekvensen eller en till och med en multipel av periodfrekvensen. (Periodfrekvensen definieras på underhållsplanraden.)<p>Mer information om hur du aktiverar och använder denna funktion finns i avsnittet [Räknarbaserade förbättringar av underhåll](#counter-based-maintenance) längre fram i denna artikel. | Inte tillämpligt | **Exempel:** En timräknare ställs in för tillgången SEK-101. En anläggningstillgångsplanrad ställs också in för tillgången. Intervalltypen för den här raden är *Upprepat på aggregerat värde (endast räknare)* och periodfrekvensen är *1000*. När underhållsplanen körs genereras en planerad underhållsrad när det aggregerade värdet för räknaren överstiger 1 000 timmar. När det aggregerade värdet för räknaren sedan överskrider 2 000 timmar genereras en annan planerad underhållsrad, och så vidare för varje ytterligare 1 000 timmar. |
| **Intervalltyp: En på aggregerat värde (endast räknare)** När underhållsplanen körs skapas en tidsplanerad underhållsrad när det ackumulerade värdet för en tillgångsräknare når periodfrekvensen som definieras på underhållsplanraden.<p>Mer information om hur du aktiverar och använder de här funktionerna finns i asvnittet [Räknarbaserade förbättringar av underhållet](#counter-based-maintenance). | Inte aktuellt | **Exempel:** En timräknare ställs in för tillgången SEK-101. En anläggningstillgångsplanrad ställs också in för tillgången. Intervalltypen för den här raden är *En gång på aggregerat värde (endast räknare)* och periodfrekvensen är *1000*. När underhållsplanen körs genereras en planerad underhållsrad när det aggregerade värdet för räknaren överstiger 1 000 timmar. |

>[!NOTE]
>När underhållsschemarader skapas för tidsbaserade underhållsplanrader är förväntad tid alltid början av dagen. För de räknarbaserade underhållsplanraderna kan förväntad tid vara när som helst under dagen.

Nedan finns exempel på hur du konfigurerar tidsbaserade och räknarbaserade underhållsplanrader:

**Exempel 1 - Tidsbaserad underhållsplanrad:** Ett smörjjobb kan ställas in i ett fast intervall, som inträffar en gång i veckan. För det ändamålet väljer du "Upprepat från plandatum" i fältet **Intervalltyp**. Se exemplet i följande bild.

![Ett servicejobb som ställs in i ett fast intervall som inträffar en gång per vecka.](media/02-preventive-maintenance.png "Ett servicejobb som ställs in i ett fast intervall, som inträffar en gång per vecka")

**Exempel 2 – Tidsbaserad underhållsplanrad:** Ett inspektionsjobb kan ställas in för att genomföras ungefär en gång i veckan. För det ändamålet väljer du "Upprepat från senaste arbetsorder" i fältet **Intervalltyp**. Se exemplet i följande bild.

![Ett inspektionsjobb som är inställt på att utföras ungefär en gång per vecka.](media/03-preventive-maintenance.png "Ett inspektionsjobb som är inställt på att utföras ungefär en gång per vecka")

**Exempel 3 – Räknarbaserad underhållsplanrad**: Bilden nedan visar en grafisk vy av en timräknare för vilken en ny underhållsschemarad skapas varje gång 250 timmar har passerat. Intervalltypen för den här raden är "Upprepat från startdatum". Startdatumet är startdatumet för de relaterade tillgångarna i detaljvyn **Alla tillgångar** snabbfliken \> **Underhållsplaner för tillgångar** fältet \> **Startdatum** eller i detaljvyn **Funktionsplats** snabbfliken \> **Underhållsplaner** fältet \> **Startdatum**. Detta är ett exempel på en *förebyggande* underhållsplan eftersom underhållsplanraden skapas automatiskt varje gång som tröskelvärdet (+ 250) uppnås.

![En timräknare som regelbundet skapar underhållsplanrader.](media/04-preventive-maintenance.png "En timräknare som regelbundet skapar underhållsplanrader")

**Exempel på 4 - Räknarbaserad underhållsplanrad:** Bilden nedan visar en grafisk vy av en minskning av räknarvärdet, som mäter slitage på bromsklossar. En underhållsschemarad skapas när en räknarregistrering under 20 mm skapas på bromsklossen. Intervalltypen för den här räknarraden är "När nedre nås" eller "En gång från senaste startdatum". Detta är ett exempel på en *reaktiv* underhållsplan eftersom underhållsschemaraden inte skapas förrän ett mått under 20 mm registreras.

![En minskning av räknarvärdet som mäter slitage på bromsklossar.](media/05-preventive-maintenance.png "En minskning av räknarvärdet som mäter bromsklossar")

**Exempel 5 – Räknarbaserad underhållsplanrad**: Bilden nedan visar en grafisk vy av en räknare med en tröskel på -18 ° Celsius. En underhållsschemarad skapas när en räknarregistrering överstiger-18 ° Celsius görs. Intervalltypen för den här räknarbaserade raden är "När övre nås". Detta är ett exempel på en *reaktiv* underhållsplan eftersom underhållsschemaraden inte skapas förrän ett mått som är högre än -18 ° Celsius registreras.

![En räknare med tröskelvärdet -18 grader Celsius.](media/06-preventive-maintenance.png "En räknare med tröskelvärdet -18 grader")

- När du skapar en ny tillgång och en sådan tillgång använder en tillgångstyp relaterad till en underhållsplan infogas underhållsplanen automatiskt i snabbfliken **Alla objekt \> Underhållsplaner för tillgångar**. I **Standardtyper för tillgång** på snabbfliken **Underhållsplaner** infogas automatiskt de relaterade underhållsplanerna.
- Om du lägger till eller tar bort tillgångstyper eller funktionsplatstyper i **Underhållsplaner** kommer denna ändring bara att återspeglas i nya tillgångar som skapas efter att du gjort ändringen.
- Om du lägger till eller tar bort resurser eller funktionsplatser i **Underhållsplaner** kommer denna ändring automatiskt att uppdateras i snabbfliken **Alla tillgångar \> Underhållsplaner för tillgångar** eller i snabbfliken **Alla funktionsplatser \> Underhållsplaner**.

Följande illustration visar ett exempel på en underhållsplan för "Lastbilsservice" på sidan **underhållsplaner**.

![Ett exempel på en underhållsplan för lastbilsservice.](media/07-preventive-maintenance.png "Ett exempel på en underhållsplan för lastbilsservice")

## <a name="add-a-maintenance-plan-to-an-asset"></a>Lägga till en underhållsplan till en tillgång

1. Gå till **Tillgångshantering \> Allmänt \> Tillgångar \> Alla tillgångar** eller **Aktiva tillgångar**.

1. Välj tillgången som du vill konfigurera en underhållsplan för och klicka på **Redigera**.

1. På snabbfliken **Underhållsplaner för tillgångar**, klicka på **Lägg till rad** för att lägga till en underhållsplan till tillgången.

1. Välj relevant underhållsplan i fältet **Underhållsplan**.

1. I fältet **Startdatum** väljer du det datum från vilket planering av förebyggande underhållsjobb kan utföras. 

1. Välj **Spara**. Fältet **Aktivt** uppdateras automatiskt.

Följande illustration visar ett exempel på underhållsplaner som anges på en tillgång på sidan **Alla tillgångar**.

![Ett exempel på underhållsplaner som ställts in för en tillgång.](media/08-preventive-maintenance.png "Ett exempel på underhållsplaner som ställts in för en tillgång")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>Räknarbaserade underhållsförbättringar

Funktionen *Förbättringar av räknarbaserat underhåll* innehåller följande funktioner:

- Alternativet för att automatiskt infoga en räknare som har värdet *0* (noll) när en tillgång skapas. Det här alternativet kan vara användbart när du använder förutsägande underhåll som baseras på räknare. När funktionen *Förbättringar av räknarbaserat underhåll* inte används måste räknare som har värdet *0* (noll) infogas manuellt.
- Möjligheten att konfigurera en räknare så att den återställs automatiskt när en arbetsorder är slutförd. Den här funktionen är praktisk om du vill schemalägga underhåll baserat på det aggregerade värdet sedan den senaste arbetsordern slutfördes.
- En ny typ av intervall för underhållsplan som kallas *Upprepat på aggregerat värde (gäller endast räknare)*. Den här typen utlöser underhåll varje gång en aggregerad räknare uppnår en multipel av ett visst värde. Underhåll kan till exempel initieras var 10 000:e timme. Mer information finns i avsnittet [Översikt över intervalltyper](#interval-types) tidigare i denna artikel.
- En annan ny typ av intervall för underhållsplan som kallas *En gång på aggregerat värde (gäller endast räknare)*. Den här typen utlöser underhåll när en aggregerad räknare uppnår ett visst värde, t.ex. 8 000 timmar. Mer information finns i avsnitt [Översikt över intervalltyper](#interval-types).

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>Aktivera funktionen för förbättringar av räknarbaserat underhåll

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Tillgångshantering*
- **Funktionsnamn:** *Funktionen för förbättringar av räknarbaserat underhåll*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>Skapa och initiera räknare när en tillgång skapas

Varje gång du skapar en tillgång kan relaterade tillgångsräknare som initieras till värdet *0* (noll) skapas automatiskt, förutsatt att du konfigurerar systemet och skapar tillgången korrekt.

1. Gå till **Tillgångshantering \> Konfigurera \> Tillgångstyper**.
1. Se till att du har en tillgångstyp som kan användas för din planerade nya tillgång. Skapa en tillgångstyp efter behov. Kontrollera att alla relevanta räknare markeras på snabbfliken **Räknare**.
1. Gå till **Tillgångshantering \> Konfigurera \> Tillgångstyper \> Räknare**.
1. För varje relevant räknare ska du se till att fältet **Totalt sammanlagd** är inställt på *Summa*.
1. Skapa tillgången på sidan **Alla tillgångar**.
1. Ställ in fältet **Tillgångstyp** till den tillgångstyp som du identifierade eller skapade i steg 2.
1. Slutför inställningen av den nya tillgången efter behov.
1. Gå till **Tillgångshantering \> Förfrågningar \> Tillgångar \> Räknare**. Du bör kunna hitta de initialiserade räknare som ställts in för din nya tillgång.

> [!NOTE]
> När initialiserade tillgångsräknare skapas görs antagandet att tillgången aldrig hade använts innan den lades till i systemet. När underhållsschemat körs för första gången använder datumet och beräkningen *0* (noll) räknarvärde som baslinje för beräkning av framtida underhåll. Om tillgången inte fungerar som den ska när den läggs till i systemet kan du manuellt justera räknarvärdet så att det matchar det faktiska räknarvärdet. För att justera ett motvärde, öppna relevant tillgång på sidan **Alla tillgångar** och sedan väljer fliken **Tillgång** i åtgärdsfönstret, i gruppen **Förebyggande**, välj **Räknare**. På sidan **Tillgångsräknare** för den valda tillgången justerar du värdet i kolumnen **Värde** för den ursprungliga räknarposten efter behov.

### <a name="automatically-reset-a-counter-value"></a>Återställ ett räknarvärde automatiskt

Du kan konfigurera systemet att automatiskt återställa en räknare varje gång som en relevant arbetsorder uppnår ett valt statusvärde.

1. Gå till **Tillgångshantering \> Inställning \> Förebyggande underhåll \> Underhållsplaner**.
1. Välj en underhållsplan i listfönstret. Återställning av räknare används på alla tillgångar som använder den här planen.
1. I avsnittet **Rader**, hitta en tillgångsräknarrad som du vill återställa en räknare för och markera kryssrutan **Återställ räknare** för raden. (Rader i tillgångsräknaren har ett värde i kolumnen **Räknare**. Räknaren som anges i den kolumnen är den räknare som kommer att återställas för den relevanta tillgången.)
1. Gå till **Tillgångshantering \> Inställningar \> Arbetsorder \> Livscykeltillstånd**.
1. Välj i listfönstret vilket livscykeltillstånd för arbetsorder som den relevanta räknaren ska återställas vid.
1. På snabbfliken **Allmänt** ställer du in **Återställ räknare** till *Ja*.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]