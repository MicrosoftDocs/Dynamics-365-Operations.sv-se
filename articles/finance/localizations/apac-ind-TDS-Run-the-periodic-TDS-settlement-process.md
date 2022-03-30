---
title: Kör den periodiska TDS-kvittningsprocessen
description: I det här avsnittet beskrivs hur du kvittar periodiskt skatteavdrag vid källan (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5b4c3a83f3fed0907dacd415f5aff9fad3c10bc6
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408390"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Kör den periodiska TDS-kvittningsprocessen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kvittar periodiskt skatteavdrag vid källan (TDS).

1. Gå till **Skatt \> Deklarationer \> Källskatt \> Betalning av källskatt**.

    [![Dialogrutan Betalning av källskatt.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. I dialogrutan **Betalning av källskatt**, i fältet **Skattetyp**, väljer du **TDS**.
3. I fältet **Skattekontonummer (TAN)** väljer du det skattekontonummer (TAN) som kvittningsprocessen ska köras för.
4. I fältet **Källskattekomponentgrupp** väljer du den TDS-komponentgrupp som kvittningsprocessen ska köras för.
5. I fältet **Kvittningsperiod** väljer du den TDS-kvittningsperiod som kvittningsprocessen ska köras för.

    > [!NOTE]
    > TDS-kvittningsprocessen körs för alla perioder som har konfigurerats för TDS-kvittningsperioden under fliken **Perioder** på sidan **Perioder för källskattekvittning** (**Skatt \> Indirekta skatter \> Källskatt \> Perioder för källskattekvittning**).

6. I fältet **Från datum** väljer du startdatumet för körningen av TDS-kvittningsprocessen.

    För en specifik period inom kvittningsperioden tas startdatumet som definieras för perioden som "från"-datumet. TDS-kvittningsperioden har till exempel två perioder: 1 april till 30 april 2009 och 1 maj till 31 maj 2009. Om du väljer **2009.04.06** (6 april 2009) som startdatum i fältet **Från datum**, körs kvittningsprocessen från den 1 april 2009.

    Om du anger en senare period i fältet **Från datum**, men utan att kvitta en tidigare period inom kvittningsperioden, utförs inte kvittningen för några tidigare perioder. TDS-kvittningsperioden har till exempel tre perioder: 1 april till 30 april 2009, 1 maj till 31 maj 2009 och 1 juni till 30 juni 2009. Om du väljer **2009.05.01** (1 maj 2009) som startdatum i fältet **Från datum** körs kvittningsprocessen från 1 maj till 31 maj 2009. Kvittningen sker inte för 1 april till 30 april 2009.

7. I fältet **Transaktionsdatum** väljer du det datum då TDS-kvittningstransaktionen ska bokföras.
8. I fältet **Version av betalning av källskatt** väljer du TDS-kvittningsversion:

     - **Original** – Använd det här alternativet om du vill köra TDS-kvittningsprocessen för första gången. Den ursprungliga betalningsversionen används bara en gång för att köra TDS-kvittningsprocessen för en kombination av TAN, en komponentgrupp för källskatt och en kvittningsperiod för källskatt.
    - **Senaste versionerna** – Använd det här alternativet om TDS-kvittningsprocessen redan har körts för den angivna perioden. Inkludera bakåtdaterade transaktioner som bokförts efter det att kvittningsprocessen tidigare körts för perioden. Du kan använda det här alternativet om du vill köra kvittningsprocessen hur många gånger som helst.

9. Markera kryssrutan **Uppdatera** för att köra TDS-kvittningsprocessen och bokföra beloppen i redovisningen. Om den här kryssrutan avmarkeras körs inte kvittningsprocessen och de ekonomiska posterna genereras inte.
10. Välj **OK** för att köra TDS-kvittningsprocessen och generera rapporten för betalning av källskatt. Status för TDS-transaktioner som ingår i kvittningsprocessen visas som **Kvittade** på sidan **Kvittning** (gå till **Leverantörsreskontra \> Betalningar \> Leverantörens betalningsjournal**, välj **Rader**, välj **Funktioner** och sedan **Kvittning**).

### <a name="important-points"></a>Viktiga poäng

- Om en komponentgrupp för källskatt inte har valts under kvittningsprocessen, sker kvittningen för alla komponentgrupper för källskatt för den valda TAN och kvittningsperioden. En separat rad skapas för varje komponentgrupp för källskatt på sidan **Öppna transaktionsredigering**.
- Kvittningsprocessen bygger på typen av bedömningskategori för en kvittningsperiod. Transaktioner där typen av bedömningskategori är **Företag** rättas och visas som en rad på sidan **Öppna transaktionsredigering**. Transaktioner där typen av bedömningskategori är något annat än **Företag** rättas och visas som en rad på sidan **Öppna transaktionsredigering**.
- Förfallodatumet för de kvittade TDS-transaktionsraderna på sidan **Öppna transaktionsredigering** baseras på betalningsvillkoren som anges för TDS-myndigheten på sidan **Leverantörer**. Om betalningsvillkoren inte definieras för TDS-leverantören visas sista dagen i kvittningsperioden som förfallodatum.
