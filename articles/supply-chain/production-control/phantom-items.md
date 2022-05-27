---
title: Fiktiva artiklar
description: Det här avsnittet beskriver hur radtypen Fiktiv kan användas för rader i en strukturlista (BOM) och en formel i Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5c9768381d35709611e4bec3d2b7793a4d896b34
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713259"
---
# <a name="phantom-items"></a>Fiktiva artiklar

[!include [banner](../includes/banner.md)]

Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel.

I bild 1 är (a) strukturlistan för produkt H och delar F och G och (b) är flödesbladet för produkter H och del F.

![Bild 1: Teknisk strukturlista.](media/product-H-part-F.png)
*Bild 1: Teknisk strukturlista*

Bild 1 visar ett exempel på en strukturlista på två nivåer. Slutprodukten H representerar en produkt för en maskinsammansättning. Maskinsammansättningen består av två delar, en elektrisk enhet (F) med två material (A och B) och en uppsättning förpackningsmaterial (G) som också har två material (C och D). Ett annat material (E) används vid allmän sammansättning av maskinen.

Bild 1 representerar teknikstrukturlistan för produkt H. Den här strukturen ger en bra översikt över delarna och komponenterna i maskinens övergripande sammansättning. Men även om produktutvecklare kanske föredrar att visa strukturlistan på detta sätt, kanske strukturen inte korrekt återger hur maskinen byggs i fabriken.

Teknikstrukturen i bild 1 anger till exempel att den elektriska enheten F sammansätts som en separat del på en separat arbetsorder. Men i verkstaden kanske det anses mer optimalt att sammansätta den elektriska enheten som en del av hela maskinsammansättningen och inte som en separat arbetsorder.

Teknikstrukturen indikerar också att del G är en separat del. Men i den här strukturen representerar del G inte en fysisk del utan en samling av förpackningsmaterial.

Därför, även om en teknikstrukturlista ger bra värde för designen av en produkt och underhåll av den designen, den behöver inte vara det mest logiska sättet att stödja produktens tillverkningskörningsprocess. Däremot representerar en tillverkningsstrukturlista det bästa sättet att skapa en produkt.

Bild 2 visar hur föregående teknikstrukturlista övergår till en tillverkningsstrukturlista. I bild 2 är (a) strukturlistan för produkt H och b är flödesbladet för produkt H.

![Bild 2: Tillverkningsstrukturlista.](media/product-H-part-B.png)
*Bild 2: Tillverkningsstrukturlista*

I den här strukturen kan du se att det inte finns några delar F och G och de material som dessa delar består av har upphöjts till nästa strukturlistenivå.

Till skillnad från teknikstrukturlistan som hade två operationsblad har tillverkningsstrukturlistan endast ett operationsblad. Förpackningsoperationen som var kopplad till del G har också utökats och ingår nu i operationsbladet för produkt H. Sammansättningen av den elektriska enheten är den första operationen. Denna order passar bra, eftersom enheten används i nästa operation som är maskinsammansättningen. Den sista operationen är förpackningsoperationen som förbrukar två förpackningsmaterial (C och D).

Övergången mellan teknikstrukturlistan och tillverkningsstrukturlistan har aktiverats via radtypen Fiktiv strukturlista. Såsom begreppet ”fiktiv” anger, har delar F och G försvunnit under övergångsperioden mellan de två typerna av strukturlista. I det här exemplet används radtypen Fiktiv till strukturlisteraderna för delar F och G i teknikstrukturlistan. När en produktions- eller batchorder skapas kopieras teknikstrukturlista till produktions- eller batchordern. Sedan när ordern beräknas, sker övergången från teknikstrukturlistan till tillverkningsstrukturlistan enligt bild 2. Från operationsbladet i bild 2 inmatas förpackningsmaterialen C och D för operationen.

## <a name="multilevel-phantom-bom-structures"></a>Fiktiva artikelstrukturlistor på flera nivåer

Radtypen Fiktiv kan användas i strukturlistor på flera nivåer, vilket visas i bild 3. I bild 3 är (a) strukturlistan för produkt G och (b) är flödesbladet för delar E och produkt G.

![Bild 3: Teknisk strukturlista del G.](media/product-G.png)
*Bild 3: Teknisk strukturlista del G*

Bild 4 visar den resulterande tillverkningsstrukturlistan och flödesbladet och strukturlisteraderna för delar E och F konfigureras så att radtypen är Fiktiv. I bild 4 är (a) strukturlistan för produkt G och (b) är flödesbladet för produkt G.

![Bild 4: Tillverkningsstrukturlista del G.](media/product-G-route-sheet-G.png)
*Bild 4: Tillverkningsstrukturlista del G*

## <a name="phantom-and-route-network"></a>Fiktiv och flödesnätverk

Fiktiva strukturlistor kan också användas för en strukturlista som har ett flödesnätverk. I ett flödesnätverk körs en eller flera åtgärder parallellt. Bild 5 visar ett exempel på ett flödesnätverk som används i en strukturlista med flera nivåer. I bild 5 är (a) strukturlistan för produkt G och F och (b) är flödesbladet för produkt G och del F som har flödesnätverk.

![Bild 5: Teknikstrukturlista del G, flödesnätverk.](media/product-G-part-F.png)
*Bild 5: Teknikstrukturlista del G, flödesnätverk.*

I bild 6 är (a) strukturlistan för produkt G och del F och (b) är flödesbladet för produkt G och del F.

![Bild 6: Tillverkningsstrukturlista del G, flödesnätverk.](media/product-G-part-F-with-route-sheet.png)
*Bild 6: Tillverkningsstrukturlista del G, flödesnätverk.*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]