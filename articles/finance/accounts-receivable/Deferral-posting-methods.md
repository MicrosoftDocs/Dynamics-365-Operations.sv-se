---
title: Bokföringsmetod för periodisering
description: I den här artikeln beskrivs skillnaderna mellan bokföringsmetoder för periodisering för intäkter och utgiftsaviseringar i abonnemangsfakturering.
author: JodiChristiansen
ms.date: 6/10/2022
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
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019105"
---
# <a name="deferral-posting-methods"></a>Bokföringsmetod för periodisering

I den här artikeln beskrivs skillnaderna mellan bokföringsmetoder för periodisering för intäkter och utgiftsaviseringar i abonnemangsfakturering.

På sida **Periodiseringsparametrar för intäkt och utgift**, alternativen för uppskjutna bokföringsmetoder är **Balansräkning** och **Resultaträkning**. Exemplet i den här artikeln förklarar skillnaderna mellan de två metoderna och anledningarna till varför du kanske använder en metod eller en annan.

Metoden **Balansräkning** använder bara två konton. Därför är mindre inställningar inblandade. Metoden **Resultaträkning** har två ytterligare konton, **Första redovisningstillfälle** och **Motkonto för redovisning**, för intäkt, rabatter och kostnader, beroende på transaktionstyp. Dessa konton ställs in på standardsidan **Standardinställningar för periodisering** (**Prenumerationsfakturering \> Periodisering av intäkt och utgift \> Konfigurera**). Även om exemplet är fokuserat på uppskjuten intäkt, kan samma koncept användas på uppskjutna rabatter och uppskjutna kostnader.

## <a name="example"></a>Exempel

Försäljningsfaktura 1 har totalt 3 000 USD och har uppskjuten intäkt. I följande register visas fördelningarna när den här försäljningsfakturan bokförs.

**Balansräkningsmetod**

| Typ | Konto | Debet | Kredit|
|---|---|---|---|
| Debet | Kundreskontra | 3,000.00 | |
| Kredit | Uppskjuten intäkt | | 3,000.00 |

**Resultaträkningsmetod**

| Typ | Konto | Debet | Kredit |
|---|---|---|---|
| Debet | Kundreskontra | 3,000.00 | |
| Debet | Motkonto för intäktsredovisning | 3,000.00 | |
| Kredit | Uppskjuten intäkt | | 3,000.00 |
| Kredit | Intäktens första redovisningstillfälle | | 3,000.00 |

Försäljningsfaktura 2 har totalt 2 000 USD och har inte uppskjuten intäkt.

| Typ | Konto | Belopp |
|---|---|---|
| Debet | Kundreskontra | 3,000.00 |
| Kredit | Intäkter | 3,000.00 |

**Balansräkningsmetodens summor för försäljningsfaktura 1 och 2 kombinerade**

| Konto | Debet | Kredit |
|---|---|---|
| Kundreskontra | 5,000.00 | |
| Intäkter | | 2,000.00 |
| Uppskjuten intäkt | | 3,000.00 |

När metoden **balansräkning** används är det inte lika enkelt att se bruttointäkten för en period. En del av intäkterna bokförs på kontot **periodiserad intäkt**. Tänk på att, eftersom intäkter redovisas varje period, finns det flera debiteringar och krediter i kontot **Uppskjuten intäkt**. Bruttointäkten för en given period blandas med in-/outs av intäktsredovisningen.

**Resultaträkningsmetodens summor för försäljningsfaktura 1 och 2 kombinerade**

| Konto | Debet | Kredit |
|---|---|---|
| Kundreskontra | 5,000.00 | |
| Intäkter | | 5,000.00 |
| Intäktsmotkonto | 3,000.00 | |
| Uppskjuten intäkt | | 3,000.00 |

Alla intäkter går till resultaträkningskontot **intäkter**. Den uppskjutna intäkten flyttas sedan från resultaträkningen till balansräkningen. Du kan enkelt se bruttointäkten eftersom allt bokförs på kontot **intäkter**. En del av den bruttointäkten uppskjuts dock. Därför flyttas den till kontot för **uppskjuten intäkt** och redovisas senare.

I metoden **resultaträkning** kan du titta på kontot **intäkter** och **intäktsmotkonto** för att se bruttointäkter för 5 000 USD och nettointäkt (netto av uppskjuten) 2 000 USD. Även om metoden **resultaträkning** kan göra rapporteringen enklare, finns det fler konton att ställa in.
