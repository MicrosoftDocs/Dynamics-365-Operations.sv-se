---
title: "Ställ upp bedrägerivarningar"
description: "Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7255f2b7e49f56a731d0e3745b4752091013668b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-fraud-alerts"></a>Ställ upp bedrägerivarningar

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order. 

Innan du installerar och använder bedrägeri kontroll regler, måste du aktivera bedrägeri kontroll och definiera grundläggande bedrägeri kontrollvärden i call center-parametrar. Det finns två typer av bedrägerier regler:

-   **Statiska regler** använder ett visst värde, t.ex. ett telefonnummer som har blivit svartlistad.
-   **Dynamiska regler** kan bestå av variabler och villkor.

Innan du skapar en dynamisk regel måste du skapa variabler och villkor som definierar som regeln gäller när regeln ska tillämpas. Om du till exempel vill skapa en regel som kräver att alla order som kunden 1202 platser som är värda skrivaremarginaler eller mer parkeras tills kunden betalningen kan verifieras. I detta fall variablerna kund 1202 och totalt skrivaremarginaler. Villkoret anger att om kunden 1202 placerar en order, och det totala beloppet är lika med eller mer än skrivaremarginaler, försäljning order måste läggas på is tills kunden betalningen kan verifieras.




