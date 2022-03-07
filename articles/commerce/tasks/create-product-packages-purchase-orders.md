---
title: " Skapa produktförpackningar för inköpsorder"
description: Den här proceduren går igenom hur du skapar ett produktpaket och använder det i en inköpsorder.
author: josaw1
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb10164be8d7a0828169cf3865f884afaa2e8408472edebe4cb0c7d4db059d8c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723247"
---
# <a name="create-product-packages-for-purchase-orders"></a> Skapa produktförpackningar för inköpsorder

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du skapar ett produktpaket och använder det i en inköpsorder. Inköpsordern ska användas för att skapa en order för en fördefinierad uppsättning av produkter. I proceduren används demonstrationsföretaget USRT.


## <a name="create-a-product-package"></a>Skapa ett produktpaket
1. Gå till Butik och handel > lagerhantering > återfyllnad > produktpaket.
2. Klicka på Ny.
3. Skriv ett värde i fältet Paketnummer.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
6. Klicka på länken på den valda raden i listan.
7. Klicka på Lägg till.
8. Skriv 0160 i fältet Artikelnummer.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Storlek.
10. Klicka på länken på den valda raden i listan.
11. Ange ett tal i fältet Kvantitet.
12. Klicka på Lägg till.
13. Skriv 0160 i fältet Artikelnummer.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Variant number.
15. Klicka på länken på den valda raden i listan.
16. Ange ett tal i fältet Kvantitet.
17. Klicka på Lägg till.
18. Skriv 0175 i fältet Artikelnummer.
19. Ange ett tal i fältet Kvantitet.
20. Klicka på Spara.
21. Stäng sidan.

## <a name="add-package-to-purchase-order"></a>Lägg till paket i inköpsorder
1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. I listan, välj samma leverantör som produktpaketet har skapats tidigare för om en leverantör valdes.
5. Växla utökningen av avsnittet Allmänt.
6. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
9. Klicka på länken på den valda raden i listan.
10. Klicka på OK.
11. Växla expanderingen av avsnittet Raddetaljer.
12. Klicka på fliken Produktpaket.
13. Klicka på Inköpsorderrad.
14. Klicka på Skapa rader från paket.
15. I listan, sök efter och välj produktpaketet som skapas i föregående steg.
16. Ange ett nummer i fältet Kvantitet.
17. Klicka på Skapa.
18. Klicka på Spara.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]