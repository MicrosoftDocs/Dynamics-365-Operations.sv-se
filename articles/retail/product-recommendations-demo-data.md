---
title: Demodata för produktrekommendationer i flera kanaler
description: Det här dokumentet syftar till att ge vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872336"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Demodata för produktrekommendationer i flera kanaler

Det här dokumentet syftar till att ge vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.

Produktrekommendationer i flera kanaler innehåller en uppsättning av redaktionellt granskade eller programmässigt genererade listor över produkter i en ordnad lista. Dessa listor kan användas i flera situationer, beroende på vad som behövs i verksamheten. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt.](../commerce/product-recommendations.md)

För att produktrekommendationer på nivåer 2 och högre beräknas Dynamics-miljöer automatiskt baserat på kunddata.
Att använda demodata för produktrekommendationer inaktiverar inte någon produktrekommendationslösning som redan har etablerats i miljön och kostnader som är förknippade med användningen.

Produktrekommendationer på nivå 1 baseras bara på de statiska demodata som lagras i en csv-fil.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Aktivera demodata för produktrekommendationer i en miljö

Kunderna måste distribuera **tillägget Dynamics 365 Commerce förhandsgranskningsdemo** för respektive miljö, som automatiskt aktiverar produktrekommendationer för demodata.

## <a name="default-demo-data"></a>Standarddemodata
Varje enskild miljö innehåller en förinstallerad uppsättning med demodata för produktrekommendationer som lagras i den kommaseparerade filen **"reco_demo_data. csv"**, som finns i samma mapp som det här dokumentet på Retail Server.

Dessa data struktureras längs följande kolumner

| Kolumnnamn         | Obligatoriskt          | Beskrivning                                                                                                                                 | Möjliga värden                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| Recolist            | :heavy_check_mark: | Den specifika listtypen för produktrekommendationer som demodatapunkten ska generera.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Det specifika driftenhetsnummer som produktrekommendationer förväntas bli indelade på.                                        |                                                                              |
| Kategori            |                    |    Den kategori som den specifika listan ska returneras för. Om ingen kategori har angetts är listan endast till för navigeringshierarkin.    |                                                                              |
| SeedItemId          |                    |    För listor som kräver startvärde (RecoPeopleAlsoBuy och RecoCart) av produkten bör dessa listor innehålla ytterligare produkter för.            |                                                                              |
| ItemIds             | :heavy_check_mark: | En eller flera produkter som kommer att returneras som resultat, avgränsade med **";"**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Anpassa demodata
Kunder kan redigera standarddemodata med all produkt- och kategoriinformation som är konfigurerad i HQ. När du har uppdaterat CSV-filen kommer de produktrekommendationer som returneras till kunderna att omedelbart avspegla ändringarna.

Tillägget innehåller en datafil som heter RecoMockDataset.csv, vilket gör att kunden kan styra den datauppsättning som används för att styrka resultaten från samma modell. Filnamnet kan styras genom tilläggskonfiguration med hjälp av inställningen **ext.Recommendations.DemoFilePath**. Detta gör det möjligt för kunderna att ha flera datauppsättningar tillgängliga som kan växlas enkelt genom konfiguration.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över produktrekommendationer](../commerce/product-recommendations.md)

[Miljöplanering](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
