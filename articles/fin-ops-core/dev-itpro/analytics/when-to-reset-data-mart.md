---
title: När du ska återställa en data mart
description: Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093222"
---
# <a name="when-to-reset-a-data-mart"></a>När du ska återställa en data mart

Det kan ta lång tid att återställa data mart. Beroende på vilka omständigheter du behöver, är det inte alltid den här åtgärden som behövs. Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>När måste du återställa data eller vill du återställa data?
Fundera över följande frågor innan du ställer in en data mart. Om du svarar ja på en eller flera frågor kan det visa att organisationen kan ha nytta av att återställa data.

- Appdatabasen har återställts, men datatorgets databas återställdes inte.
- Du kan se felaktiga data för en redovisningsperiod, vilket inte är resultatet av ett problem med rapportdesignen.
- Du ser felaktiga data under en redovisningsperiod och poster anges under Integrationsförsök på sidan **Integrationsstatus** i rapportdesigner (starta rapportdesigner och välj **Verktyg > Integrationsstatus**).
- Du har öppnat en supporthändelse och en supporttekniker har uppmanat dig att återställa data den som ett del av ett felsökningssteg.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>När det inte är lämpligt att återställa en data mart?
Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart. Dessa omfattar bland annat. 

- När orsaken inte finns i det här avsnittet.
- Du upplever prestandaproblem som är kopplade till datasynkronisering. Det hjälper inte att återställa data.
- Om du har ett återkommande återställt mönster på grund av någon av följande orsaker: 
  - **Saknade data** - Först måste du eliminera problem med rapportdesign och tidssynkronisering med datasynkronisering, till exempel observerar du att faktakartan inte har körts sedan saknade data publicerades.
  - **Integrationstillståndet ligger kvar** - Om integrationen är långsam eller verkar liga kvar är det osannolikt att det kommer att lösa problemet att återställa data mart.
  - **Det går inte att återställa** - Om ett antal försök att slutföra en återställning har gjorts och misslyckas på grund av att data saknas rekommenderar vi att du öppnar en supporthändelse och arbetar med en supporttekniker för att analysera din situation innan du försöker återställa data igen.
  - **Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa data. Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Vad en återställd data mart inte gör  
- En återställning startas först när befintliga uppgifter har slutförts. På så sätt ser du till att gamla data inte infogas. Då kanske ett meddelande visas, till exempel "Återställning av data mart kunde inte bearbetas på grund av en aktiv uppgift. Försök igen senare."
- När du återställer den inaktiveras integrationsuppgifterna och all data från data mart tas bort. Integrationen aktiveras igen.

> [!NOTE]
> Följande punkter anger två saker som du *inte* gör när du återställer data. <br>
> - Återställningar rensar inte rapportdesigner. <br>
> - När du återställer rensas inte företagsdata eller användardata om de inte har valts.
