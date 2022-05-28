---
title: Översikt över avdragen indiskt moms vid källa (TDS)
description: Det här ämnet ger detaljerad information om indiskt momsavdrag vid källan (TDS). TDS-dokumentationen innehåller funktioner för den här kapaciteten.
author: kailiang
ms.date: 03/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0947481f27323a53d5ef9c7295d8dda078fb4254
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720208"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Översikt över avdragen indiskt moms vid källa (TDS)

[!include [banner](../includes/banner.md)]

Det här ämnet ger detaljerad information om indiskt momsavdrag vid källan (TDS).

TDS-dokumentationen innehåller funktioner för den här kapaciteten. Här förklaras också de grundläggande inställningarna för TDS, beräknar TDS för transaktioner, slutför TDS-kvittningsprocessen, registrerar TDS-certifikatnummer och genererar TDS-förfrågningar, TDS-utdrag och TDS-certifikat. Dokumentationen innehåller följande ämnen:

- [Grundinställning för TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Formeldesigner och tröskelgränsfunktion som används för TDS-beräkning](apac-ind-TDS-Formula-designer.md)
- [Beräkning av TDS på fakturor, betalningar, skuldsedlar och koncerninterna transaktioner](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Periodisk TDS-kvittningsprocess och kvittning av TDS-belopp till leverantörer inom TDS-myndigheten](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Registrera och uppdatera TDS-certifikatnummer och -datum](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Introduktion till TDS

Enligt inkomstskattelagen från 1961 dras inkomstskatt av vid källan av mottagaren av tjänsten vid förskottsbetalningen eller kreditredovisningen, beroende på vilket av alternativen som inträffar först. Den person som gör betalningen måste dra av momsbeloppet och bara betala nettosaldot till tjänsteleverantören. TDS tillämpas på tjänster som staten anger, och skatten dras av genom att använda de satser som staten anger för en period. Avdragssatsen baseras på statusen för enheten som tar emot betalningen eller tillhandahåller tjänsten. Status inkluderar **Individ**, **Hinduistisk odelad familj** (**HUF**), **Företag**, **Firma**, **Association av personer** (**AOP**), **Samling individer** (**BOI**) och **Lokan myndighet**.

I de följande avsnitten listas de tjänster som TDS används på, enligt vad som angetts av Indiens regering.

**Invånare**

- Löneinkomst (under avsnitt 192)
- Ränteintäkter på värdepapper (under avsnitt 193)
- Inkomst från utdelningar (under avsnitt 194)
- Inkomst från ränta (under avsnitt 194A)
- Inkomst från lotterier eller spel (under avsnitt 194B)
- Vinst från hästkapplöpning osv. (Under avsnitt 194BB)
- Leverantörer och underleverantörer (under avsnitt 194C)
- Försäkringskommission (under avsnitt 194D)
- Intäkt från insättning enligt nationella sparscheman (under avsnitt 194EE)
- Inkomst från en gemensam fond eller UTI (under avsnitt 194F)
- Provision, ersättning, pris osv. från försäljning eller lotteri (under avsnitt 194G)
- Betalning av provision eller mäklararvode (under avsnitt 194H)
- Hyra (under avsnitt 194I)
- Yrkesservice (under avsnitt 194J)
- Inkomst från enheter (under avsnitt 194K)
- Betalning av kompensation vid anskaffning av viss fast egendom (under avsnitt 194LA)

**Icke-invånare**

- Betalningar till utländska atleter eller sportföreningar (under avsnitt 194E)
- Andra summor (under avsnitt 195)
- Inkomst med avseende på enheter som inte är invånare (under avsnitt 196A)

    - Inkomst från utländska valutor eller aktier i det indiska företaget (under avsnitt 196C)
    - Utländska investerares intäkter från värdepapper (under avsnitt 196D)
    - Lön och alla andra positiva inkomster under varje inkomsthuvud (avsnitt 192)
    - Ränta på värdepapper (avsnitt 193)
    - Annan ränta än ränta på värdepapper (avsnitt 194A)
    - Betalningar till leverantörer och underleverantörer (avsnitt 194C)
    - Vinster från lotteri eller korsord (avsnitt 194B)
    - Vinster från hästkapplöpning (avsnitt 194BB)
    - Försäkringsprovision som täcker alla betalningar för att anskaffa försäkringsaffärer (avsnitt 194D)
    - Alla andra räntor än ränta på säkerheter som ska betalas till icke-invånare som inte är ett företag eller till ett utländskt företag (avsnitt 195)
    - Betalning till atleter som inte är invånare, inklusive atlet- och sportassociationer eller -institutioner. För atleter som inte är invånare, betalningar avseende reklam samt artiklar om spel/sport i Indien i tidningar, tidskrifter och så vidare. ingår (avsnitt 194E)
    - Betalning för insättningar enligt NSS \[National Savings Scheme\] (avsnitt 194EE)
    - Betalning av återköpta enheter av gemensam fond eller UTI (avsnitt 194F)
    - Betalning av provision eller mäklararvode (avsnitt 194H)
    - Betalning av hyra (avsnitt 194I)
    - Betalning av avgifter för yrkesmässiga eller tekniska tjänster (avsnitt 194J)
    - Provision till aktieleverantörer, distributörer, inköpare och säljare av lotter, inklusive ersättning eller pris för sådana lotter (avsnitt 194G)
    - Intäkter från enheter som köpts i utländsk valuta eller långsiktig kapitalvinst som härrör från överföring av sådana enheter som köpts in i utländsk valuta (avsnitt 196B)
    - Betalning av annan inkomst än vad gäller ränta eller utdelning på värdepapper och aktier (avsnitt 196C)

TDS beräknas på inköp, försäljning, försäljningsreturer, kreditfakturor, anskaffningar av anläggningstillgångar, förskottsbetalningar, skuldsedlar, moms och koncerninterna transaktioner.

> [!NOTE]
> I det aktuella indiska skattescenariot beräknas TDS inte på försäljningstransaktioner. Systemet innehåller dock en bestämmelse för beräkning av TDS som kan återställas på försäljningstransaktioner, särskilt för koncerninterna transaktioner.

Beräkningen av TDS tar alltid hänsyn till tröskelvärdet och undantagströskeln som definieras för TDS-komponenten.

Den periodiska TDS-kvittningsprocessen måste köras, och TDS-betalningar måste kvittas mot leverantörer inom TDS-myndigheten.

Certifikatnumren och datumen för TDS-certifikat som tas emot från leverantörer eller kunder kan registreras och uppdateras. Kvartalsutdrag för Formulär 26Q och Formulär 27Q samt Formulär 16A-certifikat för TDS kan också genereras i Ekonomi.

## <a name="setting-up-and-working-with-tds"></a>Ställa in och arbeta med TDS

Här är en översikt över processen för inställning och arbete med TDS:

1. **TDS-inställning:**

    - Parameterinställningar:

        - Aktivera parametrar som är relaterade till TDS i Redovisningsparametrar.
        - Ställ in nummerserien för källskattebetalningar i Redovisningsparametrar.
        - Konfigurera parametrar i Leverantörsreskontra och Kundreskontra.

    - Grundinställning:

        - Ställ in TDS-registreringsnummer för ett företag, kunder och leverantörer.
        - Ställ in TDS-komponentgrupper.
        - Ställ in TDS-komponenter, koppla TDS-komponentgrupper till dem och definiera tröskelvärde och undantagströskel för dem.
        - Ställ in TDS-myndigheter.
        - Ställ in TDS-kvittningsperioder.
        - Ställ in TDS-momskoder och koppla TDS-komponenter till dem.
        - Ställ in TDS-momsgrupper och koppla TDS-momskoder till dem.
        - I formeldesignern definierar du en formel för att beräkna TDS för en TDS-grupp.
        - Registrera koncessionscertifikatnummer för TDS.

    - Redovisningskonton och inställningar för företag:

        - Ställ in leverantörsreskontra och kundreskontra för TDS.
        - Ställ in ett nummer för skatteavdrag och inkassokonto (TAN) och en avdragstypkategori för företaget.

    - Övriga inställningar:

        - Ställ in en betalningsplan som inkluderar TDS-allokering.
        - Ställ in en betalningsavgiftstyp för betalningar till TDS-myndigheten.
        - Ställ in information om TDS-grupper, permanenta kontonummer (PAN) och TAN för leverantörer och kunder.

2. **Beräkning av TDS i transaktioner:**

    - Fakturor och betalningar
    - Skuldsedlar
    - Förskottsbetalningar
    - Förskottsbetalningar

3. **TDS-kvittning:**

    - Periodisk TDS-kvittningsprocess
    - Kvittning av TDS-betalningar till TDS-myndigheter och generering av TDS challan

4. **TDS-förfrågningar, utdrag och certifikat:**

    - Registrera och uppdatera TDS-certifikatnummer och -datum.
    - Skapa en TDS-förfrågan och en bokförd TDS-förfrågan.
    - Generera formulär 27A, formulär 26Q och formulär 27Q TDS och kvartalsutdrag för e-TDS.
    - Generera formulär 16A TDS-certifikat.
