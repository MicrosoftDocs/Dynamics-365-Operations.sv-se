---
title: Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö
description: Det här ämnet innehåller instruktioner om hur du ansluter en Azure Data Lake Storage Gen 2-lösning till Dynamics 365 Commerce-miljöns enhetslagring. Detta är ett nödvändigt steg innan du aktiverar produktrekommendationer.
author: bebeale
ms.date: 08/31/2020
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
ms.openlocfilehash: c96c29a4d9639b02e6a60ad938b7e06f7d500c68
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466302"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö

[!include [banner](includes/banner.md)]

Det här ämnet innehåller instruktioner om hur du ansluter en Azure Data Lake Storage Gen 2-lösning till Dynamics 365 Commerce-miljöns enhetslagring. Detta är ett nödvändigt steg innan du aktiverar produktrekommendationer.

I Dynamics 365 Commerce-lösningen aggregeras de data som behövs för att beräkna rekommendationer, produkter och transaktioner i miljöns enhetslagring. Om du vill göra dessa data tillgängliga för andra Dynamics 365-tjänster, t.ex. dataanalyser, affärsstrategier och anpassade rekommendationer, måste du ansluta miljön till en kundägd Azure Data Lake Storage Gen 2-lösning.

När stegen ovan har slutförts återspeglas alla kunddata i miljöns enhetslagring automatiskt i kundens Azure Data Lake Storage Gen 2-lösning. När rekommendationer aktiveras via arbetsytan för Funktionshantering i Commerce Headquarters får rekommendationsstacken åtkomst till samma Azure Data Lake Storage Gen 2-lösning.

Under hela processen förblir kundernas data skyddade och under deras kontroll.

## <a name="prerequisites"></a>Förutsättningar

En Dynamics 365 Commerce-miljös enhetslagring måste vara anslutet till ett Azure Data Lake Gen Storage Gen2-konto och tillhörande tjänster.

Mer information om Azure Data Lake Storage Gen 2 och hur du konfigurerar det finns i [Officiell Azure Data Lake Storage Gen2-dokumentation](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Konfigurationssteg

I det här avsnittet beskrivs de konfigurationssteg som krävs för att aktivera Azure Data Lake Storage Gen2 i en miljö när det gäller produktrekommendationer.
En mer ingående översikt över de steg som krävs för att aktivera Azure Data Lake Storage Gen2 finns i [Gör enhetslagring tillgänglig som Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Aktivera Azure Data Lake Storage i miljö

1. Logga in på miljöns backoffice-Portal.
1. Sök efter **Systemparametrar** och navigera till fliken **Dataanslutningar**. 
1. Ange **Aktivera Data Lake-integrering** till **Ja**.
1. Ange sedan följande obligatorisk information:
    1. **Program-ID** // **Programhemlighet** // **DNS-namn** – Behövs för att ansluta till KeyVault där Azure Data Lake Storage-hemligheten lagras.
    1. **Hemligt namn** – Det hemliga namnet lagrat i KeyVault och används för att autentisera med Azure Data Lake Storage.
1. Spara ändringarna i det övre vänstra hörnet på sidan.

I bilden nedan visas ett exempel på Azure Data Lake Storage-konfiguration.

![Exempel på Azure Data Lake Storage-konfiguration.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Testa Azure Data Lake Storage-anslutningen

1. Testa anslutningen till KeyVault med hjälp länk **Testa Azure Key Vault**.
1. Testa anslutningen till ett Azure Data Lake Storage med hjälp länk **Testa Azure Storage**.

> [!NOTE]
> Om någon av testerna ovan misslyckas bekräftar du att all KeyVault-information som lagts till ovan är korrekt och försöker igen.

När anslutningstesten har lyckats måste du aktivera automatisk uppdatering för enhetsarkivet.

Aktivera automatisk uppdatering för enhetsarkivet genom att följa stegen nedan.

1. Sök efter **enhetsarkiv**.
1. Navigera till listan till vänster till enhet **RetailSales** och välj **redigera**.
1. Se till **Automatisk uppdatering är aktiverat** är inställd på **Ja**, välj **Uppdatera** och välj **Spara**.

I bilden nedan visas ett exempel på ett enhetslagring med automatisk uppdatering aktiverat.

![Exempel på enhetslagring med automatisk uppdatering aktiverad.](./media/exampleADLSConfig2.png)

Azure Data Lake Storage har nu konfigurerats för miljön. 

Om det inte redan är klart följer du stegen för [aktivera produktrekommendationer och anpassning](enable-product-recommendations.md) för miljön.

## <a name="additional-resources"></a>Ytterligare resurser

[Gör enhetslagring tillgängligt som en Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Lägga till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
