---
title: Schema för konsumentprisindex
description: I det här ämnet beskrivs hur du skapar en lista över tidsplaner för konsumentprisindex (KPI) som du får från Internet i syfte att fastställa eskaleringsavgiften i Prenumerationsfakturering.
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
ms.openlocfilehash: 2a69e58095844286878e27a100fa49a44a4a71f4
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560502"
---
# <a name="consumer-price-index-schedule"></a>Schema för konsumentprisindex

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar, tar bort, granskar och bearbetar KPI-scheman (konsumentprisindex). En KPI-tidsplan kan användas för att bestämma priserna för konsumtionsvaror och tjänster som du lägger till som faktureringstidsplansrader. KPI-tidsplanen kan sedan användas tillsammans med eskalerings- och rabattpriser i ett faktureringsschema, eller också kan den bearbetas manuellt för att uppdatera faktureringsbeloppen i faktureringstidsplaner. Du kan ange KPI-tidsplaner manuellt eller importera dem med hjälp av den sammansatta enhet för KPI-tidsplan.

Följ dessa steg för att lägga till en KPI-tidsplan.

1. På sidan **Tidsplan för konsumentprisindex** väljer du **Ny**.
2. I fältet **Tidsplan för konsumentprisindex** anger du ett unikt namn.
3. Ange en beskrivning i fältet **beskrivning**.
4. På fliken **Tidsplan för konsumentprisindex** väljer du **Lägg till**.
5. I fältet **Datum fär konsumentprisindex** anbger du datumet då den nya KPI-tidsplanen aktiveras
6. I fältet **Tidsplan för konsumentprisindex** anger du det namn som du angav i steg 2.
7. Välj **Spara**.

För att ta bort ett datum för KPI-tidsplan, följ dessa steg.

1. På sidan **Tidsplan för konsumentprisindex** väljer du en eller flera rader som du vill ta bort, och väljer sedan **Ta bort**.
2. Om du vill ta bort hela KPI-tidsplanen väljer du **Ta bort** i åtgärdsfönstret. Du kan inte ta bort den valda KPI-tidsplanen om denna är kopplan till en faktureringstidsplan.
3. I åtgärdsfönstret väljer du **Bearbeta** för att uppdatera de faktureringstidsplaner som använder vald KPI-tidsplan. De senaste KPI-datumen och tidsplaneringsbeloppen används för att uppdatera priserna i faktureringsplanen.
4. På snabbfliken **Process för konsumentprisindex** granskar du de uppdaterade fälten för **Nummer för faktureringstidsplan**, **Artikelnummer**, **Startdatum för fakturering**, **Slutdatum för fakturering**, **Eskaleringsdatum** samt **Eskaleringsfrekvens**.

När KPI-scheman har ställts in kan de användas för eskalering och rabattprisändringar i faktureringsscheman.

## <a name="cpi-calculation"></a>KPI-beräkning

För dessa exempel är perioden från den 1 januari 2020 till 31 december 2022. KPI-bassatsen (KPI-värdet när kontraktet inleds) är 105,65. Den 1 januari 2021 är aktuellt KPI 110,5. Den 1 januari 2022 är aktuellt KPI 114,25. Ursprungsbeloppet är 1 000 dollar.

**Exempel 1**

På sidan sidan **Faktureringsparametrar för återkommande kontrakt** ställer du in fältet **Beräkning av konsumentprisindex** på **Baskonsumentprisindex**.

För perioden 1 januari 2021 beräknas det första eskaleringsbeloppet på följande sätt, baserat på det ursprungliga beloppet:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

För perioden 1 januari 2022 beräknas det första eskaleringsbeloppet på följande sätt:

1 000 + (114,25 – 105,65) &divide; 105,65 &times; 1 000 = 1 081,40

**Exempel 2**

På sidan sidan **Faktureringsparametrar för återkommande kontrakt** ställer du in fältet **Beräkning av konsumentprisindex** på **Tidigare konsumentprisindex**.

För perioden 1 januari 2021 beräknas det första eskaleringsbeloppet på följande sätt, baserat på det ursprungliga beloppet:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

För perioden 1 januari 2022 beräknas det första eskaleringsbeloppet på följande sätt, baserat på det första eskaleringsbeloppet:

1 045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1 045,91 = 1 081,40

> [!NOTE]
> Eskaleringsprocessen använder alltid det senaste KPI-värdet, oavsett indexdatum. Om eskaleringen till exempel är i september men det senaste KPI-värdet är för juli, används juliindexet. Inga justeringar görs efter att septemberindexet har angetts.

## <a name="prorated-escalation"></a>Proportionell eskalering

Om eskaleringen sker mitt i en faktureringsperiod, fördelas beloppet proportionellt. Faktureringsperioden är till exempel från den 1 augusti 2020 till 31 juli 2021. På KPI-datumet den 1 september 2019 är KPI-värdet 244. På KPI-datumet den 1 september 2020 är detta KPI-värde lika med 250. Om det föregående priset är 1 000 används följande formler för att beräkna faktureringsbeloppet för perioden:

* *KPI-ändringar* = (250 – 244) &divide; 244 = 2,459 %
* *Aktuell nivå* = 1 000 &times; 2,459 % = 1 024,59
* *Antal dagar med aktuell nivå* = 31 juli 2021 – 1 september 2020 = 334
* *Tidigare sats* = 1 000
* *Antal dagar med föregående sats* = 31 augusti 2020 – 1 augusti 2020 = 31
* *Totalt antal dagar under faktureringsperioden* = 31 juli 2021 – 1 augusti 2020 + 1 = 365
* *Faktureringsbelopp för denna period* = (1 000 &times; 31 &divide; 365) + (1 024,59 &times; 334 &divide; 365) = 1 022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Eskalering som använder KPI och procent

Eskalering kan ske med hjälp av KPI. KPI plus en 3-procentig eskalering startar den 1 januari 2020 och har en årlig frekvens.

- Det belopp som faktureras för 1 januari 2019 till och med 31 december 2020 är 4 000.
- Faktureringsperioden som ska eskaleras är 1 januari 2020 till den 31 december 2020.
- För KPI-datumet 1 december 2018 är KPI-värdet 205,3. För KPI-datumet 1 december 2019 är KPI-värdet 219,6.

Om det tidigare värdet är 4 000 beräknas faktureringsbeloppet för denna period på följande sätt:

- *KPI-ändringar* = (219,6 – 205,3) &divide; 205,3 = 6,965 %
- *Aktuell nivå* = (4 000 &times; 6,965 %) – 4 000 = 278,60
- *Procentändringar* = (4 000 &times; 1,03) – 4 000 = 120
- *Faktureringsbelopp* = 4 000 + 278,6 + 120 = 4 398,6
