---
title: "Ställ in streckkoder"
description: "Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Operations - Retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f182f719d2e20673db9b576d9831e060c351a550
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-bar-codes"></a>Ställ in streckkoder

[!include[banner](includes/banner.md)]


Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Operations - Retail.

Du kan använda streckkoder för att köpa eller sälja produkter, spåra produktvarianter och ställa in kunder och medarbetare. Du kan också använda streckkoder till att utfärda och signera kuponger, presentkort och kreditnotor. Du kan lägga upp butiksprodukter så att de har standardstreckkoder eller anpassade interna streckkoder. Produkter kan ha fler än en streckkod. Till exempel kan en produkt ha flera streckkoder om den kommer från olika tillverkare, eller om den har varianter baserat på storlek, utförande eller färg. Streckkoder kan innehålla produktens vikt eller pris. Streckkodsmasker är mallar som används för att skapa streckkoder. **Obs!** Om du tilldelar varje variantkombination en unik streckkod kan du skanna artikelstreckkoden i kassan och sedan låta programmet bestämma vilken variant av produkten som säljs. Du kan också samla in och visa statistik om försäljningen per variant. Varje storlek-, färg- och utförandegrupp kan tilldelas ett unikt nummer som identifierar den gruppen i streckkoden. I Dynamics 365 for Operations används streckkodsmasken för att generera streckkoder automatiskt för varje variantkombination. Denna funktion kan vara praktisk om det förekommer flera storlekar, färger och utföranden eftersom antalet kombinationer ökar markant med varje variantkod som läggs till. Om denna funktion inte används måste streckkoder manuellt tilldelas varje kombination som representerar en produktvariant. Du kan skapa streckkoder manuellt eller automatiskt. Slutför följande uppgifter i den ordning som de visas i för att skapa streckkoder.

1.  [Ställ in streckkodsmasktecken](set-up-bar-code-masks.md).
2.  [Ställ in streckkodsmasker](set-up-bar-code-masks.md).
3.  Konfigurera streckkodsinställningar.
4.  Skapa streckkoder för specifika produkter.


<a name="see-also"></a>Se även
--------

[Ställ in streckkodsmasker](set-up-bar-code-masks.md)



