---
title: Vanliga frågor om återställ datatorg
description: Det här avsnittet innehåller svar på vanliga frågor om återställ datatorg.
author: jinniew
ms.date: 07/16/2021
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
ms.openlocfilehash: 90abe1fc3e84e0a9777f3eabd790a4b7e9b509c5
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638277"
---
# <a name="data-mart-resets-faq"></a>Vanliga frågor om återställ datatorg

Det här avsnittet innehåller svar på vanliga frågor om återställ datatorg. En återställning av datatorg kan vara en tidskrävande process och, beroende på omständigheter, kanske inte är den lösning som krävs. Därför innehåller det här avsnittet information om omständigheter där återställ datatorg kan hjälpa till och situationer där den är till hjälp.

## <a name="what-is-a-data-mart-reset"></a>Vad är återställning av datatorg?

En återställ datatorg inaktiverar integrationsuppgifterna, raderar alla data för datatorg och aktiverar sedan integrationen på nytt.

För att säkerställa att gamla data inte infogas kan en återställ datatorg startas först när befintliga uppgifter har slutförts. Om du försöker återställa datatorg innan alla uppgifter har slutförts kanske du får ett meddelande som till exempel: "återställ datatorg kunde inte bearbetas på grund av en aktiv uppgift. Försök igen senare."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>När måste du återställa data eller vill du återställa data?

Om ett eller flera av följande gäller i din situation kan din organisation dra fördel av en återställ datatorg:

- Återställdes programdatabasen.
- Du har öppnat en supportbegäran och en supporttekniker har uppmanat dig att återställa datatorg som ett del av ett felsökningssteg.
 
> [!NOTE]
> Processen för att återställa data påverkas av antalet redovisnings- och budgettransaktioner i databasen. Beroende på antalet transaktioner i ditt system kan en data-reset slutföras om bara 15 minuter eller så kan den ta upp till fyra timmar. Om återställningen tar längre än fyra timmar rekommenderar vi dock att du kontaktar Support.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>När är återställa en datatorg inte lämpligt?

Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart:

- Du upplever prestandaproblem som är kopplade till datasynkronisering.
- Om du har ett återkommande återställt mönster på grund av någon av följande orsaker:

    - **Data som saknas** – Om du ser att data saknas öppnar du ett supportärende hos Microsoft för att granska ditt rapportformat och eventuella problem med datasynkronisering.
    - **Låst integrationstillstånd**
    - **Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa datatorg. Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Om jag återställer datatorg, förlorar jag rapporter som jag redan har utformat?

Nej. Dina rapporter lagras i SQL-register som inte påverkas av en återställd data mart. Om du är orolig för att förlora rapporter som du har utformat, kan du backa upp designerna som du inte vill förlora. Om du vill säkerhetskopiera designer öppnar du rapportdesignern och går till **Företag \> Företag \> Byggblock \> Exportera**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Måste alla användare stänga systemet innan jag kan återställa data mart?

Nej. Användarna kan fortsätta att arbeta i systemet när data mart återställs. De kan dock inte komma åt rapporter som har skapats med Financial Reporter förrän återställningen är klar.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
