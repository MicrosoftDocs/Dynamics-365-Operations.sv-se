---
title: Produktdataentiteter
description: Denna artikel innehåller information om de olika entiteter som kan användas för att importera och exportera produktdata.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: e37e0928d8633a81d3a736527f2545cd61055a78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859210"
---
# <a name="product-data-entities"></a>Produktdataentiteter

[!include [banner](../includes/banner.md)]

För att importera och exportera produktdata måste du använda dataenheter. Följande tabell innehåller information om de produktrelaterade dataentiteterna och beskriver syftet med var och en.

| Enhet | Programobjektträdet (AOT) namn (typ) | Anteckningar |
|--------|-------------------------------------------|-------|
| Produkter version2 | `EcoResProductV2Entity` | Den här entiteten används för att importera och exportera delade produkter - distinkta produkter och produktmallar. Det möjliggör uppdateringar. Det stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för Open Data Protocol (OData). |
| Frisläppta produkter V2 | `EcoResReleasedProductV2Entity` | Den här entiteten används för att importera och exportera släppta produkter - distinkta produkter och produktmallar. Det möjliggör uppdateringar. Det kräver att den delade produkten redan har skapats. När en ny utgiven produkt importeras, uppstår en version av den delade produkten. Det finns också separata entiteter som kan användas för att importera och exportera frisläppt produktmallar och släppt distinkta varianter. Den här entiteten stöder inte set-baserade SQL-åtgärder eller ta bort åtgärder. Den är aktiverad för OData. |
| Frisläppt produktgenerering version2 | `EcoResReleasedProductCreationV2Entity` | Den här entiteten används för att importera delade produkter och frisläppta produkter i ett steg. Även om det stöder export, rekommenderas inte att använda, eftersom syftet med entiteten är produkt skapande. Det stöder inte uppdateringar. Den stöder en begränsad uppsättning fält (fält som är tillgängliga i dialogrutan Skapa produkt). Det stöder inte inställningsbaserade SQL-åtgärder. Det exponeras inte via OData. |
| Produktvarianter | `EcoResProductVariantEntity` | Den här entiteten används för att importera och exportera delade produktvarianter. Det möjliggör uppdateringar. Det kräver att dimensionsvärden redan skapas. Integreringsnyckeln är produktmall plus produktdimensioner. Entiteten stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för OData. Den stöder borttagningsåtgärder. Den kan inte utökas genom tillägg av nya produktdimensioner. |
| Produktvarianter per produktnummer-ID | `EcoResProductNumberIdentifiedProductVariantEntity` | Den här entiteten används för att importera och exportera delade produktvarianter. Det möjliggör uppdateringar. Det kräver att dimensionsvärden redan skapas. Integreringsnyckeln är produktnumret (medan integreringsnyckeln för entiteten **Produktvarianter** är produktmall plus produktdimensioner). |
| Frisläppta produktvarianter | `EcoResReleasedProductVariantEntity` | Den här entiteten används för att importera och exportera frisläppta produktvarianter. Det möjliggör uppdateringar. Det kräver att den delade produktvarianter redan har skapats. När en ny utgiven produktvarianter importeras, uppstår en version av den delade produktvarianten. Entiteten stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för OData. Även om det stöder ta bort åtgärder, som använder för närvarande orsakar skadade data på grund av ett fel i den aktuella plattformen. Entiteten kan inte utökas genom tillägg av nya produktdimensioner. |
| Frisläppta produktvarianter per produktnummer-ID | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | Denna entitet liknar entiteten **Frisläppta produktvarianter** men integreringsnyckeln är produktnumret istället för produktmall plus produktdimensioner. Den kan inte utökas genom tillägg av nya produktdimensioner. |
| Säljbara frisläppta produkter | `EcoResSellableReleasedProductEntity` | Den här entiteten används för att exportera endast säljbara produkter. Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder. Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppta produkter**. |
| Frisläppta specifika produkter V2 | `EcoResDistinctProductV2Entity` | Den här entiteten används för att exportera specifika produkter. Dessa specifika produkter kan vara produkters undertypprodukt och produktvarianter. |
| Släppta produktmallar V2 | `EcoResProductMasterV2Entity` | Den här entiteten används för att importera och exportera produktmallar. Den är inte aktiverad för datahantering. |
| Artikel - streckkod | `EcoResProductBarcodeEntityV3` | Den här entiteten används för att exportera produkter och streckkoder. Den här entiteten tillåter inte ändringsspårning, uppdateringar eller borttagningar. Om du vill använda ändringsspårning, uppdateringar eller borttagningar på streckkoder använder du enheten **Artikel – association till streckkod**. |
| Artikel-streckkod-association | `EcoResProductBarcodeAssociationEntity` | Den här entiteten används för att exportera produkter och streckkoder. Du kan spåra, uppdatera och ta bort ändringar. Om du vill använda entiteten måste *Artikel - streckkodsförbättringar* aktiveras i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Dess enhetsnyckel är `AssociationID` som skapar kopplingen mellans treckkoden och produkten. Om du vill lägga till stöd för den här nyckeln fylls tabellen `InventitemBarcodeAssociation` i med befintliga artikelstreckkodsdata när du aktiverar funktionen. Registret fylls i med hjälp av ett batchjobb, och om streckkodstabellen har ett stort antal poster kan det ta lång tid att köra batchjobbet. Därför rekommenderar vi att du planerar att aktivera funktionen (och därmed köra batch-jobbet) vid en tidpunkt som passar ditt företags schema. |
| Produktens livscykeltillstånd | `EcoResProductLifecycleSateEntity` | Den här entiteten används för att importera och exportera de olika produktlivscykeltillstånd som kan tilldelas en produkt. |

> [!NOTE]
> Du kan använda dataentiteten **frisläppta produkter V2** för att importera produkter till systemet endast om den delade produkten redan har skapats. Annars, om du vill importera produkter till systemet, måste du använda **produktskapande** dataentitet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]