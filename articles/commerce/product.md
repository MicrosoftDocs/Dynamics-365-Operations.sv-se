---
title: Lägg till produktrekommendationer i POS
description: I denna artikel beskrivs användning av produktrekommendationer för en kassaenhet (POS).
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460067"
---
# <a name="add-product-recommendations-on-pos"></a>Lägg till produktrekommendationer i POS

[!include [banner](includes/banner.md)]

I grund och botten är produktrekommendationerna ett omvandlande affärsprogram som sträcker sig över alla handelsytor för att skapa omfattande, spännande och skräddarsydda produktidentifieringsupplevelser. Om du vill använda den här funktionen i POS följer du stegen i [hur du lägger till rekommendationer i kassaenheterna.](add-recommendations-control-pos-screen.md) 

Mer information om funktioner för produktrekommendationer finns i [produktrekommendationer – översikt.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenarier

Produktrekommendationer har aktiverats för följande kassascenarier. De är tillgängliga i Cloud POS och Modern POS (MPOS).

1. På sidan **Produktdetaljer**:

    - Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationstjänsten ytterligare artiklar som kan köpas tillsammans. Beroende på tilläggen för tjänsten kan återförsäljare visa rekommendationer för **Köp liknande produkter** och **Köp liknande-beskrivning** för produkter, förutom personliga rekommendationer för användare som har en tidigare köphistorik.

    [![Rekommendationer på sidan produktinformation.](./media/proddetails.png)](./media/proddetails.png)

2. På sidan **Transaktion**:

    - I rekommendationsmotorn föreslås objekt baserat på hela listan över artiklar i korgen som ofta köps ihop.

    > [!NOTE]
    > För att kunna visa rekommendationer på sidan **Transaktion** måste återförsäljaren uppdatera skärmlayouten i Dynamics 365 Commerce. Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**.

    [![Rekommendationer på sidan Transaktion.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Konfigurera Commerce för att aktivera rekommendationer i kassa 

Om du vill ställa in produktrekommendationer bekräftar du att du har slutfört reserveringsprocessen för Commerce produktrekommendationer genom att följa stegen i [Aktivera produktrekommendationer](../commerce/enable-product-recommendations.md). Som standard visas rekommendationer på sidan **Produktinformation** och **Kundinformation** efter att du har slutfört provisioneringsstegen och informationen har avse någon kontroll. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Lägg till rekommendationer på transaktionsskärmen

1. Om du vill lägga till rekommendationer på transaktionsskärmen följer du stegen i [Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md).
1. Kör kanalkonfigurationsjobb för att återspegla ändringar som gjordes i kassaskärmlayout designern **1070** i Commerce headquarters.

> [!NOTE] 
> Om du vill aktivera kassarekommendationer genom att använda filen RecoMock kommaseparerade värden (CSV), måste du distribuera CSV-filen till Microsoft Dynamics Lifecycle Services (LCS) tillgångsbibliotek innan du konfigurerar layouthanteraren. Om du använder RecoMock CSV-filen behöver du inte aktivera rekommendationer. CSV-filen är bara tillgänglig för demonstration. Det rekommenderas för kunder eller lösningen som vill se ut som rekommendationslistor för demonstration utan att behöva köpa en enhet för lagerhållning (SKU).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
