---
title: Negativa dagar och dynamiska negativa dagar
description: Det här ämnet innehåller information om negativa dagar och dynamiska negativa dagar och hur du kan använda dem för att hjälpa ditt företag.
author: ChristianRytt
ms.date: 05/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37ae6ebd4347d3bbb414b7f1e4e0d54150878c02
ms.sourcegitcommit: c5c8f19a696ad4a3d68dffd63bfe7b484b999d2b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6097244"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Negativa dagar och dynamiska negativa dagar

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om negativa dagar och dynamiska negativa dagar och hur du kan använda dem för att hjälpa ditt företag. *Tidsgränsen för negativa dagar* representerar antalet dagar som du är villig att vänta innan du beställer ny påfyllnad när du har negativt lager.

I det här avsnittet kommer dun att få följande information:

- Hur planerade order har skapats
- Korrelationen mellan de negativa dagarnas tidsgräns och artikelns produktionstid
- Hur tidsgränsen för dynamiska negativa dagar beräknas och hur artikelns produktionstid debiteras i beräkningen
- Så här tolkar du [förslagen för att förbättra körtiden för behovsplanering av material (MPS) (huvudplanering) som är relaterade till negativa dagar](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx)

I det här avsnittet används tre hypotetiska scenarier för att förstå den här informationen. Skillnaden mellan scenariona är den punkt där du får efterfrågan: före, under eller efter artikelns produktionstidsperiod.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Scenario 1: du får efterfrågan innan artikelns produktionstidsperiod

Du kan få efterfrågan antingen relativt tidigt i artikelns produktionstid eller strax innan produktionstiden börjar. Här följer ett exempel på detta scenario:

- DemoProduct-artikeln har en inköpstid på sex dagar.
- På dag noll (1 januari) är lager nivån för DemoProduct artikel 0 (noll).
- På dag noll (1 januari) får du en försäljningsorder för en kvantitet på 10 av den DemoProduct-artikeln.
- På dag sju (8 januari) finns det en befintlig inköpsorder för kvantiteten 10 av DemoProduct-artikeln.

Bilden nedan visar en grafisk vy av detta scenario.

![Grafisk vy över scenario 1](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Fall A: negativa dagar är mindre än artikelns produktionstid

Om du ställer in de negativa dagarna till ett tal som är mindre än artikelns produktionstid söker MPS efter inleveranser för DemoProduct-artikeln inom de negativa dagarnas tidsgräns. Eftersom det inte finns några inleveranser skapar MPS en ny planerad inköpsorder. Denna planerade ordern försenas omedelbart med sex dagar (produktionstiden). Därför kommer den att anlända den 7 januari. Den befintliga inköpsordern hämtar åtgärdsmeddelandet **Avbryt**, eftersom skapandet av den nya planerade inköpsordern har gjort den överflödig.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall A för scenario 1](./media/negative-days-2.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall A för scenario 1](./media/negative-days-3.png)

Om du anser att MPS-prestanda och planens nerver fungerar, så är detta inte bra. MPS måste skapa en ny planerad order och måste beräkna förseningar och åtgärder. Dessa uppgifter är tidskrävande. Detta innebär också att ytterligare två transaktioner läggs till i planen. Å andra sidan försenas försäljningsordern med endast sex dagar, inte sju dagar.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Fall B: negativa dagar är mer än artikelns produktionstid

För att förbättra MRP-prestanda kan du ställa in de negativa dagarna till ett tal som är mer än artikelns produktionstid. Eftersom du inte får tillgång inne i produktionstiden i det här scenariot, kan du söka efter inleveranser så länge som sökningen verkar vettig. Även om körningstiden för MPS är kortare, bör du se upp för fler förseningar för orderna.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Fall C: Korrelera automatiskt artikelns produktionstid till negativa dagens tidsgräns

För att korrelera automatiskt artikelns produktionstid till negativa dagens tidsgräns använder du dynamiska negativa dagar. Om du vill använda dynamiska negativa dagar går du till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar** och sedan på fliken **Allmänt** i avsnittet **Täckning** anger du alternativet **använda dynamiska negativa dagar** till **Ja**. MRP söker sedan efter inleveranser inom den dynamiska negativa dagarnas tidsgräns. Tidsgränsen beräknas genom att använda följande formel:

Dynamiska negativa dagars tidsgräns = Ledtid för inköp + negativa dagarnas tidsgräns + (aktuellt datum – behovsdatum)

(Om standardordertypen för DemoProduct-artikeln är **produktion** eller **överföring** produktionstiden är **lagret** produktionstiden.)

När dynamiska negativa dagar används, är tidsgränsen som MPS kontrollerar för inleveranser nu 6 + 2 + 0 = 8 dagar. MRP hittar den befintliga inköpsordern och fixerar försäljningsordern mot den. Inga nya planerade order har skapats. Därför är körningstiden för MPS kortare. Följande bild visar nettobehoven för den DemoProduct-artikeln.

![Nettobehov för ärende C för scenario 1](./media/negative-days-4.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall C för scenario 1](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Fall D: Använd endast dynamiska negativa dagar

Om du ställer in de negativa dagarna till **0** (noll) och bara använder tidsgränsen för dynamiska negativa dagar, är tidsgränsen för dynamiska negativa dagar 6 + 0 + 0 = 6 dagar. I det här fallet är resultatet detsamma som resultatet i fall A i det här scenariot. MPS måste skapa en ny planerad order och måste beräkna förseningar och åtgärder. Dessa uppgifter är tidskrävande och kan också vara frustrerande. Det finns också två fler transaktioner att bearbeta. Eftersom efterfrågan inte kan uppfyllas i en tid då artikeln ska anlända, lägger detta fall till onödiga komplikationer i planen.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall D för scenario 1](./media/negative-days-6.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall D för scenario 1](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Fall E: Använd både negativa dagar som är mer än artikelns produktionstid och de dynamiska negativa dagarna tidsgräns

Om du ställer in de negativa dagarna till ett tal som är mer än artikelns produktionstid, och om du även använder tidsgränsen för dynamiska negativa dagar, så är tidsgränsen för dynamiska negativa dagar 6 + 6 + 0 = 12 dagar. Den här metoden kan ge en mycket lång tidsgräns som MPS måste söka efter resultat i. Mer information om hur ärende E är relaterat till en situation där du ställer in de negativa dagarna till en lång tidsgräns finns i avsnittet [slutsats](#conclusion) i det här avsnittet.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Scenario 2: du får efterfrågan under artikelns produktionstidsperiod

Du kan få behov av en stund under artikelns produktionstid. Här följer ett exempel på detta scenario:

- DemoProduct-artikeln har en inköpstid på sex dagar. 
- På dag noll (1 januari) är lager nivån för DemoProduct artikel 0 (noll).
- På dag fyra (januari 5), som finns inuti artikelns produktionstid, får du en försäljningsorder för en kvantitet på 10 av den DemoProduct-artikeln.
- På dag sju (8 januari) finns det en inköpsorder för kvantiteten 10 av DemoProduct-artikeln.

Bilden nedan visar en grafisk vy av detta scenario.

![Grafisk vy över scenario 2](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Fall A: negativa dagar är mindre än artikelns produktionstid

Om du ställer in de negativa dagarna till ett tal som är mindre än artikelns produktionstid söker MPS efter inleveranser för DemoProduct-artikeln inom de negativa dagarnas tidsgräns. Eftersom det inte finns några inleveranser skapar MPS en ny planerad inköpsorder som använder det aktuella datumet som orderdatum. Denna planerade ordern försenas omedelbart med sex dagar (produktionstiden). Därför kommer den att anlända den 7 januari. Den befintliga inköpsordern hämtar åtgärdsmeddelandet **Avbryt**, eftersom skapandet av den nya planerade inköpsordern har gjort den överflödig.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall A för scenario 2](./media/negative-days-9.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall A för scenario 2](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Fall B: negativa dagar är mer än artikelns produktionstid

Detta fall liknar fall B för scenario 1. Om du ställer in de negativa dagarna till ett tal som är mer än artikelns produktionstid får du ingen ny planerad order. Försäljningsordern är kopplad till den befintliga inköpsordern.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Fall C: Korrelera automatiskt artikelns produktionstid till negativa dagens tidsgräns

Detta fall liknar fall C för scenario 1 eftersom dynamiska negativa dagar fungerar precis som de gör i så fall. Tidsgränsen för dynamiska negativa dagar är nu 6 + 2 – 4 = 4 dagar. Om du använder den här metoden söker MPS efter den befintliga inköpsordern och kopplar försäljningsordern till den. Eftersom inga nya planerade order skapas är körningstiden för MPS kortare.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall C för scenario 2](./media/negative-days-11.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall C för scenario 2](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Fall D: Använd endast dynamiska negativa dagar

Om du ställer in de negativa dagarna till **0** (noll) och bara använder tidsgränsen för dynamiska negativa dagar, är tidsgränsen för dynamiska negativa dagar nu 6 + 0 – 4 = 2 dagar. I det här fallet är resultatet detsamma som resultatet i fall A i det här scenariot. En grafisk vy över vad som händer finns i fall A för det här scenariot.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Fall E: Använd både negativa dagar som är mer än artikelns produktionstid och de dynamiska negativa dagarna tidsgräns

Om du ställer in de negativa dagarna till ett tal som är mer än artikelns produktionstid, och om du även använder tidsgränsen för dynamiska negativa dagar, så är tidsgränsen för dynamiska negativa dagar 6 + 6 – 4 = 8 dagar. Den här metoden kan ge en mycket lång tidsgräns som MPS måste söka efter resultat i. Mer information om hur ärende E är relaterat till en situation där du ställer in de negativa dagarna till en lång tidsgräns finns i avsnittet [slutsats](#conclusion) i det här avsnittet.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Scenario 3: du får efterfrågan efter artikelns produktionsti

Du kanske får efterfrågan efter artikelns produktionstid Här följer ett exempel på detta scenario:

- DemoProduct-artikeln har en inköpstid på sex dagar.
- På dag noll (1 januari) är lager för DemoProduct artikel 0 (noll).
- På dag sju (januari 8), som finns utanför artikelns produktionstid, får du en försäljningsorder för en kvantitet på 10 av den DemoProduct-artikeln.
- På dag tio (11 januari) finns det en inköpsorder för kvantiteten 10 av DemoProduct-artikeln.

Bilden nedan visar en grafisk vy av detta scenario.

![Grafisk vy över scenario 3](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Fall A: negativa dagar är mindre än artikelns produktionstid

Om du ställer in de negativa dagarna till ett tal som är mindre än artikelns produktionstid ser MPS ut två dagar före försäljningsorderns behovsdatum. Eftersom det inte finns något skapar MPS en ny planerad inköpsorder den 2 januari. Den här planerade inköpsordern levereras i rätt tid för att försäljningsorderns behov ska uppfyllas. Den befintliga inköpsordern hämtar åtgärdsmeddelandet **Avbryt** eftersom det inte är nödvändigt.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall A för scenario 3](./media/negative-days-14.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall A för scenario 3](./media/negative-days-15.png)

> [!NOTE]
> På föregående skärmbild är inköpsorderns behovsdatum är 12 januari. Eftersom skärmbilden togs år 2015, när 11 januari var söndag, flyttade MRP behovsdatumet till nästa arbetsdag, som var måndag den 12 januari. Inköpsordern har dock ett leveransdatum på 11 januari.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Fall B: negativa dagar är mer än artikelns produktionstid

Om du ställer in de negativa dagarna till ett tal som är mer än artikelns produktionstid får du ingen ny planerad order. Försäljningsordern är peggad mot den befintliga inköpsordern. Därför är försäljningsordern försenad. Om du skapar en planerad order kan du leverera försäljningsordern i tid.

Bilden nedan visar en skärmbild av det här fallet.

![Skärmbild av fall B för scenario 3](./media/negative-days-16.png)

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall B för scenario 3](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Fall C: Korrelera automatiskt artikelns produktionstid till negativa dagens tidsgräns

Detta fall liknar fall C för scenario 1 eftersom dynamiska negativa dagar fungerar precis som de gör, om inte bättre, i fall B för detta scenario.

Tidsgränsen för dynamiska negativa dagar är 6 + 2 – 7 = 1 dag. I det här fallet tar systemet fortfarande hänsyn till negativa dagar i produktionstiden (2), eftersom det högsta värdet i produktionstiden mellan de negativa dagarna och de dynamiska negativa dagarna betraktas som netto. I det här fallet är därför resultatet detsamma som resultatet i fall A i det här scenariot.

Bilden nedan visar en grafisk vy av vad som händer i detta fall.

![Grafisk vy av fall C för scenario 3](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Fall D: Använd endast dynamiska negativa dagar

Om du ställer in de negativa dagarna till **0** (noll) och bara använder tidsgränsen för dynamiska negativa dagar, är tidsgränsen för dynamiska negativa dagar nu 6 + 0 – 7 = -1 dag. I detta fall tar systemet fortfarande hänsyn till den negativa dagars produktionstiden (2). I det här fallet är därför resultatet detsamma som resultatet i fall A i det här scenariot och har samma nackdelar. En grafisk vy över vad som händer finns i fall A för scenario 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Fall E: Använd både negativa dagar som är mer än artikelns produktionstid och de dynamiska negativa dagarna tidsgräns

Det här fallet är samma som fall E för scenarier 1 och 2. Det har i grunden samma fördelar och nackdelar.

## <a name="conclusion"></a>Slutsats

Eftersom de tre scenarierna i det här avsnittet visas är det en god idé att ställa in de negativa dagarna till ett tal som är mer än produktionstiden för artiklarna i disponeringsgruppen. Det är också en bra idé att bara använda dynamiska negativa dagar och att ställa in de negativa dagarna till det antal dagar som du är villiga att vänta innan du beställer ny påfyllnad när du har ett negativt lager (dvs. antalet dagar som du är villiga att ytterligare försena efterfrågan för). Dessutom bör artiklar i samma disponeringsgrupp ha liknande produktionstider.

Om du ställer in de negativa dagarna till **0** (noll) och inte använder dynamiska negativa dagar, skapar MPS alltid en ny planerad order för att uppfylla efterfrågan. I det här fallet är det viktigt att du arbetar med åtgärdsmeddelandena för att vara säker på att du inte registrerar lagret.

Du kanske vill ställa in de negativa dagarna till en lång tidsgräns och sedan arbeta med åtgärdsmeddelandena. Den här metoden ger bra planeringsresultat, men det blir också långsammare. Det kan också vara svårare att analysera eftersom du måste analysera och tillämpa åtgärdsmeddelandena. Här är ett exempel:

- DemoProduct-artikeln har en inköpstid på sex dagar.
- På dag noll (1 januari) är lager för DemoProduct artikel 0 (noll).
- På dag noll (1 januari) får du en försäljningsorder för en kvantitet på 10 av den DemoProduct-artikeln.
- På dag nio (10 januari) får du en försäljningsorder för en kvantitet på 10 av den DemoProduct-artikeln.
- På dag elva (12 januari) finns det en inköpsorder för kvantiteten 10 av DemoProduct-artikeln.
- Negativa dagar ställs in på **20** vilket är mycket mer än artikelns produktionstid.

Bilden nedan visar en grafisk vy av vad som händer.

![Grafisk granskning av exemplet](./media/negative-days-19.png)

MRP ger följande resultat.

![Resultatexempel 1](./media/negative-days-20.png)

I föregående skärmbild är försäljningsorderns behovsdatum är 9 januari i stället för 10 januari. Eftersom skärmbilden togs år 2015, när 10 januari var lördag, flyttade behovsdatumet för ordern till föregående arbetsdag, som var fredag den 9 januari.

MPS skapar en planerad inköpsorder för att uppfylla efterfrågan som begärs av den första försäljningsordern, men du rekommenderas även att annullera den planerade ordern, eftersom du kan flytta fram den befintliga inköpsordern och öka kvantiteten på den.

Resultatet är inte fel, men körtiden för MPS kan vara längre, eftersom MPS måste skapa alla förseningar och förslag. Dessutom kan planeraren kräva mer tid för att förstå MRP-resultaten. I det här fallet är det viktigast att det är viktigt att planeraren förstår och använder åtgärdsmeddelandena.

Om du minskar de negativa dagarna till en siffra som ligger närmare artikelns produktionstid och använder dynamiska negativa dagar, ger MPS följande resultat.

![Resultatexempel 2](./media/negative-days-21.png)

MPS skapar en planerad order som är kopplad till den första försäljningsordern. Sedan, som förväntat, peggas den andra försäljningsordern mot den befintliga inköpsordern, baserat på inställningen för negativa dagar. Det här planeringsresultatet är också korrekt och körningstiden för MPS kan vara kortare. I det här fallet är det inte nödvändigt att förstå och veta hur man arbetar med åtgärdsmeddelandena.

För att garantera att rätt värden registreras för ditt företag måste du tänka på både funktionaliteten och körningstiden i MPS. Därför kan det bli en liten utvärderingsversion och fel att fastställa de optimala värdena.

## <a name="see-also"></a>Se även

Mer information finns i ursprungliga blogginlägget [mer om (dynamiska) negativa dagar](/archive/blogs/axmfg/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
