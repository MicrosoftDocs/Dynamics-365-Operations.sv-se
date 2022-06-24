---
title: Hantera produktkategorier och produkter
description: Denna artikel beskriver hur marknadsföringschefer kan använda produktkategorier för att hantera relationer mellan Commerce-produkthierarki och information om frisläppt produkt.
author: ashishmsft
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0871475e0910e0a46544c56083b505ff647fd6a9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878593"
---
# <a name="manage-product-categories-and-products"></a>Hantera produktkategorier och produkter

[!include [banner](./includes/banner.md)]

Denna artikel beskriver ett bättre sätt att hantera produktkategorier och produkter i Dynamics 365 Commerce. Dessa förbättringar gör det möjligt för marknadsföringschefer att visa en struktur som delas mellan produktegenskaper bland produkter och information om frisläppt produkt.

För mer information om hur du hanterar produktkategorier på arbetsytan **Kategori- och produkthantering**, välj panelen **Produkthierarki (handel)**.

Lägg märke till den förbättrade struktur för sidan **Produkthierarki (handel)**. I tidigare versioner av appen delades produktegenskaperna upp i *Grundläggande produktegenskaper* och *Produktegenskaper för detaljhandel*, baserat på deras tillämpningsområde. Produktegenskaper (butik) är *globala* i sitt tillämpningsområde. Med andra ord delades samma värde för en viss produktegenskap av samtliga juridiska personer. Däremot är grundläggande produktegenskaper specifika *juridisk person*. Med andra ord kunde en viss grundläggande produktegenskap variera mellan olika juridiska personer beroende på individuella affärskrav för varje juridisk person.

I den förbättrade produktkategoristrukturen separeras produktegenskaper logiskt baserat på deras tillämpbarhet inom en viss grupp i syfte att reflektera strukturen i informationen om den frisläppta produkten.

![Fältgruppering baserat på egenskapens tillämpningsområde.](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person.

Om du vill hantera egenskaper i alla juridiska personer, välj **Visa för alla juridiska personer** (eller **Redigera för alla juridiska personer**).

![Visa/redigera för alla juridiska personer.](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Om du vill hantera egenskaper för en viss juridisk person **Visa för en viss juridisk person** (eller **Redigera för en viss juridisk person**).

![Visa/redigera för en viss juridisk person.](media/ToggleToEditForAllLegalEntities.PNG)

Dessutom, i den förbättrade produktkategoristrukturen kan en marknadsföringschef nu också definiera standardvärden för ytterligare en uppsättning produktegenskaper på en enskild kategorinivå. Sedan när produkter skapas ärver de standardvärden för sina produktegenskaper baserat på kopplingen av de här egenskaperna med en enskild kategori från produkthierarkin. Dessa ärvda produktegenskaper kan också ändras för respektive produkt så att dessa motsvarar individuella affärskrav.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Välja egenskaper på sidan Produkthierarki (handel) om du vill uppdatera produkter

Du kan använda den här nya förbättrade strukturen för produktegenskaper för att välja vilka uppdaterade produktegenskaper som måste skickas till associerade produkter. På sidan **Produkthierarki (handel)** på åtgärdsfönstret, välj **Kategori** och välj sedan **Uppdatera produkter** för att öppna dialogrutan **Uppdatera produkter**.

![Dialogrutan Uppdatera produkter.](media/NewUpdateProductsEnhancedView.PNG)


[!INCLUDE[footer-include](../includes/footer-banner.md)]