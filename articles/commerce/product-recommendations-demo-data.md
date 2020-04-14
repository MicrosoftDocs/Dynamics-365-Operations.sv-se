---
title: Skapa rekommendationer med demodata
description: Det här dokumentet ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.
author: bebeale
manager: AnnBe
ms.date: 03/19/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 59cb5e5c9b59ff2127149e3e47b6c30c9c938a27
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154259"
---
# <a name="create-recommendations-with-demo-data"></a>Skapa rekommendationer med demodata

[!include [banner](includes/banner.md)]

Det här dokumentet ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.

Produktrekommendationer i flera kanaler innehåller en uppsättning av redaktionellt granskade eller programmässigt genererade listor över produkter i en ordnad lista. Dessa listor kan användas i flera situationer, beroende på vad som behövs i verksamheten. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).

För att produktrekommendationer på nivåer 2 och högre beräknas Dynamics 365-miljöer automatiskt baserat på kunddata. Att använda demodata för produktrekommendationer inaktiverar inte någon produktrekommendationslösning som redan har etablerats i miljön och kostnader som är förknippade med användningen.

Produktrekommendationer på nivå 1 baseras bara på de statiska demodata som lagras i en .csv-fil.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Aktivera demodata för produktrekommendationer i en miljö
För att aktivera produktrekommendationer demonstrationsdatum måste du distribuera Dynamics 365 Commerce förhandsgranskningsdemo för respektive miljö. Då aktiveras demonstrationsdata för produktrekommendationer automatiskt.

## <a name="default-demo-data"></a>Standarddemodata
Varje enskild miljö innehåller en förinstallerad uppsättning med demodata för produktrekommendationer som lagras i den kommaseparerade filen "reco_demo_data. csv", som finns i Commerce Scale Unit.

Dessa data struktureras längs följande kolumner.

| Kolumnnamn         | Obligatoriskt          | Beskrivning                                                                                                                                 | Möjliga värden                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| Recolist            | :heavy_check_mark: | Den specifika listtypen för produktrekommendationer som demodatapunkten ska generera.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Det specifika driftenhetsnummer som produktrekommendationer förväntas bli indelade.                                        |                                                                              |
| Kategori            |                    |    Den kategori som den specifika listan ska returneras för. Om ingen kategori har angetts är listan endast till för navigeringshierarkin.    |                                                                              |
| SeedItemId          |                    |    För listor som kräver startvärde (RecoPeopleAlsoBuy och RecoCart) av produkten bör dessa listor innehålla ytterligare produkter.            |                                                                              |
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

[Aktivera ADLS i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)
