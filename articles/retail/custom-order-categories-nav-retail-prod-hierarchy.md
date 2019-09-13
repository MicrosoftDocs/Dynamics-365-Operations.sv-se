---
title: Ändra sorteringsordning för marknadsföringsenheter
description: I det här avsnittet beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter i Microsoft Dynamics 365 for Retail.
author: ashishharchwani
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2be3c1198ac6fff851be1bead2f0995202f1f0e7
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2019
ms.locfileid: "1866171"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Ändra sorteringsordning för marknadsföringsenheter

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Återförsäljare betraktar produktidentifiering som ett primärt verktyg för kundinteraktion i alla detaljhandelskanaler. Olika funktioner kan hjälpa kunder att enkelt hitta produkter. De kan till exempel bläddra bland kategorier, söka och filtrera.

I det här avsnittet beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter. Det innehåller även information om hur du ändrar sorteringsordning.

## <a name="overview"></a>Översikt

Stödet för sortering av olika marknadsföringsrelaterade entiteter har förbättrats. Det här stödet är nu bättre justerat med befintliga kundscenarier som tidigare krävde tillägg från implementeringspartners.

I tidigare versioner av Microsoft Dynamics 365 for Retail version 10.0.5 var sorteringsordningen för kategorier i navigeringsvyn alfabetisk. Med den nya anpassade sorteringsordningen kan du konfigurera sorteringsordningen för olika marknadsföringsrelaterade enheter för alla slutanvändarklienter. Dessa klienter inkluderar huvudkontor (HQ) och kundtjänster.

## <a name="configure-the-display-order-for-categories-in-the-retail-product-hierarchy"></a>Konfigurera visningsordningen för kategorier i butiksprodukthierarki

Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.

1. Gå till **Butik \> Produkter och kategorier \> Produkthierarki (butik)**.
2. Klicka på **Redigera kategorihierarki**.
3. Klicka på **Redigera**.
4. Expandera **ALLA \> Actionsporter** i trädet.
5. Expandera **ALLA \> Lagsporter** i trädet.
6. Ange ett tal i fältet **Visningsordning**. (Talet kan vara negativt.)
7. Upprepa steg 4 till och med 6 för alla ytterligare kategorier som du vill ändra ordningen för.

Visningsordningen för kanalensnavigeringshierarkin kommer att avspeglas i huvudkontoret för butiksprodukthierarkin och frisläppta produkter efter kategori.

![Produkthierarki (butik) anpassat sorterad med negativa värden](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produkter som frisläppts efter kategori sorteras baserat på produkthierarki (butik)](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Konfigurera visningsordningen för kategorier i kanalnavigeringshierarkin

Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.

1. Gå till **Butik \> Produkter och kategorier \> Navigeringskategorier för kanal**.
2. Välj hierarkin **Modenavigering** i listan.
3. Klicka på **Redigera kategorihierarki**.
4. Klicka på **Redigera**.
5. Välj **Mode \> Damkläder \> Damskor** i trädet.
6. Ange ett tal i fältet **Visningsordning**.
7. Välj **Mode \> Damkläder \> Överdelar** i trädet.

    På samma sätt kan du definiera sorteringsordningen för underkategorierna.

8. Välj **Mode \> Herrkläder \> Lediga skjortor** i trädet.
9. Ange ett tal i fältet **Visningsordning**.
10. Välj **Mode \> Herrkläder \> Jackor** i trädet.
11. Ange ett tal i fältet **Visningsordning**.
12. Upprepa för alla ytterligare kategorier som du vill ändra ordningen för.

Visningsordningen för kanalnavigeringshierarkin visas i huvudkontor, katalog och detaljhandelskanalerna.

![Anpassat sorterad kanalnavigeringshierarki](./media/ChannelNavCustomSorted.png)

![Anpassat sorterad katalognavigeringshierarki baserat på kanalnavigeringshierarkin](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Kassa med anpassade, sorterade kategorier](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Funktionen för anpassad sorteringsordning är avstängd som standard. Mer information om hur du aktiverar den här funktionen och andra funktioner finns i [Funktionshantering](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).
