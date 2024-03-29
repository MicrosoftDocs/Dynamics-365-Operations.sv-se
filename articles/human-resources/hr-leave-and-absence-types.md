---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e35c5fed886ebf9a453c22b3e04ca9ffe50b6d70
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805215"
---
# <a name="configure-leave-and-absence-types"></a>Konfigurera typer av tjänstledighet och frånvaro

[!include [preview banner](../includes/preview-banner.md)]

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

1. I arbetsytan **tjänstledighet och frånvaro** välj fliken **Länkar**.
2. Under **Inställningar**, välj **Typer av tjänstledighet och frånvaro**.
3. Välj **Ny**.
4. Ange ett namn för tjänstledighetstyp under **Typ**, ange en beskrivning under **Beskrivning** och välj ett arbetsflöde i fältet **Arbetsflödes-ID**. Utifrån tjänstledighetstypen väljer du en begäranstyp i fältet **Typ av begäran**. Välj till exempel **Semester** eller **Tjänstledighet**.
5. I **Allmänhet**, välj **Ingen**, **Schemalagd** eller **Ej schemalagd** från listrutan **Kategori**.
6. Välj en inkomstkod i listrutan **inkomstkod**.
7. Ange **under orsakskod** som krävs om du vill kräva en orsakskod. Om du vill kräva orsakskoder kan du behöva lägga till dem. Under **Orsakskoder**, välj **Lägg till**, välj en orsakskod och markera sedan kryssrutan **Aktivera** bredvid den.
8. Om begärandstypen är **Tjänstledighet**, följ dessa steg:

      1. Välj under **Obegränsad** om användare ska kunna skapa obegränsad tjänstledighet.
      2. Om **Obegränsad** har aktiverats kan du välja om medarbetarna måste skicka in ett meddelande om återgång till arbetet när de kommer tillbaka från tjänstledigheten.
      3. Om en medarbetare måste skicka meddelande om återgång till arbetet kan du aktivera **Aktivera meddelande om återgång till arbetet**. Om **Aktivera meddelande om återgång till arbetet** är aktiverat, **Bilaga som krävs** aktiveras automatiskt och kan inte inaktiveras.

9. Om användarna ska skicka dokument när de skapar eller uppdaterar tjänstledighetsansökningar kan du aktivera **Bilaga som krävs**.
10. Under **begränsa åtkomst till valda roller** väljer du om du vill begränsa åtkomsten. Välj sedan säkerhetsrollerna under **säkerhetsroller för denna tjänstledighetstyp**. Säkerhetsrollerna definieras i det arbetsflöde du markerade under **arbetsflödes-ID** tidigare i den här proceduren.
11. Under **Kalenderfärg**, välj vilken färg du vill visa på tjänstledighets- och frånvarokalendrar för den här tjänstledighetstypen.
11. Under **Uppskjutningsrelationer**, välj om du vill att den här tjänstledighetstypen antingen ska skjuta upp en annan tjänstledighetstyp eller skjutas upp av en annan tjänstledighetstyp. När en ledighetsansökan lämnas in för den uppskjutna tjänstledighetstypen, skapas en uppskjutning av tjänstledighet automatiskt för den uppskjutna tjänstledighetstypen.
12. Välj **Spara**.

## <a name="configure-leave-type-rules"></a>Konfigurera regler för tjänstledighetstyp

1. Ange avrundningsalternativ för typen **Tjänstledighet och frånvaro**. Alternativen inkluderar **Ingen**, **Upp**, **Ned** och **Närmast**. Du kan också ställa in avrundningsprecision för tjänstledighetstypen.
2. Ange **helgdagskorrigering** för tjänstledighetstypen. När du väljer det här alternativet används antalet helgdagar som infaller en arbetsdag för att avgöra hur ledighetstypen ska skjutas upp. Om t.ex. juldagen infaller på en måndag kommer personalavdelningen att subtrahera en dag från tjänstledighetstypen när periodiseringen bearbetas.

   Du kan ange helgdagar arbetstidskalender. Mer information finns i [skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md).
   
 3. Ange **Överför tjänstledighetstyp** för tjänstledighetstypen. När du väljer det här alternativet överförs alla överförda saldon till den angivna tjänstledighetstypen. Tjänstledighetstypen måste också inkluderas i planen för tjänstledighet och frånvaro. 
 
4. Definiera **utgångsregler** för tjänstledighetstypen. När du konfigurerar det här alternativet kan du välja en enhet med dagar eller månader och ange varaktighet för förfallodatum. Giltighetsdatumet för utgångsregeln används för att bestämma när batchjobbet ska köras som bearbetar utgångsdatumet för tjänstledighet eller det datum då regeln börjar gälla. Själva utgångsdatumet inträffar alltid på startdatumet för periodiseringsperioden. Till exempel, om startdatumet för periodiseringsperioden är 3 augusti 2021 och utgångsregeln sattes till 6 månader, kommer regeln att behandlas baserat på utgångsförskjutningen från startdatumet för periodiseringsperioden, så den skulle köras den 3 februari 2022. Alla tjänstledighetssaldon som finns vid förfallotiden kommer att dras från tjänstledighetstypen och återspeglas i tjänstledighetssaldot.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Konfigurera kopplingsbehov per tjänstledighetstyp

> [!NOTE]
> Om du vill använda fältet **Bilaga som krävs** måste du först aktivera funktionen **Konfigurera obligatorisk bilaga för ansökan om tjänstledighet** i funktionshantering. Mer information om hur du aktiverar funktionerna finns i [hantera funktioner](hr-admin-manage-features.md).

1. På sidan **Tjänstledighet och frånvaro** på fliken **Länkar**, under **Inställningar**, välj **Tjänstledighets- och frånvarotyper**.

2. Välj en **typ av ledighet och frånvaro** i listan. I avsnittet **Allmänt** använder du fältet **Bilaga som krävs** för att ange om en bilaga måste laddas upp när en anställd skickar en ny ledighetsbegäran för den valda ledighetstypen. 

Medarbetare måste föra över en bilaga när de skickar en ny tjänstledighetsbegäran som har en tjänstledighetstyp där fältet **obligatoriskt bilaga** är aktiverat. Om du vill visa bilagan som har förts över som en del av en tjänstledighetsbegäran kan du lämna denna till godkännare om du vill använda alternativet **Bilagor** för de arbetsobjekt som har tilldelats dem. Om du har åtkomst till en tjänstledighetsbegäran med hjälp av programmet Personal i Microsoft Teams kan alternativet **Visa detaljer** för tjänstledighetsförfrågan användas för att visa information och eventuella bilagor.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Konfigurera ledighetsenheter (timmar/dagar) per tjänstledighetstyp

> [!NOTE]
> Om du vill använda tjänstledighetsenheterna per tjänstledighetstyp måste du först aktivera **konfigurera tjänstledighetsenheter per tjänstledighetstyp** i funktionshanteringen. Mer information om hur du aktiverar funktionerna finns i [hantera funktioner](hr-admin-manage-features.md).

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
