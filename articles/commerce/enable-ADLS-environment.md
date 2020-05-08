---
title: Aktivera ADLS i en Dynamics 365 Commerce-miljö
description: I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba428765babb9ca7566da7a457368959b1c29083
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259758"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>Aktivera ADLS i en Dynamics 365 Commerce-miljö

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.

## <a name="overview"></a>Översikt

I Dynamics 365 Commerce-lösningen spåras all produktinformation och all transaktionsinformation i miljöns enhetsarkiv. Om du vill göra dessa data tillgängliga för andra Dynamics 365-tjänster, t.ex. dataanalyser, affärsstrategier och anpassade rekommendationer, måste du ansluta miljön till en kundägd Azure Data Lake Storage Gen 2 (ADLS)-lösning.

Eftersom ADLS konfigureras i en miljö, speglas alla nödvändiga data från enhetsarkivet samtidigt som de skyddas och kontrolleras av kunden.

Om produktrekommendationer eller anpassade rekommendationer också har aktiverats i miljön ger produktrekommendationerna stack åtkomst till den dedikerade mappen i ADLS för att hämta kundens data och beräkna rekommendationer baserat på den.

## <a name="prerequisites"></a>Förutsättningar

Kunder måste ha ADLS konfigurerat i en Azure-prenumeration som de äger. Det här avsnittet behandlar inte köp av en Azure-prenumeration eller inställningen av ett ADLS-aktiverat lagringskonto.

Mer information om ADLS finns i [officiell ADLS-dokumentation](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Konfigurationssteg

I det här avsnittet beskrivs de konfigurationssteg som krävs för att aktivera ADLS i en miljö när det gäller produktrekommendationer.
En mer ingående översikt över de steg som krävs för att aktivera ADLS finns i [Gör entitetsbutik tillgänglig som Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-adls-in-the-environment"></a>Aktivera ADLS i miljö

1. Logga in på miljöns backoffice-Portal.
1. Sök efter **Systemparametrar** och navigera till fliken **Dataanslutningar**. 
1. Ange **Aktivera Data Lake-integrering** till **Ja**.
1. Ange **Indroppning uppdatering av Data Lake** till **Ja**.
1. Ange sedan följande obligatorisk information:
    1. **Program-ID** // **Programhemlighet** // **DNS-namn** - Behövs för att ansluta till KeyVault där ADLS-hemligheten lagras.
    1. **Hemligtnamn** - Det hemliga namnet lagrat i KeyVault och används för att autentisera med ADLS.
1. Spara ändringarna i det övre vänstra hörnet på sidan.

I bilden nedan visas ett exempel på ADLS-konfiguration.

![Exempel på ADLS-konfiguration](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>Testa ADLS-anslutningen

1. Testa anslutningen till KeyVault med hjälp länk **Testa Azure Key Vault**.
1. Testa anslutningen till ett ADLS med hjälp länk **Testa Azure Storage**.

> [!NOTE]
> Om testerna misslyckas kontrollerar du att all KeyVault-information som lagts till ovan är korrekt och försöker igen.

När anslutningstesten har lyckats måste du aktivera automatisk uppdatering för enhetsarkivet.

Aktivera automatisk uppdatering för enhetsarkivet genom att följa stegen nedan.

1. Sök efter **enhetsarkiv**.
1. Navigera till listan till vänster till enhet **RetailSales** och välj **redigera**.
1. Se till **Automatisk uppdatering är aktiverat** är inställd på **Ja**, välj **Uppdatera** och välj **Spara**.

I bilden nedan visas ett exempel på ett enhetslagring med automatisk uppdatering aktiverat.

![Exempel på enhetslagring med automatisk uppdatering aktiverad](./media/exampleADLSConfig2.png)

ADLS har nu konfigurerats för miljön. 

Om det inte redan är klart följer du stegen för [aktivera produktrekommendationer och anpassning](enable-product-recommendations.md) för miljön.

## <a name="additional-resources"></a>Ytterligare resurser

[Gör enhetslagring tillgängligt som en Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)