---
title: Funktionella luckor mellan rapporterna för lagervärde och åldersfördelning och deras lagringsversioner
description: Funktionella luckor mellan rapporterna för lagervärde och åldersfördelning och deras lagringsversioner
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a72e2d32e755e137cebbc0bf7afb0bed08fb93f2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477656"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Funktionella luckor mellan rapporterna för lagervärde och åldersfördelning och deras lagringsversioner

[Rapporten lagring av lagerföråldringsrapport](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage.md) och [Lagringsrapport för lagervärde](/dynamics365/supply-chain/cost-management/inventory-value-report-storage.md) funktioner aktiverar Supply Chain Management för att visa stora volymer av lagertransaktioner. I varje fall sparas rapportresultaten för bläddring och export, till skillnad från de versioner av rapporterna som inte finns i minnet. Vissa funktioner i versionerna av de andra versionerna än de här rapporterna finns dock inte i lagringsversionerna. Följande underavsnitt innehåller en sammanfattning av skillnaderna och lösningar.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Lagringsrapporter inkluderar inte del summor, även om de är aktiverade i rapportlayouten

Delsummor kan orsaka problem när resultatet exporteras, särskilt om användarna ändrar postserien.

Du kan kontrollera delsummorna genom att exportera resultatet till Microsoft Excel. Om du vill kontrollera delsummor inom Supply Chain Management använder du [funktionshantering](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionerna *nya rutnätskontrollen* och *gruppering i rutnät*, vilket ger ett mycket mer flexibelt sätt att visa delsummor för en grupp efter kolumn. Mer information finns i [Rutnätsmöjligheter](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities.md).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Rapporten lagringsvärde för lagerhanteringskonto stöder inte redovisningskontoinformation

Du kan köra råbalansen för att få fram saldot för lagerkonton och jämföra det med rapporten **lagring för lagervärde**.
