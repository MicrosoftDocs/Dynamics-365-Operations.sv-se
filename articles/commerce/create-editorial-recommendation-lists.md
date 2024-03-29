---
title: Skapa granskade rekommendationer manuellt
description: Denna artikel förklarar hur inköpare manuellt kan skapa och hantera produktlistor för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e1a1b402165c5cb35696cf1cf6630770ad07508a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892688"
---
# <a name="manually-create-curated-recommendations"></a>Skapa granskade rekommendationer manuellt

[!include [banner](includes/banner.md)]

Denna artikel förklarar hur inköpare manuellt kan skapa och hantera produktrekommendationslistor för Microsoft Dynamics 365 Commerce-kunder.

Granskade listor är samlingar med enskilt innehåll som skapas och granskas av personer.  

## <a name="create-a-new-list"></a>Skapa en ny lista

Följ de här stegen om du vill skapa en granskad produktrekommendationslista.

1. Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationslistor**.
1. Välj **Ny**.
1. I fältet **List-ID** anger du ett värde.
1. I fältet **Listnamn** anger du ett värde.
    - **Listnamn** är titeln på listan som visas i avsnittet granskade listor i modulen **produktsamling**.
1. För att lägga till produkter i listan, välj **Lägg till produkter**.
1. Om du vill ändra ordningen på produkterna i listan anger du ett värde i kolumnen **visningsordning**.
    - Om två produkter har samma visningsordningsvärde kan den slutgiltiga ordningen på dessa två resultat skilja sig från backoffice.
1. Välj **Spara** för att spara listan.

## <a name="example-list"></a>Exempellista

![Exempel på granskad lista i backoffice.](./media/examplecuratedrecolist.png)

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

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]