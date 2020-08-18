---
title: Automatisera leverantörsbetalningsförslag
description: I det här avsnittet beskrivs hur organisationer som betalar leverantörer i ett återkommande schema kan automatisera processen att generera leverantörsbetalningsförslag.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: a1e3305bff99fa39240176ac9fc7aaee84b98e6c
ms.sourcegitcommit: be51e892003778e71b67fb409a8e16965c89b5ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2020
ms.locfileid: "3618421"
---
# <a name="automate-vendor-payment-proposals"></a>Automatisera leverantörsbetalningsförslag

[!include [banner](../includes/banner.md)]

Organisationer som betalar leverantörer i ett återkommande schema kan nu automatisera processen att generera leverantörsbetalningsförslag. Automatisering av leverantörsbetalningsförslags definierar följande uppgifter:

- När betalningsförslag körs
- Vilka kriterier används för att välja de fakturor som ska betalas
- Vilken leverantörsbetalningsjournal som leder till betalning sparas i

Automatisering av betalningsförslag bokför inte betalningarna automatiskt. Därför kan du fortsätta att använda alla de validerings- och arbetsflödesprocesser som du använder för att godkänna de betalningar som skapas.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Definiera förekomst av leverantörsbetalningsförslag

Automatiserade leverantörsbetalningsförslag använder ramverket för processautomatisering. Olika affärsprocesser använder det här ramverket för att definiera upprepningen av en vald process. För leverantörsbetalningsförslag kan du få åtkomst till automatisering av **Leverantörsreskontra \> Betalningsinställning \> Processautomatisering**.

Använd först alternativet **Skapa ny process** och markera **Leverantörsbetalningsförslag**. En guide vägleder dig genom processen att ställa in leverantörsbetalningsförslaget.

## <a name="general-page"></a>Sidan allmänt

På sidan **Allmänt** i guiden anger du namnet på leverantörsbetalningsförslaget som du skapar. Om du till exempel betalar alla lokala leverantörer med check på måndagen anger du ett beskrivande namn, t.ex. **Lokalt\_Check**. Namnet som du anger visas i vyn veckovis automatisering i arbetsytan **leverantörsbetalningar**.

Definiera sedan ägaren till betalningsjournalen som skapas. Ägaren är vanligen betalningsansvarig för leverantörsreskontra (AP), som ansvarar för betalningsjournalen när den har skapats.

De återstående inställningarna på sidan är allmänna och används för att definiera förekomstmönstret för den här versionen av leverantörsbetalningsförslaget. Om en förekomst t.ex. är till för betalningar med check på måndag kan du definiera den så att den körs varje vecka och välja måndag som veckodag när den körs. Du kan också ange en tidig planeringstid, t.ex. kl. 02:00 så att processautomatiseringen slutförs innan nästa arbetsdag börjar.

Det är viktigt att du använder guiden för att definiera när leverantörsbetalningsförslaget bearbetas. Du definierar inte när leverantörsbetalningarna skapas, skrivs ut och bokförs. I vyn vecka visas processautomatiseringen för leverantörsbetalningsförslag på de dagar som har valts i förekomstmönstret.

Mer information om de övriga fälten på sidan **Allmänt** finns i dokumentationen för processautomatisering.

## <a name="vendor-payment-proposal-page"></a>Sida för leverantörsbetalningsförslag

Nästa sida i guiden är sidan **leverantörsbetalningsförslag**. Den används för att definiera kriterierna för att välja leverantörsfakturor som ska betalas ut. I allmänhet finns samma alternativ i betalningsförslaget i leverantörsbetalningsjournalen. Det finns dock några få undantag. Till exempel måste alla datum på den här sidan definieras som relativa datum, eftersom datumet för betalningsförslaget ändras varje gång förslaget körs.

### <a name="journal-name"></a>Journalnamn

Fältet **Journalnamn** definierar det journalnamn som leverantörsbetalningarna skapas i. Resultatet av automatisering av leverantörsbetalningsförslag skapar betalningar i den definierade journalen, men journalen bokförs inte.

### <a name="from-date-and-to-date"></a>Datum från/datum till

I stället för att definiera ett "från"-datum och ett "till"-datum för att välja fakturor utifrån förfallodatum eller kassarabattdatum måste du använda alternativet **Ange till datumkriterier** och fältet **Justering av antalet dagar för till-datum** för att definiera "till"-datumet. Det finns inget begrepp för ett "från"-datum i automatisering av betalningsförslag.

Som standard är alternativet **Ange till datumkriterium** inställt på **Nej**. Om du använder standardvärdet kommer processen att välja alla fakturor för betalning när processen körs, eftersom inget "till"-datum har definierats.

Om du ställer in alternativet **Definiera till datumkriterium** till **Ja**, använd fältet **Justering av antalet dagar för till-datum** väljs som angivet antal dagar före eller efter det datum då processen körs. Talet kan vara positivt, negativt eller 0 (noll). Då kommer systemet att betala fakturor där förfallodatum, eller kassarabattdatum, är angivet antal dagar före eller efter det datum då processen körs. För alla fakturor som förfaller på eller före fredag skapar betalningsserien betalningar till alla leverantörer med check på onsdag. Ange i så fall fältet **Justering av antalet dagar för till-datum** till **2**. När en förekomst av betalningsförslaget körs på onsdag den 25 mars kommer alla fakturor som har ett förfallodatum eller kassarabattdatum på eller före den 27 mars att väljas för betalning.

### <a name="minimum-payment-date"></a>Tidigaste betalningsdatum

Tidigaste betalningsdatumet definierar det tidigaste datum som användes när du skapade betalningar. Du måste först ställa in alternativet **Definiera kriterier för minsta betalningsdatum** till **Ja**. Med den här inställningen kan du använda funktionen för minsta betalningsdatum. Om alternativet anges till **Ja**, använd fältet **Justering av antalet dagar för minsta betalningsdatum** för att minsta betalningsdatum som angivet antal dagar före eller efter det datum då processen körs. Talet kan vara positivt, negativt eller 0 (noll). Betalningsserien genererar till exempel betalningar på onsdag för att inkludera alla betalningar som har ett minsta betalningsdatum som infaller föregående måndag. Ange i så fall fältet **Justering av antalet dagar för minsta betalningsdatum** till **-2**.

Nedan visas ett exempel på hur fälten för "till"-datumet och det minsta betalningsdatumet fungerar tillsammans. Automatisering av betalningsförslag har ställts in för att köras på onsdag. Fältet **Justering av antalet dagar för till-datum** anges till **1** för att definiera "till"-datumet baserat på förfallodatumet. Fältet **Justering av antalet dagar för minsta betalningsdatum** anges till **-2**. Om automatiseringen av betalningsprocessen startar på onsdag 25 mars kommer alla fakturor som förfaller på eller före 26 mars att inkluderas i betalningsförslaget. Betalningsförslag genereras på följande sätt:

- Alla fakturor som förfaller på eller före den 23 mars kommer att ha betalningsdatumet 23 mars.
- Fakturor som förfaller den 24 mars kommer att ha betalningsdatumet 24 mars.
- Fakturor som förfaller den 25 mars kommer att ha betalningsdatumet 25 mars.
- Fakturor som förfaller den 26 mars kommer att ha betalningsdatumet 26 mars.

### <a name="summarized-payment-date"></a>Summerat betalningsdatum

Det sammanfattade betalningsdatumet används endast när fältet **Period** anges till **Total** för betalningsmetoden på fakturorna. Om fältet **Period** anges till **Total** för dina betalningsmetoder, måste du ange **Definiera kriterier för sammanfattade betalningsdatum** till **Ja**. Om alternativet anges till **Ja**, använd fältet **Justering av antalet dagar för sammanfattande betalningsdatum** för att sammanfattande betalningsdatum som angivet antal dagar före eller efter det datum då processen körs. Talet kan vara positivt, negativt eller 0 (noll). Till exempel genererar serien betalningar på onsdag och företaget vill skapa en sammanfattande betalning på onsdag. Ange i så fall fältet **Justering av antalet dagar för sammanfattande betalningsdatum** till **0**.

### <a name="records-to-include"></a>Poster som ska ingå

Filteralternativen kan fortfarande definieras för betalningsförslaget. Om ett filter har definierats visas inte filter kriterierna på guidesidan. De kan dock visas genom att du öppnar filtret på nytt.

De återstående fälten för förslaget fungerar på samma sätt som de fungerar för betalningsförslaget i leverantörsbetalningsjournalen. Mer information om de andra fälten finns i [skapa leverantörsbetalningar genom att använda betalningsförslag](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Vissa lands-/regionsspecifika fält och vissa offentliga sektor fält är ännu inte tillgängliga i automatisering av leverantörsbetalningsförslag.

Vi rekommenderar att du utvärderar om hur automatiseringen kommer att vara fördelaktig i din organisation, baserat på dina krav.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Visa resultaten av en automatisering av leverantörsbetalningsförslag

Efter att automatiseringsserien för leverantörsbetalningsförslaget har skapats visas förekomsterna för varje betalning i veckovy för processautomatisering. För leverantörsbetalningar har den veckovisa vyn för processautomatisering lagts till i arbetsytan **Leverantörsbetalningar** och sidan **Processens automatisering**.

[![Veckovisläge för processautomatisering i arbetsytan för leverantörsbetalningar](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

Veckovisvy för automatisering av process i arbetsytan **leverantörsbetalningar** visar bara automatiseringar av leverantörsbetalningsförslag. Den visar alla förekomster av betalningar under den aktuella veckan, för alla juridiska enheter som den inloggade användaren har säkerhetsbehörigheter till. Om till exempel betalningsansvarig för leverantörsreskontra är ansvarig för betalningar i USMF- och USSI-företagen ser han eller hon förekomsten av automatisering av leverantörsbetalningsförslag för dessa två företag men inte för andra företag.

[![Veckovis vy över processautomatisering för USMF- och USSI-företagen](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Varje förekomst visar företaget som betalningsjournalen har eller kommer att skapas i. Om betalningar skapas med hjälp av centraliserade betalningar är det företag som visas det företag som betalningarna skapas i. Förekomsten visar inte nödvändigt vis vilka företags fakturor som kommer att betalas ut.

Namnet på varje förekomst visas också för att identifiera betalningsförslaget.

Dessutom visas status för varje förekomst. Följande statusvärden används:

- **Planerad** – betalningsförslaget är planerat men har ännu inte körts.
- **Fel** – betalningsförslaget har körts men ett fel har uppstått. Du kan visa felen genom att välja knappen **Visa resultat**.
- **Slutfört** – betalningsförslaget har körts. Du kan visa betalningarna genom att välja länken **Visa betalningar**. Den här länken öppnar betalningsjournalen som skapades av förekomsten.

När betalningarna har skapats kan du visa betalningsbeloppen i journalen. Beloppen visas i transaktionsvalutan. Om betalningsjournalen t.ex. innehåller betalningar både i USD och kanadensiska dollar visas de totala betalningarna för respektive valuta. 

Betalningsjournalen kan tas bort när den har skapats genom processautomatisering. Om en betalning är helt borttagen inträffar följande händelser:

- Statusen för processautomatiseringen för veckan förblir **slutförd**.
- Processen tar bort betalningssummor och länken **Visa betalningar** ersätts med knappen **Visa resultat**.
- När du visar resultaten visas ett meddelande om att den ursprungliga journalen har tagits bort.

När en betalning har tagits bort är fakturorna öppna igen för betalning. En ny förekomst kan sedan skapas för att betala fakturorna igen.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Redigera automatisering av leverantörsbetalningsförslag

Med ramverk för processautomatisering kan du redigera betalningen, serien och de händelser som skapas för betalningsförslaget. Serien kan redigeras från sidan **Processautomatisering** eller veckovis visning av processens automatisering. Om till exempel AP-chefen bestämmer sig för att generera alla kontroller för inhemska leverantörer på onsdag, i stället för måndag, kan han eller hon hitta en förekomst i vyn vecka och välja **Visa/redigera – serie**. Om du redigerar en serie uppmanas du att ange om ändringen ska göras för alla befintliga förekomster eller bara för nya förekomster. Historiska händelser som redan har statusen **slutförd** eller som slutade i **fel** status ändras inte.

Du kan också lägga till en ny förekomst eller ändra en befintlig förekomst. Nästa exempel på betalningsförslag är inställt på onsdag 1 januari, men detta datum är en helgdag. Du kan ändra förekomsten från antingen den veckovisa vyn för processautomatisering eller från sidan **Processautomatisering**. En sida öppnas som visar schemainformation och kriterier för betalningsförslag. Här kan du redigera den planerade tiden och det aktuella datumet. Du kan även redigera kriterierna för betalningsförslag om det behövs ändringar. Om du till exempel ändrar det schemalagda datumet för betalningsinstansen från den 1 januari till den 2 januari, kanske du också vill ändra de relativa datumen för till-datumet.

Du kan också inaktivera en förekomst eller en serie. Om du vill inaktivera en förekomst och avbryta bearbetningen av den markerar du den i vyn bearbeta en veckovis process och väljer **inaktivera**. Du kan inaktivera en serie på sidan **processautomatisering**.

## <a name="security-for-payment-proposal-automations"></a>Säkerhet för automatisering av betalningsförslag

Följande uppgifter och behörigheter har lagts till för automatisering av leverantörsbetalnings förslag. Dessa uppgifter och privilegier är standardsäkerhetsinställningar, men de kan ändras utifrån organisationens krav. Om inte bara AP-chefen men även betalningsansvarig för leverantörsreskontra kan redigera och skapa upprepat schema, tilldela uppgiften **Behåll upprepade scheman** till den person i rollen betalningsansvarig för leverantörsreskontra.

| Programbehörighet                              | Roll                                                                       | Privilegier |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Underhåll schemaläggningsserier          | Leverantörsreskontrachef                                                   | Denna uppgift ger rätt att skapa och underhålla serier för automatisering av betalningsförslag och förekomst via följande privilegier:<ul><li>Underhåll förekomster av scheman</li><li>Underhåll schemaläggningsserier</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Visa endast veckovis vy för förekomster</li></ul> |
| Fråga om förekomster av scheman | Betalningsansvarig för leverantörsreskontra, betalning, ansvarig för centraliserade leverantörsreskontrabetalningar | Denna uppgift ger rätt att visa automatisering av betalningsförslagförekomst via följande privilegier:<ul><li>Visa förekomster av scheman</li><li>Visa endast veckovis vy för förekomster</li></ul> |
| Fråga om schemaläggningsserier      | None                                                                       | Denna uppgift ger rätt att visa inställningar för serier och förekomster via följande privilegier:<ul><li>Visa förekomster av scheman</li><li>Visa listsidan med förekomster</li><li>Visa endast veckovis vy för förekomster</li></ul>|
| Underhåll förekomster av scheman     | None                                                                       | Denna uppgift ger rätt att skapa och upprätthålla en förekomst genom följande privilegier:<ul><li>Underhåll förekomster av scheman</li><li>Visa endast veckovis vy för förekomster</li></ul> |
