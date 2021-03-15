---
title: Skapa en plan för tjänstledighet och frånvaro
description: Skapa frånvaroplaner i Dynamics 365 Human Resources för olika typer av tjänstledighet.
author: andreabichsel
manager: tfehr
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 90a3d624dac6c78dfbf2479c5ac7eab76dd4b542
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115958"
---
# <a name="create-a-leave-and-absence-plan"></a>Skapa en plan för tjänstledighet och frånvaro

Definiera tjänstledighet och frånvaroplaner i Dynamics 365 Human Resources för varje typ av tjänstledighet du erbjuder. Tjänstledighets- och frånvaroplaner kan periodiseras i olika frekvenser, t.ex. per år, månad eller halvmånad. Planer kan även definieras som ett anslag, där en enda ackumulering sker på ett visst datum. Du kan till exempel skapa en plan som ger flytande helgdagar varje år.

Med tjänstledighetsplaner i nivåer kan medarbetarna få förmåner baserat på hur mycket tid de har ägnat åt en organisation. Med nivåplaner aktiveras automatisk registrering i ytterligare förmånstider.

Du kan ange högsta överföringsbelopp eller lägsta saldo för att endast de anställda ska kunna använda den förmånstid som de har periodiserats.

Med en nivåplan kan du till exempel bevilja en förmån på 80 timmars betald ledighet (PTO) för nya medarbetare. Därefter kan du bevilja 120 timmar för 60 månaders tjänst.

Du kan också skapa befattningsfria förmåner, t.ex. förmånstimmar som endast gäller chefer.

## <a name="create-a-leave-plan"></a>Skapa en tjänstledighetsplan

1. På sidan **Tjänstledighet och frånvaro** klickar du på **Skapa ny plan**.

2. Under **information**, ange **namn**, **startdatum**, **beskrivning** och **tjänstledighetstyp** för planen.

Om funktionen **Konfigurera flera tjänstledighetstyper för en enskild tjänstledighets- och frånvaroplan** är aktiverad konfigureras tjänstledighetstyper i **Periodiseringsschema** istället under **Detaljer**. För varje post i registret för periodiseringsschema kan du ange en tjänstledighetstyp. När den här funktionen är aktiverad måste du dessutom använda nya dataenheter för integration eller andra scenarier där du behöver använda entiteter. 

De nya entiteterna är:

- Transaktion för tjänstledighets- och frånvarobank V2
- Anmälan om tjänstledighet och frånvaro V2
- Plannivå för tjänstledighet och frånvaro V2
- Plan för tjänstledighet och frånvaro V2
- Ledighetsansökan V2

 > [!IMPORTANT]
   > När du har aktiverat den här funktionen kan du inte inaktivera den.

3. Definiera periodiseringar på fliken **Periodiseringar**. Avskrivningar bestämmer när och hur ofta en medarbetare tilldelas ledighet. I det här steget definierar du principer för när periodiseringar ska tilldelas och policyer om att lämna ersättningar för allokeringen.

   1. Välj ett värde i listrutan **periodiseringsfrekvens**:

      - Dagligen
      - Varje vecka
      - Två veckor
      - Halvmånadsvis
      - Månatlig
      - Kvartalsvis
      - Halvårsvis
      - Årligen
      - Ingen

   2. Välj ett alternativ i listrutan **Periodiseringsperiodbas** om du vill ange det startdatum som ska användas för beräkning av periodiseringsperioder:

      | Periodiseringsperiodbas | Beskrivning |
      | --- | --- |
      | **Startdatum för planen** | Periodiseringsperiodens startdatum är det datum då planen är tillgänglig. |
      | **Medarbetarspecifikt datum** | Periodiseringsperiodens startdatum beror på en medarbetarhändelse:</br><ul><li>Anpassad (du måste ange ett datum för periodisering av varje enskild anmälan)</li><li>Jubileumsdatum</li><li>Ursprungligt anställningsdatum</li><li>Datum för tjänsteålder</li><li>Arbetarens justerade startdatum</li><li>Arbetarens startdatum</li></ul> |

   3. Välj ett alternativ i listrutan **Belöningsdatum för periodisering**:

      - **Periodiseringens slutdatum** – medarbetaren kommer att tilldelas ledighet på den sista dagen av belöningsperioden. Om du vill periodisera den korrekta mängden måste periodiseringsprocessen innehålla hela perioden. Om periodiseringsperioden t.ex. är 1 januari 2020 till 31 januari 2020, måste du köra periodiseringen för 1 februari 2020 för att inkludera januari.

      - **Periodiseringens startdatum** – medarbetaren kommer att tilldelas ledighet på den första dagen av belöningsperioden.

   4. Välj ett alternativ i listrutan **Periodiseringspolicy vid registrering**: Det här värdet anger hur periodiseringen ska beräknas när en medarbetare registrerar sig i mitten av en periodiseringsperiod.

      - **Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar. Denna skillnad tillämpas när periodiseringar bearbetas.

      - **Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.

      - **Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.

   5. Välj ett alternativ i listrutan **Periodiseringspolicy vid avregistrering**: Det här värdet anger hur periodiseringen ska beräknas när en medarbetare avregistrerar sig i mitten av en periodiseringsperiod.

      - **Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar. Denna skillnad tillämpas när periodiseringar bearbetas.

      - **Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.

      - **Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.

4. Definiera schemat för periodisering på fliken **Periodiseringsschema**. Periodiseringsschema avgör:

   - Hur en medarbetare tillfaller ledighet
   - Vilka belopp medarbetaren ska tillfallas
   - Vilka belopp som ska överföras

   Nivåerna kan skapas så att ledig tid beviljas baserat på olika nivåer.

   Om du har timanställda kan du tilldela ledig tid baserat på antalet arbetstimmar i stället för anställningstid i organisationen. Data för arbetade timmar lagras vanligtvis i ett system för tid och närvaro. Du kan importera regelbundna och övertidstimmar som har utförts från tids- och närvarosystemet och använda dem som grund för en medarbetares belöning.
   
    1. Välj ett alternativ i listrutan **periodiseringstyp**:

      - **Månaders tjänst** – basera periodiseringsschemat på tjänstemånader.

      - **Antal arbetade timmar** – basera periodiseringsschemat på arbetade timmar. Mer information om periodiseringar för arbetade timmar finns i [periodiserad ledighet baserat på arbetade timmar](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Mer information om periodiseringssaldon finns i [periodiserad ledighet baserat på arbetade timmar](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Ange värden i registret för periodiseringsscheman:

      - **Månaders tjänst** – det minsta antalet månader som medarbetare måste arbeta om du vill ha rätt till periodiseringar. Om du inte behöver ett minimum ställer du in värdet på 0.

      - **Arbetade timmar** – det minsta antalet timmar som medarbetare måste arbeta per periodiseringsperiod för att ha rätt till periodiseringar. Om du inte behöver ett minimum ställer du in värdet på 0.

      - **Periodiseringsbelopp** – antalet timmar eller dagar som medarbetare periodiserar per period. Perioden baseras på periodiseringsfrekvensen.

      - **Minsta saldo** – Ett negativt värde kan användas för minsta saldot om anställda kan begära mer ledighet än vad de har tillgängligt.

      - **Maximal överföring** – Periodiseringsprocessen kommer att justera ledighetssaldon som överstiger det maximalt överförda saldot på startdatumet.

      - **Beviljad mängd** – Det initiala antalet timmar eller dagar som medarbetaren har beviljats när de först registrerar sig i ledighetsplanen. Mängden periodiseras inte för varje periodiseringsperiod.
      
Om funktionen **Konfigurera flera tjänstledighetstyper för en enskild tjänstledighets- och frånvaroplan** är aktiverad, väljer du ett alternativ från typen **tjänstledighetstyp**. 

   > [!IMPORTANT]
   > När du har aktiverat den här funktionen kan du inte inaktivera den.

Om funktionen **Använd Heltidslön** är aktiverad använder personal den heltidslön (FTE) som definierats för befattningen för att proportionellt fördela medarbetarens periodisering. Om till exempel heltid är 0,5 och periodiseringen är 10, kommer medarbetaren att periodisera 5. Du kan bara använda den här funktionen om du aktiverar flera tjänstledighetstyper.  

5. Välj **Spara**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Periodisera ledig tid baserat på antal arbetade timmar

Om du har timanställda kan du tilldela ledig tid baserat på antalet arbetstimmar i stället för anställningstid i organisationen. Data för arbetade timmar lagras vanligtvis i ett system för tid och närvaro. Du kan importera regelbundna och övertidstimmar som har utförts från tids- och närvarosystemet och använda dem som grund för en medarbetares belöning.

När du väljer arbetade timmar som periodiseringsform kan du använda två typer av timmar för periodiseringen: vanlig och övertid. Periodiseringsbehandling för planer för arbetstimmar använder periodiseringsfrekvensen, tillsammans med periodiseringperiod, för att fastställa vilka timmar som ska periodiseras.

### <a name="annual-accrual-frequency"></a>Årlig periodiseringsfrekvens

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Periodiseringsfrekvens varje månad

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 8/1/2018-8/31/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 8/1/2018-8/31/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Periodiseringsfrekvens var fjortonde dag

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 8/16/2018-8/31/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 8/16/2018-8/31/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Periodiseringsfrekvens varje vecka

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 8/27/2018-8/31/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 8/27/2018-8/31/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Tilldelade tjänstledighetsplaner för anställda

I tilldelade tjänstledighetsplaner för anställda visas nivågrund och typ av timmar visas för planer för arbetstimmar. Faktiska arbetstimmar för periodiseringsperioderna från aktuella datumet visas även för aktiva planer.

### <a name="loading-data"></a>Läser in data

Du kan importera faktiska timmar kan importeras med hjälp av entiteten **Arbetade tjänstledighets- och frånvarotimmar** i datahantering. Om du använder arbetstidskalendrar verifierar importen att ordinarie arbetstid inte överskrider de schemalagda timmarna per dag som kalendern definierar. Importen kontrollerar att antalet arbetstimmar under en viss dag inte överstiger 24. 

Följande information behövs för att importera faktiska timmar som ska användas i periodiseringsprocessen för ledigheten:

- Personalnummer 
- Arbetsdag
- Typ
- Timmar

Ett enstaka datum kan bara ha en av varje typ associerad med uppgiften.

| Personalnummer       | Arbetsdag           | Typ                  | Timmar                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Vanligt               | 8                    |       
| 000337                | 8/7/2018             | Vanligt               | 8                    |
| 000337                | 8/7/2018             | Övertid              | 3                    |
| 000337                | 8/8/2018             | Vanligt               | 8                    |
| 000337                | 8/7/2018             | Vanligt               | 8                    |
| 000337                | 8/9/2018             | Vanligt               | 8                    |

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

Aktuellt saldo (160) = periodiserad mängd (200) – begärd mängd (40)

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

Aktuellt saldo (22) = periodiserad mängd (5x6) – begärd mängd (8)

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

Aktuellt saldo (7) = periodiserad mängd (5x3) – begärd mängd (8)

### <a name="forecasted-balance"></a>Prognostiserat saldo

*Prognossaldot* är mängden ledighet som är tillgängligt ett framtida datum. Periodiseringar och överförda justeringar prognostiseras fram till detta datum.

Personal använder följande formel:

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
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3.00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)
- [Periodisera planer för tjänstledighet och frånvaro](hr-leave-and-absence-accrue.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]