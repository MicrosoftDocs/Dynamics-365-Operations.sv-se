---
title: Förbättra förutsägelsemodellen
description: I den här artikeln beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: cb725f4e8f7b9dd81077f5c85059a024f3146092
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846898"
---
# <a name="improve-the-prediction-model"></a>Förbättra förutsägelsemodellen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs funktioner som du kan använda för att förbättra prestandan för förutsägelsemodeller. Du börjar förbättra din modell på arbetsytan **Prediktioner av kundbetalning** i Microsoft Dynamics 365 Finance. Förbättringsstegen slutförs sedan i AI Builder.

## <a name="select-historical-outcomes"></a>Välj historiska resultat

Du väljer först ett eller flera av de tre möjliga resultaten för fakturor: **i tid**, **sent** och **mycket sent**. Alla tre resultat ska väljas. Om du avmarkerar något av resultaten kommer fakturorna att filtreras bort från träningsprocessen och noggrannheten i förutsägelsen försämras.

[![Bekräfta resultat.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Om din organisation bara behöver två resultat ändrar du tröskelvärdena **Sent** och **Mycket sent** till 0 (noll) dagar. På så sätt komprimerar du på ett effektivt sätt förutsägelsen till en binär status av **I tid** eller **Sent**.

## <a name="select-fields"></a>Välj fält

När du väljer fält som ska ingå i modellen måste du vara medveten om att listan innehåller alla tillgängliga fält i Microsoft Dataverse-registret som har mappats till datan i Azure-datasjön. Vissa av dessa fält bör **inte** väljas. De fält som inte ska väljas finns i en av tre kategorier:

- Fältet är obligatoriskt för Dataverse-registret, men det finns inga säkerhetskopierade data för det i datasjön.
- Fältet är ett ID och passar därför inte för maskininlärningsfunktionen.
- Fältet visar information som inte är tillgänglig under förutsägelse.

I följande avsnitt visas de fält som är tillgängliga för entiteterna faktura och kund, och där listas de fält som **inte** ska väljas för träning. Kategorin som anges för vart och ett av fälten refererar till kategorierna i föregående lista.
 
### <a name="invoice-dataverse-table"></a>Fakturaregister för Dataverse

I följande illustrationer visar de fält som är tillgängliga för fakturaregistret.

[![Tillgängliga fält för fakturatabellen.](./media/available-fields.png)](./media/available-fields.png)

Följande fält ska inte väljas för träning:

- **Fakturakonto** (kategori 2)
- **Är stängt** (kategori 3) – Det här fältet används för att filtrera fakturor för träning (stängt) och förutsägelse (ej stängt).
- **Namn** (kategori 1)
- **Käll-ID** (kategori 2)
- **Källpost** (kategori 2)
- **Källtabell** (kategori 2)

### <a name="customer-dataverse-table"></a>Kundregister för Dataverse

I följande illustrationer visas de fält som är tillgängliga för kundregistret.

[![Tillgängliga fält för kundregistret.](./media/related-entities.png)](./media/related-entities.png)

Följande fält ska inte väljas för träning:

- **Radens unika nyckel** (kategori 2)

## <a name="filters"></a>Filter

Du kan filtrera fakturorna som används för utbildning genom att ställa in filterkriterier för fält på fakturan eller i kundregistren. Du kan till exempel ange ett tröskelvärde om du bara vill inkludera fakturor där summan är lika med eller högre än ett specifikt belopp. Du kan också exkludera fakturor som har associerats med kunder i en viss kundgrupp.

Mer information om hur du filtrerar data finns i [Skapa en förutsägelsemodell](/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
