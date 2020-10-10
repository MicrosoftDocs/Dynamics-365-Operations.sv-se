---
title: Aktivera rekommendationer för "köp liknande produkter"
description: I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: da957850072e233a41a042d5857f81ddbf178f7a
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818384"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Aktivera rekommendationer för "köp liknande produkter"

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Med hjälp av rekommendationerna "köp liknande produkter" i Dynamics 365 Commerce används funktionerna hos artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för visuellt likartade produkter till kunder. Genom att göra rekommendationer av typen "köp liknande produkter" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare öka kundtillfredsställelsen genom att hjälpa kunderna att enkelt hitta vad de vill ha.

Funktionerna för "köp liknande produkter" rekommendationer använder produktbilder av produktvarianter för att hitta och rekommendera visuellt likartade produkter i en återförsäljares produktkatalog. 

Rekommendationerna för "köp liknande produkter" i både kassa- (POS) och näthandelsupplevelser.

### <a name="example-scenarios"></a>Exempelscenarier

- En kund visar en svartrandig tröja och får en rekommendation om liknande tröja i rött. Kunden väljer den rekommenderade produkten i stället för den ursprungligen visade produkten och får rekommendationer för liknande produkter i rött. 
- En kund använder rekommendationer om "köp liknande produkter" för att upptäcka matchande örhängen för en ring som kunden är intresserad av att köpa.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Aktivera rekommendationerna "köp liknande produkter" i Commerce-administration

Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Gen2.

### <a name="prerequisites"></a>Förutsättningar

Innan återförsäljare kan börja visa rekommendationer från "köp liknande produkter", finns det två steg:

- [Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce-administration.
- Kontrollera att mediaservern stöder HTTPS-anrop.

För att rekommendationsmotorn ska få åtkomst till produktbilderna måste återförsäljare generera produktens URL:er. För att generera URL:er i Commerce-administration, följ de här stegen.

1. Gå till **Produktbilder**.
1. I åtgärdsfönstret, välj **Definiera mediemall**.
1. I egenskaper **Definiera mediemall** under **Media-URL:er**, välj **Generera URL:er**.

> [!NOTE]
> När du aktiverar rekommendationsfunktionen "köp liknande produkter", börjar processen att generera listor över produktrekommendationer. Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i kassan.

Gör så här om du vill aktivera rekommendationer funktionen "köp liknande produkter" i Commerce-administration.

1. Gå till **Funktionshantering**.
1. I listan över tillgängliga funktioner söker du efter och väljer **köp liknande produkter**.
1. I det högra fönstret väljer du **Aktivera** för att aktivera tjänsten.

I följande bild visas funktionen **köp liknande produkter** på sidan **Funktionshantering** i Commerce-administration.

![Funktionen handla liknande utseende på sidan funktionshantering i Commerce-administration](./media/enableshopsimilarlooks.png)

När föregående uppgifter har slutförts förbättras kassaterminaler automatiskt med en panel för **köp liknande produkter**. Genom att välja **Se mer** användare av kassaterminal kan tas till en dedikerad sida för "köp liknande produkter" som kan filtreras ytterligare.

> [!NOTE]
> Om du inaktiverar funktionen "köp liknande produkter" rekommenderar vi att inga andra typer av produktrekommendationer påverkas. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Lägga till en knapp för köp liknande produkter på sidan med produktinformation genom att använda Commerce-webbplatsskaparen

När du har aktiverat rekommendationerna "köp liknande produkter" i Commerce-administration kan du välja ett alternativ i Commerce-webbplatsskaparen för att lägga till knappar **köp liknande produkter** i köprutan på valfri produktinformationssida (PDP). En kund som väljer den här knappen tas till en särskild sida "köp liknande produkter" som returnerar visuellt likartade produkter. Kunden kan använda väljare för att filtrera produkterna ytterligare.

Lägg till en knapp för **Köp liknande produkter** till en PDP genom att använda Commerce-webbplatsskaparen, följ dessa steg.

1. Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.
1. I vänster navigeringsfönstret, välj modul för köpruta.
1. I det högra navigeringsfönstret markerar du kryssrutan **Aktivera länken köp liknande produkter**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. När sidan har publicerats innehåller PDP en knapp för **köp liknande produkter**.

Bilden nedan visar kryssrutan **Aktivera länken köp liknande produkter** och knappen **köp liknande produkter** på en exempel PDP i webbplatsskaparen.

![Aktivera länken köp liknande produkter och knappen köp liknande produkter på en PDP i webbplatsskaparen.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)
