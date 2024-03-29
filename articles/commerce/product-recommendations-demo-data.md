---
title: Skapa rekommendationer med demodata
description: Denna artikel ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en miljö av typen "Nivå-1, enskild miljö" med hjälp av i förväg ifyllda, anpassningsbara demodata.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7e3df414b3c16c28b6f5ca04f765d91c1312ada4
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9459979"
---
# <a name="create-recommendations-with-demo-data"></a>Skapa rekommendationer med demodata

[!include [banner](includes/banner.md)]

Denna artikel ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en miljö av typen "Nivå-1, enskild miljö" med hjälp av i förväg ifyllda, anpassningsbara demodata.

Produktrekommendationer i flera kanaler innehåller en uppsättning av redaktionellt granskade eller programmässigt genererade listor över produkter i en ordnad lista. Dessa listor kan användas i flera situationer, beroende på vad som behövs i verksamheten. Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).

För att produktrekommendationer på nivåer 2 och högre beräknas Dynamics 365-miljöer automatiskt baserat på kunddata. Att använda demodata för produktrekommendationer inaktiverar inte någon produktrekommendationslösning som redan har etablerats i miljön och kostnader som är förknippade med användningen.

Produktrekommendationer på nivå 1 baseras bara på de statiska demodata som lagras i en .csv-fil.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Aktivera demodata för produktrekommendationer i en miljö
För att aktivera produktrekommendationer demonstrationsdatum måste du distribuera Dynamics 365 Commerce förhandsgranskningsdemo för respektive miljö. Då aktiveras demonstrationsdata för produktrekommendationer automatiskt.

## <a name="default-demo-data"></a>Standarddemodata
Varje enskild miljö innehåller en förinstallerad uppsättning med demodata för produktrekommendationer som lagras i den kommaseparerade filen "reco_demo_data. csv", som finns i Commerce Scale Unit.

Dessa data struktureras längs följande kolumner.

| Kolumnnamn         | Obligatoriskt          | beskrivning                                                                                                                                 | Möjliga värden                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| Recolist            | :heavy_check_mark: | Den specifika listtypen för produktrekommendationer som demodatapunkten ska generera.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li><li>RecoPicks</li><li>RecoSimilarVisual</li><li>RecoSimilarTextual</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Det specifika driftenhetsnummer som produktrekommendationer förväntas bli indelade.                                        |                                                                              |
| Kategori            |                    |    Den kategori som den specifika listan ska returneras för. Om ingen kategori har angetts är listan endast till för navigeringshierarkin.    |                                                                              |
| SeedItemId          |                    |    För listor som kräver startvärde (RecoPeopleAlsoBuy och RecoCart) av produkten bör dessa listor innehålla ytterligare produkter.            |                                                                              |
| CustomerId          |                    |    För listor som kräver ett kund-ID (RecoPicks).  Standardvärdet "0" gäller för alla kunder.          |                                                                              |
| ItemIds             | :heavy_check_mark: | En eller flera produkter som kommer att returneras som resultat, avgränsade med ";".                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Anpassa demodata
Du kan redigera standarddemodata med all produkt- och kategoriinformation som är konfigurerad i HQ. När du har uppdaterat .csv-filen kommer de produktrekommendationer som returneras till kunderna att omedelbart avspegla ändringarna.

Tillägget innehåller en datafil som heter RecoMockDataset.csv, vilket gör att du kan styra den datauppsättning som används för att styrka resultaten från samma modell. Filnamnet kan styras genom tilläggskonfiguration med hjälp av inställningen **ext.Recommendations.DemoFilePath**. Detta gör det möjligt för dig att ha flera datauppsättningar tillgängliga som kan växlas enkelt genom konfiguration.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Lägga till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
