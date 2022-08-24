---
title: Aktivera rekommendationer för "köp liknande produkter"
description: I denna artikel beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: 26eb436d889ac81cde730daca9b44d1deeda6c74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282061"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Aktivera rekommendationer för "köp liknande produkter"

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.

Med hjälp av rekommendationerna "köp liknande produkter" i Dynamics 365 Commerce används funktionerna hos artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för visuellt likartade produkter till kunder. Genom att göra rekommendationer av typen "köp liknande produkter" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare öka kundtillfredsställelsen genom att hjälpa kunderna att enkelt hitta vad de vill ha.

Funktionerna för "köp liknande produkter" rekommendationer använder produktbilder av produktvarianter för att hitta och rekommendera visuellt likartade produkter i en återförsäljares produktkatalog. 

Rekommendationerna för "köp liknande produkter" i både kassa- (POS) och näthandelsupplevelser.

### <a name="example-scenarios"></a>Exempelscenarier

- En kund visar en svartrandig tröja och får en rekommendation om liknande tröja i rött. Kunden väljer den rekommenderade produkten i stället för den ursprungligen visade produkten och får rekommendationer för liknande produkter i rött. 
- En kund använder rekommendationer om "köp liknande produkter" för att upptäcka matchande örhängen för en ring som kunden är intresserad av att köpa.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Aktivera rekommendationerna "köp liknande produkter" i Commerce headquarters

Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Gen2.

### <a name="prerequisites"></a>Förutsättningar

Innan återförsäljare kan börja visa rekommendationer från "köp liknande produkter", finns det två steg:

- [Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce headquarters.
- Kontrollera att mediaservern stöder HTTPS-anrop.

För att rekommendationsmotorn ska få åtkomst till produktbilderna måste återförsäljare generera produktens URL:er. För att generera URL:er i Commerce headquarters, följ de här stegen.

1. Gå till **Produktbilder**.
1. I åtgärdsfönstret, välj **Definiera mediemall**.
1. I egenskaper **Definiera mediemall** under **Media-URL:er**, välj **Generera URL:er**.

> [!NOTE]
> När du aktiverar rekommendationsfunktionen "köp liknande produkter", börjar processen att generera listor över produktrekommendationer. Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i POS.

Gör så här om du vill aktivera rekommendationer funktionen "köp liknande produkter" i Commerce headquarters.

1. Gå till **Funktionshantering**.
1. I listan över tillgängliga funktioner söker du efter och väljer **köp liknande produkter**.
1. I det högra fönstret väljer du **Aktivera** för att aktivera tjänsten.

I följande bild visas funktionen **köp liknande produkter** på sidan **Funktionshantering** i Commerce headquarters.

![Funktionen Köp liknande produkter på sidan Funktionshantering i Commerce headquarters.](./media/enableshopsimilarlooks.png)

När föregående uppgifter har slutförts förbättras kassaterminaler automatiskt med en panel för **köp liknande produkter**. Genom att välja **Se mer** användare av kassaterminal kan tas till en dedikerad sida för "köp liknande produkter" som kan filtreras ytterligare.

> [!NOTE]
> Om du inaktiverar funktionen "köp liknande produkter" rekommenderar vi att inga andra typer av produktrekommendationer påverkas. Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Lägga till en knapp för köp liknande produkter på sidan med produktinformation genom att använda Commerce-webbplatsbyggaren

När du har aktiverat rekommendationerna "köp liknande produkter" i Commerce headquarters kan du välja ett alternativ i Commerce-webbplatsbyggaren för att lägga till knappar **köp liknande produkter** i köprutan på valfri produktinformationssida (PDP). En kund som väljer den här knappen tas till en särskild sida "köp liknande produkter" som returnerar visuellt likartade produkter. Kunden kan använda väljare för att filtrera produkterna ytterligare.

Lägg till en knapp för **Köp liknande produkter** till en PDP genom att använda Commerce-webbplatsbyggaren, följ dessa steg.

1. Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.
1. I vänster navigeringsfönstret, välj modul för köpruta.
1. I det högra navigeringsfönstret markerar du kryssrutan **Aktivera länken köp liknande produkter**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. När sidan har publicerats innehåller PDP en knapp för **köp liknande produkter**.

Bilden nedan visar kryssrutan **Aktivera länken köp liknande produkter** och knappen **köp liknande produkter** på en exempel PDP i webbplatsskaparen.

![Aktivera kryssrutan för länken Sök liknande produkter och knappen Köp liknande produkter på en PDP i webbplatsskaparen.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
