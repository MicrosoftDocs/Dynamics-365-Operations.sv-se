---
title: Produktkategorihantering
description: "Det här avsnittet beskriver hur marknadsföringschefer kan använda produktkategorier (butik) för att hantera relationer mellan butiksprodukthierarki och information om frisläppt produkt."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a>Förbättrad produkt- och kategorihantering

[!include[banner](./includes/banner.md)]

Det här avsnittet beskriver ett bättre sätt att hantera produktkategorier (butik) och produkter i Dynamics 365 for Retail. Dessa förbättringar gör det möjligt för marknadsföringschefer att visa en gemensam struktur för produktegenskaper bland detaljhandelsprodukter och information om frisläppt produkt.

Om du vill ha mer information om hur du hanterar produktkategorier (butik), gå till **Produkthierarki (butik)** från arbetsytan **Kategori- och produkthantering** och notera förbättrad struktur för sidan **Produkthierarki (butik)**.

![Arbetsytan Kategori- och produkthantering](media/LaunchRetailProductHierarchy.png)

I tidigare versioner delades produktegenskaperna upp i **Grundläggande produktegenskaper** och **Produktegenskaper för detaljhandel**, baserat på deras tillämpningsområde. **Produktegenskaper för detaljhandel** var *global* efter tillämpningsområde vilket innebär att en given **Produktegenskap för detaljhandel**, delas lika mellan alla juridiska personer. **Grundläggande produktegenskaper** är *specifika för juridisk person*. Med andra ord kunde en viss **Grundläggande produktegenskap** variera mellan olika juridiska personer baserat på individuella affärskrav.

I den förbättrade produktkategoristrukturen separeras produktegenskaper logiskt baserat på deras tillämpbarhet inom en viss grupp i syfte att reflektera formstrukturen i informationen om den frisläppta produkten.

![Gruppering av fält baserat på deras tillämpningsområde](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person. För att göra detta, välj antingen **Visa/redigera för samtliga juridiska personer** eller **Visa/redigera för en specifik juridisk person**.

![Växla vy mellan en person och alla juridiska personer](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Växla vy mellan en person och alla juridiska personer](media/ToggleToEditForAllLegalEntities.PNG)  

Jämfört med tidigare versioner i den nya produktkategoristrukturen (butik) kan en marknadsföringschef också definiera standardvärden för ytterligare en uppsättning produktegenskaper på en enskild kategorinivå. När produkten skapas kommer dessa standardinställda produktegenskapvärden att ärvas av en produkt baserat på deras koppling till en enskild kategori från produkthierarkin (butik). Dessa ärvda produktegenskaper kan också ändras för respektive produkt så att dessa motsvarar individuella affärskrav.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Välj egenskaper i kategoriformuläret för detaljhandelsprodukt om du vill uppdatera produkter 
 
Du kan använda den här nya förbättrade strukturen för produktegenskaper för att välja vilka uppdaterade produktegenskaper som måste skickas till associerade produkter. 

![Ny utökad vy över Uppdatera produkter](media/NewUpdateProductsEnhancedView.PNG) 

Marknadsföringschefer kan modifiera dessa ärvda produktegenskaper för respektive produkt så att dessa motsvarar individuella affärskrav.


