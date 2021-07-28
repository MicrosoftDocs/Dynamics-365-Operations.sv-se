---
title: Momsrapport för Sverige
description: I det här avsnittet beskrivs hur du ställer in och genererar momsrapporten för juridiska personer i Sverige.
author: anasyash
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 262684
ms.search.region: Sweden
ms.author: anasyash
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e8d63117585ff95149fe279d914d6b854cf081f8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347796"
---
# <a name="sales-tax-report-for-sweden"></a>Momsrapport för Sverige

[!include [banner](../includes/banner.md)]


Allmän information om hur du ställer in mervärdesskattutdraget (moms) finns i [momsrapportering för Europa](emea-vat-reporting.md).

## <a name="set-up-the-report-layout-for-sales-tax-authorities"></a>Ställ in rapportlayouten för skattemyndigheter

Om du vill skapa en momsrapport i rätt format för rätt skattemyndighet, måste du först ställa in rapportlayouten för skattemyndigheter.

1. Gå till **Moms** \> **Indirekt moms** \> **Moms** \> **Skattemyndigheter.**
2. På sidan **Momsmyndigheter** väljer du den skattemyndighet som ska användas i momskoderna för momskvittningsperioden.
3. I fältet **rapportlayout**, välj **Svensk rapportlayout**.

## <a name="set-up-sales-tax-reporting-codes-for-vat-reporting"></a>Ställ in momsrapporteringskoder för momsrapportering

Ställ in momsrapporteringskoder genom att följa instruktionerna i [ställa in momsrapporteringskoder](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/SE-VAT-declaration/articles/finance/general-ledger/tasks/set-up-sales-tax-reporting-codes.md). Följande tabell innehåller ett exempel på momsrapporteringskoder för Sverige.

| **Kod och motsvarande fält i momsdeklarationen** | **Beskrivning**                                                                                                                                                                                    |
|-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 05                                                    | Försäljning som omfattas av moms, exklusive rutor 06, 07 och 08                                                                                                                                       |
| 06                                                    | Självleverans som omfattas av moms                                                                                                                                                                 |
| 07                                                    | Momspliktig bas på marginalschema beskattning                                                                                                                                                            |
| 08                                                    | Hyresintäkt på frivillig skatteskuld                                                                                                                                                           |
| 10                                                    | Utgående moms på 25 procent vid försäljning i rutorna 05 till 08                                                                                                                                           |
| 11                                                    | Utgående moms på 12 procent vid försäljning i rutorna 05 till 08                                                                                                                                           |
| 12                                                    | Utgående moms på 6 procent vid försäljning i rutorna 05 till 08                                                                                                                                            |
| 20                                                    | Inköp av varor från ett annat land inom Europeiska unionen (EU)                                                                                                                                        |
| 21                                                    | Inköp av tjänster från annat EU-land                                                                                                                                                      |
| 22                                                    | Inköp av tjänster från ett land eller en region utanför EU                                                                                                                                      |
| 23                                                    | Inköp av varor i Sverige som köparen är ansvarig för                                                                                                                                          |
| 24                                                    | Andra inköp av tjänster                                                                                                                                                                        |
| 30                                                    | Utgående moms på 25 procent vid försäljning i rutorna 20 till 24                                                                                                                                           |
| 31                                                    | Utgående moms på 12 procent vid försäljning i rutorna 20 till 24                                                                                                                                           |
| 32                                                    | Utgående moms på 6 procent vid försäljning i rutorna 20 till 24                                                                                                                                            |
| 50                                                    | Skattepliktig grund vid import                                                                                                                                                                            |
| 60                                                    | Utgående moms på 25 procent på import i fält 50                                                                                                                                                   |
| 61                                                    | Utgående moms på 12 procent på import i fält 50                                                                                                                                                   |
| 62                                                    | Utgående moms på 6 procent på import i fält 50                                                                                                                                                    |
| 35                                                    | Försäljning av varor till ett annat EU-land                                                                                                                                                               |
| 36                                                    | Försäljning av varor utanför EU                                                                                                                                                                      |
| 37                                                    | Mellanliggande inköp av varor i fall där triangulering ingår                                                                                                                                |
| 38                                                    | Mellanliggande försäljning av varor i fall där triangulering ingår                                                                                                                                    |
| 39                                                    | Försäljning av tjänster till handel i ett annat EU-land                                                                                                                                                 |
| 40                                                    | Övrig försäljning av tjänster som tillhandahålls utanför Sverige                                                                                                                                           |
| 41                                                    | Försäljning där inköparen är skyldig att betala moms i Sverige                                                                                                                                              |
| 42                                                    | Annan försäljning osv.                                                                                                                                                                             |
| 48                                                    | Ingående moms att dra av                                                                                                                                                                            |
| 49                                                    | Moms att betala eller återställa i momsrapporten beräknas värdet i den här rutan automatiskt som summan av rapportkoderna 10, 11, 12, 30, 31, 32, 60, 61 och 62, plus rapporteringskoden 48. |

## <a name="set-up-sales-tax-codes"></a>Ställ in momskoder

Ställ in momskoder genom att följa instruktionerna i avsnitten, [momskoder för momsrapportering](emea-vat-reporting.md#sales-tax-codes-for-vat-reporting) och [momsöversikt](../general-ledger/indirect-taxes-overview.md).

## <a name="generate-a-sales-tax-payment-and-print-the-swedish-sales-tax-report"></a>Generera en momsbetalning och skriva ut svensk momsrapport

Beräkna momsbeloppen för kvittningsperioden i slutet av momsrapportperioden.

1. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Kvitta och bokför moms**.
2. I dialogrutan **Rapportera moms för kvittningsperiod** anger du följande fält.

| **Fält**                 | **Beskrivning**                                                                                                                                                                                                                                                                         |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kvittningsperiod         | Välj tillämplig rapporteringsperiod.                                                                                                                                                                                                                                                 |
| Från datum                 | Ange det första datumet i den momskvittningsperiod som moms ska beräknas för. Det här värdet motsvarar datumet i fältet **Från** på sidan **Momskvittningsperioder**.                                                                                 |
| Transaktionsdatum          | Ange datum när momsrapporten beräknas. Standardvärdet är det aktuella datumet. Momsbetalningen beräknas för alla transaktioner som bokfördes under kvittningsperioden.                                                                                  |
| Momsbetalningsversion | Välj typ av momskvittning. Om denna momskvittning är den första momskvittningen för perioden väljer du **Original**. Om en momskvittning redan har genererats väljer du **Senaste korrigeringar**. Mer information finns i [Skapa momsbetalning](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/general-ledger/tasks/create-sales-tax-payment.md). |

3. Välj **OK**. Fyll i följande fält i dialogruta **Svensk momsrapport**.

| **Fält**                       | **Beskrivning**                                                                                                                                                                                                                                                 |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skattevaluta                    | Välj den valuta som avgör vilka transaktioner som ska ingå i rapporten. I rapporten tas båda transaktionerna som genereras med hjälp av momsvalutan och transaktionerna som genereras med hjälp av momskoderna som använder momsvalutan. |
| Rapporteringsvaluta              | Välj den utländska valuta som rapporten ska genereras i.                                                                                                                                                                                             |
| Valutakursen på rapporteringsdatumet | Ställ in det här alternativet på **Ja** om du vill ange att valutakursen för rapportdatumet ska användas för alla transaktioner i rapporten.                                                                                                                      |

4. Klicka på **OK** om du vill generera momsbetalningen.

## <a name="print-a-sales-tax-payment-report-from-a-sales-tax-payment"></a>Skriv ut en momsbetalningsrapport från en momsbetalning

1. Gå till **moms** \> **förfrågningar och rapporter** \> **momsbetalningar**.
2. På sidan **Momsbetalning**, välj posten och sedan **Skriv ut rapport**.
3. I dialogrutan ställer du in fälten enligt beskrivningen i föregående avsnitt och väljer sedan **OK**.

## <a name="report-sales-tax-for-a-settlement-period"></a>Rapportera moms för en kvittningsperiod

Du kan också skapa en svensk momsrapport genom att använda begäran **Rapportera moms för kvittningsperiod**.

1. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Rapportera moms för kvittningsperiod**.
2. Ange fältet **Kvittningsperiod**, **Från datum**, **Momsvaluta** och **Rapporteringsvaluta** enligt beskrivningen i avsnittet [Generera en momsbetalning och skriv ut svensk momsrapport](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/SE-VAT-declaration/articles/finance/localizations/emea-swe-Sales-tax-payment-report-for-Sweden.md#generate-a-sales-tax-payment-and-print-the-swedish-sales-tax-report) tidigare i detta ämne.
3. I fältet **Momsbetalningsversion**, välj ett att följande alternativ:

    - **Original** – Generera en rapport för momstransaktioner för den första bokförda kvittningsberäkningen för perioden.
    - **Korrigeringar** – Generera en rapport för momstransaktioner för efterföljande kvittningsberäkningen för perioden.
    - **Total lista** – generera en rapport för alla försäljningstransaktioner för perioden. Dessa transaktioner inkluderar ursprungliga och korrigerade transaktioner.

4. Välj **OK**.
5. Ange fälten **Momsvaluta**, **Rapporteringsvaluta** och **Växlingskurs på rapporteringsdatumet** enligt beskrivningen i avsnittet [Generera en momsbetalning och skriv ut svensk momsrapport](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/SE-VAT-declaration/articles/finance/localizations/emea-swe-Sales-tax-payment-report-for-Sweden.md#generate-a-sales-tax-payment-and-print-the-swedish-sales-tax-report).

## <a name="example"></a>Exempel

Följande exempel visar hur du kan ställa in momskoder och momsrapporteringskoder, bokföra transaktioner och generera svensk momsrapport.

1. Gå till **Skatt** \> **Indirekt moms** \> **Moms** \> **Momskoder** och ställ in följande momskoder.

| **Momskod** | **Procentsats** | **Beskrivning**                                                                        |
|--------------------|----------------|----------------------------------------------------------------------------------------|
| SE25               | 25             | Lokal försäljning och inköp med en kostnad på 25 procent                                   |
| SE12               | 12             | Lokal försäljning och inköp med en kostnad på 12 procent                                   |
| SE6                | 6              | Lokal försäljning och inköp med en kostnad på 6 procent                                    |
| SEEU25             | 25             | EU-inköp med en kostnad på 25 procent där alternativet **importavgift** är inställt på **Ja**.   |
| SEEU12             | 12             | EU-inköp med en kostnad på 12 procent där alternativet **importavgift** är inställt på **Ja**.   |
| SEEU6              | 6              | EU-inköp med en kostnad på 6 procent där alternativet **importavgift** är inställt på **Ja**.    |
| SEImp25            | 25             | Importera till en kostnad på 25 procent där alternativet **importavgift** är inställt på **Ja**.         |
| SEImp12            | 12             | Importera till en kostnad på 12 procent där alternativet **importavgift** är inställt på **Ja**.         |
| SEImp6             | 6              | Importera till en kostnad på 6 procent där alternativet **importavgift** är inställt på **Ja**.          |
| SERC25             | 25             | Återfört tillägg till en kostnad på 25 procent där alternativet **importavgift** är inställt på **Ja**. |
| SERC12             | 12             | Återfört tillägg till en kostnad på 12 procent där alternativet **importavgift** är inställt på **Ja**. |
| SERC6              | 6              | Återfört tillägg till en kostnad på 6 procent där alternativet **importavgift** är inställt på **Ja**.  |
| SEEUS              | 0              | Försäljning inom EU där alternativet **undantag** anges till **Ja**.                                |
| SEThird            | 0              | Exportförsäljning där alternativet **undantag** anges till **Ja**.                            |

2. På sidan **Momskoder** på snabbfliken **Rapportinställning** tilldelar rapporteringskoder till momskoder.

   Följande tabell visar hur du tilldelar momsrapporteringskoder till momskoder.

| **Momskod** | **Skattepliktig försäljning** | **Skattefri försäljning** | **Momsskuld** | **Skattepliktiga inköp** | **Momsfordran** | **Skattepliktig import** | **Importavgift** | **Motbokning av importavgift** |
|--------------------|-------------------|-------------------|-----------------------|-----------------------|--------------------------|--------------------|-------------|--------------------|
| SE25               | 05                |                   | 10                    |                       | 48                       |                    |             |                    |
| SE12               | 05                |                   | 11                    |                       | 48                       |                    |             |                    |
| SE6                | 05                |                   | 12                    |                       | 48                       |                    |             |                    |
| SEEU25             |                   |                   |                       |                       |                          | 20                 | 48          | 30                 |
| SEEU12             |                   |                   |                       |                       |                          | 20                 | 48          | 31                 |
| SEEU6              |                   |                   |                       |                       |                          | 20                 | 48          | 32                 |
| SEImp25            |                   |                   |                       |                       |                          | 50                 | 48          | 60                 |
| SEImp12            |                   |                   |                       |                       |                          | 50                 | 48          | 61                 |
| SEImp6             |                   |                   |                       |                       |                          | 50                 | 48          | 62                 |
| SERC25             |                   |                   |                       |                       |                          | 23                 | 48          | 30                 |
| SERC12             |                   |                   |                       |                       |                          | 23                 | 48          | 31                 |
| SERC6              |                   |                   |                       |                       |                          | 23                 | 48          | 32                 |
| SEEUS              |                   | 35                |                       |                       |                          |                    |             |                    |
| SEThird            |                   | 36                |                       |                       |                          |                    |             |                    |

   > [!NOTE]
   > Den föregående konfigurationen är bara ett exempel och beror på strukturen för de momskoder som används. Om du vill att värdena ska beräknas och överföras till momsrapporten, för varje momskod som används i momsbetalningsprocessen, måste du ställa in en relevant momsrapporteringskod i ett eller flera fält på fliken **rapportinställningar**.
   
3. Bokför följande transaktioner. Till exempel för kundfakturor gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**, för leverantörsfakturor gå till **Leverantörsreskontra** \> **Fakturor** \> **Fakturajournal**.

| **Datum**        | **transaktionstyp**            | **Nettobelopp** | **Momsbelopp** | **Momskod** | **Förväntad momsbas – rapporteringskod** | **Förväntat momsbelopp – rapporteringskod** |
|-----------------|---------------------------------|----------------|----------------|--------------------|----------------------------------------|------------------------------------------|
| 1 januari 2020 | Kundfaktura                | 100            | 25             | SE25               | 5                                      | 10                                       |
| 1 januari 2020 | Leverantörsfaktura (EU)             | 100            | 12             | SEEU12             | 20                                     | 31 – Utgående moms 48 – momsavdrag      |
| 1 januari 2020 | Lerantörsfaktura (import)         | 100            | 6              | SEImp6             | 50                                     | 62 – Utgående moms 48 – momsavdrag      |
| 1 januari 2020 | Kundfaktura (EU)           | 100            | 0              | SEEUS              | 35                                     | Inte tillämpligt                           |
| 1 januari 2020 | Kundfaktura (export)       | 100            | 0              | SEThird            | 36                                     | Inte tillämpligt                           |
| 1 januari 2020 | Leverantörsfaktura (återfört tillägg) | 100            | 25             | SERC25             | 23                                     | 30 – Utgående moms 48 – momsavdrag      |

4. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Kvitta och bokför moms**. I dialogrutan **Rapportera moms för kvittningsperiod** i fältet **Momsbetalningsversion** välj **Original**.
5. Skriv ut rapporten och granska alla data.

    ![Ursprunglig lista över momsrapportering.](media/1_Sales_tax_reporting.png)

6. Bokför den nya transaktionen. Gå till exempel till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.

| **Datum**        | **transaktionstyp**   | **Nettobelopp** | **Momsbelopp** | **Momskod** | **Förväntad momsbas – rapporteringskod** | **Förväntat momsbelopp – rapporteringskod** |
|-----------------|------------------------|----------------|----------------|--------------------|----------------------------------------|------------------------------------------|
| 1 januari 2020 | Kundfaktura (dom) | 100            | 6              | SE6                | 5                                      | 12                                       |

7. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Kvitta och bokför moms**. I dialogrutan **Rapportera moms för kvittningsperiod** i fältet **Momsbetalningsversion** välj **Senaste korrigeringar**.
8. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Rapportera moms för kvittningsperiod**. I dialogrutan **Rapportera moms för kvittningsperiod** i fältet **Momsbetalningsversion** välj **korrigeringar**. På bilden nedan visas resultatet.

    ![Rapportlista över momskorrigeringar.](media/2_Sales_tax_reporting.png)

9. Gå till **Moms** \> **Deklarationer** \> **Moms** \> **Rapportera moms för kvittningsperiod**. I dialogrutan **Rapportera moms för kvittningsperiod** i fältet **Momsbetalningsversion** välj **total lista**. På bilden nedan visas resultatet.

    ![Komplett lista över momsrapportering.](media/3_Sales_tax_reporting.png)

## <a name="report-vat-declaration-to-the-tax-authority"></a>Rapportera momsdeklaration till skattemyndigheten

När du har genererat svenska momsrapporten använder du informationen på den för att fylla i momsdeklarationen för den svenska momsmyndigheten i det officiella formatet. Följande illustration visar vad den svenska momsdeklarationen har sett ut sedan 2016.

![Svensk momsdeklarationsrapport.](media/4_Swedish_VAT_declaration.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]