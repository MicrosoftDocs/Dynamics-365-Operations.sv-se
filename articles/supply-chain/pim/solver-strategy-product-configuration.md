---
title: Lösarstrategi för produktkonfiguration
description: Denna artikel beskriver hur du kan använda problemlösarstrategin för att förbättra prestandan för produktkonfiguration.
author: t-benebo
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b0b53da17bd106be60966d856d29d81a1e57f91
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065537"
---
# <a name="solver-strategy-for-product-configuration"></a>Lösarstrategi för produktkonfiguration

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du kan använda problemlösarstrategin för att förbättra prestandan för produktkonfiguration.

Konceptet för problemlösarstrategier infördes i kumulativ uppdatering 7 (CU7) för Microsoft Dynamics AX 2012 R2. Detta utökades i den kumulativa uppdateringen 8 (CU8) för Microsoft Dynamics AX 2012 R3 samt för appar för ekonomi och drift, Enterprise edition 7.3.

Konceptet problemlösarstrategi består nu av följande strategier:

- Standard
- Minimala domäner först
- Uppifrån och ned
- Z3

## <a name="solver-strategy"></a>Lösarstrategi 

En modell för produktkonfiguration kan formuleras som ett [begränsningsbaserad problem (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf). Microsoft Solver Foundation (MFS) erbjuder två typer av problemlösarstrategier för att lösa de CSPer som kan användas från produktkonfigurationsmodeller. Dessa problemlösarstrategier är beroende av [heuristik](https://techterms.com/definition/heuristic), som används för att bestämma den ordning som variabler av CSPer beaktas när problem löses. Heuristik kan påverka prestanda betydligt när ett problem eller en problemklass löses.

Problemlösarstrategin för produktkonfigurationsmodeller vilka problemlösare som används med heuristik. **Standardstrategierna**, **Minsta domän första**, och **uppifrån och ned** använder två problemlösare från MSF medan **Z3**-strategin använder problemlösaren Z3. 

Studier av verkliga kundimplementationer har visat att en ändring i problemlösarstrategin för produktkonfigurationsmodellen kan minska svarstiden från minuter till millisekunder. Det är därför värt att prova olika problemlösarstrategier för att hitta den mest effektiva strategin för din produktkonfigurationsmodell.

## <a name="change-the-settings-for-the-solver-strategy"></a>Ändra inställningarna för problemlösarstrategin

För att ändra problemlösarstrategin på sidan **produktkonfigurationsmodeller** i åtgärdsfönstret, välj **modellegenskaper**. Därefter väljer du problemlösarstrategi i dialogrutan **redigera modelluppgifter**.

[![Ändra problemlösarstrategi.](./media/solver-strategy.png)](./media/solver-strategy.png)

Det finns för närvarande ingen logik som automatiskt identifierar den mest effektiva strategin för begränsningsbaserad konfiguration. Därför måste du prova en problemlösarstrategi i taget.

Följande tabell innehåller rekommendationer om problemlösarstrategin i olika scenarier.

| Lösarstrategi      | Använd strategin i det här scenariot |
|----------------------|-----------------------------------|
| Standard              | **Standard** strategin har optimerats för att lösa modeller som utnyttjar registerbegränsningar. Studier av kundimplementation har visat att det här alternativet är den mest effektiva strategin i scenarier där registerbegränsningar är mycket vanliga. |
| Minimala domäner först | Strategierna **Minsta domänen först** och **uppifrån och ned** hör nära samman. Studier av kundimplementation har visat att strategin **uppifrån och ned** är bättre än strategin **Minsta domän först**. Men strategin **Minsta domän först** behålls i produkten för bakåtkompatibilitet. Båda dessa problemlösarstrategier för har visat sig vara effektivare på att lösa modeller som innehåller flera aritmetiska uttryck och där ingen registerbegränsningar används. I vissa fall kan **standard** strategin vara bättre än båda de andra strategierna. Kom alltså ihåg att prova alla strategier. |
| Ovansida ned             | Strategierna **Minsta domänen först** och **uppifrån och ned** hör nära samman. Studier av kundimplementation har visat att strategin **uppifrån och ned** är bättre än strategin **Minsta domän först**. Men strategin **Minsta domän först** behålls i produkten för bakåtkompatibilitet. Båda dessa problemlösarstrategier för har visat sig vara effektivare på att lösa modeller som innehåller flera aritmetiska uttryck och där ingen registerbegränsningar används. I vissa fall kan **standard** strategin vara bättre än båda de andra strategierna. Kom alltså ihåg att prova alla strategier. |
| Z3                   | Vi rekommenderar att du använder strategin **Z3** som standardstrategin. Om du oroar dig för prestanda och skalbarhet kan du utvärdera andra strategier. |

## <a name="additional-resources"></a>Ytterligare resurser

[Produktkonfiguration – översikt](build-product-configuration-model.md)

[Heuristik](https://techterms.com/definition/heuristic)

[Begränsningsbaserad problem](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
