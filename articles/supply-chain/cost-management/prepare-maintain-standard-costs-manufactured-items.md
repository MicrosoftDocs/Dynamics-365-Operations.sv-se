---
title: Förbereda underhåll av standardkostnader för tillverkade artiklar
description: Denna artikel beskriver hur du förbereder för underhåll av kostnader för tillverkade artiklar.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 423da8022faf8066c5aa524c49c5071d0871de04
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886027"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Förbereda underhåll av standardkostnader för tillverkade artiklar

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du förbereder för underhåll av kostnader för tillverkade artiklar. Hur du gör för tillverkade artiklar skiljer sig något från hur du gör för inköpta artiklar.

De principer som tilldelas tillverkade artiklar kan påverka kostnadsberäkningarna för de överordnade tillverkade artiklarna. För att förbereda underhåll av kostnader för tillverkade artiklar följ dessa steg:

1. Tilldela en artikelmodellgrupp till den tillverkade artikeln. 

   Artikelmodellgruppen identifierar att standardkostnaderna ska användas.

2. Tilldela en artikelgrupp till den tillverkade artikeln. 

   Artikelgruppen innehåller de redovisningskonton som gäller för den tillverkade artikeln. Redovisningskontona för en tillverkad artikel som har lagermodellen standardkostnad omfattar flera produktionsavvikelser, kostnadsändringsavvikelsen och omvärderingen av lagerkostnad.

3. Tilldela lagermåttet till artikeln. 

   Artikelns kostnader uttrycks alltid i artikelns lagermåttenhet.

4. Tilldela inte en kostnadsgrupp till en tillverkad artikel, såvida den inte ska behandlas som en inköpt artikel.

5. Tilldela en strukturlisteberäkningsgrupp till den tillverkade artikeln. 

   Artikelns strukturlisteberäkningsgrupp definierar de varningsvillkor som gäller. På så sätt kan varningsmeddelanden genereras om möjliga orsaker till beräkningsfelet när en strukturlisteberäkning utförs. Ett varningsmeddelande kan till exempel identifiera när en aktiv strukturlista eller ett flöde inte finns. Beräkningsgruppen för strukturlistan innehåller en princip för att stoppa nedbrytning som anger när en tillverkad artikel borde hanteras som en inköpt artikel.

6. Tilldela en standardorderkvantitet till den tilldelade artikeln om den har konstanta kostnader. 

   Standardorderkvantiteten är en redovisningspartistorlek för amortering av konstanta kostnader. Exempel på konstanta kostnader inkluderar inställningstider i flödesåtgärder och en konstant komponentkvantitet i en strukturlista (BOM).

7. Definiera strukturlistan för den tillverkade artikeln. 

   Du kan definiera en eller flera strukturlisteversioner för den tillverkade artikeln. Kontrollera att de versioner som du vill använda har markerats som godkända och aktiva och att de har önskade giltighetsdatum. Strukturlisteversionen kan gälla för hela företaget eller för en viss site.

8. Definiera flödet för den tillverkade artikeln. 

   Du kan definiera en eller flera flödesversioner för den tillverkade artikeln. Kontrollera att de versioner som du vill använda har markerats som godkända och aktiva och att de har önskade giltighetsdatum. Flödesversionen måste gälla för en viss site.

Om du vill använda flödesinformation i kostnadssyfte krävs ytterligare förberedelser. Till exempel måste de kostnadskategorier som tilldelas flödesåtgärder vara korrekta och fullständiga.

## <a name="related-articles"></a>Relaterade artiklar

[Periodisera konstanta kostnader för en tillverkad artikel](amortize-constant-costs-manufactured-item.md)

[Ställ in produkter som antingen kan produceras eller anskaffas](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]