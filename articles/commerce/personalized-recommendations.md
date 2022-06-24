---
title: Aktivera anpassade produktrekommendationer
description: I denna artikel beskrivs hur du gör anpassade produktrekommendationer tillgängliga för kunder i Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2be5e59d51e183863da9c82d4ff733e830b8b69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864874"
---
# <a name="enable-personalized-recommendations"></a>Aktivera anpassade rekommendationer

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du gör anpassade produktrekommendationer tillgängliga för kunder i Microsoft Dynamics 365 Commerce.

I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga. På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i POS. När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.

## <a name="personalization-prerequisites"></a>Anpassningskrav

Innan du gör personliga produktrekommendationer tillgängliga för kunder bör du tänka på att produktrekommendationer bara stöds för användare av Commerce som har migrerat deras lagring till Azure Data Lake Store. Innan kunderna får egna produktrekommendationer måste återförsäljare [aktivera produktrekommendationer](enable-product-recommendations.md).

> [!NOTE]
> Genom att aktivera produktrekommendationer aktiverar du också anpassningar. Om du inaktiverar anpassningar stänger du emellertid inte av de andra typerna av produktrekommendationer.

Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).

## <a name="turn-on-personalization"></a>Aktivera anpassning

Så här aktiverar du anpassning.

1. Sök efter **funktionshantering** i Commerce Headquarters.
1. Välj **alla** om du vill visa en lista över tillgängliga funktioner. 
1. Ange **rekommendationer** i sökrutan.
1. Välj funktionen **Anpassade produktrekommendationer**.
1. I egenskapsfönstret **Anpassade produktrekommendationer** välj **Aktivera nu**.

![Aktivera anpassning.](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> När du aktiverar anpassningar startas processen för generering av anpassade produktrekommendationslistor. Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i POS.

## <a name="personalized-lists"></a>Anpassade listor

Förutom att göra anpassningar av befintliga datorgenererade listor, kan du med hjälp av rekommendationstjänsten anpassa produktidentifieringsupplevelsen både online och i POS.

När anpassningen är aktiverad kan återförsäljare visa köparna anpassade "Val för dig"-listor online eller "rekommenderade kunder" i kassaterminaler. Dessutom kan återförsäljare lägga till anpassningar i befintliga produktrekommendationslistor och tillhandahålla allmän dataskyddsförordning (GDPR) avanmälningsupplevelse för autentiserade användare. Om du inaktiverar anpassning inaktiveras även dessa funktioner.

### <a name="online-picks-for-you-lists"></a>"Val för dig"-listor online

En Val för dig-lista är en lista med maskininlärning med artificiell intelligens (AI-ML) som visar en autentiserad användare en anpassad lista över föreslagna produkter. Den här listan är baserad på användarens inköpshistorik i flera kanaler. Anpassade rekommendationer uppdateras dynamiskt när användaren gör fler inköp. Den här typen av lista har också stöd för kategorifiltrering, så att återförsäljare kan visa de bästa valen baserat på navigationshierarkier.

Innan listan "Val för dig"-listan kan visas på alla näthandelssidor måste följande användarkrav uppfyllas:

- Användarna måste vara inloggade. Anonyma användare ser inte anpassade rekommendationer.
- Användarna måste ha minst ett inköp på sitt konto.
- Användarna måste välja att få anpassade rekommendationer.

I bilden nedan visas ett exempel på en lista över "val för dig"-lista på en nätbutiks sida.

!["Val för dig"-lista online.](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>"Rekommenderad för kunder"-listor i POS

För att förbättra sin klientelingupplevelse kan återförsäljare anpassa befintliga sidor med kundinformation genom att lägga till en snabb "Rekommenderad för kund"-lista.

I bilden nedan visas ett exempel på en lista över "rekommenderad för kund"-lista i en kassaterminal.

!["Rekommenderas för kunder"-lista i kassan.](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Använd anpassningar för befintliga rekommendationslistor

Återförsäljare kan göra anpassningar av befintliga rekommendationslistor, t.ex. "nytt", "trend", "bästsäljare", "människor gillar också" och "köps ofta ihop". När anpassningar tillämpas på befintliga listor, tas de objekt som en inloggad användare tidigare köpt bort från dessa listor. För både anonyma användare och användare som väljer att få anpassade rekommendationer visas standardversionerna av de befintliga listorna. Därför behöver inte detaljister manuellt upprätthålla separata sidupplevelser.

En inloggad användare har till exempel redan köpt den svarta klockan och de bruna arbetsstövlar som visas i listan "trend – standard" i följande bild. Därför kommer användarna att se nya produkter i stället för dessa produkter, som de visas i listan "trend – anpassa".

![Använda anpassning.](./media/applypersonalization.png)

Om du vill använda anpassningar för en befintlig rekommendations lista i webbplatsskaparen för Commerce följer du stegen nedan.

1. Öppna en befintlig sidan i webbplatsskaparen som innehåller en modul för produktinsamling.
1. I vänster navigeringsfönstret, välj produktinsamlingsmodul.
1. I höger navigeringsfönstret, under **Produkter** väljer du listan.
1. I dialogrutan **Välj konfiguration för produktlista**, under **Typ**, välj listtyp.
1. Markera kryssrutan **Använd anpassning** och välj sedan **OK**.

    ![Använda anpassningar i en trendlista.](./media/ApplyPersonalizationToTrending.PNG)

1. Spara sidan, slutför redigeringen av den och publicera den. När sidan har publicerats kommer de inloggade användarna att se anpassade trendlistor.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
