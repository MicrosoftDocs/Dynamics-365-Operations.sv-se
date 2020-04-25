---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198060"
---
# <a name="configure-leave-and-absence-types"></a>Konfigurera typer av tjänstledighet och frånvaro

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

9. Välj **Spara**.

## <a name="configure-leave-type-rules"></a>Konfigurera regler för tjänstledighetstyp

1. Ange avrundningsalternativ för tjänstledighetstypen. Alternativen inkluderar **Ingen**, **Upp**, **Ned** och **Närmast**. Du kan också ställa in avrundningsprecision för tjänstledighetstypen.

2. Ange **helgdagskorrigering** för tjänstledighetstypen. När du väljer det här alternativet använder personal antalet helgdagar som infaller en arbetsdag för att avgöra hur ledighetstypen ska skjutas upp. Om t.ex. juldagen infaller på en måndag kommer personalavdelningen att subtrahera en dag från tjänstledighetstypen när periodiseringen bearbetas.

   Du kan ange helgdagar arbetstidskalender. Mer information finns i [skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
   
## <a name="configure-preview-features"></a>Konfigurera förhandsfunktioner

Om du har aktiverat förhandsfunktioner för tjänstledighet och frånvaro, måste du också konfigurera inställningarna för dem.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Välj tjänstledighetstyp för att överföra de saldon som ska överföras till. Du kan också skapa en ny tjänstledighetstyp för överföring. 

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)
- [Skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
