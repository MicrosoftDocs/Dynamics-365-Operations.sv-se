---
title: Förbättrad hantering av batchspårade artiklar
description: I det här avsnittet beskrivs den förbättrade hanteringen av batchspårade artiklar under bokföringsprocessen av utdrag i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 513b6ca84fa71e851a5a3e4275e0b6572789e1eb
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485793"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Förbättrad hantering av batchspårade artiklar

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs den förbättrade hanteringen av batchspårade artiklar under bokföringsprocessen av utdrag i Microsoft Dynamics 365 Commerce.

I Dynamics 365 Commerce-kassan kan batchnummer inte registreras för batchspårade artiklar vid försäljningstillfället. För specifika konfigurationer, när försäljning bokförs vid Commerce-administration genom kundorder- eller utdragsbokföring, förväntar sig Commerce-systemet att det finns giltiga batchnummer för batchspårade artiklar och att de används under faktureringen.

Om det finns giltiga batchnummer för produkter används de vid faktureringsprocessen för både kundorder och försäljningsorder från utdragsbokföringen. Om det inte finns giltiga batchnummer för produkter kan faktureringen av kundorder inte bokföras och kassaanvändaren får ett felmeddelande. Utdragsbokföringen går sedan in i ett feltillstånd även om ett negativt lager har aktiverats för produkterna.

När negativt lager har aktiverats för batchspårade artiklar innebär de förbättringar som gjorts av Commerce att faktureringen av kund- och försäljningsorder som görs via utdragsbokföring inte blockeras för dessa artiklar om lagret är 0 (noll) eller om det inte finns något batchnummer. Den förbättrade funktionen använder ett standardiserat batch-ID för försäljningsrader när det inte finns batchnummer.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Definiera standardvärdet för det batch-ID som används för kundorder

Gör på följande sätt för att definiera standardvärdet för det batch-ID som används för kundorder.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar** i Commerce-administration.
1. På fliken **Kundorder**, på snabbfliken **Order** anger du ett värde i fältet för **standardvärde för batch-ID**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Definiera standardvärdet för det batch-ID som används för försäljningsorder via utdragsbokföring

Gör på följande sätt för att definiera standardvärdet för det batch-ID som används för försäljningsorder via utdragsbokföring.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar** i Commerce-administration.
1. På fliken **Bokföra**, på snabbfliken **Lageruppdatering** anger du ett värde i fältet för **standardvärde för batch-ID**.

> [!NOTE]
> - Funktionen för standardvärde för batch-ID är bara tillgänglig när avancerad distributionslagerhantering har aktiverats för det specifika butikslagret och artiklarna. I en framtida version kommer funktionen för standardvärde för batch-ID också att fungera för tillfällen då avancerad distributionslagerhantering inte är aktiverad.
> - Stöd för den förbättrade hanteringen av batchspårade artiklar under bokföringen av icke-avancerade scenarier för distributionslagerhantering infördes i Commerce-version 10.0.5.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
