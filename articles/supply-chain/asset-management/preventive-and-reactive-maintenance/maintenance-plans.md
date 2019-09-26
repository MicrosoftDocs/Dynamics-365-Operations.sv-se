---
title: Underhållsplaner
description: I det här avsnittet beskrivs underhållsplaner i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5a89e85dc92d57b0a5d2fc7e7a5910c7be09387c
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875895"
---
# <a name="maintenance-plans"></a>Underhållsplaner


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


En underhållsplan definierar när ett tidigare planerat förebyggande underhållsjobb ska utföras på en tillgång. Underhållsplaner kan relateras till tillgångar, tillgångstyper, funktionsplatser eller funktionsplatstyper, men först skapas de underhållsplaner som ska användas i företaget.

En underhållsplan kan ha flera underhållsplanrader. Typ och intervall för underhållsjobb anges på underhållsplanraden. Det finns två typer av underhållsplanrader:

- Tid  
- Räknare  

Underhållsplanrader av typen "Tid" används för återkommande planerat underhåll baserat på ett fast tidsintervall. Underhållsplanrader av typen "Räknare" används för planerat underhåll eller reaktivt underhåll baserat på tillgångsräknarregistreringar. En underhållsplan kan innehålla flera underhållsplanrader av båda typerna.

>[!NOTE]
>Om inga räknarvärden har registrerats för en räknartyp för en tillgång, utelämnas underhållsplanensrader.

Först skapar du de underhållsplaner du behöver för dina förebyggande underhållsjobb och väljer de tillgångstyper, tillgångar, funktionsplatstyper och de funktionsplatser som ska vara relaterade till varje underhållsplan. Efteråt kan du även lägga till underhållsplaner till en tillgång eller en funktionsplats, vilket görs i **Alla tillgångar** > välj till gång > snabbfliken **Underhållsplan för tillgång** eller **Alla funktionsplatser** > välj en funktionsplats > snabbfliken **Underhållsplaner**.

Om du lägger till en underhållsplan för tillgångstyper eller funktionsplatstyper, innebär det att när du skapar nya till gångar eller funktionsplatser med dessa tillgångstyper eller funktionsplatstyper läggs tillgången eller funktionsplatsen automatiskt till i underhållsplanen. Startdatum för relationen till en underhållsplan blir det aktuella datumet, vilket kan behöva justeras.

## <a name="set-up-maintenance-plans"></a>Ställ in underhållsplaner

I det här avsnittet beskrivs hur du ställer in underhållsplanrader och ger exempel på hur de kan användas.

1. Klicka på **Tillgångshantering** > **Inställning** > **Förebyggande underhåll** > **Underhållsplaner**.

2. Klicka på **Ny** för att skapa en ny sekvens.

3. Infoga ett ID i fältet **Underhållssekvens** och ett namn i fältet **Namn**.

4. I fältet **Plandatum** anger du det startdatum från vilket planering kan utföras för underhållsplanen. Observera att tidsbaserade underhållsplanrader kan ha andra plandatum.

5. Välj "Ja" i den växlingsknappen **Aktiv** om du vill aktivera underhållsplanen.

>[!NOTE]
>Om du inaktiverar en underhållsplan skapas inga schemaposter i underhållsplanen när du kör ett schemalagt underhållsplanjobb.

6. Fälten **Tolerans dagar före** och **Tolerans dagar efter** är relaterade till underhållsplansrader för vilka kryssrutan **Undertryck överlappande underhållsjobb** har markerats (se steg 17). Fälten "Tolerans" används för att utöka intervallet i dagar då, om flera underhållsplaner överlappar, det mest omfattande/största jobbet skapas som en underhållsplaneringsrad under planering av underhållsplan, medan mer frekventa, överlappande jobb utelämnas vid planering av underhållsplanen. Infoga antal dagar i fältet **Tolerans dagar före**, till exempel "2".

7. Om du har infogat ett värde i **Tolerans dagar före** ska du även infoga antalet dagar i fältet **Tolerans dagar efter**, till exempel "2".

>[!NOTE]
>Exemplet som beskrivs i detta och föregående steg innebär att om flera underhållsplanrader överlappar och **Undertryck överlappande underhållsjobb** har valts för en eller flera rader, utökas perioden för att utelämna underhållsschemarader till sammanlagt fem dagar (förväntat startdatum på underhållsschemaraden *och* två dagar före *och* två dagar efter detta datum).

8. Fälten i gruppen **Detaljer** på snabbfliken **Detaljer** visar det antal underhållsplanrader som har ställts in i underhållsplanen samt antalet tillgångar och funktionsplatser som är relaterade till underhållsplanen.

9. På snabbfliken **Rader** klickar du på **Lägg till tidsrad** eller **Lägg till räknarrad** om du vill skapa en ny underhållsplanrad.

10. Infoga en beskrivning för raden i fältet **Arbetsorderbeskrivning**. Beskrivningen överförs till relaterade arbetsorder.

11. Välj jobbtypen som underhållsplanraden är relaterad till i fältet **Underhållsjobbtyp**.

12. I fälten **Variant av underhållsjobbtyp** och **Yrkesgren** väljer varianten av underhållsjobbtypen och en yrkesgren för underhållsjobbtypen.

13. I fälten **Slutför inom dagar** och **Slutför inom timmar** kan du infoga förväntat slutdatum i dagar eller timmar. Det förväntade slutdatumet infogas i förhållande till det förväntade startdatumet, som beräknas när underhållsplanrader skapas. Du kan till exempel infoga "7" i fältet **Slutför inom dagar** för att ange att det relaterade jobbet ska slutföras inom en vecka från det förväntade startdatumet.

14. I fältet **Intervalltyp** väljer du den typ av intervall som ska användas på underhållsplanraden, till exempel "Upprepat..." eller "En gång...". Se tabellen [Översikt över intervalltyper](## Interval types overview) nedan om du vill se en beskrivning av relationen mellan intervalltyper och radtyper.

15. Fältet **Period** relaterar bara till tidsbaserade radtyper. Välj periodtypen som är relaterad till periodfrekvensen.

16. I fältet **Periodfrekvens** anger du hur många gånger raden ska användas för att planera förebyggande underhållsjobb. Exempel: Om du har skapat en rad av typen "Räknare", och räknaren är produktionskvantitet och du infogar siffran "20 000" i det här fältet, skapas nya underhållsserierader under förebyggande underhållsplanering varje gång du förväntar dig att producera 20 000 fler artiklar.

17. Kryssrutan **Undertryck överlappande underhållsjobb** avser både tidsbaserade och räknarbaserade radtyper. Markera kryssrutan om du vill ta bort poster för underhållsplaner som skapas för samma datum. Detta är relevant om du t ex. har skapat en 1-månads inspektionsrad, en 6-månaders inspektionsrad och en 1-års inspektionsrad. För den 1-åriga inspektionen vill du bara att inspektionen skall utföras, inte de två andra inspektionerna som också skulle passa inom tidsramen. För att du ska kunna ställa in det här exemplet korrekt ställer du in en 1-års inspektionsrad som den första raden, 6-månadersraden som den andra raden och 1-månadsraden som den tredje raden, och markerar kryssrutan **Undertryck överlappande underhållsjobb** för 1-månads- och 6-månadersraderna. På så sätt ser du till att inspektionerna för en månad och sex månader utelämnas när du når 1-årsmarkeringen och att en underhållsschemarad endast skapas för 1-årsinspektionsraden.

>[!NOTE]
>Exemplet som beskrivs i det här steget visar att det mest omfattande jobbet, som innehåller det största antalet uppgifter och som inte utförs så ofta, alltid ska infogas som den första raden. De vanligaste jobben infogas som separata rader i frekvensordning, där det vanligaste jobbet placeras längst ned i listan.

18. Fältet **Räknare** relaterar bara till räknarbaserade radtyper. Välj den räknartyp som ska användas på raden. Om en räknartyp inte är aktiv för en relaterad tillgång utelämnas underhållsplanraden.

19. Fältet **Gräns för tillgångsräknartid i dagar** är bara relaterad till räknarbaserade radtyper. Infoga ett nummer som definierar hur många dagar bakåt räknaregistreringarna kontrolleras när underhållsplaneringen utförs. Detta innebär hur långt tillbaka används data (befintliga räknarregistreringar) för att beräkna trenden som bestämmer hur många underhållsschemarader som skapas.

>*Exempel:* Om räknarregistreringar förväntas göras en gång i månaden kan du infoga siffran 365 i det här fältet eftersom underhållsplaneringen alltid kommer att baseras på de senaste 12 månaderna och därför skapa underhållsschemarader baserat på trenden för det senaste året. Om du däremot infogar siffran 10 i det här fältet förväntar du att räknarregistreringarna ska göras oftare, till exempel dagligen. Det innebär att när du planerar underhållsplanen används räknarregistreringar för de senaste 10 dagarna som grund för planeringen av underhållsschemarader.

20. Fältet **Plandatum** relaterar bara till tidsbaserade radtyper. Om underhållsplanraden har ett annat planeringsdatum än hela underhållsplanen väljer du ett datum i fältet **Plandatum** på raden.

21. I fältet **Servicenivå** kan du välja en servicenivå för arbetsorder som en ytterligare avgränsning på underhållsplanraden som ska användas som servicenivå på arbetsorder.

22. Markera kryssrutan **Autoskapa** om du vill att en arbetsorder automatiskt ska skapas enligt den valda underhållsplanraden när du planerar underhållsplaner.

23. Om du har markerat kryssrutan **Autoskapa** kan du välja en arbetsordertyp för den automatiskt skapade arbetsordern i fältet **Arbetsordertyp**. Om du har markerat kryssrutan **Autoskapa** och inte väljer någon arbetsordertyp i det här fältet, används arbetsordertypen som valts i **Tillgångshantering** > **Inställning** > **Parametrar för tillgångshantering** >  länken **Arbetsorder** > fältet **Förebyggande arbetsorder**.

24. Använd fälten **Från säsong** och **Till säsong** för att skapa en upprepad tidsbaserad underhållsplanrad inom en 12-månadersperiod. *Exempel:* Utrustning som används för att underhålla grönområden måste få service varje vår inom en fördefinierad period. Infoga startdatumet för den period som ska upprepas i fältet **Säsong från**.

25. Infoga slutdatumet för den period som ska upprepas i fältet **Säsong till**.

26. I fältet **Resulterande period** visas den aktuella perioden som ska upprepas. När den aktuella perioden har passerat, och du startar ett nytt år, kommer perioden som visas i det här fältet att uppdateras för att återspegla nästa period i upprepningssekvensen.

27. På snabbfliken **Tillgångar** väljer du de tillgångar som ska relateras till underhållsplanen.

28. På snabbfliken **Tillgångstyper** väljer du de tillgångstyper som ska relateras till underhållsplanen.

29. På snabbfliken **Funktionsplatser** väljer du de funktionsplatser som ska relateras till underhållsplanen. Om det behövs kan du göra inställningarna mer specifika genom att välja en relaterad tillgångstyp, tillverkare och modell.

30. På snabbfliken **Funktionsplatstyper** väljer du de funktionsplatstyper som ska relateras till underhållsplanen.

>[!NOTE]
>När arbetsorder skapas manuellt på tillgångar som täcks av en leverantörsgaranti visas en dialogruta som gör användaren medveten om garantin. Skapandet av arbetsordern kan sedan annulleras. Kontrollen av en garantirelation utelämnas för arbetsorder som skapas automatiskt.

## <a name="interval-types-overview"></a>Översikt över intervalltyper

| Intervalltyp och beskrivning                                                                                                                                                                                                                                                                                                                                                                                                       | Radtyp: Tid                                                                                                                                                                                                                                                                                                                                                           | Radtyp: Räknare                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Intervalltyp: Upprepat från plandatum** Räkningen startar från det plandatum som används och när du planerar underhållsplaner skapas underhållsschemarader för när intervallet förväntas nås.                                                                                                                                                                                                                | **Plandatumet** på underhållsplanraden används. Om inget plandatum har valts på raden används **Plandatumet** för underhållsplanen. Exempel: Om siffran 3 infogas i fältet **Periodfrekvens** och "År" har valts i fältet **Period** skapas en ny underhållsschemarad en gång vart tredje år.                             | **Plandatumet** för underhållsplanen används. Om räknaren har ersatts används det senaste ersättningsdatumet som plandatum.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Intervalltyp: Upprepat från startdatum** Räkningen börjar från startdatumet på tillgångsrelationen. Datumet väljs i detaljvyn **Alla tillgångar** > snabbfliken **Underhållsplaner för tillgångar** > fältet **Startdatum** eller i detaljvyn **Alla funktionsplatser** > snabbfliken **Underhållsplaner** > fältet **Startdatum**. När du planerar underhållsplaner skapas en underhållsplanrad när intervallet nås. | Startdatum för underhållsplanraden på tillgången eller funktionsplatsen används. Om det fältet är tomt används **Plandatumet** för underhållsplanen.                                                                                                                                                                                                 | Startdatum för underhållsplanraden på tillgången eller funktionsplatsen används. Om det fältet är tomt används **Plandatumet** för underhållsplanen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Intervalltyp: Upprepat från senaste arbetsorder** Antalet starter från det faktiska slutdatumet och tiden för den senaste arbetsordern som slutfördes på till gången *och* kombinationen av variant av underhållsjobbtyp och yrkesgren. Datumet och tiden visas i fältet **Faktiskt slut** i detaljvyn **Alla arbetsorder**.                                                                                                                                 | Faktiskt slutdatum och faktisk sluttid för arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren används. Om ingen slutförd arbetsorder hittas används i stället ett av de datum som anges i intervalltypen "Upprepat från startdatum" som beskrivs ovan.                                                                                             | Faktiskt slutdatum och faktisk sluttid för arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren används. Om slutdatum och sluttid lämnades tomt på arbetsordern används i stället ett av de datum som anges i intervalltypen "Upprepat från startdatum" som beskrivs ovan.                                                                                                                                                                                                                                                                                                                                                                           |
| **Intervalltyp: En gång från plandatum** Se beskrivningen för intervalltypen "Upprepat från plandatum" ovan. Den enda skillnaden är att denna intervalltyp bara ska användas en gång.                                                                                                                                                                                                                                                   | Se beskrivning för intervalltypen "Upprepat från plandatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service.                                                                                                                                                                                                                             | Se beskrivning för intervalltypen "Upprepat från plandatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. **Anmärkning 1:** Den här intervalltypen är bara relevant om räknaren ersätts varje gång du utför ett underhållsjobb eller servicejobb. Om en räknare av någon anledning har ersatts före slutet av det planerade intervallet, beräknas en ny tid för jobbet från tidpunkten för bytet av räknaren. **Anmärkning 2:** Om räknaren ersätts när underhålls- eller servicejobbet slutförs, fungerar denna intervalltyp som intervalltypen "Upprepat från plandatum" ovan.                                             |
| **Intervalltyp: En gång från startdatum** Se beskrivningen för intervalltypen "Upprepat från startdatum" ovan. Den enda skillnaden är att denna intervalltyp bara ska användas en gång.                                                                                                                                                                                                                                                 | Se beskrivning för intervalltypen "Upprepat från startdatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service.                                                                                                                                                                                                                            | Se beskrivning för intervalltypen "Upprepat från startdatum" ovan. Det här intervallet används vanligtvis för ett engångsjobb för underhåll eller service. **Anmärkning 1** ovan gäller även för den här intervalltypen. **Anmärkning 3:** Om räknaren ersätts när underhålls- eller servicejobbet slutförs, fungerar denna intervalltyp som intervalltypen "Upprepat från startdatum" ovan.                                                                                                                                                                                                                                                                                                |
| **Intervalltyp: När övre nås** Den här intervalltypen gäller endast räknare och används för att indikera en övre gräns som ställts in på underhållsplanraden. Underhållsschemaposter får det förväntade startdatumet och tidpunkten för räknarregistreringen, vilket innebär att dessa poster skapas med ett förväntat startdatum som är lika med eller tidigare än systemdatumet.                                                | Inte tillämpligt                                                                                                                                                                                                                                                                                                                                                                       | Räknarintervallet indikerar en övre gräns. Om denna gräns överskrids när du skapar en räknarregistrering skapas en underhållsschemarad när du planerar förebyggande underhåll.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Intervalltyp: När nedre nås** Den här intervalltypen gäller endast räknare och används för att indikera en nedre gräns som ställts in på underhållsplanraden. Underhållsschemaposter får det förväntade startdatumet och tidpunkten för räknarregistreringen, vilket innebär att dessa poster skapas med ett förväntat startdatum som är lika med eller tidigare än systemdatumet.                                                 | Inte tillämpligt                                                                                                                                                                                                                                                                                                                                                                       | Räknarintervallet indikerar en nedre gräns. Om denna gräns passeras när du skapar en räknarregistrering skapas en underhållsschemarad när du planerar förebyggande underhåll.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Intervalltyp: Länkad från startdatum** (endast en gång) En underhållsplan kan innehålla fler rader med den här intervalltypen och dessa rader är kopplade till varandra. Vanligtvis skapar du en underhållsplan som innehåller enbart rader med den här intervalltypen. Underhållsschemarader skapas genom identifiering av den underhållsplanrad som har det första förväntade startdatumet och tiden.                                                                                                                                                                                                                                                                                                                                                                                           | Se beskrivning för intervalltypen "En gång från startdatum" ovan. Exempel: Du skapar två rader i en underhållsplan för ett servicejobb på en bil: en tidsbaserad rad med en 1-årsperiod och en räknarbaserad rad med en 25 000 km-gräns. En underhållsschemarad skapas för den gräns som först uppnås. För den här radtypen skapar du raden med 1-årsperioden.                                                                                                                                                                                   | Se beskrivning för intervalltypen "En gång från startdatum" ovan. Exempel: Du skapar två rader i en underhållsplan för ett servicejobb på en bil: en tidsbaserad rad med en 1-årsperiod och en räknarbaserad rad med en 25 000 km-gräns. En underhållsschemarad skapas för den gräns som först uppnås. För den här radtypen skapar du raden med 25 000 km-gränsen. Exempel för att skapa två räknarrader: Du kan också ställa in en underhållsplan med två länkade, räknarbaserade rader där den första raden har en gräns på 10 000 producerade artiklar och den andra raden gäller den maskin eller resurs som kräver service efter att ha körts 3 000 timmar.                                                                                                                                                           |
| **Intervalltyp: Länkat från senaste arbetsorder** (upprepas efter varje slutförd arbetsorder) En underhållsplan kan innehålla fler rader med den här intervalltypen och dessa rader är kopplade. Vanligtvis skapar du en underhållsplan som innehåller enbart rader med den här intervalltypen. Underhållsschemarader skapas genom identifiering av den underhållsplanrad som har det första förväntade startdatumet och tiden.                                                                                                                                                                                                                                                                                                                                                             | Den här intervalltypen fungerar på ett och samma sätt som "Länkat från startdatum", som beskrivs ovan. Den enda skillnaden är det datum som intervalltypen baseras på. Datumet som används är det faktiska datumet och tiden för den senaste arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren.                                                                                                                                                                                                                                                           | Den här intervalltypen fungerar på ett och samma sätt som "Länkat från startdatum", som beskrivs ovan. Den enda skillnaden är det datum som intervalltypen baseras på. Datumet som används är det faktiska datumet och tiden för den senaste arbetsordern som har slutförts på tillgången *och* kombinationen av underhållsjobbtyp / variant av underhållsjobbtyp / yrkesgren.                                                                                                                   |


>[!NOTE]
>När underhållsschemarader skapas för tidsbaserade underhållsplanrader är förväntad tid alltid början av dagen. För de räknarbaserade underhållsplanraderna kan förväntad tid vara när som helst under dagen.

Nedan finns exempel på hur du ställer in tidsbaserade och räknarbaserade underhållsplanrader:

**Exempel 1 - Tidsbaserad underhållsplanrad:** Ett smörjjobb kan ställas in i ett fast intervall, som inträffar en gång i veckan. För det ändamålet väljer du "Upprepat från plandatum" i fältet **Intervalltyp**, vilket visas i bilden nedan.

![Figur 2](media/02-preventive-maintenance.png)

**Exempel 2 – Tidsbaserad underhållsplanrad:** Ett inspektionsjobb kan ställas in för att genomföras ungefär en gång i veckan. För det ändamålet väljer du "Upprepat från senaste arbetsorder" i fältet **Intervalltyp**, vilket visas i bilden nedan.

![Figur 3](media/03-preventive-maintenance.png)

**Exempel 3 – Räknarbaserad underhållsplanrad**: En grafisk illustration av en timräknare för vilken en ny underhållsschemarad skapas varje gång 250 timmar har passerat. Intervalltypen för den här raden är "Upprepat från startdatum". Startdatumet är startdatumet för de relaterade tillgångarna i detaljvyn **Alla tillgångar** > snabbfliken **Underhållsplaner för tillgångar** > fältet **Startdatum** eller i detaljvyn **Funktionsplats** > snabbfliken **Underhållsplaner** > fältet **Startdatum**. Detta är ett exempel på en *förebyggande* underhållsplan eftersom underhållsplanraden skapas automatiskt varje gång som tröskelvärdet (+ 250) uppnås. Bilden nedan visar ett grafiskt exempel.

![Figur 4](media/04-preventive-maintenance.png)


**Exempel på 4 - Räknarbaserad underhållsplanrad:** En grafisk illustration av en minskning av räknarvärdet, som mäter slitage på bromsklossar. En underhållsschemarad skapas när en räknarregistrering under 20 mm skapas på bromsklossen. Intervalltypen för den här räknarraden är "När nedre nås" eller "En gång från senaste startdatum". Detta är ett exempel på en *reaktiv* underhållsplan eftersom underhållsschemaraden inte skapas förrän ett mått under 20 mm registreras. Bilden nedan visar ett grafiskt exempel.

![Figur 5](media/05-preventive-maintenance.png)


**Exempel 5 – Räknarbaserad underhållsplanrad**: En grafisk illustration av en räknare med en tröskel på -18 ° Celsius. En underhållsschemarad skapas när en räknarregistrering överstiger-18 ° Celsius görs. Intervalltypen för den här räknarbaserade raden är "När övre nås". Detta är ett exempel på en *reaktiv* underhållsplan eftersom underhållsschemaraden inte skapas förrän ett mått som är högre än -18 ° Celsius registreras. Bilden nedan visar ett grafiskt exempel.

![Figur 6](media/06-preventive-maintenance.png)

- När du skapar en ny tillgång och en sådan tillgång använder en tillgångstyp relaterad till en underhållsplan infogas underhållsplanen automatiskt i **Alla objekt** >  snabbfliken **Underhållsplaner för tillgångar**. I **Standardtyper för tillgång** på snabbfliken **Underhållsplaner** infogas automatiskt de relaterade underhållsplanerna.  
- Om du lägger till eller tar bort tillgångstyper eller funktionsplatstyper i **Underhållsplaner** kommer denna ändring bara att återspeglas i nya tillgångar som skapas efter att du gjort ändringen.  
- Om du lägger till eller tar bort resurser eller funktionsplatser i **Underhållsplaner** kommer denna ändring automatiskt att uppdateras i **Alla tillgångar** >  snabbfliken **Underhållsplaner för tillgångar** eller i **Alla funktionsplatser** >  snabbfliken **Underhållsplaner**.  


![Figur 7](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Lägga till en underhållsplan till en tillgång

1. Klicka på **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar** eller **Aktiva tillgångar**.

2. Välj tillgången som du vill ställa in en underhållsplan för och klicka på **Redigera**.

3. På snabbfliken **Underhållsplaner för tillgångar**, klicka på **Lägg till rad** för att lägga till en underhållsplan till tillgången.

4. Välj relevant underhållsplan i fältet **Underhållsplan**.

5. I fältet **Startdatum** väljer du det datum från vilket planering av förebyggande underhållsjobb kan utföras. 

6. Klicka på **Spara**. Fältet **Aktivt** uppdateras automatiskt.


![Figur 8](media/08-preventive-maintenance.png)
