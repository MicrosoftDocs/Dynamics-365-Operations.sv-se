---
title: "Ställ upp bedrägerivarningar"
description: "Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a>Ställ upp bedrägerivarningar

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order. 

Innan du installerar och använder bedrägeri kontroll regler, måste du aktivera bedrägeri kontroll och definiera grundläggande bedrägeri kontrollvärden i call center-parametrar. Det finns två typer av bedrägerier regler:

-   **Statiska regler** använder ett visst värde, t.ex. ett telefonnummer som har blivit svartlistad.
-   **Dynamiska regler** kan bestå av variabler och villkor.

Innan du skapar en dynamisk regel måste du skapa variabler och villkor som definierar som regeln gäller när regeln ska tillämpas. Om du till exempel vill skapa en regel som kräver att alla order som kunden 1202 platser som är värda skrivaremarginaler eller mer parkeras tills kunden betalningen kan verifieras. I detta fall variablerna kund 1202 och totalt skrivaremarginaler. Villkoret anger att om kunden 1202 placerar en order, och det totala beloppet är lika med eller mer än skrivaremarginaler, försäljning order måste läggas på is tills kunden betalningen kan verifieras.




