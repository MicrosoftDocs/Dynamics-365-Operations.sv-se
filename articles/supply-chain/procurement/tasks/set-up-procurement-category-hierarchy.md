---
title: Ställ in en anskaffningskategorihierarki
description: I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess.
author: RichardLuan
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44fd02d37ec4e6431ca25dc980ed1d1785e45fac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239360"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Ställ in en anskaffningskategorihierarki

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess. Dessa uppgifter utförs vanligtvis av en inköpschef. Innan du kan starta den här proceduren måste det finnas en kategorihierarki av typen anskaffning. Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget.


## <a name="add-a-new-procurement-category"></a>Lägg till en ny anskaffningskategori.
1. Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Försändelse > Anskaffningskategorier**.
2. I åtgärdsfönstret klickar du på **Redigera kategorihierarki**. Den aktuella anskaffningskategorihierarkin visas till vänster på sidan. Du är på väg att ändra hierarkin.  
3. I åtgärdsfönstret klickar du på **Ny kategorinod**. Systemet väljer toppnoden som standard. Om du kör den här proceduren som en uppgiftsguide kan du klicka på fliken Lås upp och välja en annan överordnad nod att infoga den nya noden i. Lås uppgifthandboken igen och klicka på noden Ny kategori när det är klart.  
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Beskrivning** anger du ett värde.
6. Skriv ett värde i fältet **Eget namn**. Det egna namnet är valfritt. Detta visas i kategorisökningar tillsammans med kategorinamnet.  
7. Välj **Spara**.

## <a name="add-products-to-your-new-procurement-category"></a>Lägg till produkter i den nya anskaffningskategorin
1. Gå till **Anskaffning och källa > Försändelse > Anskaffningskategorier**. Välj den nod som du precis lade till. Om du kör den här proceduren som en uppgiftsguide kanske du behöver låsa upp uppgiftsguiden för att välja noden.  
2. Växla expansionen av avsnittet **Produkter**.
3. Klicka på **Lägg till** i associerade produkter med anskaffningskategorin.
4. Välj de produkter som du vill lägga till i anskaffningskategorin.
5. Välj pilen för att lägga till produkter till tabellen **Valda**.
6. Välj **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]