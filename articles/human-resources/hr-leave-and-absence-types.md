---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63970f69a437864675eada975c54446325fb60e2
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639592"
---
# <a name="configure-leave-and-absence-types"></a>Konfigurera typer av tjänstledighet och frånvaro

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Tjänstledighetstyper i Dynamics 365 Human Resources definierar olika typer av frånvaro som medarbetare kan rapportera. Du kan skräddarsy tjänstledighetstyper enligt organisationens behov. Exempel på tjänstledighetstyper:

- Betald ledighet (PTO)
- Obetald tjänstledighet
- Betald semester
- Sjukfrånvaro
- Sjukledighet
- Föräldraledighet
- Kortvarig funktionsnedsättning
- Ledighet p.g.a. dödsfall

## <a name="add-a-leave-type"></a>Lägg till en tjänstledighetstyp

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Typer av tjänstledighet och frånvaro**.

3. Välj **Ny**.

4. Ange ett namn för tjänstledighetstyp under **Typ**, välj ett arbetsflöde från **arbetsflödes-ID** och ange en beskrivning under **Beskrivning**.

5. I **Allmänhet**, välj **Ingen**, **Schemalagd** eller **Ej schemalagd** från listrutan **Kategori**.

6. Välj en inkomstkod i listrutan **inkomstkod**.

7. Ange **under orsakskod** som krävs om du vill kräva en orsakskod. Om du vill kräva orsakskoder kan du behöva lägga till dem. Under **Orsakskoder**, välj **Lägg till**, välj en orsakskod och markera sedan kryssrutan **Aktivera** bredvid den.

8. Under **begränsa åtkomst till valda roller** väljer du om du vill begränsa åtkomsten. Välj sedan säkerhetsrollerna under **säkerhetsroller för denna tjänstledighetstyp**. Säkerhetsrollerna definieras i det arbetsflöde du markerade under **arbetsflödes-ID** tidigare i den här proceduren.

9. Under **Kalenderfärg**, välj vilken färg du vill visa på tjänstledighets- och frånvarokalendrar för den här tjänstledighetstypen. 

10. Under **Uppskjutningsrelationer**, välj om du vill att den här tjänstledighetstypen antingen ska skjuta upp en annan tjänstledighetstyp eller skjutas upp av en annan tjänstledighetstyp. När en ledighetsansökan lämnas in för den uppskjutna tjänstledighetstypen, skapas en uppskjutning av tjänstledighet automatiskt för den uppskjutna tjänstledighetstypen. 

10. Välj **Spara**.

## <a name="configure-leave-type-rules"></a>Konfigurera regler för tjänstledighetstyp

1. Ange avrundningsalternativ för tjänstledighetstypen. Alternativen inkluderar **Ingen**, **Upp**, **Ned** och **Närmast**. Du kan också ställa in avrundningsprecision för tjänstledighetstypen.

2. Ange **helgdagskorrigering** för tjänstledighetstypen. När du väljer det här alternativet använder personal antalet helgdagar som infaller en arbetsdag för att avgöra hur ledighetstypen ska skjutas upp. Om t.ex. juldagen infaller på en måndag kommer personalavdelningen att subtrahera en dag från tjänstledighetstypen när periodiseringen bearbetas.

   Du kan ange helgdagar arbetstidskalender. Mer information finns i [skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
   
 3. Ange **Överför tjänstledighetstyp** för tjänstledighetstypen. När du väljer det här alternativet överförs alla överförda saldon till den angivna tjänstledighetstypen. Tjänstledighetstypen måste också inkluderas i planen för tjänstledighet och frånvaro. 
 
4. Definiera **utgångsregler** för tjänstledighetstypen. När du konfigurerar det här alternativet kan du välja en enhet med dagar eller månader och ange varaktighet för förfallodatum. Giltighetsdatumet för utgångsregeln används för att bestämma när batchjobbet ska köras som bearbetar utgångsdatumet för tjänstledighet eller det datum då regeln börjar gälla. Själva utgångsdatumet inträffar alltid på startdatumet för periodiseringsperioden. Till exempel, om startdatumet för periodiseringsperioden är 3 augusti 2021 och utgångsregeln sattes till 6 månader, kommer regeln att behandlas baserat på utgångsförskjutningen från startdatumet för periodiseringsperioden, så den skulle köras den 3 februari 2022. Alla tjänstledighetssaldon som finns vid förfallotiden kommer att dras från tjänstledighetstypen och återspeglas i tjänstledighetssaldot.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Konfigurera kopplingsbehov per tjänstledighetstyp

> [!NOTE]
> Om du vill använda fältet **Bilaga som krävs** måste du först aktivera funktionen **(Förhandsgranskning) Konfigurera obligatorisk bilaga för ansökan om tjänstledighet** i funktionshantering. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

1. På sidan **Tjänstledighet och frånvaro** på fliken **Länkar**, under **Inställningar**, välj **Tjänstledighets- och frånvarotyper**.

2. Välj en ledighet och frånvaro i listan. I avsnittet **Allmänt** använder du fältet **Bilaga som krävs** för att ange om en bilaga måste laddas upp när en anställd skickar en ny ledighetsbegäran för den valda ledighetstypen. 

Medarbetare måste föra över en bilaga när de skickar en ny tjänstledighetsbegäran som har en tjänstledighetstyp där fältet **obligatoriskt bilaga** är aktiverat. Om du vill visa bilagan som har förts över som en del av en tjänstledighetsbegäran kan du lämna denna till godkännare om du vill använda alternativet **Bilagor** för de arbetsobjekt som har tilldelats dem. Om du har åtkomst till en tjänstledighetsbegäran med hjälp av programmet Personal i Microsoft Teams kan alternativet **Visa detaljer** för tjänstledighetsförfrågan användas för att visa information och eventuella bilagor.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Konfigurera ledighetsenheter (timmar/dagar) per tjänstledighetstyp

> [!NOTE]
> Om du vill använda tjänstledighetsenheterna per tjänstledighetstyp måste du först aktivera **(förhandsgranskning) konfigurera tjänstledighetsenheter per tjänstledighetstyp** i funktionshanteringen. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

> [!IMPORTANT]
> Tjänstledighetstyperna i en juridisk person använder som standard tjänstledighetsenheterna från konfigurationen av tjänstledighetsparametrar på den juridiska personens nivå.
> 
> Tjänstledighetsenheten för tjänstledighets- och frånvarotypen kan bara ändras om det inte finns några tjänstledighetstransaktioner för tjänstledighetstypen.
> 
> Funktionen kan inte stängas av efter att den har slagits på.

1. På sidan **Tjänstledighet och frånvaro** på fliken **Länkar**, under **Inställningar**, välj **Tjänstledighets- och frånvarotyper**.

2. Välj en ledighet och frånvaro i listan. Sedan, i avsnittet **Allmänt** i fältet **Enhet** väljer du tjänstledighetsenheten. Du kan välja **timmar** eller **dagar**.

3. Valfritt: Om du har valt **Timmar** i fältet **Enhet** kan du använda fältet **Aktivera halvdags definition** för att ange om anställda kan välja den första halvdagen eller den andra halvdagens ledighet om de begär en halvdagars ledighet.

Medarbetare som skickar en ny tjänstledighetsbegäran kan välja olika typer av tjänstledighet när de vill skapa sin tjänstledighetsbegäran. Alla tjänstledighetstyper som väljs som en del av en enda tjänstledighetsbegäran ska dock ha samma tjänstledighetsenhet. Medarbetare kan visa tjänstledighetsenheten för varje tjänstledighetstyp i formuläret **Ledighetsbegäran**. 

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)
- [Skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
- [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md)
- [Skapa ett arbetsflöde för köpa och sälja ledighetsansökan](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
