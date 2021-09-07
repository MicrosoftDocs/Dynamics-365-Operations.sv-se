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
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385733"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Journalbokföringsfel på grund av obalans

[!include [banner](../includes/banner.md)]

Detta ämne förklarar varför debet och kredit kanske inte kan balanseras i verifikationstransaktioner, varför transaktionerna inte kan bokföras. Detta avsnitt innehåller även steg för korrigering av problemet.

## <a name="symptom"></a>Symptom

I vissa fall kan en journal inte bokföras och följande meddelande visas: "Balansen mellan transaktionerna på en specifik verifikation är inkorrekt för ett visst datum (redovisningsvaluta: 0,01 - rapporteringsvaluta: 0,06)." Varför kan journalen inte bokföras?

## <a name="resolution"></a>Lösning

Vid bokföring i Redovisning måste alla verifikationer balanseras i transaktionsvalutan, redovisningsvalutan och rapporteringsvalutan, om dessa valutor har definierats på sidan **Redovisningskonfiguration**. (Verifikationerna balanseras när de totala debetbeloppen är lika med det total kreditbeloppet.)

Längst ned på journalradssidan visas summor i redovisningsvalutan och rapporteringsvalutan. De visas **inte** i transaktionsvalutan för transaktioner i utländsk valuta. Dessutom visar felmeddelandet som användarna får under simulering eller bokföring endast skillnaderna i redovisningsvaluta och rapporteringsvaluta. De visas inte i transaktionsvalutan eftersom en enda verifikation kan ha mer än en transaktionsvaluta och journalen kan innehålla verifikationer i olika transaktionsvalutor. Det är därför viktigt att du kontrollerar att transaktionsvalutabeloppen för respektive verifikation är balanserade.

### <a name="transaction-currency"></a>Transaktionsvaluta

Under simulering och bokföring verifierar systemet att alla verifikationer är balanserade i transaktionsvalutan. För varje verifikation som anges kan det finnas en eller flera valutor för transaktionsvalutan. En verifikation som registreras i den allmänna journalen kan till exempel ha två transaktionsvalutor när kontanter förs över från ett bankkonto som använder euro (EUR) till ett bankkonto som använder kanadensiska dollar (CAD).

Om en verifikation bara har en (1) transaktionsvaluta måste de totala debetbeloppen vara lika med de totala krediterna för verifikationen. Kunder har upplevt följande scenarier där bokföringen misslyckades korrekt eftersom transaktionsvalutabeloppen inte balanserats:

- De totala debet- och totalkreditbeloppen balanserades **inte** i transaktionsvalutan, men de balanserades däremot för redovisningsvalutan och rapporteringsvalutan. En kund förutsatte att verifikationen fortfarande skulle bokföras. Detta antagande var emellertid fel. **Transaktionsvalutabeloppen på en verifikation måste alltid balanseras när alla rader i verifikationen har samma valuta.**
- Verifikationen importerades genom Microsoft Excel, och användaren trodde att transaktionsvalutabeloppen hade balanserats. I Excel-arbetsboken angavs de importerade beloppen som **numeriska** värden, inte **valutavärden**. I detta scenario hade de numeriska beloppen i arbetsboken mer än två decimaler, och mer än två decimaler togs med när beloppen importerades. Därför var inte debiteringarna lika med krediterna eftersom saknade bråkdelen av ett öre. Journalen återspeglar inte denna skillnad mellan raderna i verifikationen eftersom beloppen som visas bara har två decimaler.
- Verifikationen importerades via Excel, och användaren trodde att transaktionsvalutabeloppen hade balanserats. Även om verifikationen hardebalanserats hade vissa rader på verifikationen olika transaktionsdatum. Om du lagde till de totala debetbeloppen och totala kreditbeloppen per verifikations- och transaktionsdatum, så var dessa inte balanserade. Nu förhindrar systemet detta scenario. En verifikation kan bara ha ett transaktionsdatum. Detta krav tillämpas när du anger en verifikation via den allmänna journalen i systemet. Det tillämpades emellertid inte ursprungligen när en verifikation importerades via Excel.

I ett scenario som stöds kan en verifikation ha mer än en transaktionsvaluta. I det här fallet kontrollerar systemet **inte** att debet är lika med kredit i transaktionsvalutan, detta eftersom valutorna inte matchar. Istället verifierar systemet att beloppen i redovisningsvalutan är balanserade.

### <a name="accounting-currency"></a>Redovisningsvaluta

Om alla rader i en verifikation har samma transaktionsvaluta, och om beloppen i transaktionsvalutan är balanserade, verifierar systemet att beloppen i redovisningsvalutan har balanserats. Om verifikationen anges i en utländsk valuta används valutakursen på verifikationsraderna för att översätta transaktionsvalutabeloppen till redovisningsvalutan. Först översätts varje enskild rad i verifikationen. Raderna summeras sedan för att bestämma debet- och kreditsummorna. Eftersom varje rad översätts kanske debet- och kreditsummorna inte balanseras. Om skillnaden ändå ligger inom värdet för **Maximal öresdifferens** som definierats på sidan **Redovisningsparametrar** bokförs verifikationen, och skillnaden bokförs automatiskt på kontot för öresdifferens.

Om verifikationen har mer än en transaktionsvaluta omsätts varje rad i verifikationen till redovisningsvalutan, och raderna summeras för att bestämma debet- och kreditsummorna. För att vara balanserat måste debet och kredit balanseras, och det får inte finnas någon öresavrundningsdifferens.

### <a name="reporting-currency"></a>Rapporteringsvaluta

Om alla rader i en verifikation har samma transaktionsvaluta, och om beloppen i transaktionsvalutan är balanserade, verifierar systemet att beloppen i rapporteringsvalutan har balanserats. Om verifikationen anges i en utländsk valuta används valutakursen på verifikationsraderna för att översätta transaktionsvalutabeloppen till rapporteringsvalutan. Först översätts varje enskild rad i verifikationen. Raderna summeras sedan för att bestämma debet- och kreditsummorna. Eftersom varje rad översätts kanske debet- och kreditsummorna inte balanseras. Om skillnaden ändå ligger inom värdet för **Maximal öresavrundning i rapporteringsvalutan** som definierats på sidan **Redovisningsparametrar** bokförs verifikationen, och skillnaden bokförs automatiskt på kontot för öresdifferens.

Om verifikationen har mer än en transaktionsvaluta översätts varje rad i verifikationen till rapporteringsvalutan, och raderna summeras sedan för att bestämma debet- och kreditsummorna. För att vara balanserat måste debet och kredit balanseras, och det får inte finnas någon öresavrundningsdifferens.
