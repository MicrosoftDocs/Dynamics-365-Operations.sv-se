---
title: Produktdataentiteter
description: Det här avsnittet innehåller information om de olika entiteter som kan användas för att importera och exportera produktdata.
author: cvocph
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 83191ea3d07ec9e2ed6261ee997e06b802ee7645
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935949"
---
# <a name="product-data-entities"></a>Produktdataentiteter

[!include [banner](../includes/banner.md)]

För att importera och exportera produktdata måste du använda dataenheter. Följande tabell innehåller information om de produktrelaterade dataentiteterna och beskriver syftet med var och en.

| Enhet | Programobjektträdet (AOT) namn (typ) | Anteckningar |
|--------|-------------------------------------------|-------|
| Produkter version2 | EcoResProductV2Entity | Den här entiteten används för att importera och exportera delade produkter - distinkta produkter och produktmallar. Det möjliggör uppdateringar. Det stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för Open Data Protocol (OData). |
| Frisläppta produkter V2 | EcoResReleasedProductV2Entity | Den här entiteten används för att importera och exportera släppta produkter - distinkta produkter och produktmallar. Det möjliggör uppdateringar. Det kräver att den delade produkten redan har skapats. När en ny utgiven produkt importeras, uppstår en version av den delade produkten. Det finns också separata entiteter som kan användas för att importera och exportera frisläppt produktmallar och släppt distinkta varianter. Den här entiteten stöder inte set-baserade SQL-åtgärder eller ta bort åtgärder. Den är aktiverad för OData. |
| Frisläppt produktgenerering version2 | EcoResReleasedProductCreationV2Entity | Den här entiteten används för att importera delade produkter och frisläppta produkter i ett steg. Även om det stöder export, rekommenderas inte att använda, eftersom syftet med entiteten är produkt skapande. Det stöder inte uppdateringar. Den stöder en begränsad uppsättning fält (fält som är tillgängliga i dialogrutan Skapa produkt). Det stöder inte inställningsbaserade SQL-åtgärder. Det exponeras inte via OData. |
| Produktvarianter | EcoResProductVariantEntity | Den här entiteten används för att importera och exportera delade produktvarianter. Det möjliggör uppdateringar. Det kräver att dimensionsvärden redan skapas. Integrations nyckeln är produktmall plus produktdimensioner. Entiteten stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för OData. Den stöder borttagningsåtgärder. Den kan inte utökas genom tillägg av nya produktdimensioner. |
| Produktvarianter per produktnummer-ID | EcoResProductNumberIdentifiedProductVariantEntity | Den här entiteten används för att importera och exportera delade produktvarianter. Det möjliggör uppdateringar. Det kräver att dimensionsvärden redan skapas. Integrationsnyckeln är produktnumret (medan integrations nyckeln för entiteten **Produktvarianter** är produktmall plus produktdimensioner). |
| Frisläppta produktvarianter | EcoResReleasedProductVariantEntity | Den här entiteten används för att importera och exportera frisläppta produktvarianter. Det möjliggör uppdateringar. Det kräver att den delade produktvarianter redan har skapats. När en ny utgiven produktvarianter importeras, uppstår en version av den delade produktvarianten. Entiteten stöder inte inställningsbaserade SQL-åtgärder. Den är aktiverad för OData. Även om det stöder ta bort åtgärder, som använder för närvarande orsakar skadade data på grund av ett fel i den aktuella plattformen. Entiteten kan inte utökas genom tillägg av nya produktdimensioner. |
| Frisläppta produktvarianter per produktnummer-ID | EcoResProductNumberIdentifiedReleasedProductVariantEntity | Denna entitet liknar entiteten **Frisläppta produktvarianter** men integrationsnyckeln är produktnumret istället för produktmall plus produktdimensioner. Den kan inte utökas genom tillägg av nya produktdimensioner. |
| Säljbara frisläppta produkter | EcoResSellableReleasedProductEntity | Den här entiteten används för att exportera endast säljbara produkter. Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder. Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppta produkter**. |
| Frisläppta specifika produkter V2 | EcoResDistinctProductV2Entity | Den här entiteten används för att exportera specifika produkter. Dessa specifika produkter kan vara produkters undertypprodukt och produktvarianter. |
| Släppta produktmallar V2 | EcoResProductMasterV2Entity | Den här entiteten används för att importera och exportera produktmallar. Den är inte aktiverad för datahantering. |
| Artikel - streckkod | EcoResProductBarcodeEntity | Den här entiteten används för att exportera produkter och streckkoder. |
| Produktens livscykeltillstånd | EcoResProductLifecycleSateEntity | Den här entiteten används för att importera och exportera de olika produktlivscykeltillstånd som kan tilldelas en produkt. |

> [!NOTE]
> Du kan använda dataentiteten **frisläppta produkter V2** för att importera produkter till systemet endast om den delade produkten redan har skapats. Annars, om du vill importera produkter till systemet, måste du använda **produktskapande** dataentitet.
