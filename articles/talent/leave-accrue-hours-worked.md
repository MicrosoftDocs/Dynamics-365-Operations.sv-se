---
title: Periodisering av ledig tid baserat på antal arbetade timmar
description: Det här avsnittet beskriver hur tjänstledighetsplaner kan konfigureras för att periodisera ledig tid baserat på timmar.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8589527f75f48c16244c93c3fdbe3ce7fcd4e366
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519105"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Periodisering av ledig tid baserat på antal arbetade timmar

[!include [banner](includes/banner.md)]


## <a name="overview"></a>Översikt

Organisationer med timanställda kan tilldela ledig tid baserat på antalet arbetstimmar i stället för anställningstid i organisationen. Antalet arbetade timmar lagras vanligtvis i ett system för tid och närvaro. I Talent: Core HR, denna normala arbetstid och övertid kan importeras och användas som underlag för en medarbetares ersättning.

## <a name="leave-plans"></a>Tjänstledighetsplaner

Inom tjänstledighetsplanen kan periodiseringstypen antingen vara tjänstemånader eller arbetstid. När arbetstid markeras finns det två typer av timmar för den på periodiseringen: vanlig och övertid.

Gör följande om du vill ställa in arbetstid:

1. På sidan **Planer för tjänstledighet och frånvaro** klickar du på **Skapa ny plan**.
2. Ange ett namn för tjänstledighetsplanen.
3. Välj periodiseringsfrekvensen för planen.
5. Välj startdatumet för planen.
6. Välj periodiseringperiodunderlag och markera det medarbetarspecifika datumet om det behövs.
7. För periodiseringsschema, välj **Arbetade timmar** som periodiseringstyp.
8. Välj typ av timmar som ska användas för periodiseringen.
9. Ange antalet arbetade timmar och det associerade periodiseringsbeloppet, minimisaldo och högsta överföring eller beviljad tid.

Periodiseringsbehandling för planer för arbetstimmar använder periodiseringsfrekvensen, tillsammans med periodiseringperiod, för att fastställa vilka timmar som ska periodiseras.

## <a name="annual-accrual-frequency"></a>Årlig periodiseringsfrekvens

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Periodiseringsfrekvens varje månad

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 8/1/2018-8/31/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 8/1/2018-8/31/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Periodiseringsfrekvens var fjortonde dag

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 8/16/2018-8/31/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 8/16/2018-8/31/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Periodiseringsfrekvens varje vecka

| Datum för periodiseringsersättning    | Nivå för arbetade timmar    | Periodiseringstid        | Datum antal arbetstimmar   | Faktiska arbetade timmar| Belöning               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 8/27/2018-8/31/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 8/27/2018-8/31/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Tilldelade tjänstledighetsplaner för anställda

I tilldelade tjänstledighetsplaner för anställda visas nivågrund och typ av timmar för planer där arbetstimmar definieras som periodiseringstyp. För aktiva planer visas även faktiska arbetstimmar för periodiseringsperioderna från aktuella datumet även som referens. 

## <a name="loading-data"></a>Läser in data

Faktiska timmar kan importeras med hjälp av entiteten Arbetade tjänstledighets- och frånvarotimmar i datahantering. Om du använder arbetstidskalendrar verifierar importen att ordinarie arbetstid inte överskrider de schemalagda timmarna per dag som kalendern definierar. Importen kontrollerar att antalet arbetstimmar under en viss dag inte överstiger 24 timmar. 

Följande information behövs för att importera faktiska timmar som ska användas i periodiseringsprocessen för ledigheten:

+ Personalnummer 
+ Arbetsdag
+ Typ
+ Timmar

Ett enstaka datum kan bara ha en av varje typ associerad med uppgiften.

| ANSTÄLLNINGSNUMMER       | ARBETSDAG           | TYP                  | TIMMAR                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Vanligt               | 8                    |       
| 000337                | 8/7/2018             | Vanligt               | 8                    |
| 000337                | 8/7/2018             | Övertid              | 3                    |
| 000337                | 8/8/2018             | Vanligt               | 8                    |
| 000337                | 8/7/2018             | Vanligt               | 8                    |
| 000337                | 8/9/2018             | Vanligt               | 8                    |
