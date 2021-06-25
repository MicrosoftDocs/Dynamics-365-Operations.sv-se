---
title: Kassaposition (förhandsversion)
description: I det här ämnet beskrivs hur funktionen för kassaflödesprognoser förutsäger organisationens kassaposition för specifika tider. Här beskrivs också vilka alternativ som finns för att visa prognoser för olika perioder.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: b3b32bac436dc0be7ae4c072f4e560ad6d8b6d81
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186502"
---
# <a name="cash-position-preview"></a>Kassaposition (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Kassaposition är projektionen av kassaflödet som prognosticeras på kort sikt. Den baseras på projektionen av inbetalningar från kunder som betalar utestående fakturor och order, samt även de kontantutbetalningar som betalas till leverantörer för inköpsfakturor och order.

När systemet förutsäger kundbetalningar använder det betalningsförutsägelser från funktionen för kundbetalningsförutsägelse. Utan betalningsförutsägelser används den genomsnittliga tid som krävs för att konvertera en kundfaktura till en betalning för varje kund för att beräkna ett betalningsdatum. För öppna kundorder beräknar systemet fakturadatumet genom att använda det genomsnittliga antalet dagar för orderrader per kund som ska faktureras. Sedan används fakturadatumet som indata för funktionen för betalningsförutsägelse. Funktionen för kundbetalningsförutsägelse beräknar ett betalningsdatum för varje orderrad. 

Betalningsdatumet för utestående fakturor uppskattas [beräknas] från betalningsförutsägelserna genom att välja ett datum som motsvarar 50 procent av den kumulativa fördelningsfunktionen som erhålls från den förutsagda gruppens (bucket) sannolikhet.

Ett liknande tillvägagångssätt används för att förutsäga betalningar till leverantörer. För varje leverantör beräknar systemet den genomsnittliga tid som krävs för att konvertera en leverantörsfaktura till en betalning. Det antalet dagar används sedan för att beräkna betalningsdatumet. För öppna leverantörsorder beräknar systemet fakturadatumet genom att beakta det genomsnittliga antalet dagar som krävs för att konvertera orderrader till en faktura för varje leverantör. För varje leverantör beräknar systemet sedan betalningsdatumet genom att använda den genomsnittliga tid som krävs för att konvertera en leverantörsfaktura till en betalning.

Den övre delen av fliken **Kassaposition** innehåller ett kassapositionsdiagram. Det här diagrammet visar kassainflöden och kassautflöden och deras inverkan på den totala likviditetsbalansen. Detaljerna i diagrammet kan visas på dagliga, veckovisa, månadsvisa och kvartalsvisa perioder. När du väljer **Dagligen** kan du visa prognoser för nästföljande 21 dagar. När du väljer **Varje vecka** kan du visa prognoser för nästföljande 20 veckor. När du väljer **Varje månad** kan du visa prognoser för nästföljande 12 månader. När du väljer **Varje kvartal** kan du visa prognoser för nästföljande 12 kvartal. Du kan dölja diagrammet om du behöver mer utrymme på skärmen för att visa innehållet på fliken **Kassaposition**.

I den nedre delen av fliken **Kassaposition** visas information om positionen, kassaflöden, planerade betalningar och bankkonton.

- Informationen i rutnätet **Positionsinformation** visas i tre sektioner: en lista med likviditetskonton, en lista över dokument som utgör kassainflöden och en lista över dokument som utgör kassautflöden. Rutnätet visar även kassapositionssaldon. För den första period som du visar är saldot för likviditetskontona den ingående balansen. För efterföljande perioder beräknas saldona för likviditetskontona baserat på tillägg av kassainflöden och subtraktionen av kassautbetalningar från tidigare perioder. Om du vill visa information om de transaktioner som utgör saldot väljer du länken **Saldo**.
- I rutnätet **Kassaflöde** visas kassainflöden, ackumulerade kassautflöden per period och deras inverkan på likviditetskontosaldon. För den första perioden är saldot för likviditetskontona den ingående balansen. För efterföljande perioder beräknas saldona för likviditetskontona baserat på tillägg av kassainflöden och subtraktionen av kassautbetalningar från tidigare perioder.
- I rutnätet **Förväntat banksaldo** visas förväntade kassautflöden och deras inverkan på likviditetskontona.
- I rutnätet **Bankkonto** visas inverkan av förväntade kassainflöden och kassautflöden på banksaldot.

Skapa en ögonblicksbild om du vill spara och redigera kassapositionen. Mer information om hur du arbetar med ögonblicksbilder finns i [Översikt över ögonblicksbilder](payment-snapshots.md).

#### <a name="privacy-notice"></a>Sekretesspolicy
Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
