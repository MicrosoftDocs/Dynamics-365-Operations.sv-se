---
title: Transportrabatt
description: I den här artikeln beskrivs leveransrabattfunktionerna i Microsoft Dynamics 365 Commerce och de inställningar som krävs för att använda dem.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473861"
---
# <a name="shipping-discount"></a>Transportrabatt

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs leveransrabattfunktionerna i Microsoft Dynamics 365 Commerce och de inställningar som krävs för att använda dem.

Gratis- eller rabatterad leverans är en faktor som påverkar kundernas online-inköpsbeslut. För att öka intäkterna per transaktion använder många återförsäljare en gratisleveransförmån för att motivera kunderna till att öka kundvagnens storlek.

Commerce stöder en leveransrabatt som gör att butikerna kan konfigurera en rabattprocent på leveransavgifterna för en specifik leveransmetod när det totala försäljningsbeloppet för kvalificerade artiklar i transaktionen uppfyller särskilda kriterier. Ett exempel på ett scenario som använder leveransrabattkapaciteten är "Spendera 50 $ eller mer för att få gratis leverans över natten."

## <a name="prerequisites"></a>Förutsättningar

Leveransrabatten stöds av Commerces [avancerade automatiska avgifter i flerkanal](/dynamics365/unified-operations/retail/omni-auto-charges). För att fraktrabattfunktionen ska fungera måste du aktivera konfigurationen **Använd avancerade automatiska debiteringar** på fliken **Kundorder** på sidan **Commerce-parametrar** i Commerce headquarters. Återförsäljare kan använda funktionen för avancerad autoavgifter för att ställa in olika typer av avgifter, till exempel hantering, installation och avyttrande.

Leveransrabatten används bara i leveransavgifterna. Därför måste en återförsäljare ange vilka avgifter som är fraktkostnader. För att ange leveransavgifter, i Commerce headquarters, gå till **kanalinställningar \> avgifter \> avgiftskod** och ange alternativet **Leveransavgift** till **ja** för önskad avgift.

![Ange en kostnad som en leveranskostnad.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Konfiguration

Leveransrabatten är skiktbaserad och stöder bara beräkningstypen **Procentuell rabatt**. Om du vill ställa in en leveransrabatt, i Commerce headquarters, gå till **Prissättning och rabatter \> Leveranströskelrabatt**. Du kan sedan ange det leveranssätt som rabatten gäller för, definiera ett eller flera beloppströsklar och ställa in rabattprocenten för varje tröskelvärde. Du kan också konfigurera en lista över kategorier eller produkter som kvalificerade artiklar. På så sätt räknas bara försäljningsbeloppet mot artiklarna i en transaktion när prissättningsmotorn utvärderar om transaktionssumman är lika med tröskelvärdet.

> [!NOTE]
> Till skillnad från andra rabatttyper skapas inte rabattrader för leveransrabatten. I stället redigeras leveranskostnaden direkt och namnet på rabatten bifogas till tilläggsbeskrivningen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
