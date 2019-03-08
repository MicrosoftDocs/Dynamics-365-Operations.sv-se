---
title: Batchbearbetning av notifieringar
description: Det här avsnittet innehåller information om batchbearbetning av notifieringar i Microsoft Dynamics 365 for Finance and Operations.
author: tjvass
manager: AnnBe
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 482cf30b4f82e8801ebc12e3925c1efb09f7eb1e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341935"
---
# <a name="batch-processing-of-alerts"></a>Batchbearbetning av notifieringar

[!include [banner](../includes/banner.md)]

Notifieringar bearbetas med funktionen för batchbearbetning i Microsoft Dynamics 365 for Finance and Operations. Du måste ställa in batchbearbetning innan notifieringar ska kunna skickas.

Finance and Operations stöder två typer av händelser:

- Händelser som utlöses av ändringsbaserade händelser. Dessa händelser kallas för skapa/ta bort- och uppdateringshändelser.
- Händelser som utlöses av förfallodatum.

Du kan ställa in batchprocesser för varje typ av händelser.
        
## <a name="batch-processing-for-change-based-events"></a>Batchbearbetning för ändringsbaserade händelser

Finance and Operations läser alla ändringsbaserade händelser som har inträffat sedan batchbearbetningen senast kördes. Ändringsbaserade händelser innefattar uppdateringar av fält, borttagning av poster och skapande av poster. Händelserna jämförs med de villkor som har ställts in i notifieringsreglerna. Batchprocessen skapar en notifiering när en händelse matchar regelvillkoren.

### <a name="frequency-for-change-based-events"></a>Frekvens för ändringsbaserade händelser

För ändringsbaserade händelser kan du ställa in ett batchjobb som utlöser beabetningen av en händelse en kort tid efter det att händelsen loggats av systemet. Om du ställer in batchjobbet till att återkomma oftare får användare notifieringarna tidigare efter utförda ändringar. En hög frekvens för batchbearbetning kan påverka systemets prestanda allvarligt.

Å andra sidan kan ett batchjobb som återkommer oftare, och som är tidsplanerat för tider när systembelastningen är låg, bidra till att förbättra systemets prestanda. En låg frekvens för batchbearbetning kanske inte uppfyller användarnas behov av snabba notifieringar.

När du ställer in frekvensen för av batchbearbetning för ändringsbaserade händelser bör du se till att det finns en balans mellan tidslinjerna för notifieringarna och hela systemets prestanda. Dessa överväganden blir mer relevanta allt eftersom antalet användare som skapar varningsregler ökar. Frekvensen påverkar inte antalet händelser som måste bearbetas. Men om fler användare skapar regler, måste fler kontroller utföras. Den här typen av datautbyte kan påverka systemets prestanda.

#### <a name="the-risks-of-low-batch-frequency"></a>Riskerna med låg batchfrekvens

Om du ställer in en låg frekvens för batchbearbetning för ändringsbaserade händelser kan data som är relevanta för villkoren i notifieringsreglerna ändras innan batchen behandlas. Därför kanske du förlorar notifieringar.

En notifieringsregel ställs till exempel in på att utlösa en notifiering när händelsen **kundkontakten ändras** och villkoret är **kund = BB**. Med andra ord, om kundkontakten för kund BB ändras kommer händelsen att loggas. Emellertid ställs batchbearbetningssystemet in så att batchbearbetning uppstår mer sällan än datainmatning. Om kundens namn ändras från **BB** till **AA** innan händelsen bearbetas kommer data i databasen inte längre att matcha data i regeln **kund = BB**. Därför när händelsen slutligen bearbetas skapas ingen notifiering.

### <a name="set-up-processing-for-change-based-alerts"></a>Ställa in bearbetning för ändringsbaserade notifieringar

1. Gå till **Systemadministration**&gt;**Periodiska uppgifter**&gt;**Notifieringar**&gt;**Ändringsbaserade notifieringar**.
2. I dialogrutan **Ändringsbaserade notifieringar**, ange lämplig information.

## <a name="batch-processing-for-due-date-events"></a>Batchbearbetning för händelser med förfallodatum

Finance and Operations hittar alla händelser som orsakas av förfallodatum och dessa händelser jämförs med de villkor som har ställts in i notifieringsreglerna. Batchprocessen skapar en notifiering när en händelse matchar regelvillkoren.

### <a name="frequency-for-due-date-events"></a>Frekvens för händelser med förfallodatum

För händelser med förfallodatum vill du kanske ställa in batchjobb som körs under natten eller vid specifika tidpunkter på dagen för att balansera systembelastningen. Vi rekommenderar att du ställer in batchjobbet så att det körs minst en gång per dag. Om notifieringar ska skickas så tidigt som möjligt, ställer du in batchbearbetningen till att utföras omedelbart efter att systemdatumet ändras. Om du vill skapa notifieringar för händelser för förfallodatum som inträffar efter att ett batchjobb har bearbetat notifieringar, kan du köra batchjobbet igen samma dag.

Till exempel har ett batchjobb körts under en viss dag. Du kan sedan skapa en inköpsorder som har ett förfallodatum som ska utlösa en notifiering samma dag. Om du vill få notifieringen den dagen, måste du köra batchjobbet igen när inköpsordern skapas. Om du inte kör batchjobbet en gång till den dagen, hittar följande dags batchjobb eventuella händelser med förfallodatum som inte bearbetade under föregående dagar.

> [!NOTE]
> Även när batchprocessen körs mer än en gång per dag, skapas notifieringarna inte två gånger för samma händelse för förfallodatum och villkor. Notifieringar skapas endast för datum som förfallit på grund av ändringar i systemet som efter det att den senaste batchjobbet kördes.

### <a name="batch-processing-window"></a>Batchbearbetningsfönster

Bearbetningen av notifieringsregler i ett företag kan stoppas av flera skäl. Dessa orsaker omfattar semester, systemfel eller andra problem som förhindrar att batchjobb körs under en viss tid.

Om du vill förhindra att notifieringar med förfallodatum blir föråldrade på grund av att batchjobbet inte har körts i flera dagar kan du ställa in ett batchbearbetningsfönster. Ett batchbearbetningsfönster kan användas för att förhindra att ett batchjobb körs under ett visst antal dagar.

Om du ställer in ett batchbearbetningsfönstret skickas en notifiering när notifieringsregeln bearbetas även om notifieringen överskrider tidsgränsen som definierats i kriteriet för förfallodatumet. En notifiering fortsätter att skickas så länge den inte överskrider den period som definieras av denna tidsgräns plus batchbearbetningsfönstret. En notifiering skickas emellertid inte längre när perioden som definieras av tidsgränsen plus batchbearbetningsfönstret överskrids.

### <a name="set-up-processing-for-due-date-alerts"></a>Ställa in bearbetning för notifieringar för förfallodatum

1. Gå till **Systemadministration**&gt;**Periodiska uppgifter**&gt;**Notifieringar**&gt;**Notifieringar om förfallodatum**.
2. I dialogrutan **Notifieringar om förfallodatum**, ange lämplig information.
