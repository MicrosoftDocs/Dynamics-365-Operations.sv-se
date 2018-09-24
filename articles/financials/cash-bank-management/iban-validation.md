---
title: Hantera validering av internationellt bankkontonummer (IBAN)
description: "Det här avsnittet förklarar hur du hanterar validering av internationellt bankkontonummer (IBAN)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: sv-se
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Hantera validering av internationellt bankkontonummer (IBAN)

[!include [banner](../includes/banner.md)]

Validering av internationellt bankkontonummer (IBAN) ökar mängden validering som görs när du lägger till ett IBAN till ett bankkonto.

Strukturen i IBAN lagras i Microsoft Dynamics 365 for Finance and Operation och laddas automatiskt när du först använder IBAN på bankkonton. Bankkontonumret ingår i strukturen som definieras för ett IBAN-nummer. Utifrån denna struktur, om placering och längden på kontonummer i IBAN inte matchar den position som definieras i strukturen för varje land eller region kommer du att få varningsmeddelanden.

## <a name="set-up-iban-structures"></a>Ställ in IBAN-strukturer

1. Gå till **Kassa- och bankhantering \> Inställningar \> IBAN-strukturer**.
2. Observera att IBAN strukturerna för varje land eller region har ställts in automatiskt.
3. Om du måste anpassa strukturerna för ett visst land eller region kan du redigera dem.
4. Strukturdefinitionerna kommer att ingå i varje ny utgåva. Du kan använda menyn **Återställ strukturer** för att hämta de senaste definitionerna efter varje uppdatering.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Validera IBAN-strukturen på ett bankkonto

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Skapa ett bankkonto.
3. På snabbfliken **Ytterligare information**, ange ett IBAN.

    Om placeringen och längden på kontonummer i IBAN inte matchar den position som definieras i strukturen för varje land eller region kommer du att få ett meddelande. Du kan inte fortsätta om längden på IBAN inte motsvaras av längden i IBAN-strukturen.

    Valideringen kontrollerar även att bankkontonumret stämmer överens med delen i IBAN-numret som representerar numret på bankkontot. Om bankkontonumret  inte överensstämmer visas ett varningsmeddelande. Detta meddelande är bara en varning. Du kan fortsätta trots att bankkontonumret inte stämmer överens.

