---
title: När du ska återställa en data mart
description: Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "5989002"
---
# <a name="when-to-reset-a-data-mart"></a>När du ska återställa en data mart

Det kan ta lång tid att återställa data mart. Beroende på vilka omständigheter du behöver, är det inte alltid den här åtgärden som behövs. Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>När måste du återställa data eller vill du återställa data?
Fundera över följande frågor innan du ställer in en data mart. Om du svarar ja på en eller flera frågor kan det visa att organisationen kan ha nytta av att återställa data.

- Återställdes programdatabasen?
- Om du har öppnat en supporthändelse och en supporttekniker har uppmanat dig att återställa data mart som en del av ett felsökningssteg.
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>När det inte är lämpligt att återställa en data mart?
Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart. Dessa omfattar bland annat. 

- Du upplever prestandaproblem som är kopplade till datasynkronisering. 
- Om du har ett återkommande återställt mönster på grund av någon av följande orsaker: 
  - **Data som saknas** 
  - **Låst integrationstillstånd** 
  - **Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa data. Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.
 
## <a name="what-is-a-data-mart-reset"></a>Vad är återställning av data mart?
- En återställning startas först när befintliga uppgifter har slutförts. På så sätt ser du till att gamla data inte infogas. Då kanske ett meddelande visas, till exempel "Återställning av data mart kunde inte bearbetas på grund av en aktiv uppgift. Försök igen senare."
- När du återställer den inaktiveras integrationsuppgifterna och all data från data mart tas bort. Integrationen aktiveras igen.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Om jag återställer data mart, förlorar jag rapporter som jag redan har utformat? 
Nej, dina rapporter lagras i SQL-register som inte påverkas av en återställd data mart. Om du är orolig för att förlora rapporter som du har utformat, kan du backa upp designerna som du inte vill förlora. Om du vill säkerhetskopiera dem öppnar du rapportdesignern och går till **Företag > Företag > Byggblock > Exportera**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>Måste alla användare stänga systemet för att återställa data mart?
Nej, användarna kan fortsätta att arbeta i systemet när data mart återställs. De kan dock inte komma åt rapporter som har skapats med Financial Reporter förrän återställningen är klar. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
