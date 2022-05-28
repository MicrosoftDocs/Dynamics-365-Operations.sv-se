---
title: Importformat for konsolidering
description: Detta ämne innehåller detaljerad information om det importformat som används när du konsoliderar ekonomiska data från flera juridiska personer.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 5bea69d72ac93d29ae67dd6d762e1376d9a282f0
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735795"
---
# <a name="import-format-for-consolidation"></a>Importformat for konsolidering

[!include [banner](../includes/banner.md)]

Detta ämne innehåller detaljerad information om det importformat som används när du konsoliderar ekonomiska data från flera juridiska personer. Importformatet måste sparas som en textfil (.txt).

## <a name="import-format"></a>Importformat

I tabellen nedan visas det importformat som du bör använda när du gör en konsolidering i samband med import.

| Postregister | Format | Anteckningar |
|--------------|---------|-------|
| 1            | 170150, Goodwill, 4 | <ul><li>Postregistret</li><li>Huvudkonto-ID för källa</li><li>Huvudkontoraden</li><li>Huvudkontotypen</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>Huvudkonto-ID</li><li>Transaktionsdatumet</li><li>Räkenskapsperiodtyp (**0** = Öppnande, **1** = Verksamhet, samt **2** = Stängning)</li><li>Transaktionsvalutan</li><li>Debet eller kredit (**0** = Debet och **1** = Kredit)</li><li>Bokföringsskikt</li><li>Transaktionsbelopp</li><li>Kvantitet</li><li>Lokalt RecID (tvetydigt, unikt int64-värde för transaktionen)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>Postnumret (transaktionsnummer för budgetrubrik)</li><li>Standarddatum för budgetrubrik</li><li>ID för budgetmodell</li><li>Budgettyp (**1** – Ursprunglig budget, **2** – Överföring, **3** – Ändring, **4** – Inteckning, **5** – Förinteckning, **6** – Överförd budget, **7** – Projekt, **8** – Anläggningstillgångar, **9** – Efterfrågeprognos, **10** – Inflödesprognos, **11** – Enhetliga fördelningar, **12** – Preliminär budget.)</li><li>Datum för raden</li><li>Huvudkonto-ID för raden</li><li>Valutakod för raden</li><li>Beloppet för raden i transaktionsvalutan</li><li>Uppräkningens heltalsvärde för budgettypen för raden (utgift eller intäkt)</li></ul> |
| 4            | DEMF | RecordCompany är juridisk person för Källa. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>Huvudkonto-ID</li><li>Transaktionsdatum</li><li>Räkenskapsperiodtyp (0 Öppnande, 1 Verksamhet, 2 Stängning)</li><li>Transaktionsvaluta</li><li>Debet eller kredit (0 för Debet och 1 för Kredit)</li><li>Bokföringsskikt</li><li>Transaktionsbelopp</li><li>Antal</li><li>Lokalt RecID (tvetydigt, unikt int64-värde för transaktionen)</li></ul>  |
| 6            | Affärsenhet, 1 avdelning, 2 | Attributen för den ekonomiska dimension som har definierats i segmentordningen.<p>På sidan **Exportera** kan du bekräfta attributdefinitionerna.</p> |
| 7            | 002,1,658 | <ul><li>Värdet för ekonomisk dimension</li><li>Den ekonomiska dimensionen, som det index som anges i RecordDimensions</li><li>Ett tvetydigt, unikt post-ID som är kopplat till det unika post-ID:t från RecordTrans eller RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Dimensionsvärden som associeras med transaktionen från RecordBudget</li><li>Den ekonomiska dimensionen, som det index som anges i RecordDimensions</li><li>Ett tvetydigt post-ID för den rad som är justerad efter transaktionsradernas ordning i filen</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
