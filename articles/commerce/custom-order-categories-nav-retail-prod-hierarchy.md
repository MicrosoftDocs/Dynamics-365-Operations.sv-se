---
title: Ändra sorteringsordning för marknadsföringsenheter
description: I denna aritkel beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter i Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265847"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Ändra sorteringsordning för marknadsföringsenheter


[!Include [banner](includes/banner.md)]

Återförsäljare betraktar produktidentifiering som ett primärt verktyg för kundinteraktion i alla kanaler. Det finns flera funktioner som hjälper kunderna att enkelt upptäcka produkter. Kunder kan till exempel bläddra bland kategorier, söka och filtrera.

I denna artikel beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter. Det innehåller även information om hur du ändrar sorteringsordning.

## <a name="overview"></a>Översikt

I Handel stämmer sorteringen av olika marknadsföringsrelaterade enheter efter befintliga kundscenarier och kräver inte längre tillägg från implementeringspartner.

I Handel version 10.0.5 och tidigare var sorteringsordningen för kategorier i navigeringsvyn alfabetisk. Med den nuvarande anpassade sorteringsordningen kan du konfigurera sorteringsordningen för olika marknadsföringsrelaterade enheter för alla slutanvändarklienter. Dessa klienter inkluderar huvudkontor (HQ) och kundtjänster.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Konfigurera visningsordningen för kategorier i produkthierarki

Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.

1. Gå till **Retail and Commerce \> Produkter och kategorier \> Produkthierarki och handel**.
2. Klicka på **Redigera kategorihierarki**.
3. Klicka på **Redigera**.
4. Expandera **ALLA \> Actionsporter** i trädet.
5. Expandera **ALLA \> Lagsporter** i trädet.
6. Ange ett tal i fältet **Visningsordning**. (Talet kan vara negativt.)
7. Upprepa steg 4 till och med 6 för alla ytterligare kategorier som du vill ändra ordningen för.

Visningsordningen för kanalensnavigeringshierarkin kommer att avspeglas i huvudkontoret för handelsprodukthierarkin och frisläppta produkter efter kategori.

![Anpassad produkthierarki sorterad med negativa värden.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produkter som frisläppts efter kategori med anpassad sortering baserad på produkthierarki.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Konfigurera visningsordningen för kategorier i kanalnavigeringshierarkin

Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.

1. Gå till **Retail and Commerce \> Produkter och kategorier \> Navigeringskategorier för kanal**.
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

Visningsordningen för kanalnavigeringshierarkin visas i huvudkontor, katalog och kanalerna.

![Anpassat sorterad kanalnavigeringshierarki.](./media/ChannelNavCustomSorted.png)

![Anpassat sorterad katalognavigeringshierarki baserad på kanalnavigeringshierarkin.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Kassa med anpassade, sorterade kategorier.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Som standard är funktionen **Aktivera visningsordning för marknadsföringsenheter** inaktiverad. Använd [funktionshantering](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera den. När du har aktiverat funktionen kör du CDX-jobbet **Global konfiguration -1110** från distributionsschemat.
> Om kategorierna inte uppdateras i kassan måste du återaktivera enheten. Kategoriinformation hämtas när enhetsaktivering inträffar, så enheten kan behöva tillbakavisa kategoriinformationen med uppdaterade visningsordning. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
