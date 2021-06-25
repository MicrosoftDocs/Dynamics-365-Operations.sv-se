---
title: Förbättra prediktionsmodellen (förhandsversion)
description: I det här avsnittet beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186652"
---
# <a name="improve-the-prediction-model-preview"></a>Förbättra prediktionsmodellen (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller. Du börjar förbättra din modell på arbetsytan **Prediktioner av kundbetalning** i Microsoft Dynamics 365 Finance. Förbättringsstegen slutförs sedan i AI Builder.

## <a name="select-historical-outcomes"></a>Välj historiska resultat

Du väljer först ett eller flera av de tre möjliga resultaten för fakturor: **i tid**, **sent** och **mycket sent**. Alla tre resultat ska väljas. Om du avmarkerar något av resultaten kommer fakturorna att filtreras bort från träningsprocessen och noggrannheten i förutsägelsen försämras.

[![Bekräfta resultat](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Om din organisation bara behöver två resultat ändrar du tröskelvärdena **Sent** och **Mycket sent** till 0 (noll) dagar. På så sätt komprimerar du på ett effektivt sätt förutsägelsen till en binär status av **I tid** eller **Sent**.

## <a name="select-fields"></a>Välj fält

När du väljer fält som ska ingå i modellen måste du vara medveten om att listan innehåller alla tillgängliga fält i Microsoft Dataverse-registret som har mappats till datan i Azure-datasjön. Vissa av dessa fält bör **inte** väljas. De fält som inte ska väljas finns i en av tre kategorier:

- Fältet är obligatoriskt för Dataverse-registret, men det finns inga säkerhetskopierade data för det i datasjön.
- Fältet är ett ID och passar därför inte för maskininlärningsfunktionen.
- Fältet visar information som inte är tillgänglig under förutsägelse.

I följande avsnitt visas de fält som är tillgängliga för entiteterna faktura och kund, och där listas de fält som **inte** ska väljas för träning. Kategorin som anges för vart och ett av fälten refererar till kategorierna i föregående lista.
 
### <a name="invoice-dataverse-table"></a>Fakturaregister för Dataverse

I följande illustrationer visar de fält som är tillgängliga för fakturaregistret.

[![Tillgängliga fält för fakturaregistret](./media/available-fields.png)](./media/available-fields.png)

Följande fält ska inte väljas för träning:

- **Fakturakonto** (kategori 2)
- **Är stängt** (kategori 3) – Det här fältet används för att filtrera fakturor för träning (stängt) och förutsägelse (ej stängt).
- **Namn** (kategori 1)
- **Käll-ID** (kategori 2)
- **Källpost** (kategori 2)
- **Källtabell** (kategori 2)

### <a name="customer-dataverse-table"></a>Kundregister för Dataverse

I följande illustrationer visas de fält som är tillgängliga för kundregistret.

[![Tillgängliga fält för kundregistret](./media/related-entities.png)](./media/related-entities.png)

Följande fält ska inte väljas för träning:

- **Radens unika nyckel** (kategori 2)

## <a name="filters"></a>Filter

Filtren stöder för närvarande inte scenariot för förutsägelser av kundbetalning. Välj därför **Hoppa över detta steg** och fortsätt till sammanfattningssidan.

[![Fokusmodell med filter](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
