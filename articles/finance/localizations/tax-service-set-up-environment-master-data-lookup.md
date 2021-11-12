---
title: Ställa in en miljö för att söka efter huvuddata
description: I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.
author: kai-cloud
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 901f8bcb0220355866952b68e92bc2dd906bb430
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700414"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Ställa in en miljö för att söka efter huvuddata

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.

1. Konfigurera Microsoft Power Platform-integrering i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Microsoft Power Platform-integrering – tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). När du har slutfört det här steget visas namnet på Microsoft Power Platform-miljön i avsnittet **Power Platform-integration**.
2. Gå till [Microsoft Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/environments) och välj miljönamnet. Miljöns URL är inte angiven.
3. Konfigurera Dynamics 365 Finance och Dataverse. Mer information finns i [Skaffa lösningen virtuell entitet](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) samt i [Autentisering och auktorisering](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Ställ in följande entiteter: Mer information finns i [Aktivera Microsoft Dataverse virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. Ange Regulatory Configuration Service (RCS). Öppna till arbetsytan **Funktionshantering** och aktivera följande funktioner:

    - Dataverse-datakällor för elektronisk rapportering
    - Stöd för Dataverse-datakällor för skattetjänst
    - Globaliseringsfunktioner

6. Logga in på RCS med hjälp av ett admin-konto för klientorganisation.
7. Gå till **Elektronisk rapportering** > **Anslutna program**. 
8. Om du vill lägga till en post, välj **Ny** och ange följande fältinformation. 

    - Ange sedan ett namn i fältet **Namn**.
    - I fältet **Typ** väljer du **Dataverse**.
    - I fältet **Program** anger du din Dataverse-URL.
    - I fältet **Klientorganisation** anger du din klientorganisation.
    - I fältet **Anpassad URL** anger du din Dataverse-URL och tillägger "/api/data/v9.1".

9. Välj **Kontrollera anslutning** och slutför anslutningsprocessen. 

    [![Knappen Kontrollera anslutning.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Gå till **Elektronisk rapportering** > **Skattekonfigurationer** och importera skattekonfigurationer från [Skattekonfigurationer](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Sidan Skattekonfigurationer, modellträd för skattedata.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Gå till **Modellmappning för beskattningsbart dokument** eller **Modellmappning för Dataverse** om du använder en Microsoft-konfiguration, och i fältet **Anslutet program** väljer du sedan den post som du skapade i steg 7.
12. Ange **Standard för modellmappning** som **Ja**.

    [![Modellmappningssida.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
