---
title: " Ställ in regler och parametrar för direktleverans och centraliserad distribution"
description: I den här proceduren visas stegen för att skapa Påfyllnadsregler.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 776defca4a9d2a860901efe9e8890fd11ec8ce7302c53dc1507cc77ff501aded
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753062"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a> Ställ in regler och parametrar för direktleverans och centraliserad distribution

[!include [banner](../includes/banner.md)]

I den här proceduren visas stegen för att skapa Påfyllnadsregler. Påfyllnadsregler kan användas för att styra hur produkter fördelas till butikerna när du använder direktleverans och centraliserad distribution. Påfyllnadsregler kan ställas in för butiker eller butiksgrupper. Vikten som definieras för varje rad i en regel ska kontrollera kvantiteterna av hur produkter ska bli distribuerade mellan butiker när de använder påfyllnadsregler som fördelningsmetoden i direktleverans eller centraliserad distribution. I den här proceduren används demonstrationsföretaget USRT.

1. Gå till Påfyllnadsregler.
2. Klicka på Ny.
3. Ange ett värde i fältet Påfyllnadsregel.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klicka på Lägg till.
7. Markera vald rad i listan.
    * Du kan välja påfyllnadshierarki eller kanal för typen. Värdena styr om urvalet i Namn kommer att bli en hierarki med kanaler eller en specifik kanal.  Låt inställningen vara Återanskaffningshierarki i det här exemplet.  
8. Välj ett värde i fältet Namn.
    * Standardviktvärdet fylls i från den vikt som definieras på lagerstället.  Vikten kan användas för en lagerpåfyllnadsregel eller så kan du ange en ny vikt i fältet Vikt.  
9. Ange ett nummer i fältet Vikt.
10. Klicka på Lägg till.
11. Markera vald rad i listan.
12. Välj Kanal i fältet Typ.
13. Ange eller välj ett värde i fältet Namn.
14. Ange ett nummer i fältet Vikt.
15. Klicka på Spara.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]