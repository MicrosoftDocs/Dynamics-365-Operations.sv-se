---
title: Hantering och skapande av produktkategorier
description: "Detta avsnitt beskriver de förbättringar som gjorts inom hanteringsupplevelsen för produktkategorier inom detaljhandel. Dessa förbättringar gör det möjligt för marknadsföringschefer att skapa en korrelation mellan hierarkin bland detaljhandelsprodukter och frisläppt produktinformation."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: 
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 6b9afb40b68b672514c083d99efbc9bd098dd561
ms.openlocfilehash: b158ff5b277c125e0aa158c071007ed8a0f25482
ms.contentlocale: sv-se
ms.lasthandoff: 10/03/2017

---

# <a name="product-category-management-and-creation"></a>Hantering och skapande av produktkategorier

[!include[banner](./includes/banner.md)]

De förbättringar som har gjorts inom hanteringsupplevelsen för produktkategorier inom detaljhandeln gör det möjligt för marknadsföringschefer att skapa en korrelation mellan hierarkin bland detaljhandelsprodukter och frisläppt produktinformation. I arbetsytan **Kategori- och produkthantering** väljer du **Hierarki för detaljhandelsprodukt** för att öppna sidan **Ny struktur för produktkategori inom detaljhandel** om du vill visa dessa förbättringar. 

I tidigare versioner delades produktegenskaperna upp i grundläggande produktegenskaper och produktegenskaper för detaljhandel, baserat på omfattningen av deras tillämpbarhet. Produktegenskaperna inom detaljhandel var *globala*. Med andra ord delades samma värde för en viss produktegenskap av samtliga juridiska personer. Grundläggande produktegenskaper var *specifika för juridisk person*. Med andra ord kunde en viss produktegenskap variera mellan olika juridiska personer baserat på individuella affärskrav.

I och med dessa förbättringar för produktkategorier i kategorin Detaljhandelsprodukter fortsätter vi att separera olika fält. Detta sker baserat på dessas tillämpbarhet inom en viss grupp i syfte att reflektera formstrukturen i den frisläppta produktinformationen.

Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person. Välj helt enkelt **Visa/redigera för samtliga juridiska personer** eller **Visa/redigera för en specifik juridisk person** efter behov.

Marknadsföringschefer kan även definiera standardvärden för en ytterligare uppsättning produktegenskaper på individuell kategorinivå. Dessa egenskapsvärden går i arv till en produkt baserat på produktens koppling till en kategori när produkten skapas.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Välj egenskaper i kategoriformuläret för detaljhandelsprodukt om du vill uppdatera produkter

Du kan använda logiska gruppegenskaper för att välja vilka uppdaterade produktegenskaper som ska appliceras på associerade produkter.

Marknadsföringschefer kan modifiera dessa ärvda produktegenskaper för respektive produkt så att dessa motsvarar individuella affärskrav.

