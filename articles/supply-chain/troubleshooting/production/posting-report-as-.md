---
title: Fel när journalen Rapportera som klar bokförs
description: När du bokför journalen Rapportera som klar får du ett felmeddelande om att den beställda kvantiteten inte kan minskas.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026904"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Fel när journalen Rapportera som klar bokförs

KB-nummer: 4612891

## <a name="symptoms"></a>Symtom

När du bokför journalen **Rapportera som klar** uppstår ett fel och följande felmeddelande visas:

> Det går inte att minska beställd kvantitet eftersom det inte finns tillräckligt med öppna lagertransaktioner med status Beställt. Artiklarna köps, tas emot eller registreras.

Det här felet uppstår endast när fältet **Felkvantitet** är inställt på den första raden av journalen **Rapporter som klar** och fältet **Bra kvantitet** är inställt på den sista raden. Om fältet **Felkvantitet** anges på den sista raden uppstår inget fel.

## <a name="resolution"></a>Upplösning

För att förhindra detta fel öppnar du sidan **Produktionskontrollparametrar** och sedan, under fliken **Allmänt**, ställer du in alternativet **Öka kvarvarande kvantitet med felkvantitet** på *Ja*.
