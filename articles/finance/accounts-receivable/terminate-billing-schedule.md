---
title: Avsluta faktureringsscheman
description: Det här ämnet beskriver hur du avslutar faktureringsscheman och faktureringsschemarader i abonnemangsfakturering.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: df81cc888e893c6a4a127e1a43426a0a0b56f0d1
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470463"
---
# <a name="terminate-billing-schedules"></a>Avsluta faktureringsscheman

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du avslutar faktureringsscheman och faktureringsschemarader i abonnemangsfakturering. När du säger upp ett faktureringsschema måste det ha statusvärdet **Aktiv**. Den får inte ha status **spärrad**. När du säger upp ett faktureringsschemarad måste det ha statusvärdet **Aktiv**. Huvudavsnittet i faktureringsplanen påverkas inte när du säger upp en faktureringsschemarad.

Du avslutar ett faktureringsschema eller en faktureringsplansrad genom att gå till någon av följande platser:

- Listsidan **alla/aktiva faktureringsscheman**
- Ett specifikt faktureringsschema på sidan **Alla faktureringsscheman**
- Ett specifikt faktureringsschemarad på sidan **Alla faktureringsscheman**

> [!NOTE]
> Om du vill avsluta flera faktureringsscheman samtidigt använder du sidan **bearbetning för massavslutning**.

## <a name="terminate-a-billing-schedule-or-line"></a>Avsluta ett faktureringsschema eller linje

Följ dessa steg för att avsluta ett faktureringsschema eller en faktureringsschemarad.

1. Välj ett faktureringsschema eller en faktureringsplansrad och välj sedan **Avsluta**. 
2. Ställ in fält för **uppsägningsdatum**, **uppsägningstyp** och **orsakskod**.
3. Ställ in fältet **Kreditalternativ** till **Utfärda kredit**.
4. Välj **Avsluta**.

Statusvärdet för faktureringsplanen ändras baserat på uppsägningstypen du valt. Om du valde **Resterande strukturgrupp** som uppsägningstyp är statusen för alla rader i faktureringsplanen den senaste **faktureringen**. Statusvärdet för faktureringsplanen förblir **Aktiv** tills den sista fakturan bearbetas. När den sista fakturan har bearbetats uppdateras status till **Avslutad**. Om du valde **Resterande strukturgrupp** som uppsägningstyp uppdateras statusen för faktureringsschemat omedelbart till **Avslutad**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Avsluta ett faktureringsschema eller en faktureringsrad och tillämpa en återbetalning

Följ dessa steg för att avsluta ett faktureringsschema eller en faktureringsschemarad och tillämpa en återbetalning.

1. Välj ett faktureringsschema eller en faktureringsplansrad och välj sedan **Avsluta**.
2. Ställ in fält **uppsägningsdatum**, **uppsägningstyp**, **orsakskod** och **kreditalternativ**.
3. Välj **Avsluta med återbetalning**. Sidan **För bearbetning av massavslut** visas och filtreras så att det visar faktureringsschemat.
4. Välj **visa förhandsgranskning** för att visa raderna för faktureringsscheman och välj sedan **Process**.

När krediteringen har bearbetats öppnar du sidan **Visa faktureringsdetaljer** för att granska kredit som har tillämpats för faktureringsschemat. Om kreditbeloppet är större än 0 (noll) tas alla framtida ofakturerade rader bort och ersätts med fakturadetaljrader som visar de negativa beloppen för den kredit som har tillämpats på faktureringsplanen.

### <a name="view-example"></a>Visa exempel

Ett faktureringsschema innehåller följande information:

- Startdatum är 1 januari 2020.
- Slutdatumet är 31 december 2020.
- Faktureringsperiodbeloppet är 100,00 per månad.
- Fakturor har skapats för faktureringsperioder från januari till juli.
- Datumet för kontraktets uppsägning är den 15 juni 2020.

När kreditjusteringen bearbetas tas alla framtida faktureringsperioder (augusti till och med december) bort från sidan **Visa faktureringsdetaljer**. En kreditjusteringsrad läggs till efter faktureringsperioden i juli:

- 16 juni – 31 juli, med ett kreditbelopp på 150,00

Om funktionen för ej fakturerad intäkt används uppdateras sidan **Granska journalpost ofakturerad intäkt** uppdateras med uppsägningsposten.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Avsluta ett faktureringsschema eller en faktureringsrad och linje utan att tillämpa en kredit

Följ dessa steg för att avsluta ett faktureringsschema eller utan att ansöka om en kredit, följ dessa steg.

1. Välj ett faktureringsschema eller en faktureringsplansrad och välj sedan **Avsluta**.
2. Ställ in **datum för uppsägning**.
3. Ställ in fältet **Uppsägningstyp** på **Ingen justering** Fältet **Kreditalternativ** ställs automatiskt in på **Ingen kredit**.
3. Ställ in fältet **Orsakskod**.
4. I fältet **Uppsägningsnoteringar** anger du eventuella noteringar som krävs.
5. Välj **Avsluta**. 

När uppsägningen bearbetas tas alla faktureringsdetaljrader efter uppsägningsdatumet bort. (Dessa rader omfattar den rad som innehåller uppsägningsdatumet.) Fakturor kan inte skapas för de uppsagda raderna. Om uppsägningen tas bort kommer alla uppsagda rader att läggas till på sidan **Visa faktureringsinformation** och bli tillgängliga för fakturering.

## <a name="fields"></a>Fält

Sidan **Visa faktureringsinformation** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------| 
| Uppsägningsdatum | Välj datum när du vill avsluta ett faktureringsschema eller faktureringsschemarad. |
| Uppsägningstyp | <p>Välj uppsägningstyp:</p><ul><li>**Justera tidsplanering** – Klipp ut faktureringsperioderna för raden vid uppsägningsdatumet och ändra status för raden till **Senaste fakturering**. Om det finns ett schema för avvisning för radartikeln justeras det genom att beloppet som inte längre ska redovisas återföras. Om faktureringsstartdatumet in ligger efter uppsägningsdatumet tas de återstående faktureringsperioderna bort.</li><li>**Resterande växel** – Lägg till eventuella återstående belopp för faktureringsperioden i uppsägningsperioden och ändra status för raden till **Senaste fakturering**. Om det finns ett uppskjutningsschema för raden uppdateras slutdatumet för uppskov. Om faktureringens startdatum in ligger efter uppsägningsdatumet läggs det totala beloppet för alla återstående faktureringsperioder till i faktureringsperioden, och de återstående faktureringsperioderna tas bort.</li><li>**Ingen justering** – Avsluta faktureringsperioderna för raden på det angivna uppsägningsdatumet. Inga justeringar görs. När denna avslutningstyp väljs, fältet **Kreditalternativ** anges till **Ingen kredit** och **Proportionellt dagligen** anges till **Nej**. Båda dessa fält blir skrivskyddade och kan inte ändras.</li></ul> |
| Kreditalternativ | <p>Välj hur kredit ska tillämpas när du avslutar en faktureringsplansrad:</p><ul><li>**Kreditjustering** – Skapa en kreditjustering för ett faktureringsschema när en rad har avslutats. Kreditjusteringen visas i en framtida faktureringsperiod för faktureringsschemat. Justeringen justerar även fakturabeloppet automatiskt för nästa faktureringsperiod tills kredit har slutförts för faktureringsschemat.</li><li>**Utfärda kredit** – Skapa en kreditnota när ett faktureringsschema eller en faktureringsschemarad avslutas.</li><li>**Ingen kredit** – Skapa inte en kreditjustering eller en kreditnota när ett faktureringsschema eller en faktureringsschemarad avslutas. Det här alternativet är endast tillgängligt när du använder en uppsägning av typen **Ingen justering** för att avsluta ett faktureringsschema.</li></ul><p>Standardalternativet från sidan **Faktureringsparametrar för återkommande kontrakt**.</p> |
| Orsakskod | Välj orsakskoden för uppsägningen. |
| Orsaksbeskrivning | Beskrivningen av orsakskoden. |
| Anteckningar om uppsägning | Ange eventuella anteckningar om uppsägningen. |

<!--## Additional information-->
