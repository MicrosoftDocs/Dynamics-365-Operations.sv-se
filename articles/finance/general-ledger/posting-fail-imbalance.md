---
title: Journalbokföringsfel på grund av obalans
description: Detta ämne förklarar varför debet och kredit kanske inte kan balanseras i verifikationstransaktioner, varför transaktionerna inte kan bokföras. Detta avsnitt innehåller även steg för korrigering av problemet.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fc413f8230849653aef8c2951f1749823edded6e
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605439"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Journalbokföringsfel på grund av obalans

[!include [banner](../includes/banner.md)]

Detta ämne förklarar varför debet och kredit kanske inte kan balanseras i verifikationstransaktioner, varför transaktionerna inte kan bokföras. Detta avsnitt innehåller även steg för korrigering av problemet.

## <a name="symptom"></a>Symptom

I vissa fall kan en journal inte bokföras och följande meddelande visas: "Balansen mellan transaktionerna på en specifik verifikation är inkorrekt för ett visst datum (redovisningsvaluta: 0,01 - rapporteringsvaluta: 0,06)." Varför kan journalen inte bokföras?

## <a name="resolution"></a>Lösning

Vid bokföring i Redovisning måste alla verifikationer balanseras i transaktionsvalutan, redovisningsvalutan och rapporteringsvalutan, om dessa valutor har definierats på sidan **Redovisningskonfiguration**. (Verifikationerna balanseras när de totala debetbeloppen är lika med det total kreditbeloppet.)

Längst ned på journalradssidan visas summor i redovisningsvalutan och rapporteringsvalutan. De visas **inte** i transaktionsvalutan för transaktioner i utländsk valuta. Dessutom visar felmeddelandet som användarna får under simulering eller bokföring endast skillnaderna i redovisningsvaluta och rapporteringsvaluta. De visas inte i transaktionsvalutan eftersom en enda verifikation kan ha mer än en transaktionsvaluta och journalen kan innehålla verifikationer i olika transaktionsvalutor. Därför är det viktigt att du manuellt kontrollerar att transaktionsvalutabeloppen för varje verifikation som bara har en transaktionsvaluta är balanserade.

### <a name="transaction-currency"></a>Transaktionsvaluta

Under simulering och bokföring verifierar systemet att alla verifikationer med bara en enda transaktionsvaluta är balanserade i transaktionsvalutan. För varje verifikation som anges kan det finnas en eller flera valutor för transaktionsvalutan. En verifikation som registreras i den allmänna journalen kan till exempel ha två transaktionsvalutor när kontanter förs över från ett bankkonto som använder euro (EUR) till ett bankkonto som använder kanadensiska dollar (CAD).

Om en verifikation bara har en (1) transaktionsvaluta måste de totala debetbeloppen vara lika med de totala krediterna i transaktionsvalutan för verifikationen. Kunder har upplevt följande scenarier där bokföringen misslyckades korrekt eftersom transaktionsvalutabeloppen inte balanserats:

- De totala debet- och totalkreditbeloppen balanserades **inte** i transaktionsvalutan, men de balanserades däremot för redovisningsvalutan och rapporteringsvalutan. En kund förutsatte att verifikationen fortfarande skulle bokföras. Detta antagande var emellertid fel. **Transaktionsvalutabeloppen i en verifikation måste alltid balanseras när alla rader i verifikationen har samma transaktionsvaluta.**
- Verifikationen importerades med en dataenhet via Data Management Framework (DMF), och användaren trodde att transaktionsvalutabeloppen har balanserats. Vissa belopp i importfilen hade mer än två decimaler, och mer än två decimaler togs med när beloppen importerades. Därför var inte debiteringarna lika med krediterna eftersom saknade bråkdelen av ett öre. Journalen återspeglar inte denna skillnad mellan raderna i verifikationen eftersom beloppen som visas bara har två decimaler.
- Verifikationen importerades med en datatabell via DMF, och användaren trodde att transaktionsvalutabeloppen hade balanserats. Även om **verifikationen** hade balanserats, hade vissa rader i verifikationen olika transaktionsdatum. Om du lade till de totala debetbeloppen och de totala kreditbeloppen i transaktionsvalutan per **verifikations- och transaktionsdatum**, så balanserades inte dessa. Detta krav tillämpas när du anger en verifikation via den allmänna journalen i systemet. Detta genomdrivs emellertid inte när en verifikation importeras med en datatabell via DMF.

I ett scenario som stöds kan en verifikation ha mer än en transaktionsvaluta. I det här fallet kontrollerar systemet **inte** att debet är lika med kredit i transaktionsvalutan, detta eftersom valutorna inte matchar. Istället verifierar systemet att beloppen i redovisningsvalutan är rapporteringsvalutan är balanserade.

### <a name="accounting-currency"></a>Redovisningsvaluta

Om alla rader i en verifikation har samma transaktionsvaluta, och om beloppen i transaktionsvalutan är balanserade, verifierar systemet att beloppen i redovisningsvalutan har balanserats. Om verifikationen anges i en utländsk valuta används valutakursen på verifikationsraderna för att översätta transaktionsvalutabeloppen till redovisningsvalutan. Först översätts varje rad i verifikationen och avrundas till två decimaler. Raderna summeras sedan för att bestämma debet- och kreditsummorna. Eftersom varje rad översätts kanske debet- och kreditsummorna inte balanseras. Om skillnadens absoluta värde ändå ligger inom värdet för **Maximal öresdifferens** som definierats på sidan **Redovisningsparametrar** bokförs verifikationen, och skillnaden bokförs automatiskt på kontot för öresdifferens.

Om verifikationen har mer än en transaktionsvaluta omsätts varje rad i verifikationen till redovisningsvalutan och avrundas till två decimaler, och raderna summeras för att bestämma debet- och kreditsummorna. För att kunna anses balanserade måste debet och kredit balanseras, antingen i omräknad form eller när redovisningsvalutans öresavrundningsdifferens inkluderas.

### <a name="reporting-currency"></a>Rapporteringsvaluta

Om alla rader i en verifikation har samma transaktionsvaluta, och om beloppen i transaktionsvalutan är balanserade, verifierar systemet att beloppen i rapporteringsvalutan har balanserats. Om verifikationen anges i en utländsk valuta används valutakursen på verifikationsraderna för att översätta transaktionsvalutabeloppen till rapporteringsvalutan. Först översätts varje rad i verifikationen och avrundas till två decimaler. Raderna summeras sedan för att bestämma debet- och kreditsummorna. Eftersom varje rad översätts kanske debet- och kreditsummorna inte balanseras. Om skillnaden ändå ligger inom värdet för **Maximal öresavrundning i rapporteringsvalutan** som definierats på sidan **Redovisningsparametrar** bokförs verifikationen, och skillnaden bokförs automatiskt på kontot för öresdifferens.

Om verifikationen har mer än en transaktionsvaluta omsätts varje rad i verifikationen till rapporteringsvalutan och avrundas till två decimaler, och raderna summeras sedan för att bestämma debet- och kreditsummorna. För att kunna anses balanserade måste debet och kredit balanseras, antingen i omräknad form eller när rapporteringsvalutans öresavrundningsdifferens inkluderas.

### <a name="example-for-an-accounting-currency-imbalance"></a>Exempel på en obalans i redovisningsvaluta

> [!NOTE]
> Beloppet i rapporteringsvalutan beräknas från transaktionsvalutabeloppet på samma sätt som beloppet i redovisningsvalutan.

Valutakurs: 1,5

| Rad | Verifikation | Konto | Valuta | Debet (transaktion) | Kredit (transaktion) | Debet (redovisning) | Kredit (redovisning) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5,00 (4,995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5,00 (4,995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10,00 | | 15.00 |
| **Totalt** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

Redovisningsvalutan är i obalans med 0,01. Så länge som den maximala öresavrundningen i redovisningsvalutan är minst 0,01 bokförs skillnaden automatiskt på öresdifferenskontot, och verifikationen bokförs automatiskt.
