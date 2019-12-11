---
title: Synkronisera produktklassificeringar i Dynamics 365 Retail
description: I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698175"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a>Synkronisera produktklassificeringar i Dynamics 365 Retail

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Retail.

## <a name="overview"></a>Översikt

Om du vill använda produktvärderingar i flera kanaler, t.ex vid kassan (POS) och i kundtjänst, måste produktvärderingar från tjänsten omdömen och recensioner importeras till databas för butikskanal. När produktvärderingar görs tillgängliga i flera kanaler kan de hjälpa kunderna indirekt under sina interaktioner med säljare.

Detta avsnitt beskriver följande uppgifter:

1. Konfigurera ett batchjobb i butik för import av produktvärderingar.
1. Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.
1. Göra produkt produktvärderingar tillgängliga i kassan.

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a>Konfigurera ett batchjobb i butik för import av produktvärderingar

> [!IMPORTANT]
> Innan du börjar ska du kontrollera att version 10.0.6 eller senare av Retail är installerad.

### <a name="initialize-the-retail-scheduler"></a>Initiera schemaläggare för butik

För att initiera schemaläggare för butik, följ dessa steg.

1. Gå till **butik \> inställningar av administrationen \> butik schemaläggare \> Initiera butik schemaläggare**. Du kan också söka efter "initiera butik schemaläggare".
1. I dialogrutan **Initiera butik schemaläggare** se till att alternativet **ta bort befintligt konfiguration** anges till **nej** och klicka sedan på **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Kontrollera deljobbet RetailProductRating

Så här kontrollerar du att deljobb **RetailProductRating** finns:

1. Gå till **butik \> inställningar av administrationen \> butik schemaläggare \> deljobb i schemaläggare**. Du kan också söka efter "Deljobb i schemaläggare".
1. I deljobbslistan, sök efter deljobbet **RetailProductRating**.

Följande illustration visar ett exempel på deljobbdetaljer i butik.

![Detaljer för deljobbet RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Om du inte hittar deljobbet **RetailProductRating** kanske du redan har kört jobbet **synkronisera produktklassificering** och **1040 CDX**-jobb innan du initierade butik schemaläggare. I det här fallet följer du stegen nedan för att köra jobbet **fullständig datasynkronisering**.
>
> 1. Gå till **butik \> inställningar av administrationen \> butik schemaläggare \> kanaldatabas**. Du kan också söka efter "Kanaldatabas".
> 1. Välj den kanaldatabas som ska synkroniseras.
> 1. I åtgärdsfönstret, välj **Fullständig datasynkronisering**.
> 1. I dialogrutan **Välj ett distributionsschema**, välj **1040 - produkter** och sedan **OK**.
> 1. Upprepa stegen i föregående procedur för att kontrollera att **RetailProductRating**-deljobbet har skapats.

### <a name="import-product-ratings"></a>Importera produktvärdering

Om du vill importera produktvärderingar till butik från klassificering och recensioner följer du stegen nedan.

1. Gå till **butik \> inställningar av administrationen \> butik schemaläggare \> Synkronisera produktklassificeringsjobb**. Du kan också söka efter "synkronisera produktklassificeringsjobb".
1. I dialogrutan **Dra produktvärderingar** på snabbfliken **Kör i bakgrunden** välj **Återkommande**.
1. I dialogrutan **Definiera upprepning** ange ett mönster för återkommande. (Det föreslagna värdet är två timmar.) Schemalägg inte en återkommande tid som är mindre än en timme.
1. Välj **OK**.
1. Ange alternativet **Batchbearbetning** till **Ja**. Den här inställningen säkerställer att du kan granska loggarna och verifiera status för batchjobbet.
1. Klicka på **OK** för att schemalägga batchjobbet.

Följande illustration visar ett exempel på konfiguration av batchjobb i butik.

![Konfiguration av batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.

För att kontrollera att batchjobbet **Synkronisera produktklassificeringar** lyckas, följ dessa steg.

1. Gå till **Butik \> Systemadministratör \> Frågor \> Batchjobb** eller om du använder en lagerhållningsenhet (SKU) för endast butik **Butik \> Frågor och rapporter \> Batchjobb**. Du kan alternativt söka efter batchjobb.
1. Om du vill visa information om batchjobbet går du till kolumnen **jobbeskrivning** och söker efter en beskrivning som innehåller "Visa produktklassificeringar" i batchjobbets lista.
1. Välj jobb-ID om du vill visa detaljer för batchjobbet, t.ex. tidsplanerat startdatum/-tid och upprepningstext.

I följande illustration visas ett exempel på detaljerna i batchjobbet när batchjobbet är tidsplanerat för körning med två timmars intervall.

![Detaljer för batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Göra produkt produktvärderingar tillgängliga i kassan.

Lösningen för klassificeringar och recensioner i Dynamics 365 Commerce är en flerkanalslösning. Produktklassificeringar visas dock inte som standard i kassan. För att hjälpa kunder i butikerna se värderingar och recensioner när de får hjälp av säljarna måste du aktivera produktvärderingar i kassan.

Så här aktiverar du produktrecensioner i kassan.

1. Öppna **Butik \> Butiksinställning \> Parametrar \> Butiksparametrar**. Du kan också söka efter "butiksparametrar".
1. På fliken **konfigurationsparametrar** välj **Ny**.
1. Ange ett namn som till exempel **RatingsAndReviews.EnableProductRatingsForRetailStores** och ange värdet till **sant**.
1. Välj **Spara**.
1. Gå till **Butik \> Butik-IT \> Distributionsschema**. Du kan också söka efter "fördelningsplan".
1. I jobblistan, välj **1110** (**Global konfiguration**) och välj sedan **Kör nu**.
1. När jobbet har körts kontrollerar du att produktklassificeringen nu visas i kassan.

Följande illustration visar ett exempel på konfigurationen av parametrarna för butik som ska aktiveras för produktvärderingar i kassan.

![Konfiguration av butiksparametrarna (butik) för produktvärderingar i kassan](media/rnr-hq-enable-ratings-in-pos.png)

Följande illustration visar ett exempel på produktvärderingar i kassan.

![Produktvärderingar i kassan](media/rnr-pos-catalog-ratings.png)

Följande illustration visar ett exempel på produktvärderingar kundtjänstkanaler.

![Produktvärderingar i en kundtjänstkanal](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)
