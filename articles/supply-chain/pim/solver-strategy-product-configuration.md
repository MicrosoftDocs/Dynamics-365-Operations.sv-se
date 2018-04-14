---
title: "Lösarstrategi för produktkonfiguration"
description: "Det här avsnittet beskriver hur du kan använda problemlösarstrategin för att förbättra prestandan för produktkonfiguration."
author: cvocph
manager: AnnBe
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 4544128e580b30b14a6236a9a6147ff0a8641d72
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="solver-strategy-for-product-configuration"></a>Lösarstrategi för produktkonfiguration

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan använda problemlösarstrategin för att förbättra prestandan för produktkonfiguration.

Konceptet för problemlösarstrategier infördes i kumulativ uppdatering 7 (CU7) för Microsoft Dynamics AX 2012 R2. Den förlängdes i kumulativ uppdatering 8 (CU8) för Microsoft Dynamics AX 2012 R3 och Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3.

Konceptet problemlösarstrategi består nu av följande strategier:

- Standard
- Minimala domäner först
- Uppifrån och ned
- Z3

## <a name="solver-strategy"></a>Lösarstrategi 

En modell för produktkonfiguration kan formuleras som ett [begränsningsbaserad problem (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf). Microsoft Solver Foundation (MSF) erbjuder två typer av problemlösarstrategier för att lösa de CSPer som kan användas från produktkonfigurationsmodeller. Dessa problemlösarstrategier är beroende av [heuristik](https://techterms.com/definition/heuristic), som används för att bestämma den ordning som variabler av CSPer beaktas när problem löses. Heuristik kan påverka prestanda betydligt när ett problem eller en problemklass löses.

I Finance and Operations avgör problemlösarstrategin för produktkonfigurationsmodeller vilka problemlösare som används med heuristik. **Standardstrategierna**, **Minsta domän första**, och **uppifrån och ned** använder två problemlösare från MSF medan **Z3**-strategin använder problemlösaren Z3. 

Studier av verkliga kundimplementationer har visat att en ändring i problemlösarstrategin för produktkonfigurationsmodellen kan minska svarstiden från minuter till millisekunder. Det är därför värt att prova olika problemlösarstrategier för att hitta den mest effektiva strategin för din produktkonfigurationsmodell.

## <a name="change-the-settings-for-the-solver-strategy"></a>Ändra inställningarna för problemlösarstrategin

För att ändra problemlösarstrategin på sidan **produktkonfigurationsmodeller** i åtgärdsfönstret, välj **modellegenskaper**. Därefter väljer du problemlösarstrategi i dialogrutan **redigera modelluppgifter**.

[![Att ändra problemlösarstrategi.](./media/solver-strategy.png)](./media/solver-strategy.png)

Det finns för närvarande ingen logik som automatiskt identifierar den mest effektiva strategin för begränsningsbaserad konfiguration. Därför måste du prova en problemlösarstrategi i taget.

Följande tabell innehåller rekommendationer om problemlösarstrategin i olika scenarier.

| Lösarstrategi      | Använd strategin i det här scenariot |
|----------------------|-----------------------------------|
| Standard              | **Standard**strategin har optimerats för att lösa modeller som utnyttjar registerbegränsningar. Studier av kundimplementation har visat att det här alternativet är den mest effektiva strategin i scenarier där registerbegränsningar är mycket vanliga. |
| Minsta domän först | Strategierna **Minsta domänen först** och **uppifrån och ned** hör nära samman. Studier av kundimplementation har visat att strategin **uppifrån och ned**, som introducerades i CU8, är bättre än strategin **Minsta domän först**. Men strategin **Minsta domän först** behålls i produkten för bakåtkompatibilitet. Båda dessa problemlösarstrategier för har visat sig vara effektivare på att lösa modeller som innehåller flera aritmetiska uttryck och där ingen registerbegränsningar används. I vissa fall kan **standard** strategin vara bättre än båda de andra strategierna. Kom alltså ihåg att prova alla strategier. |
| Uppifrån och ned             | Strategierna **Minsta domänen först** och **uppifrån och ned** hör nära samman. Studier av kundimplementation har visat att strategin **uppifrån och ned**, som introducerades i CU8, är bättre än strategin **Minsta domän först**. Men strategin **Minsta domän först** behålls i produkten för bakåtkompatibilitet. Båda dessa problemlösarstrategier för har visat sig vara effektivare på att lösa modeller som innehåller flera aritmetiska uttryck och där ingen registerbegränsningar används. I vissa fall kan **standard** strategin vara bättre än båda de andra strategierna. Kom alltså ihåg att prova alla strategier. |
| Z3                   | Vi rekommenderar att du använder strategin **Z3** som standardstrategin. Om du oroar dig för prestanda och skalbarhet kan du utvärdera andra strategier. |

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa produktkonfigurationsmodell](build-product-configuration-model.md)

[Heuristik](https://techterms.com/definition/heuristic)

[Begränsningsbaserad problem](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)

