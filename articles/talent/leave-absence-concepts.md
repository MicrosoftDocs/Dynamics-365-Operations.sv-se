---
title: Begrepp för tjänstledighet och frånvaro
description: Det här avsnittet beskriver begrepp för tjänstledighet och frånvaro och hur ledighetssaldon fastställs.
author: andreabichsel
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: ''
ms.openlocfilehash: 96e3aa74e513a2421b04bac049400cf71042e2c8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519104"
---
# <a name="leave-and-absence-concepts"></a>Begrepp för tjänstledighet och frånvaro

[!include[banner](../includes/banner.md)]

De begrepp och termer som beskrivs i det här avsnittet kan hjälpa dig att avgöra hur en medarbetare tilldelats ledighet och hur denna medarbetares tidssaldo beräknas. Läs mer om ledighet och frånvaro i [Hantering av tjänstledighet och frånvaro](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Detaljer om tjänstledighetsplan

### <a name="start-date"></a>Startdatum

Startdatumet är det datum då periodiseringsbehandling börjar. Startdatumet används också som jubileumsdatum för att beräkna överföringsmängd.

## <a name="accruals"></a>Periodiseringar

Periodiseringar bestämmer när och hur ofta en medarbetaren belönas med ledighet. Policyer om när periodiseringar bör tilldelas och policyer om proportionell fördelning definieras i avsnittet **periodiseringar** när du ställer in planen för tjänstledighet och frånvaro.

### <a name="accrual-frequency"></a>Periodiseringsfrekvens

Periodiseringsfrekvensen definierar hur ofta ledighet periodiseras eller tilldelas. Följande alternativ är tillgängliga:

- Dagligen
- Varje vecka
- Varannan vecka
- Halvmånadsvis
- Månatlig
- Kvartalsvis
- Halvårsvis
- Årligen
- Ingen

### <a name="accrual-period-basis"></a>Periodiseringsperiodbas

Periodiseringperiodunderlaget bestämmer datumet som används för att beräkna periodiseringsperioder. Följande alternativ är tillgängliga:

- **Startdatum för planen**
- **Datum för särskilda medarbetare** – när det här alternativet väljs bestäms källan för första datumvärdet som används för att beräkna periodiseringsperioder. Följande alternativ är tillgängliga:

    - Anpassa
    - Jubileumsdatum
    - Ursprungligt anställningsdatum
    - Datum för tjänsteålder
    - Arbetarens justerade startdatum
    - Arbetarens startdatum

### <a name="accrual-award-date"></a>Belöningsdatum för periodisering

Belöningsdatum för periodisering bestämmer när och hur ofta en medarbetaren belönas med ledighet. Följande alternativ är tillgängliga:

- **Periodiseringens slutdatum** – medarbetaren kommer att tilldelas ledighet på den sista dagen av belöningsperioden.

    Om du vill periodisera den korrekta mängden måste periodiseringsprocessen innehålla hela perioden. Exempelvis är 1 januari 2018 till och med 31 januari 2018 periodiseringsperioden. För januari att ingå måste då avskrivningen köras för 1 februari 2018.

- **Periodiseringens startdatum** – medarbetaren kommer att tilldelas ledighet på den första dagen av belöningsperioden.

### <a name="accrual-policy-on-enrollment"></a>Periodiseringspolicy vid registrering

Periodiseringspolicyn vid registreringen definierar hur periodiseringen beräknas när medarbetaren har registrerats i mitten av en periodiseringsperiod. Följande alternativ är tillgängliga:

- **Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar. Denna skillnad tillämpas när periodiseringar bearbetas.
- **Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.
- **Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.

### <a name="accrual-policy-on-unenrollment"></a>Periodiseringspolicy vid avregistrering

Periodiseringspolicyn vid avregistreringen definierar hur periodiseringen beräknas när medarbetaren har avregistrerats i mitten av en periodiseringsperiod. Följande alternativ är tillgängliga:

- **Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar. Denna skillnad tillämpas när periodiseringar bearbetas.
- **Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.
- **Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.

## <a name="accrual-schedule"></a>Periodiseringsschema

Periodiseringsschemat avgör hur en medarbetare periodiserar ledig tid och vilka mängder som den medarbetaren ska periodisera och överföra. Nivåerna kan skapas så att ledig tid beviljas baserat på olika nivåer.

### <a name="months-of-service"></a>Tjänstgöringsmånader

Värdet **månader** anger minsta antalet månader som medarbetare måste arbeta om du vill ha rätt till periodiseringar. Om inget lägsta krävs för medarbetare är värdet **0**.

### <a name="hours-worked"></a>Arbetade timmar

Värdet **Arbetade timmar** anger minsta antalet timmar som medarbetare måste arbeta per periodiseringsperiod för att ha rätt till periodiseringar. Om inget lägsta krävs för medarbetare är värdet **0**.

### <a name="accrual-amount"></a>Periodiseringstid

Den periodiserade mängden är antalet timmar eller dagar som medarbetare periodiserar per period. Perioden baseras på periodiseringsfrekvensen.

### <a name="minimum-balance"></a>Lägsta saldo

Ett negativt värde kan användas för minsta saldot om anställda kan begära mer ledighet än vad de har tillgängligt.

### <a name="maximum-carry-forward"></a>Maximal överföring

Periodiseringsprocessen kommer att justera ledighetssaldon som överstiger det maximalt överförda saldot på startdatumet.

### <a name="grant-amount"></a>Bevilja mängd

Beviljad mängd är initiala antalet timmar eller dagar som medarbetaren har beviljats när de först registrerar sig i ledighetsplanen. Mängden periodiseras inte för varje periodiseringsperiod.

## <a name="enrollments-and-balances"></a>Registrera och saldon

### <a name="enrollment-date"></a>Datum för anmälan

Anmälningsdatumet bestämmer när medarbetaren kan börja periodisera ledig tid. Om medarbetaren till exempel har registrerats på en plan för semester den 15 juni 2018 kan hon inte periodisera ledig tid före 15 juni 2018.

### <a name="current-balance"></a>Aktuellt saldo

Aktuellt saldo är mängden ledighet som är tillgänglig för begäran om ledighet. Denna mängd inkluderar periodiseringar, godkända begäran och justeringar som aktuellt datum.

### <a name="current-balance-examples"></a>Exempel på aktuellt saldo

#### <a name="annual-plan"></a>Årlig plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Årlig            | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 1 januari 2019 (1/1/2019), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Begära mängd | Registrera saldo (den 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Aktuellt saldo (160) = periodiserad mängd (200) - begärd mängd (40)

#### <a name="semimonthly-plan"></a>Halvmånadsvis plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Halvmånadsvis       | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 1 maj 2018 (5/1/2018), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Begära mängd | Registrera saldo (den 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Aktuellt saldo (22) = periodiserad mängd (5x6) - begärd mängd (8)

#### <a name="monthly-plan"></a>Månadsvis plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Halvmånadsvis       | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 1 maj 2018 (5/1/2018), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Begära mängd | Registrera saldo (den 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Aktuellt saldo (7) = periodiserad mängd (5x3) - begärd mängd (8)

### <a name="forecasted-balance"></a>Prognossaldo

*Prognossaldot* är mängden ledighet som är tillgängligt ett framtida datum. Periodiseringar och överförda justeringar prognostiseras fram till detta datum.

Följande formel används:

Måndag prognostiserat saldo = aktuellt saldo – begäran + periodiseringar – överför justering

### <a name="forecasted-balance-examples"></a>Exempel på prognostiserat saldo

#### <a name="annual-plan"></a>Årlig plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Årlig            | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Aktuellt saldo | Prognostiserat saldo (den 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Prognostiserat saldo (40) = periodiserad mängd (20) + aktuellt saldo (40) – överför justering (20)

#### <a name="semimonthly-plan"></a>Halvmånadsvis plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Halvmånadsvis       | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Aktuellt saldo | Prognostiserat saldo (den 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Prognostiserat saldo (35) = periodiserad mängd (5x3) + aktuellt saldo (40) – överför justering (20)

#### <a name="monthly-plan"></a>Månadsvis plan

**Planinställningar**

| Startdatum för planen | Datum för anmälan | Periodiseringsfrekvens | Periodiseringsperiodbas | Belöningsdatum för periodisering    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Halvmånadsvis       | Startdatum för planen      | Slut på periodiseringsperiod |

Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.

**Resultat**

| Periodiseringstid | Lägsta saldo | Maximal överföring | Aktuellt saldo | Prognostiserat saldo (den 2/15/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Prognostiserat saldo (30) = periodiserad mängd (10x1) + aktuellt saldo (40) – överför justering (20)

### <a name="proration-balance-examples"></a>Exempel på proportionell fördelning av saldo

#### <a name="prorated-monthly-plan"></a>Månatlig plan med proportionell fördelning

**Planinställningar**

| Startdatum för planen | Periodiseringsfrekvens | Periodiseringsperiodbas |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Månatlig           | Startdatum för planen      |

**Resultat**

| Medarbetare            | Tjänstgöringsmånader | Datum för anmälan | Startdatum | Periodiseringstid | Bearbeta periodisering | Balans |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2,53    |

#### <a name="full-accrual-monthly-plan"></a>Fullständig månatlig plan för periodisering

**Planinställningar**

| Startdatum för planen | Periodiseringsfrekvens | Periodiseringsperiodbas |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Månatlig           | Startdatum för planen      |

**Resultat**

| Medarbetare            | Tjänstgöringsmånader | Datum för anmälan | Startdatum | Periodiseringstid | Bearbeta periodisering | Balans |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Ingen månatlig plan för periodisering

**Planinställningar**

| Startdatum för planen | Periodiseringsfrekvens | Periodiseringsperiodbas |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Månatlig           | Startdatum för planen      |

**Resultat**

| Medarbetare            | Tjänstgöringsmånader | Datum för anmälan | Startdatum | Periodiseringstid | Bearbeta periodisering | Balans |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.00    |
