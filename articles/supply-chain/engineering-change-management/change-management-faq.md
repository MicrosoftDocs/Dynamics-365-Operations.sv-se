---
title: Vanliga frågor och svar om konstruktionsändringshantering
description: Detta ämne innehåller vanliga frågor och svar om funktionen för konstruktionsändringshantering.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9c95c1f2342654ca2bbee57959becc85291eebbc
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187281"
---
# <a name="engineering-change-management-faq"></a>Vanliga frågor och svar om konstruktionsändringshantering

[!include [banner](../includes/banner.md)]

Detta ämne innehåller vanliga frågor och svar om funktionen för konstruktionsändringshantering.

## <a name="should-i-track-the-version-in-transactions"></a>Ska jag spåra versionen i transaktionerna?

När du skapar en kategori för konstruktionsändringar erbjuder sidan **Kategoriinformation för konstruktionsändring** ett alternativ kallat **Spåra version i transaktioner**. Vad är detta för inställning, och vad gör den?

- Om du ställer in alternativet **Spåra version i transaktioner** som *Ja* kommer fältet **Dimensionsgrupp** att filtreras till att endast visa dimensionsgrupper där versionen är en aktiv dimension.
- Om du ställer in alternativet **Spåra version i transaktioner** som *Nej* kommer fältet **Dimensionsgrupp** att filtreras till att endast visa versionsdimensionen **inte** är en aktiv dimension.

### <a name="if-you-track-the-version-in-transactions"></a>Om du spårar versionen i transaktioner

För konstruktionskategorier där du har valt en dimensionsgrupp där versionen är en aktiv dimension, spårar du versioner i transaktioner för produkter i den kategorin. Om så är fallet kommer konstruktionsprodukten att vara en produktmall, och varje version av produkten blir en produktvariant som använder versionsdimensionen. Andra dimensioner kan användas tillsammans med versionsdimensionen.

I detta fall behandlas varje konstruktionsversion som en variant i alla processer. Om du har en specifik variant i en transaktion (så att du kan avgöra vilken variant som sålts eller köpts) måste du därför hantera lager för respektive version. Huvudplaneringen planerar leverans för varje version och så vidare. Om du drar tillbaka en version från marknaden måste du manuellt justera från- och giltighetsdatumen för denna så att dessa återspeglar ändringen. Du måste också hantera lagret för att se till att du inte har oanvända versioner av artiklar i lagerställena.

Trots att det här alternativet kräver mer hanteringsinsatser rekommenderar vi det om du behöver en hög spårningsbarhet för de specifika versioner som används i respektive transaktion.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Om du inte spårar versionen i transaktioner

För konstruktionskategorier där du har valt en dimensionsgrupp där versionen **inte** är en aktiv dimension kan du **inte** spåra versioner i transaktioner för produkter i den kategorin. I detta fall kommer konstruktionsprodukten – såvida du inte använder någon annan dimension – att vara en specifik produkt. Produkten kommer fortfarande att ha en version, och du kan hantera information om specifika versioner (till exempel deras strukturlista \[BOM] och flöde), men du kan inte spåra vilken specifik version som använts i respektive transaktion. Giltighetsdatumen "Till" och "Från" anger giltigheten för respektive version.

Det här alternativet är mycket enklare att hantera eftersom du bara behöver göra nödvändiga ändringar i en ändringsorder för att kunna byta version och sedan uppdatera giltighetsdatum från och till i konstruktionsversionen. Produktionsprocesserna hämtar sedan den strukturlista och det flöde som krävs för produkten (och dess specifika version).

De flesta organisationer väljer det här alternativet eftersom det tillhandahåller hantering av versioner och ändringar, men det medför inte någon extra omkostnad för att spåra versionen i varje transaktion, i lagret eller under huvudplaneringen.

## <a name="which-fields-are-copied-from-the-released-item-template"></a>Vilka fält kopieras från den frisläppta artikelmallen?

När ett konstruktionsföretag skapar en konstruktionsprodukt, skapas den produkten som en frisläppt produkt i konstruktionsföretaget. Den frisläppta produkten som skapas baseras på den valda *frisläppta artikelmallen*. (Den frisläppta artikelmallen är i sig en befintlig frisläppt produkt.) Den frisläppta artikelmallen används också när produkten frisläpps till ett operativt företag. I varje fall definierar den frisläppta artikelmallen de flesta fältvärden för den frisläppta produkten, och dessa värden kommer från den kopplade sidan **Frisläppt produktinformation**.

I följande register visas de fält som kopieras under de här processerna.

| Snabbflik | Fält som kopieras vid produktgenerering i konstruktionsföretaget | Fält som kopieras vid frisläppning till ett operativt företag |
|---|---|---|
| **Allmänt** | Alla fält i avsnittet **Administration** | Samma fält som kopieras för konstruktionsföretaget |
| **Inköp** | Alla fält | Alla fält utom **Enhet** |
| **Sälj** | Alla fält i följande avsnitt: **Försäljningsorder**, **Administration**, **Beskattning**, **Prisuppdatering**, **Basförsäljningspris**, **Avgifter**, **Rabatter** och **Alternativa produkter** | Samtliga fält kopieras för konstruktionsföretaget, med undantag för **Enhet** |
| **Utländsk handel** | Alla fält | Alla fält |
| **Hantera lager** | Alla fält och avsnitt *utom* **Fysiska dimensioner** och **Faktisk vikt** | Samtliga fält kopieras för konstruktionsföretaget, med undantag för **Enhet** |
| **Tekniker**, **Planera**, **Hantera kostnader**, **Hantera projekt**, **Ekonomiska dimensioner** och **Lagerställe** | Alla fält | Alla fält utom **Strukturlisteenhet** |
| **Produktvarianter** | Alla fält i avsnittet **Standardproduktvariant** | Samma fält som kopieras för konstruktionsföretaget |

Förutom de fält som visas i föregående register kopieras alla standardorderinställningar från den frisläppta artikelmallen, både när produkten skapas i konstruktionsföretaget och när den frisläpps till ett operativt företag. (Om du vill visa standardorderinställningarna för en frisläppt artikelmall öppnar du relevant **Frisläppt produktinformation**-sida och väljer sedan i åtgärdsfönstret fliken **Hantera lager** och **Standardorderinställningar**.)

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Ska jag skapa en separat juridisk person för att skapa konstruktionsprodukter eller använda en befintlig juridisk person?

Dina affärsbehov bestämmer huruvida du ska skapa en ny juridisk person för att skapa konstruktionsprodukter.

Genom att skapa ett separat konstruktionsföretag kan du separera konstruktionsdata och sedan lägga till ändringar för dina lokala operativa företag efter behov. På så sätt kan du uppnå följande mål:

- Behålla en separat entitet där konstruktionsprodukterna skapas och hanteras.
- Förhindra att konstruktionsprodukter visas tillsammans med resten av de frisläppta produkterna tills de är färdiga och frisläppta.
- Tydligt skilja på data som styrs av konstruktions- och lokala data.

Å andra sidan bör du troligen använda en befintlig juridisk person som ett konstruktionsföretag om följande villkor gäller för dig:

- Du har bara en juridisk person i systemet och/eller så behöver du ingen tydlig avgränsning mellan produkter som håller på att konstrueras.
- Du vill inte kopiera vissa data, till exempel resursgrupper, resurser, funktioner och (kanske) webbplatser.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Vilken är nomenklaturen för konstruktionsversioner och varianter?

Nomenklaturen för konstruktionsprodukter och produktvarianter fungerar på följande sätt:

- För konstruktionsprodukten (det vill säga den specifika produkten om inga dimensioner används, eller produktmallen om någon dimension används) definieras nomenklaturen för nummerregel i kategorin för konstruktionsprodukt. Du kan där välja att använda en nummerserie, textkonstanter samt attributnamn och värden.
- För varje variant av en konstruktionsprodukt (om din konstruktionsprodukt är en produktmall ställs varianter in i kategorin för konstruktionsprodukt där du anger dimensionsgrupp) definieras nomenklaturen för nummerregel för respektive variant i dimensionsgruppen. I detta fall kan du använda produkt-ID:t för mallen samt dimensionsvärden och namn.
