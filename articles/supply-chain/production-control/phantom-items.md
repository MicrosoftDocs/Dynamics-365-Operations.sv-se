---
title: Fiktiva artiklar
description: Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel i Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 8e1b241c826e89909590ae16c8458bc49df995bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572827"
---
# <a name="phantom-items"></a>Fiktiva artiklar

[!include [banner](../includes/banner.md)]

Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel.

I bilden nedan (a) är strukturlistan för produkt H och delar F och G och (b) flödesbladet för produkter H och del F.

![Exempel på en strukturlistestruktur på två nivåer.](media/product-H-part-F.png)

Illustrationen visar ett exempel på en strukturlista på två nivåer. Slutprodukten H representerar en produkt för en maskinsammansättning. Maskinsammansättningen består av två delar, en elektrisk enhet (F) med två material (A och B) och en uppsättning förpackningsmaterial (G) som också har två material (C och D). Ett annat material (E) används vid allmän sammansättning av maskinen.

![Teknikstrukturen för produkt H.](media/product-H-part-B.png)

Bilden ovan representerar teknikstrukturlistan för produkt H. Den här strukturen ger en bra översikt över delarna och komponenterna i maskinens övergripande sammansättning. Men även om produktutvecklare kanske föredrar att visa strukturlistan på detta sätt, kanske strukturen inte korrekt återger hur maskinen byggs i fabriken.

T.ex. teknikstrukturen i föregående illustration anger till exempel att den elektriska enheten F sammansätts som en separat del på en separat arbetsorder. Men i verkstaden kanske det anses mer optimalt att sammansätta den elektriska enheten som en del av hela maskinsammansättningen och inte som en separat arbetsorder.

Teknikstrukturen indikerar också att del G är en separat del. Men i den här strukturen representerar del G inte en fysisk del utan en samling av förpackningsmaterial.

Därför, även om en teknikstrukturlista ger bra värde för designen av en produkt och underhåll av den designen, den behöver inte vara det mest logiska sättet att stödja produktens tillverkningskörningsprocess. Däremot representerar en tillverkningsstrukturlista det bästa sättet att skapa en produkt.

Följande bild visar hur föregående teknikstrukturlista övergår till en tillverkningsstrukturlista. I den här illustrationen (a) är strukturlistan för produkt H och b flödesbladet för produkt H.

I den här strukturen kan du se att det inte finns några delar F och G och de material som dessa delar består av har upphöjts till nästa strukturlistenivå.

Till skillnad från teknikstrukturlistan som hade två operationsblad har tillverkningsstrukturlistan endast ett operationsblad. Förpackningsoperationen som var kopplad till del G har också utökats och ingår nu i operationsbladet för produkt H. Sammansättningen av den elektriska enheten är den första operationen. Denna order passar bra, eftersom enheten används i nästa operation som är maskinsammansättningen. Den sista operationen är förpackningsoperationen som förbrukar två förpackningsmaterial (C och D).

Övergången mellan teknikstrukturlistan och tillverkningsstrukturlistan har aktiverats via radtypen Fiktiv strukturlista. Såsom begreppet ”fiktiv” anger, har delar F och G försvunnit under övergångsperioden mellan de två typerna av strukturlista. I det här exemplet används radtypen Fiktiv till strukturlisteraderna för delar F och G i teknikstrukturlistan. När en produktions- eller batchorder skapas kopieras teknikstrukturlista till produktions- eller batchordern. Sedan när ordern beräknas, sker övergången från teknikstrukturlistan till tillverkningsstrukturlistan enligt föregående illustrationer. Från operationsbladet i den andra bilden inmatas förpackningsmaterialen C och D för operationen.

## <a name="multilevel-phantom-bom-structures"></a>Fiktiva artikelstrukturlistor på flera nivåer

Radtypen Fiktiv kan användas i strukturlistor på flera nivåer, vilket visas i följande illustration. I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för delar E och produkt G.

![Den fiktiva radtypen som används i strukturlistestruktur på flera nivåer.](media/product-G-route-sheet-G.png)

Följande bild visar den resulterande tillverkningsstrukturlistan och flödesbladet och strukturlisteraderna för delar E och F konfigureras så att radtypen är Fiktiv. I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för produkt G.

![Produkt G.](media/product-G.png)

## <a name="phantom-and-route-network"></a>Fiktiv och flödesnätverk

Fiktiva strukturlistor kan också användas för en strukturlista som har ett flödesnätverk. I ett flödesnätverk körs en eller flera åtgärder parallellt. Nedan visas ett exempel på ett flödesnätverk som används i en strukturlista med flera nivåer. I den här illustrationen (a) är strukturlistan för produkt G och F och (b) flödesbladet för produkt G och del F som har flödesnätverk.

![Exempel på ett flödesnätverk som används i en strukturlistestruktur i flera nivåer.](media/product-G-part-F.png)

I bilden nedan (a) är strukturlistan för produkt G och del F och (b) flödesbladet för produkt G och del F.

![Strukturlistan för produkt G och del F, samt flödesbladet för produkt G och del F.](media/product-G-part-F-with-route-sheet.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]