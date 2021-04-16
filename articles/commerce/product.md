---
title: Lägg till produktrekommendationer i POS
description: I det här avsnittet beskrivs användning av produktrekommendationer för en försäljningsenhet (POS).
author: bebeale
ms.date: 05/26/2020
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
ms.openlocfilehash: a1a25e3d5bc1cc5c1c7509186451fdfef50dd6cf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792349"
---
# <a name="add-product-recommendations-on-pos"></a>Lägg till produktrekommendationer i POS

[!include [banner](includes/banner.md)]

I grund och botten är produktrekommendationerna ett omvandlande affärsprogram som sträcker sig över alla handelsytor för att skapa omfattande, spännande och skräddarsydda produktidentifieringsupplevelser. Om du vill använda den här funktionen i POS följer du stegen i [hur du lägger till rekommendationer i kassaenheterna.](add-recommendations-control-pos-screen.md) 

Mer information om funktioner för produktrekommendationer finns i [produktrekommendationer – översikt.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenarier

Produktrekommendationer har aktiverats för följande kassascenarier. De är tillgängliga i Cloud POS och Modern POS (MPOS).

1. På sidan **Produktdetaljer**:

    - Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationstjänsten ytterligare artiklar som kan köpas tillsammans.

    [![Rekommendationer på sidan produktinformation](./media/proddetails.png)](./media/proddetails.png)

2. På sidan **Transaktion**:

    - I rekommendationsmotorn föreslås objekt baserat på hela listan över artiklar i korgen som ofta köps ihop.

    > [!NOTE]
    > För att kunna visa rekommendationer på sidan **Transaktion** måste återförsäljaren uppdatera skärmlayouten i Dynamics 365 Commerce. Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**.

    [![Rekommendationer på sidan Transaktion](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Konfigurera Commerce för att aktivera rekommendationer i kassa

Så här ställs produktrekommendationer in:

1. Se till att tjänsten har uppdaterats till **10.0.6 version.**
2. Följ instruktionerna om hur du [aktiverar produktrekommendationer](../commerce/enable-product-recommendations.md) för ditt företag.
3. Tillval; Om du vill visa rekommendationer på transaktionsskärmen, gå då till **Skärmlayout**, välj din skärmlayout, starta **Designer för skrämlayout**, och släpp sedan kontrollen **Rekommendationer** där så behövs.
4. Gå till **Handelsparametrar**, välj **Maskininlärning** och välj **Ja** under **Aktivera kassarekommendationer**.
5. Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på POS. Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Felsök problem där du redan produktrekommendationer aktiverade

- Gå till **Handelsparametrar** \> **Rekommendationslistor** \> **Inaktivera produktrekommendationer** och kör **Globalt konfigurationsjobb \[9999\]**. 
- Om du har lagt till **rekommendationskontroll** till din transaktionsskärm med **Layoutdesigner för skärm**, ta även bort den.
- Om du har fler frågor läser du [Vanliga frågor om produktrekommendationer](../commerce/faq-recommendations.md) för mer information.

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