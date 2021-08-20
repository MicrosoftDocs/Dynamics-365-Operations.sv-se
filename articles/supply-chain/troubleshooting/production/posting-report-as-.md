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
ms.openlocfilehash: 50a11aba46519a3a81c313aa1f685d45dcf35f64b50bc921d93968efab13b7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750940"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Fel när journalen Rapportera som klar bokförs

KB-nummer: 4612891

## <a name="symptoms"></a>Symtom

När du bokför journalen **Rapportera som klar** uppstår ett fel och följande felmeddelande visas:

> Det går inte att minska beställd kvantitet eftersom det inte finns tillräckligt med öppna lagertransaktioner med status Beställt. Artiklarna köps, tas emot eller registreras.

Det här felet uppstår endast när fältet **Felkvantitet** är inställt på den första raden av journalen **Rapporter som klar** och fältet **Bra kvantitet** är inställt på den sista raden. Om fältet **Felkvantitet** anges på den sista raden uppstår inget fel.

## <a name="resolution"></a>Upplösning

För att förhindra detta fel öppnar du sidan **Produktionskontrollparametrar** och sedan, under fliken **Allmänt**, ställer du in alternativet **Öka kvarvarande kvantitet med felkvantitet** på *Ja*.
