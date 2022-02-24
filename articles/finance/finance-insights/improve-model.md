---
title: Förbättra prediktionsmodellen (förhandsversion)
description: I det här avsnittet beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646089"
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

När du väljer fält som ska ingå i modellen måste du vara medveten om att listan innehåller alla tillgängliga fält i Common Data Service-entiteten som har mappats till data i Azure-datasjön. Vissa av dessa fält bör **inte** väljas. De fält som inte ska väljas finns i en av tre kategorier:

- Fältet är obligatoriskt för Common Data Service-entiteten, men det finns inga säkerhetskopierade data för det i datasjön.
- Fältet är ett ID och passar därför inte för maskininlärningsfunktionen.
- Fältet visar information som inte är tillgänglig under förutsägelse.

I följande avsnitt visas de fält som är tillgängliga för entiteterna faktura och kund, och där listas de fält som **inte** ska väljas för träning. Kategorin som anges för vart och ett av fälten refererar till kategorierna i föregående lista.
 
### <a name="invoice-common-data-model-entity"></a>Common Data Model-entiteten Faktura

I följande illustrationer visar de fält som är tillgängliga för fakturaentiteten.

[![Tillgängliga fält för entiteten faktura](./media/available-fields.png)](./media/available-fields.png)

Följande fält ska inte väljas för träning:

- **Fakturakonto** (kategori 2)
- **Är stängt** (kategori 3) – Det här fältet används för att filtrera fakturor för träning (stängt) och förutsägelse (ej stängt).
- **Namn** (kategori 1)
- **Käll-ID** (kategori 2)
- **Källpost** (kategori 2)
- **Källtabell** (kategori 2)

### <a name="customer-common-data-model-entity"></a>Common Data Model-entiteten Kund

I följande illustrationer visar de fält som är tillgängliga för kundentiteten.

[![Tillgängliga fält för entiteten kund](./media/related-entities.png)](./media/related-entities.png)

Följande fält ska inte väljas för träning:

- **Radens unika nyckel** (kategori 2)

## <a name="filters"></a>Filter

Filtren stöder för närvarande inte scenariot för förutsägelser av kundbetalning. Välj därför **Hoppa över detta steg** och fortsätt till sammanfattningssidan.

[![Fokusmodell med filter](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

#### <a name="privacy-notice"></a>Sekretesspolicy
Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.
