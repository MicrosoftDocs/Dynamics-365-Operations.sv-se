--- 
title: "Kontrollera lagertillgängligheten"
description: "Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: 
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 62338fe11c30781f264e626fad835a2ba9dca837
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="check-the-availability-of-stock"></a>Kontrollera lagertillgängligheten

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer. Den visar också hur du kan få leveransinformation relaterad till en artikel. Fysisk lagerbehållning är den lagerbehållning som är tillgänglig – det vill säga den har köpts, mottagits och registrerats. Lagerbehållningen omfattar den tillgängliga lagerbehållningen och även det lager som har beställts och förväntas inkomma, men som ännu inte tagits emot eller registrerats. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder USMF, kan du använda exempelvärdena som visas. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="check-on-hand-inventory-for-an-item"></a>Kontrollera lagerbehållning för en artikel
1. Gå till Lagerhantering > Förfrågningar och rapporter > Lagerbehållning.
2. Markera raden med artikelnumret.
    * Välj det register där raden ställs in på lagerbehållning och angetts i fältet artikelnumret du vill fråga lagerbehållningen per artikelnummer.  
3. I fältet Kriterier väljer du den artikel du vill lägga söka.
    * Om du använder företaget för USMF-demonstrationdata, kan du välja M9201.  
4. Klicka på OK.
5. Klicka på Dimensioner.
    * De dimensioner som fliken kan du, väljer du hur mycket information du vill se om din lagerbehållning. Om du behöver data som är relaterade till reservation, måste du se alla lagerdimensioner för artiklarna som använder avancerade processer för lagerställe (WHS).  
6. Klicka på OK.
7. Klicka på Relaterad information i åtgärdsfönstret.
    * Om du inte ser den här, kan du behöva klicka på ellipsknappen (…) Om du vill se ytterligare åtgärderfönsterväljare.  
8. Klicka på Leveransöversikt.
    * Tillförselöversiktfliken innehåller information om varor för en viss artikel, till exempel den tillgängliga kvantiteten, produktionstiden och leverantörsinformation.  
9. Expandera avsnittet I lager.
10. Visa avsnittet Leverantörer.
11. Stäng sidan.
12. Stäng sidan.

## <a name="check-physical-on-hand-inventory"></a>Kontrollera fysisk lagerbehållning
1. Gå till Lagerstyrning > Förfrågningar och rapporter > Fysisk lagerbehållning.
2. Skriv ett värde i fältet Artikelnummer.
    * Du kan använda plats- och lagerställesfälten för att filtrera listan med artiklar.  
3. Uppdatera sidan.
4. Klicka på Visa dimensioner.
    * På fliken Visa dimensioner kan du välja hur mycket information du vill se om din lagerbehållning.  
5. Klicka på OK.
6. Stäng sidan.

## <a name="check-on-hand-inventory-by-location"></a>Kontrollera lagerbehållningen efter plats
1. Gå till Lagerstyrning > Förfrågningar och rapporter > Behållning efter plats.
2. Ange ett värde i fältet Lagerställe.
    * Om du använder företaget för USMF-demonstrationdata, kan du använda ”51".  
3. Uppdatera sidan.
4. Klicka på Visa dimensioner.
5. Klicka på OK.
6. Stäng sidan.


