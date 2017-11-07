---
title: "Ställ in streckkoder"
description: "Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fdc56bf468babd4b0b0652d9791114af676c8470
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-codes"></a>Ställ in streckkoder

[!include[banner](includes/banner.md)]


Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Retail.

Du kan använda streckkoder för att köpa eller sälja produkter, spåra produktvarianter och ställa in kunder och medarbetare. Du kan också använda streckkoder till att utfärda och signera kuponger, presentkort och kreditnotor. Du kan lägga upp butiksprodukter så att de har standardstreckkoder eller anpassade interna streckkoder. Produkter kan ha fler än en streckkod. Till exempel kan en produkt ha flera streckkoder om den kommer från olika tillverkare, eller om den har varianter baserat på storlek, utförande eller färg. Streckkoder kan innehålla produktens vikt eller pris. Streckkodsmasker är mallar som används för att skapa streckkoder. **Obs!** Om du tilldelar varje variantkombination en unik streckkod kan du skanna artikelstreckkoden i kassan och sedan låta programmet bestämma vilken variant av produkten som säljs. Du kan också samla in och visa statistik om försäljningen per variant. Varje storlek-, färg- och utförandegrupp kan tilldelas ett unikt nummer som identifierar den gruppen i streckkoden. I Dynamics 365 for Retail används streckkodsmasken för att generera streckkoder automatiskt för varje variantkombination. Denna funktion kan vara praktisk om det förekommer flera storlekar, färger och utföranden eftersom antalet kombinationer ökar markant med varje variantkod som läggs till. Om denna funktion inte används måste streckkoder manuellt tilldelas varje kombination som representerar en produktvariant. Du kan skapa streckkoder manuellt eller automatiskt. Slutför följande uppgifter i den ordning som de visas i för att skapa streckkoder.

1.  [Ställ in streckkodsmasktecken](set-up-bar-code-masks.md).
2.  [Ställ in streckkodsmasker](set-up-bar-code-masks.md).
3.  Konfigurera streckkodsinställningar.
4.  Skapa streckkoder för specifika produkter.


<a name="see-also"></a>Se även
--------

[Ställ in streckkodsmasker](set-up-bar-code-masks.md)




