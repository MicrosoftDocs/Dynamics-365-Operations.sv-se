---
title: Använda prediktioner av kundbetalning (förhandsversion)
description: I det här avsnittet beskrivs förutsättningarna och de övergripande steg som krävs för att använda en bedömningsversion av Finance-insikter.
author: ShivamPandey-msft
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 51cd69563a7a5b30e932f1aad828d095cc55b075
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827228"
---
# <a name="use-customer-payment-predictions-preview"></a>Använda prediktioner av kundbetalning (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du använder förutsägelser om kundbetalning. Innan du använder den här funktionen måste du kontrollera att du har slutfört inställningsstegen för den. Mer information finns i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).

Du kan visa förutsägelser om kundbetalningar i arbetsytan **Hantera kundkredit och samlingar** och på två nya listsidor, **Betalningsförutsägelse per transaktion** och **Betalningsförutsägelse per kund**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Arbetsytan Hantera kundkredit och samlingar

På arbetsytan **Hantera kundkredit och samlingar** finns två nya paneler, **Betalningsförutsägelse per transaktion** och **Kunder med förutsagda stora sena saldon**.

- Panelen **Betalningsförutsägelse per transaktion** visar antalet öppna kundtransaktioner som sannolikt har en betalning som är mindre än 50 procent i bucketen **I tid**. Du kan välja den här panelen för att öppna listsidan **Betalningsförutsägelse per transaktion**.
- Panelen **Kunder med förutsagda stora sena saldon** visar antalet kunder för vilka mer än hälften (50 procent) och det totala saldot förutsägs betalas sent och/eller mycket sent. Du kan välja den här panelen för att öppna listsidan **Betalningsförutsägelse per kund**.

[![Arbetsytan Hantera kundkredit och samlingar](./media/manage-customer-credit-collections.png)](./media/manage-customer-credit-collections.png)

### <a name="payment-predictions-per-transaction-list-page"></a>Listsidan Betalningsförutsägelse per transaktion

På listsidan **Betalningsförutsägelse per transaktion** kan du visa sannolikheten för betalning för öppna transaktioner i bucketen **I tid**, **Sent** och **Mycket sent**. För varje transaktion i rutnätet visar kolumnen **Sannolikhet för I tid** sannolikheten för att fakturan ska betalas på eller före förfallodatumet. Om sannolikheten för en betalning i tid är mindre än 50 procent visas en röd cirkel bredvid procentsatsen i kolumnen **Sannolikhet för I tid** för att indikera risken för sen betalning.

[![Listsidan Betalningsförutsägelse per transaktion](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

I fönstret **Relaterad information** till höger på sidan visas mer information om förutsägelserna:

- För transaktionen som har valts i rutnätet visar snabbfliken **Betalningsförutsägelse** detaljer om betalningsförutsägelserna i bucketen **I tid**, **Sent** och **Mycket sent**. I avsnittet **Främsta faktorer** visas de främsta faktorer som påverkade förutsägelserna. De främsta faktorerna är attribut för den valda transaktionen och/eller kunden för transaktionen.
- På snabbfliken **Kundinsikter** visas den aktuella fakturan, betalningen och inkassostatistiken för kunden för den valda transaktionen.
- På snabbfliken **Kundhistorik** visas kundens betalningshistorik i bucketen **I tid**, **Sent** och **Mycket sent**.

Data i avsnittet **Främsta faktorer** och på snabbflikarna **Kundinsikter** och **Kundhistorik** bidrar till att förklara betalningsförutsägelserna. Det kan hjälpa till att öka förtroendet för förutsägelserna.

[![Grafiska indikatorer för betalningsförutsägelser i fönstret Relaterad information](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="payment-prediction-per-customer-list-page"></a>Listsidan Betalningsförutsägelse per kund

På listsidan **Betalningsförutsägelse per kund** visas det totala ingående saldot och det belopp som förutsägs att betalas i bucketen **I tid**, **Sent** och **Mycket sent**.

[![Sidan Betalningsförutsägelse per kund](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

Betalningsbeloppet i varje bucket beräknas som summan av det vägda genomsnittet för transaktionssaldot. Detta belopp beräknas utifrån betalningssannolikheten i varje bucket.

En kund har till exempel tre öppna transaktioner som har följande sannolikhet för betalning i varje bucket.

| Transaktion | Mängd | Sannolikhet för betalning i tid | Sannolikhet för betalning sent | Sannolikhet för betalning mycket sent |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10 procent                  | 50 procent               | 40 procent                    |
| T2          | 1 000  | 50 procent                  | 30 procent               | 20 procent                    |
| T3          | 10,000 | 1 procent                   | 4 procent                | 95 procent                    |

I det här fallet förutsägs betalningarna för varje bucket på följande sätt.

| Buckets   | Transaktion T1      | Transaktion T2         | Transaktion T3            | Totalt |
|-----------|---------------------|------------------------|---------------------------|-------|
| I tid   | 100 × 10 ÷ 100 = 10 | 1 000 × 50 ÷ 100 = 500 | 10 000 × 1 ÷ 100 = 100    | 610   |
| Sen      | 100 × 50 ÷ 100 = 50 | 1 000 × 30 ÷ 100 = 300 | 10 000 × 4 ÷ 100 = 400    | 750   |
| Mycket sent | 100 × 40 ÷ 100 = 40 | 1 000 × 20 ÷ 100 = 200 | 10 000 × 95 ÷ 100 = 9 500 | 9,740 |

I fönstret **Relaterad information** till höger på sidan visas mer information om förutsägelserna:

- För transaktionen som har valts i rutnätet visar snabbfliken **Betalningsförutsägelse** detaljer om betalningsförutsägelserna i bucketen **I tid**, **Sent** och **Mycket sent**. I avsnittet **Främsta faktorer** visas de främsta faktorer som påverkade betalningarna. De främsta faktorerna är attribut för den valda transaktionen och/eller kunden för transaktionen.
- På snabbfliken **Kundinsikter** visas den aktuella fakturan, betalningen och inkassostatistiken för kunden för den valda transaktionen.
- På snabbfliken **Kundhistorik** visas kundens betalningshistorik i bucketen **I tid**, **Sent** och **Mycket sent**.

Data i avsnittet **Främsta faktorer** och på snabbflikarna **Kundinsikter** och **Kundhistorik** bidrar till att förklara betalningsförutsägelserna. Det kan hjälpa till att öka förtroendet för förutsägelserna.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Förbättra noggrannheten i betalningsförutsägelser

Du kan visa noggrannheten hos betalningsförutsägelser genom att gå till **Kredit och inkasso \> Konfigurera \> Finance-insikter \> Parametrar för ekonomiinsikter**. På fliken **Kundbetalningsinsikter** visar avsnittet **Förutsägelsemodell** noggrannheten i förutsägelsemodellen som en procentandel.

[![Noggrannheten i betalningsförutsägelser](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

Om du inte är nöjd med noggrannheten väljer du länken **Förbättra modellens noggrannhet** för att öppna AI Builder-tilläggets upplevelse. I AI Builder-tilläggets upplevelse kan du välja eller avbryta urvalet av fält tills du har valt de fält som du tror är viktigast för en korrekt förutsägelse av betalningssannolikhet. När du är klar kan du enkelt återträna förutsägelsemodellen och publicera dina ändringar. Den nyligen tränade förutsägelsemodellen hämtas automatiskt för förutsägelser i Dynamics 365 Finance.

[![AI Builder-tilläggsupplevelse](./media/ai-builder.png)](./media/ai-builder.png)

## <a name="release-details"></a>Frisläppningsinformation

Den allmänt tillgängliga förhandsversionen av Ekonomiska insikter finns tillgänglig för distribution i USA, Europa och Storbritannien. Microsoft lägger stegvis till support för fler regioner.

Funktionerna för allmänt tillgänglig förhandsversion kan och ska bara aktiveras i nivå-2-sandbox-miljöer. Konfiguration och AI-modeller som skapas i en sandbox-miljö kan inte migreras till en produktionsmiljö. Mer information finns i [Tilläggsavtal för Microsoft Dynamics 365 förhandsversioner](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]