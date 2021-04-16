---
title: Påfyllnadsallokering
description: I det här avsnittet beskrivs hur du ställer in påfyllnadsallokeringssteget, bland annat hur du aktiverar parallellbearbetning för det.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: feee33a7d4ea3f0d9c4d671210293a28aac14f61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823177"
---
# <a name="wave-allocation"></a>Påfyllnadsallokering

[!include [banner](../includes/banner.md)]

Påfyllnadsbearbetning kan vara tidskrävande och den största delen av bearbetningstiden läggs på allokeringssteget och i arbetsskapandesteget.

Det är nu möjligt att köra varje steg parallellt, vilket kan förbättra prestandan för påfyllnadsbearbetningen och tillåta ett större genomflöde av påfyllnader i samma lagerställe. I det här avsnittet beskrivs hur du ställer in den påfyllnadsallokeringsmetod som ska köras parallellt. Mer information om hur du ställer in att skapande av arbete ska köras parallellt finns i [Planera skapande av arbete under påfyllnad](configure-wave-schedule-work-creation.md).

Tidigare var det bara möjligt att fördela en påfyllnad vid ett lagerställe åt gången. Begränsningen har tagits bort och ersatts av en ny begränsning som bara låser artikeln och dimensionerna som finns ovanför platsen i reservationshierarkin. Dimensioner ovanför platsen inkluderar alltid produktdimensioner. Om till exempel en artikel har konfigurerats med hjälp av *Färg*, kan varianterna för *Röd*, *Blå* och *Gul* bearbetas parallellt.

Det innebär att om samma artikel med samma dimensioner ovanför platsen allokeras av en påfyllnad, måste andra påfyllnader vänta och få ett lås på samma artikel och dimensioner. Om låset inte kan anskaffas inom rimlig tid uppstår ett fel och påfyllnadsbearbetningen misslyckas.

För att parallellbearbetning ska kunna användas måste påfyllnad köras i batch.

## <a name="performance-improvements"></a>Prestandaförbättringar

Prestandaförmåner vid parallell bearbetning finns i två kategorier:

- **Förbättrat genomflöde** - Genomflödet för påfyllnader förbättrar vanligtvis även om parallellbearbetning av påfyllnaden inte är konfigurerad, särskilt för scenarier där det inte finns någon överlappning av artiklar inom påfyllnaden.
- **Förbättring av allokeringen för en enstaka påfyllnad** - Testning av kunddata har visat en prestandaförbättring på nära 50 % efter att den har växlats till parallell allokering. Den parallella bearbetningen görs per artiklar och dimensioner ovanför platsen, så förbättringarna beror på hur många olika artiklar en påfyllnad innehåller, den tillgängliga infrastrukturen och längden på allokeringen jämfört med längden på skapandet av arbetet.

## <a name="configure-parallel-allocation"></a>Konfigurera en parallell allokering

### <a name="warehouse-management-parameters"></a>Parametrar för lagerstyrning

Om du vill använda parallell allokeringsbearbetning går du till **Lagerstyrning > Inställningar > Parametrar för lagerstyrning**, öppnar fliken **Påfyllnadsbearbetning** och gör följande inställningar:

- **Påfyllnadsbearbetning av batchgrupp** - Välj den batchgrupp som den första bearbetningen av påfyllnaden ska använda. Den efterföljande bearbetningen av allokeringen kan göras med hjälp av olika batchgrupper.
- **Bearbeta påfyllnader i batch** - Ställ in detta till *Ja* om du vill använda parallell bearbetning.
- **Vänta till lås (ms)** - Ange tiden, i millisekunder, som ett allokeringssteg ska vänta på en systemresurs som har låsts av ett annat allokeringssteg. När denna tid överskrids, bearbetas påfyllnaden inte, och ett meddelande visas. Vi rekommenderar att du minst några sekunder tillåter att allokeringen av en logisk enhet slutförs.

Information om dessa och andra alternativ för påfyllnadsbearbetning på sidan **Lagerstyrningsparametrar** finns i [Lagerställeparametrar för påfyllnadsbearbetning](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Metoder för bearbetning av påfyllnad

Så här ställer du in parallellbearbetning:

1. Gå till **Lagerstyrning > Inställningar > Påfyllnader > Metoder för påfyllnadsprocess**.
1. Välj `allocateWave`-metod i rutnätet.
1. Klicka på **Uppgiftskonfiguration** i åtgärdsfönstret.
1. Sidan **Uppgiftskonfiguration av påfyllnadspostmetod** öppnas. I det här rutnätet visas en lista över alla lagerställen där du har konfigurerat `allocateWave`-metoden. Parallellbearbetning används bara för lagerställen som listas. Använd knapparna i åtgärdsfönstret om du vill lägga till eller ta bort lagerställen från rutnätet. 
1. Gör följande inställningar för varje lagerställe:
    - **Maximalt antal batchuppgifter** - Ange det antal batchuppgifter som ska användas för allokeringen för det valda lagerstället. Det optimala antalet batchuppgifter beror på vilken infrastruktur som är tillgänglig och vilka andra batchjobb som bearbetas på servern. Tester gjorda på en miljö med fyra kärnor som dedikerades till påfyllnadsbearbetning visar att användning av åtta uppgifter ger bra resultat.
    - **Batchgrupp för påfyllnadsbearbetning** - Specifika batchgrupper kan användas för olika lagerställen så att allokeringsbearbetningen kan skalas ut per lagerställe.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Aktivera eller inaktivera parallellisering för alla juridiska personer

Vi rekommenderar att du ställer in `allocateWave` metoden så att den körs parallellt för alla juridiska personer, eftersom detta bidrar till att förbättra prestandan för påfyllnadsbearbetningen. Med början i Supply Chain Management version 10.0.17, funktionen *Påfyllnadsparallellisering för allokera påfyllnadsmetoden* är aktiverat som standard för alla nya och uppdaterade installationer och kan inte stängas av igen. När du har aktiverat funktionen händer följande:

- `allocateWave` metoden uppdateras för att inkludera en inställning för uppgiftskonfiguration som låter dig använda sidan **Metod för påfyllnadsbearbetning** för att definiera antalet uppgifter som ska köras samtidigt, motsvarande antalet parallella processer. Som ett resultat av detta minskas den tid som används på fyllnadssteget (som normalt sett är 30 % till 60 % av den totala bearbetningstiden) med en faktor som grovt motsvarar antalet uppgifter. Du kan också välja vilken batch som ska tilldelas för att bearbeta dessa uppgifter. Tänk på att alla juridiska personer kommer att konfigureras för bearbetning av påfyllnader i batch. För de lager som redan är konfigurerade för att bearbeta påfyllnader i batch och för de lager som redan är konfigurerade för att använda `allocateWave` metod parallellt kommer den befintliga konfigurationen att behållas.
- Som standard konfigureras alla nya juridiska personer till att bearbeta påfyllnader i batch. Alla nya lagerställen med alternativet **lagerhanteringsprocesser** aktiverade kommer att `allocateWave` metoden konfigureras så att de körs parallellt som standard.
- På sidan **Lagerstyrningsparametrar** anges **Behandla påfyllnader i batch** anges till *Ja* och **Vänta på lås (ms)** till en standard på 15 sekunder. Det innebär att alla påfyllnader kommer att köras i batch. När en påfyllnad körs får den ett lås på objektet och dimensionerna ovanför platsen under allokeringssteget. När en annan påfyllnadsbearbetningsuppgift försöker hämta samma lås för samma post kommer det att blockeras tills den nuvarande processen avslutas. Inställningarna **Vänta på lås (ms)** fastställer den maximala tid som systemet ska vänta innan låset släpps.

Parallell allokeringsbearbetning kräver att påfyllnadsbearbetning körs i batch. Därför kommer du att minska din påfyllnadsbearbetningsprestanda om du stänger av inställningen **Behandla spara i batch** setting, speciellt om parallellbearbetning använder en parallell process som definieras av uppgiftskonfigurationen för relevanta påfyllnadsmetoder.

Om det behövs kan du ångra alla inställningar som gjorts som standard när funktionen *Påfyllnadsparallellisering för allokera påfyllnadsmetoden* aktiveras automatiskt för din instans. Om du vill göra det här:

- Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**. På fliken **Påfyllnadsbearbetning** använder du de prioriterade värdena för **Bearbeta påfyllnader i batch** och **Vänta på lås (ms)**.
- Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**. Välj `allocateWave` metod. I åtgärdsfönstret, välj **Uppgiftskonfiguration** för att öppna en sida som visar varje lager där metoden är inställd på att köras parallellt. Ändra eller radera antalet batchuppgifter och den tilldelade påfyllnadsgruppen för respektive lagerställe i listan efter behov.

## <a name="troubleshooting"></a>Felsökning

### <a name="troubleshoot-using-the-infolog"></a>Felsöka med informationsloggen

Eftersom batchramverket används fångas fel som in under påfyllnadsbearbetningen in som en del av informationsloggarna för batchjobb. Så här läser du batchjobben relaterade till en påfyllnad:

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj den påfyllnad du vill kontrollera.
1. I åtgärdsfönstret, öppna fliken **påfyllnad** och från gruppen **påfyllnad** välj **batchjobb**.

Påfyllnadsbearbetningen är självkorrigerande, så eventuella fel som upptäcks under bearbetningen ska rapporteras med hjälp av informationsloggen.

Ett vanligt fel som uppstår vid parallellbearbetning kan vara att två påfyllnader försöker allokera samma artikel samtidigt och en inte slutförs så att den andra påfyllnaden inte kan uppnå ett lås inom den angivna tiden. Om denna situation inträffar kommer batchjobbsloggen att innehålla information som anger att låset för artikeln inte kunde förvärvas, och då måste den påfyllnad som misslyckades bearbetas på nytt.

Eftersom bearbetningen sker parallellt måste data underhållas i olika register för att informationen ska kunna spåras. Det innebär att loggarna för batchjobben kan innehålla fel som dubblettnyckelfel.

Felen från batchuppgifterna är också en del av batchjobbloggen. Den viktigaste informationen finns vanligtvis längst ned.

I sällsynta fall, till exempel om SQL-anslutningen avslutats, kan påfyllnadsbearbetningen sluta i ett inkonsekvent tillstånd där batchjobbet verkar köras men bearbetningen stoppas. Påfyllnaden kan inte hantera fel som detta, så ett försök att rensa upp misslyckade påfyllnader görs när nästa påfyllnad körs. Du kan också utföra följande steg om den aktuella påfyllnaden är i ett inkonsekvent läge:

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj den påfyllnad du vill rensa.
1. I åtgärdsfönstret, öppna fliken **påfyllnad** och från gruppen **påfyllnad** välj **Rensa påfyllnadsdata**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Felsöka med hjälp av påfyllnadens förloppslogg

Om alternativet **Skapa påfyllnadens förloppslogg** är aktiverat på sidan **Lagerstyrningsparametrar** skapas en loggpost varje gång som allokering för en artikel och dess dimensioner börjar och slutar. Du bör endast aktivera den här loggen om det behövs, till exempel under den första testningen eller vid felsökning. När det här alternativet är aktiverat kan du visa loggen genom att göra följande:

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj den påfyllnad du vill kontrollera.
1. I Åtgärdsfönstret, på fliken **påfyllning**, i gruppen **påfyllning**, markerar du **Förlopp**.
