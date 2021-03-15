---
title: Synkronisera produktklassificeringar i Dynamics 365 Commerce
description: I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7318d53535a93352425f811ec90572e65aeb696
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006295"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>Synkronisera produktklassificeringar i Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Om du vill använda produktvärderingar i flera kanaler, t.ex vid POS och i kundtjänst, måste produktvärderingar från tjänsten omdömen och recensioner importeras till databas för handelskanal. När produktvärderingar görs tillgängliga i flera kanaler kan de hjälpa kunderna indirekt under sina interaktioner med säljare.

Detta avsnitt beskriver följande uppgifter:

1. Konfigurera **synkroniseringsjobb för produktklassificering** som ett batchjobb för att synkronisera produktklassificeringar från **tjänsten omdömen och recensioner**.
1. Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.
1. Göra produkt produktvärderingar tillgängliga i POS.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Konfigurera ett batchjobb för att synkronisera produktvärderingar

> [!IMPORTANT]
> Innan du börjar ska du kontrollera att version 10.0.6 eller senare av Dynamics 365 Commerce är installerad.

### <a name="initialize-the-commerce-scheduler"></a>Initiera schemaläggare för handel

För att initiera schemaläggare för handel, följ dessa steg.

1. Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Initiiera schemaläggare för handel**. Du kan också söka efter "initiera schemaläggare för handel".
1. I dialogrutan **Initiera schemaläggare för handel** se till att alternativet **ta bort befintligt konfiguration** anges till **nej** och klicka sedan på **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Kontrollera deljobbet RetailProductRating

Så här kontrollerar du att deljobb **RetailProductRating** finns:

1. Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Deljobb i schemaläggare**. Du kan också söka efter "Deljobb i schemaläggare".
1. I deljobbslistan, sök efter deljobbet **RetailProductRating**.

Följande illustration visar ett exempel på deljobbdetaljer i handel.

![Detaljer för deljobbet RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Om du inte hittar deljobbet **RetailProductRating** kanske du redan har kört jobbet **synkronisera produktklassificering** och **1040 CDX**-jobb innan du initierade schemaläggare för handel. I det här fallet följer du stegen nedan för att köra jobbet **fullständig datasynkronisering**.

> 1. Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Kanaldatabas**. Du kan också söka efter "Kanaldatabas".
> 1. Välj den kanaldatabas som ska synkroniseras.
> 1. I åtgärdsfönstret, välj **Fullständig datasynkronisering**.
> 1. I dialogrutan **Välj ett distributionsschema**, välj **1040 – produkter** och sedan **OK**.
> 1. Upprepa stegen i föregående procedur för att kontrollera att **RetailProductRating**-deljobbet har skapats.

### <a name="import-product-ratings"></a>Importera produktvärdering

Om du vill importera produktvärderingar till handel från klassificering och recensioner följer du stegen nedan.

1. Gå till **Butik och handel \> Inställningar av administrationen \> Schemaläggare för handel \> Synkronisera produktklassificeringsjobb**. Du kan också söka efter "synkronisera produktklassificeringsjobb".
1. I dialogrutan **Dra produktvärderingar** på snabbfliken **Kör i bakgrunden** välj **Återkommande**.
1. I dialogrutan **Definiera upprepning** ange ett mönster för återkommande. (Det föreslagna värdet är två timmar.) Schemalägg inte en återkommande tid som är mindre än en timme.
1. Välj **OK**.
1. Ange alternativet **Batchbearbetning** till **Ja**. Den här inställningen säkerställer att du kan granska loggarna och verifiera status för batchjobbet.
1. Klicka på **OK** för att schemalägga batchjobbet.

Följande illustration visar ett exempel på konfiguration av batchjobb i handel.

![Konfiguration av batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.

För att kontrollera att batchjobbet **Synkronisera produktklassificeringar** lyckas, följ dessa steg.

1. Gå till **Butik och handel \> Systemadministratör \> Frågor \> Batchjobb** eller om du använder en lagerhållningsenhet (SKU) för endast handel **Butik och handel \> Frågor och rapporter \> Batchjobb**. Du kan alternativt söka efter batchjobb.
1. Om du vill visa information om batchjobbet går du till kolumnen **jobbeskrivning** och söker efter en beskrivning som innehåller "Visa produktklassificeringar" i batchjobbets lista.
1. Välj jobb-ID om du vill visa detaljer för batchjobbet, t.ex. tidsplanerat startdatum/-tid och upprepningstext.

I följande illustration visas ett exempel på detaljerna i batchjobbet i Commerce när batchjobbet är tidsplanerat för körning med två timmars intervall.

![Detaljer för batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Göra produkt produktvärderingar tillgängliga i POS.

Lösningen för klassificeringar och recensioner i Dynamics 365 Commerce är en flerkanalslösning. Produktklassificeringar visas dock inte som standard i POS. För att hjälpa kunder i butikerna se värderingar och recensioner när de får hjälp av säljarna måste du aktivera produktvärderingar i POS.

Så här aktiverar du produktrecensioner i POS.

1. Gå till **Butik och handel \> Inställning av Commerce \> Parametrar \> Commerceparametrar**. Du kan också söka efter "Handelparametrar".
1. På fliken **konfigurationsparametrar** välj **Ny**.
1. Ange ett namn som till exempel **RatingsAndReviews.EnableProductRatingsForRetailStores** och ange värdet till **sant**.
1. Välj **Spara**.
1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**. Du kan också söka efter "fördelningsplan".
1. I jobblistan, välj **1110** (**Global konfiguration**) och välj sedan **Kör nu**.
1. När jobbet har körts kontrollerar du att produktklassificeringen nu visas i POS.

Följande illustration visar ett exempel på konfigurationen av parametrarna för Commerce som ska aktiveras för produktvärderingar i POS.

![Konfiguration av handelsparametrarna för produktvärderingar i POS](media/rnr-hq-enable-ratings-in-pos.png)

Följande illustration visar ett exempel på produktvärderingar i POS.

![Produktvärderingar i POS](media/rnr-pos-catalog-ratings.png)

Följande illustration visar ett exempel på produktvärderingar kundtjänstkanaler.

![Produktvärderingar i en kundtjänstkanal](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]