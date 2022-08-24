---
title: Vanliga frågor om återställ datatorg
description: Den här artikeln innehåller svar på vanliga frågor om återställ datatorg.
author: jinniew
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.search.form: ''
ms.openlocfilehash: 949bf64fefe2dc70541eb5a94518d6b9fe1d3eb8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289919"
---
# <a name="data-mart-resets-faq"></a>Vanliga frågor om återställ datatorg

Den här artikeln innehåller svar på vanliga frågor om återställ datatorg. En återställning av datatorg kan vara en tidskrävande process och, beroende på omständigheter, kanske inte är den lösning som krävs. Därför innehåller den här artikeln information om omständigheter där återställ datatorg kan hjälpa till och situationer där den är till hjälp.

## <a name="what-is-a-data-mart-reset"></a>Vad är återställning av datatorg?

En återställ datatorg inaktiverar integrationsuppgifterna, raderar alla data för datatorg och aktiverar sedan integrationen på nytt.

För att säkerställa att gamla data inte infogas kan en återställ datatorg startas först när befintliga uppgifter har slutförts. Om du försöker återställa datatorg innan alla uppgifter har slutförts kanske du får ett meddelande som till exempel: "återställ datatorg kunde inte bearbetas på grund av en aktiv uppgift. Försök igen senare."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>När måste du återställa data eller vill du återställa data?

Om ett eller flera av följande gäller i din situation kan din organisation dra fördel av en återställ datatorg:

- **Återställdes programdatabasen**
- **Du har öppnat en supportbegäran** – en supporttekniker har uppmanat dig att återställa datatorg som ett del av ett felsökningssteg.
- **Stor andel föråldrade poster** – Föråldrade poster ger inte själva nödvändigtvis rätt att återställa datatorg. En hög procentsats av föråldrade data kan försämra den totala genereringen av rapporter och integrationsprestanda och få extra användning av databasutrymme. Vi rekommenderar att du genomför en datamart-återställning för att ta bort inaktuell data när det finns mer än 80 % inaktuell data i datamarten.
 
> [!NOTE]
> Processen för att återställa data påverkas av antalet redovisnings- och budgettransaktioner i databasen. Beroende på antalet transaktioner i ditt system kan en data-reset slutföras om bara 15 minuter eller så kan den ta upp till fyra timmar. Om återställningen tar längre än fyra timmar rekommenderar vi dock att du kontaktar Support.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>När är återställa en datatorg inte lämpligt?

Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart:

- Du upplever problem med dataintegrationsprestanda.
- Din Financial Reporter-integration är inte aktiverad. 

    - Det innebär att redovisningsdata inte längre synkroniseras till dina data i Financial Reporting. I Financial Reporter kanske du inte får aktuella nummer för dina ekonomirapporter. Detta inträffar vanligtvis om du inte har använd Financial Reporter på länge.
    - Du uppmanas att aktivera integrationen genom att återställa data. Du kan fortsätta genom att välja **Ja**. Du kan också välja att återställa data mär en senare tidpunkt. När integrationen har aktiverats synkroniseras redovisningsdata återigen i Financial Reporter. 
- Om du har ett återkommande återställt mönster på grund av någon av följande orsaker:

    - **Saknade eller oväntade data i rapporten** – Om du ser att data saknas öppnar du ett supportärende hos Microsoft för att granska ditt rapportformat och eventuella problem med datasynkronisering.
    - **Låst integrationsläge** – Om du ser att integrationsstatusen har körts kan det bero på ett stort antal transaktioner i systemet. Denna stat kommer att lösa sig. Om du däremot ser att integreringsstatusen har körts i fler än fyra timmar måste du öppna en supportbiljett hos Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Om jag återställer datatorg, förlorar jag rapporter som jag redan har utformat?

Nej. Dina rapporter lagras i SQL-register som inte påverkas av en återställd data mart. Om du är orolig för att förlora rapporter som du har utformat, kan du backa upp designerna som du inte vill förlora. Om du vill säkerhetskopiera designer öppnar du rapportdesignern och går till **Företag \> Företag \> Byggblock \> Exportera**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Måste alla användare stänga systemet innan jag kan återställa data mart?

Nej. Användarna kan fortsätta arbeta i systemet när data mart återställs. De kan dock inte komma åt rapporter som har skapats med Financial Reporter förrän återställningen är klar.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
