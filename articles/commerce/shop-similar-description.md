---
title: Aktivera rekommendationer för "sök efter liknande beskrivning"
description: I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna för "leta efter liknande beskrivning" i Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b6b397b1f21e3dfcdb4a2b7fe67ddb541d090a97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234399"
---
# <a name="enable-shop-similar-description-recommendations"></a>Aktivera rekommendationer för "köp liknande beskrivning"

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna för "leta efter liknande beskrivning" i Microsoft Dynamics 365 Commerce.

Med hjälp av rekommendationsfunktionen för "sök liknande beskrivning" i Dynamics 365 Commerce används artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för produkter med beskrivningar som liknar det som kunden söker. Genom att göra rekommendationer av typen "sök efter liknande beskrivning" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare göra det lättare för kunder att enkelt hitta vad de vill ha.

Rekommendationsfunktionerna för "sök efter liknande beskrivning" använder produktens namn och beskrivningen av sagda produkter för att hitta och rekommendera likartade produkter i en återförsäljares produktkatalog.

Rekommendationerna för "köp liknande produkter" finns i såväl kassa- (POS) som näthandelsupplevelserna.

## <a name="example-scenarios"></a>Exempelscenarier

Följande exempelscenarier visar de typer av rekommendationer som funktionen "sök efter liknande beskrivning" kan ge:

- En kund ser ett par hornbågade glasögon i retro-stil och får en uppsättning rekommendationer för andra glasögon med liknande design, inom återförsäljarens bransch.
- En kund använder rekommendationer för "sök efter liknande beskrivning" för att upptäcka kaffesmaker som liknar en han/hon nyligen inköpt från återförsäljaren.

## <a name="set-up-shop-similar-description-recommendations"></a>Konfigurera rekommendationer för "sök efter liknande beskrivning"

Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Förutsättningar

Innan rekommendationer för "sök efter liknande beskrivning" kan visas för kunderna måste du uppfylla följande förutsättningar:

- [Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce-administration.
- Kontrollera att mediaservern stöder HTTPS-anrop.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Aktivera rekommendationsfunktionen för "sök efter liknande beskrivning"

Gör så här om du vill aktivera rekommendationsfunktionen "sök efter liknande beskrivning" i Commerce-administrationen.

1. I arbetsytan **Funktionshantering**, i listan över tillgängliga funktioner, söker du efter och väljer **Sök efter liknande beskrivning**.
1. Välj **Aktivera** i höger fönster.

> [!NOTE]
> När du aktiverar funktionen börjar systemet att generera listor med produktrekommendationer. Det kan krävas upp till en dag för att dessa listor ska bli tillgängliga och synliga online och i kassan.
>
> Om du inaktiverar funktionen påverkas inte andra typer av produktrekommendationer. Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Lägg till en Sök efter liknande beskrivning-knapp på produktinformationssidor

När du har aktiverat rekommendationsfunktionen "sök efter liknande beskrivning" i Commerce-administrationen kan du lägga till en **Sök efter liknande beskrivning**-knapp i köprutan på valfri produktinformationssida (PDP). En kund som väljer den här knappen tas till en särskild **Sök efter liknande beskrivning**-sida som visar visuellt likartade produkter. Kunden kan därefter använda väljare för att filtrera produkterna ytterligare.

Lägg till en **Sök efter liknande beskrivning**-knapp på en PDP med hjälp av Commerce-webbplatsbyggaren genom att följa följande steg.

1. Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.
1. I vänster navigeringsfönstret, välj modul för köpruta.
1. I det högra fönstret väljer du kryssrutan **Aktivera länken Sök efter liknande beskrivning**.
1. Välj **Spara**.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. När sidan har publicerats innehåller PDP en knapp för **Sök efter liknande beskrivning**.

Bilden nedan visar kryssrutan **Aktivera länken Sök efter liknande beskrivning** och knappen **Sök efter liknande beskrivning** på en exempel-PDP i webbplatsbyggaren.

![Aktivera kryssrutan Sök efter liknande beskrivningslänk och knappen Sök efter liknande beskrivning på en PDP i webbplatsbyggaren](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]