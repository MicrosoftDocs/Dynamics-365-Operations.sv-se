---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/15/2021
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
ms.openlocfilehash: 39e4c4b9c83ca648c21ac20bd20b739af8a6b9ed
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271137"
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
 
## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)
- [Skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
- [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md)
- [Skapa ett arbetsflöde för köpa och sälja ledighetsansökan](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
