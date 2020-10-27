---
title: Kom i gång med tillgångsleasing
description: I det här avsnittet beskrivs funktionen tillgångsleasing och visar information för dessa lån genom att följa stegen för att skapa ett tillgångsleasing.
author: moaamer
manager: Ann Beebe
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5f8f86861f65f3da71843f6fd4a64e4199e86627
ms.sourcegitcommit: 9668af8d918faec37abe1881e550872cd6b73259
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "3970018"
---
# <a name="asset-leasing-get-started"></a>Kom i gång med tillgångsleasing

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs funktionen tillgångsleasing och visar information för dessa lån genom att följa stegen för att skapa ett tillgångsleasing. Avsnittet definierar också vilken terminologi som används i användargränssnittet och i dokumentationen. Leasing av tillgångar är en avancerad funktion för hantering, spårning och automatisering av finansiella transaktioner för leasade tillgångar i Microsoft Dynamics 365 Finance. Leasing av tillgångar uppfyller IAS (IFRS 16) och US GAAP standard (ASC 842). Leasing av tillgångar samlar in och bearbetar information om leasing och genererar journalposter för leasingens livscykel från första redovisningstillfället, månatliga journalposter, till nedskrivningar och uppsägningar av leasingavtalet. Leasing av tillgångar integreras sömlöst med andra komponenter i Dynamics 365 Finance, inklusive anläggningstillgångar, leverantörsreskontra och redovisning.

Mer information om redovisningsstandarder finns i standarddokumentationen för IFRS 16 och US GAAP ASC 842.

## <a name="asset-leasing-elements"></a>Element för leasing av tillgångar
I bilden nedan visas huvudelementen i affärsprocessen för leasingavtal.

[![Element för leasing av tillgångar](./media/overview-01.png)](./media/overview-01.png)

En leasad tillgång innehåller följande huvudkomponenter:

- **Leasingavtal** - leasegivaren äger tillgången och samtycker till leasingtagaren att leasa en tillgång för en viss period i utbyte mot regelbundna leasingavgifter. Utöver det juridiska avtalet mellan leasegivaren och leasetagaren, inrättas beslut om förvaltning av ledningen, t.ex. sannolikheten för att ett förlängningsalternativ och överföring av äganderätten ska överlåtas.

- **Leasingberäkning och klassificering per redovisningsstandard** - leasingberäkningen och klassificeringen identifierar redovisningsstandarden som används vid den första och efterföljande mätningen, samt det klassificeringstest som avgör vad leasingtypen kommer att vara. En leasing kan vara en finansiell leasing, en operationell leasing, en kortfristig leasing eller en lågvärdesleasing. Systemet beräknar också nuvärdet av framtida minsta leasingavgifter för värdering och klassificering.

- **Leasingtransaktioner** - tillgångsleasing har stöd för det första erkännandet av tillgång med nyttjanderätt för leasing i balansräkningen, samt efterföljande mätningar för antingen leasing i balansräkning eller leasing utanför balansräkning. Den första igenkänningstransaktionen mäter nuvärdet av framtida lägsta leasingbetalningar. Dessa data används för att bestämma värdet på den initiala tillgång med nyttjanderätt som ska användas och leasingansvar, vilket påverkar företagets balansräkning. Vid den efterföljande mätningen av månatliga leasingtransaktion ingår en ackumulering av ränta på leasingbeloppet, vilket ökar leasingskulden. Den mäter också periodisering av leasingavgifter som minskar leasingskulden och som senare kommer att betalas ut till leasegivaren. Måttet inkluderar även amorteringen av den tillgång med nyttjanderätt.

  För leasing utanför balansräkningen beräknar systemet den linjära leasingkostnaden över den som är mindre: tillgångens ekonomiska livslängd eller leasingperioden. Leasingjusteringar mäter kontraktsändringar, t.ex. ett leasingtillägg eller en utökning och den nedskrivningstransaktion som använder den tillgång med nyttjanderätt som används som värde för ej återbetalningsbara kostnader.

  Leasing av tillgångar integreras med redovisningen för att säkerställa att alla bokförda leasingtransaktioner uppdaterar kontoplanen. Leasing av tillgångar integreras med leverantörsreskontra för att spåra leasegivare i leverantörsreskontra och ta framtida betalningar därifrån. Integreringen med anläggningstillgångar gör att du kan spåra leasingavtal i anläggningstillgångar som registrerats och bokför transaktioner tillgång med nyttjanderätt, inklusive det första redovisningstillfället, avskrivningen och nedskrivningen av tillgången, från anläggningstillgångar.   

## <a name="asset-leasing-components"></a>Komponenter för leasing av tillgångar 
Kartor för leasing av tillgångar, leasinginformation, betalningsplaner, start- och slutdatum samt betalningsfrekvensen. Det automatiserar även beräkningar för nuvärde, månatliga leasingbetalningar, ränta och leasingamortering. Systemet utför leasingklassificeringstest, beroende på konfigurationen. Systemet skapar och bokför även motsvarande leasingtransaktioner som är baserade på det ramverk som har definierats av redovisningsstandarden som du följer.

Följande diagram visar leasingboken, leasingavtalet, beräknad betalningsplan, klassificeringstesterna för leasing och leasingböcker samt motsvarande redovisningstransaktioner.

[![Leasing, leasingbok och betalningsplan](./media/overview-02.png)](./media/overview-02.png)

- **Leasingbok** - leasingboken innehåller all information om leasingavtalet, t.ex. leasingvillkor, verkligt värde och leasingbetalningar. Den innehåller också redovisningsstandarden som du följer, leasingtypen och tröskelvärdena som beaktas i leasingklassificeringstestet. Leasingboken innehåller också de leasingtransaktioner som bokförts i redovisningen. 
  
- **Leasing** - leasingen bevarar den information om leasing av tillgång som utgör grunden för leasing av tillgång, leasinginformationens källa är ett leasingavtal och ett ledningsbeslut som båda utförs utanför Dynamics 365 Finance. Tillgångens verkliga värde är det pris som skulle betalas för en tillgång i en transaktion på mätningsdatumet. Detta värde kan bero på tillgångstypen, marknadsvillkoren och andra kriterier som kan beaktas vid bedömningen. Det verkliga värdet för tillgången kommer att beaktas i klassificeringstestets ekvation.

- **Tillgångens livslängd** - Detta motsvarar de återstående perioderna för en tillgångs livslängd, från leasingens startdatum. Tillgångens livslängd kommer att beaktas i klassificeringstestets ekvation. Den skiljer sig från den livslängd som definierats i anläggningstillgångar.

- **Marginell låneränta** - Detta är den räntesats som används för att beräkna nuvärdet. Systemet använder den implicita satsen om den är definierad i leasingdata för att beräkna nuvärdet av leasingbetalningarna. Om den implicita satsen inte är definierad kommer systemet att använda marginell låneränta.

- **Typ av annuitet** - Denna leasingbetalning förfaller antingen i början av betalningsperioden eller vid slutet av perioden. Detta kan vara betalning i förskott eller förfallodatum (i början av leasingbetalningsperioden) eller vanlig annuitet (i slutet av leasingbetalningsperioden).

  Den första månaden kommer att betraktas som noll för förskottsbetalning. den första månaden kommer att betraktas som en betalning för resterande skuld.

- **Sammanslagningsintervall** - Detta motsvarar antalet perioder som ränta är sammansatta per år. Detta kan vara månads vis (12 perioder per år), kvartalsvis (fyra perioder per år), halvårs (två perioder per år) eller per år (en period per år). Antalet perioder kommer att beaktas vid beräkningen av nuvärdet.

- **Startdatum** - Detta är det datum då leasegivaren gör tillgången tillgänglig för användning av leasetagaren. Alla leasingberäkningar och transaktioner kommer att baseras på startdatumet. Startdatumet bör infalla i början av en period (månadens första dag) för att säkerställa att efterföljande beräkningar blir korrekta. Du kan använda fältet **signaturdatum för kontraktet** för att ange det faktiska datum då kontraktet undertecknades.

- **Leasingvillkor** - Detta är leasingperiodens längd, i månader.

> [!NOTE] 
> Definitionen av leasingperioden baseras på antalet perioder, eller intervall, på betalningsplanraderna. Det definierade antalet intervall kommer att konverteras till månader.

- **Betalningsplanrad** - detta registrerar leasingbetalningar per period. Det anger också om en förlängningsperiod ska utnyttjas och inkluderas i den initiala mätningen av tillgång med nyttjanderätt och leasingskuld. Du kan definiera startdatum för leasingbetalningar och periodintervall som representerar leasingens längd, som kan vara dagar, månader eller år.

- **Betalningsfrekvens** - Detta anger om betalningen är månatlig, kvartalsvis, halvårs eller årligen. Slutdatumet beräknas automatiskt utifrån startdatumet och antalet angivna perioder.

- **Betalningsplan** - Detta är det beräknade nuvärdet, baserat på den tidslängd som täcks av leasingbetalningarna, beloppen för betalningarna, periodens sammanlagda perioder och annuitetstyp.

- **Perioder** - Detta är de leasingperioder som återspeglar den sammansatta interna och annuitetstypen. Det sammanlagda intervallet avgör hur perioder delas upp. Du kan ställa in följande sammanlagda intervall:

  - Varje månad, 12 perioder per år
  - Varje kvartal, 4 perioder per år
  - Varje halvår, 2 perioder per år
  - Varje år, 1 period per år

Den första perioden börjar med period noll om annuitetstypen är förfallodatum för annuitet. Annars kommer den första perioden börja med en om annuitetstypen är utestående förfallna skulder.

- **Månader** - Detta indikerar antalet kalender månader över leasingtiden. Betalningsbeloppet är det belopp som har definierats enligt betalningsfrekvensen. Det beräknade nuvärdet är den aktuella värdebaserade leasingbetalningen per period, de sammansatta intervallen och marginell låneränta.

> [!NOTE] 
> Nuvärdet beräknas utifrån den diskonterade kassaflödesekvationen.

- **Böcker** - Detta är den förkonfigurerade inställningen för varje leasing. I boken definieras de tillämpliga redovisningsstandarderna, leasingtyperna och tröskeln som används som grund för klassificeringstesten. Klassificeringstest används för att ange leasingtypen automatiskt.

- **Redovisningsramverk** - det här visar den valda redovisningsstandarden, antingen IFRS 16 och ASC 842, som du har stöd för. Redovisningsstandarden anges i den bok som är kopplad till leasing. Redovisningsstandarden bestämmer vilka redovisningskonton som anges i bokföringsprofilen.

- **Leasingtyper** Detta visar vilken av de två typerna av leasing som kommer att användas, antingen en finansiell leasing eller ett operationell leasing. Enligt en finansiell leasing överförs risker och belöningar som rör leasad tillgång till leasetagaren. Under en operationell leasing behålls risker och belöningar som rör leasad tillgång med leasegivaren. Ett tredje alternativ är en automatisk identifiering av leasingtypen, antingen finansiell eller operationell, baserat på de definierade tröskelvärdena i boken. Denna automatiska identifiering utförs under omklassificeringstestet för leasing.

- **Tröskelvärden** - Detta används i testerna av leasingavtal för att fastställa om tillgången klassificeras som något av följande:

  - **Leasingvillkor** - Detta är den procentandel av nyttjande perioden som ska användas i klassificeringstestet. Leasingavtalet klassificeras som finansiell om leasingtypen är inställd på automatisk och om leasingperioden över tillgångens livslängd är större än eller lika med den procentsats som definierats här.

  - **Nuvarande värde** - Detta är den procentandel av tillgångens verkliga värde som ska användas i klassificeringstestet. Leasingavtalet klassificeras som finansiell om leasingtypen är inställd på automatisk och om det nuvarande värdet av framtida leasingbetalningar över tillgångens verkliga värde är större än eller lika med den procentsats som definierats här.

  - **Kortsiktig leasing** - om leasingperioden är mindre än eller lika med det definierade värdet, kommer leasing att klassificeras som en kortsiktig leasing.

  - **Lågvärde** - om tillgångens verkliga värde är mindre än eller lika med det definierade värdet, kommer leasing att klassificeras som en lågvärdesleasing.

  - **Leasingklassificering och transaktioner** Leasingklassificering är en automatiserad process för att klassificera leasing på grundval av fastställda tröskelvärden i böcker förutom andra klassificeringskriterier för att identifiera om leasingen är en finansiell leasing, operationell leasing, korttidsleasing eller lågvärdesleasing. Detta används även för att identifiera om processen för uppskjuten hyra följs.

Klassificeringstest omfattar överföring av ägarskap, inköpsalternativ, leasingperiod, nuvärde och unik tillgång. I följande diagram illustreras testerna av leasingklassificeringen.

[![Test av leasingklassificering](./media/overview-03.png)](./media/overview-03.png)

Varje leasingtyp hanterar redovisningen på olika sätt för olika leasingtransaktioner. Transaktionerna inkluderar initial bokföring, räntekostnad, förfallen leasingbetalning och leasingavskrivning och de baseras på följande redovisningsstandarder (IFRS 16 eller ASC 842). Redovisningskonton definieras under leasingbokföringsprofilen för varje transaktionstyp och redovisningsramverk.

## <a name="asset-leasing-transactions"></a>Transaktioner för tillgångsleasing

#### <a name="initial-recognition"></a>Första redovisningstillfälle 
Den första redovisningen av en leasad tillgång använder det beräknade nuvärdet så att det kan rapporteras i balansräkningen. Redovisningsposten för detta genereras automatiskt. Transaktionen debiterar kontot för tillgång med nyttjanderätt och krediterar kontot för operationell leasingskuld enligt följande. Om en anläggningstillgång är kopplad till leasingen återspeglas den ursprungliga bokföringstransaktionen som anskaffning av anläggningstillgångar. I det här scenariot måste du definiera en bokföringsprofil för anläggningstillgångar som ska bokföras på kontot för tillgång med nyttjanderätt. 

> [!NOTE]
> Operationell leasing stöds bara av US GAAP ASC 842.

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operationell leasing under US GAAP              |     Tillgång med nyttjanderätt      |     Operationell leasingskuld       |
|     Finansiell leasing under IFRS och US GAAP        |     Tillgång med nyttjanderätt      |     Operationell leasingskuld       |

#### <a name="lease-liability-amortization-interest-expense"></a>Amortering av leasingskuld (räntekostnader) 
Räntan för en leasing identifieras genom att ränta beräknas för leasingens startbalans, leasingbetalningar per period, låneränta och sammansatta intervallperioder per år. Räntebeloppet ökar det konto som används för att låna ut skulden genom att kreditera det, som återspeglas i företagets balansräkning. Transaktionen inkluderar också en debettransaktion till kontot för räntekostnader, som återspeglas i resultaträkningen för ekonomiska leasingavtal och till utgiftskontot för leasing för operationell leasing.

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Post för operationell leasingskuld under US GAAP ASC 842    |     Räntekostnad          |     Operationell leasingskuld         |
|     Post för finansiell leasingskuld under IFRS och US GAAP      |     Räntekostnad          |     Finansiell leasingskuld           |

#### <a name="accrued-lease-payment"></a>Upplupen leasingbetalning
En upplupen leasingbetalning identifieras som en framtida betalning för leasingavtal som beror på att processen är en betalningstransaktion från bank eller kontantkonton. Leasingbetalningen minskar leasingskulden genom att debitera leasingskuldkontot mot om en leverantörs under redovisning har definierats som en leverantör, eller när kreditsidan bokförs till ett huvudbokskonto för växelskuld då betalningen utförs mot antingen leverantör eller växelskuld.

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operationell leasing under US GAAP              |  Operationell leasingskuld    |   Leverantörsskuld (redovisning)/växelskuld  |
|     Finansiell leasing under IFRS och US GAAP        |  Finansiell leasingskuld      |   Leverantörsskuld (redovisning)/växelskuld  |

#### <a name="asset-depreciation"></a>Avskrivning av tillgång
Tillgång med nyttjanderätt skrivs av över det som är mindre - tillgångens livslängd eller leasingperioden. Metoden för att beräkna avskrivning för US GAAP (ASC 842) baseras på skillnaden mellan den linjära leasingkostnaden och räntebeloppet. Ränta på finansiell leasing beräknas med en linjär standardmetod. Leasingavskrivningen påverkar vinst- och förlusträkningen genom att debitera räntekostnader. Balansräkningen påverkas av att du krediterar ackumulerad tillgång med nyttjanderätt för finansiell leasing. För operationell leasing krediterar avskrivningen leasingutgiftskontot. Om leasing är kopplad till en anläggningstillgång utförs avskrivningstransaktionerna endast från modulen för anläggningstillgångar. 

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operationell leasing under US GAAP              |  Leasingkostnad                |   Ackumulerad avskrivning av tillgång med nyttjanderätt     |
|     Finansiell leasing under IFRS och US GAAP        |   Utgift för avskrivning av tillgång med nyttjanderätt   |   Ackumulerad avskrivning av tillgång med nyttjanderätt    |

#### <a name="short-term-lease"></a>Korttidsleasing
En korttidsleasing identifieras som en utgift, vilket kommer att påverka en organisations resultaträkning. Den genererade leasingbetalningen debiterar kontot för leasingkostnader och krediterar växelskulden eller leverantörens redovisningskonto.

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Post för korttidsleasing under IFRS och US GAAP     |  Leasingkostnad                |   Leverantörsskuld (redovisning)/växelskuld  |

#### <a name="low-value-lease"></a>Lågvärdesleasing
En lågvärdesleasing identifieras som en utgift, vilket kommer att påverka en organisations resultaträkning. Den genererade leasingbetalningen debiterar leasingkostnaden och krediterar växelskulden eller leverantörens redovisning.

|     Typ                                          |     Debet                     |     Kredit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Post för lågvärdesleasing under IFRS och US GAAP      |  Leasingkostnad                |   Leverantörsskuld (redovisning)/växelskuld  |


#### <a name="index-revaluation"></a>Omvärdering av index
Detta är kontot för tillgångsleasing för variabla leasingbetalningar som mäts med en indexränta. Ändringar i leasingbetalning som orsakas av förändringar i indexränta utgör en leasingjustering enligt IFRS 16. Leasingskulden och tillgångar med nyttjanderätt kommer att justeras för att redovisa de nya betalningarna. 

|     Typ                                          |     Debet                             |     Kredit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Indexomvärderingsposter under IFRS vid ökning  |  Tillgång med nyttjanderätt       |   Operationell leasingskuld |
|   Indexomvärderingsposter under IFRS vid minskning  |  Operationell leasingskuld  |   Tillgång med nyttjanderätt      |

När betalningarna ändras på grund av en ändring i indexräntan, ändras endast de variabla betalningarna om det inte finns några ändringar av kassaflöden, t.ex. ändringar i leasingvillkor som är relaterade till räntesatser under US GAAP ASC 842.

#### <a name="lease-adjustment"></a>Leasingjustering
Leasing av tillgångar gör att leasing kan justeras om leasingvillkoren ändras, leasing utökas eller om det finns ytterligare omständigheter under vilka ett leasing kräver en justering. Leasingjusteringar bokförs för att öka eller minska tillgång med nyttjanderätt och leasingskuld. Justeringsprocessen överför utgående saldon för skuldamortering och tillgångens saldo på justeringsdatumet. När en leasing kopplas till en anläggningstillgång bokförs den faktureringsjustering som används för användning av det ID som har tilldelats för anläggningstillgångar. 

|     Typ                                          |     Debet                             |     Kredit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Leasingjusteringspost för IFRS och US GAAP vid ökning     |  Tillgång med nyttjanderätt       |   Operationell leasingskuld |
|   Leasingjusteringspost för IFRS och US GAAP vid minskning     |  Operationell leasingskuld  |   Tillgång med nyttjanderätt      |


#### <a name="lease-impairment"></a>Leasingnedskrivning
Detta motsvarar överföring av saldoavdrag för tillgång med nyttjanderätt. Identifiera beloppet för nedskrivning, transaktionsdatum och perioder som återstår. Den kvarvarande tillgång med nyttjanderätt kan periodiseras på linjär basis. Nedskrivningslogiken för leasing tar hänsyn till tillgångens överföringsvärde i avskrivningsplanen för tillgången.  

|     Typ                                          |     Debet                             |     Kredit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Nedskrivningstransaktion för IFRS och US GAAP           |  Nedskrivningsutgift                   |    Tillgång med nyttjanderätt     |

>[!NOTE]
> Om leasingen kopplas till en anläggningstillgång ska nedskrivningen bokföras från anläggningstillgångar eftersom avskrivning av tillgångar körs från modulen för anläggningstillgångar.

**Dubbel valuta** Leasingtransaktioner kan bokföras i en annan valuta än redovisnings- och rapporteringsvalutan. Valutakursen definieras i redovisningen vid startdatumet. Du kan ändra valutakurserna genom att ställa in fältet **fast valutakurs** till **ja** när du skapar leasingen. När du anger leasingtransaktioner använder den första bokföringstransaktionen och de efterföljande avskrivningstransaktionerna använder valutakursen från och med startdatumet. De efterföljande betalningarna och räntetransaktionerna kommer att använda den aktuella aktiva valutakursen. 

## <a name="create-an-asset-lease"></a>Skapa en tillgångsleasing
Gör på följande sätt om du vill skapa en ny leasing. 

1. Om du vill använda **Leasing av tillgångar** måste du aktivera den med arbetsytan **Funktionshantering**. Från arbetsytan **Funktionshantering**, välj **Alla** så att alla funktioner visas på sidan. Välj **Leasing av tillgångar** och välj sedan **Aktivera nu**.
2. Gå till **Leasing av tillgångar > Vanlig > Sammanfattning av leasing**. Ange obligatoriska fält på snabbfliken **Allmänt**. 
   - **Leasingdetaljer**
   - **Tillgångens livslängd (månader)**
   - **Leasinggrupp**
   - **Marginell låneränta (%)**
   - **Intervall för sammanslagning**
   - **Typ av annuitet**
   - **Valuta**
   - **Startdatum**

3. Flytta till snabbfliken **Betalningsplanrader** och ange en betalningsrad och välj sedan **Skapa scheman**.

4. Välj **Räkenskapsböcker**. 

5. Växla till snabbfliken **Allmänt**. Den **initiala tillgång med nyttjanderätt** och **leasingskuld** beräknas. 

6. Flytta till snabbfliken **Test av leasingklassificering** om du vill kontrollera värdet i fältet **Leasingtyp**. 

   Den automatiska **Leasingtypen** delas utifrån kriterierna som definieras på sidan **Böcker**.

7.  Gå till **Betalningsplan** under avsnittet **Funktioner**.  

   På sidan **Betalningsplan** visas framtida betalningsplaner för ett leasing-ID. Välj **Bekräfta schema** om du vill kunna bokföra transaktionerna för **första redovisningen**. 

[![Funktionen första redovisningen](./media/overview-13.png)](./media/overview-13.png)

8. Välj **första redovisningstillfället** för att skapa journalen för första redovisningstillfället. 

9. Välj **Journaler för leasing av tillgångar** om du vill bokföra transaktionen för första redovisningstillfället. 

   Från betalningsplanen kan du öppna en detaljerad sida med en lista över de tillgångar med nyttjanderätt som används för tillfället. 
 
   **Planen för amortering av leasingskulder** visar det räntebelopp som har beräknats för varje period.
   
10. Skapa journalen och gå till **Journaler för leasing av tillgångar**. **Planen för amortering av leasingskulder** visas också i räntetransaktionerna.

   Sidan **avskrivningsplan för tillgången** visar avskrivningstransaktioner för valt leasing-ID. 

   [![Sida för ROU transaktioner för tillgång](./media/overview-20.png)](./media/overview-20.png)

   Sidan **ROU transaktioner för tillgång** anger första redovisningstillfället, ackumulerad avskrivning och tillgångens saldo. 

   På sidan **Transaktion av leasingskulder** visas det första redovisningstillfället, betalningen av leasingränta, leasingbetalning och saldo för leasingskuld. 

