---
title: Kontrollera lagertillgängligheten
description: Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer.
author: ShylaThompson
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66b6b365958820a76f733df5eb2aabf6c3c4ebac
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383514"
---
# <a name="check-the-availability-of-stock"></a>Kontrollera lagertillgängligheten

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer. Den visar också hur du kan få leveransinformation relaterad till en artikel. Fysisk lagerbehållning är den lagerbehållning som är tillgänglig – det vill säga den har köpts, mottagits och registrerats. Lagerbehållningen omfattar den tillgängliga lagerbehållningen och även det lager som har beställts och förväntas inkomma, men som ännu inte tagits emot eller registrerats. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder USMF, kan du använda exempelvärdena som visas. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="check-on-hand-inventory-for-an-item"></a>Kontrollera lagerbehållning för en artikel
1. Gå till **Navigeringsfönster > Moduler > Lagerhantering > Förfrågningar och rapporter > Lagerbehållning**.
2. Markera raden med **artikelnumret**. Välj det register där raden ställs in på lagerbehållning och angetts i fältet artikelnumret du vill fråga **lagerbehållningen** per **artikelnummer**.
3. I fältet **Kriterier** väljer du den artikel du vill lägga söka. Om du använder företaget för USMF-demonstrationdata, kan du välja M9201.  
4. Klicka på **OK**.
5. I **åtgärdsfönstret** klickar du på **Dimensioner**. Fliken **dimensioner** låter dig välja hur mycket information du vill se om din lagerbehållning. Om du behöver data som är relaterade till reservation, måste du se alla lagerdimensioner för artiklarna som använder avancerade processer för lagerställe (WMS).
6. Klicka på **OK**.
7. I **åtgärdsfönstret**, klicka på **Relaterad information**. Om du inte ser det här alternativet kan du behöva klicka på ellipsknappen (…) för att se ytterligare alternativ för åtgärderfönster.
8. Klicka på **Leveransöversikt**. Fliken **Leveransöversikt** innehåller information om varor för en viss artikel, till exempel den tillgängliga kvantiteten, produktionstiden och leverantörsinformation.  
9. Expandera avsnittet **I lager**.
10. Expandera avsnittet **Leverantörer**.
11. Stäng sidan.
12. Stäng sidan.

## <a name="check-physical-on-hand-inventory"></a>Kontrollera fysisk lagerbehållning
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Förfrågningar och rapporter > Fysisk lagerbehållning**.
2. I fältet **Artikelnummer**, skriv ett värde. Du kan använda plats- och lagerställesfälten för att filtrera listan med artiklar. 
3. Uppdatera sidan.
4. I **Åtgärdsfönstret** klickar du på **Visa dimensioner**. På fliken Visa dimensioner kan du välja hur mycket information du vill se om din lagerbehållning.
5. Klicka på **OK**.
6. Stäng sidan.

## <a name="check-on-hand-inventory-by-location"></a>Kontrollera lagerbehållningen efter plats
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Förfrågningar och rapporter > Behållning efter plats**.
2. Ange ett värde i fältet **Lagerställe**. Om du använder företaget för USMF-demonstrationdata, kan du använda ”51".  
3. Uppdatera sidan.
4. Klicka på **Visa dimensioner**.
5. Klicka på **OK**.
6. Stäng sidan.

