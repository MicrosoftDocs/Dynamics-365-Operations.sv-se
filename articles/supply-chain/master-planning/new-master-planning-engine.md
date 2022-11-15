---
title: Migrering till Planeringsoptimering för huvudplanering
description: Denna artikel innehåller information om den nya huvudplaneringsmotorn, Planeringsoptimering samt migrering från den befintliga motorn.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: dbbc58f0dcd833f63e84a73ac68ada60bd0c291d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739962"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migrering till Planeringsoptimering för huvudplanering

[!include [banner](../includes/banner.md)]

Den inbyggda huvudplaneringsmotorn är schemalagd att göras föråldrad (inaktuell). Det ersätts med tillägget Planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management. I denna artikel finns information om påverkan på nya och befintliga distributioner. Den innehåller information om obligatoriska åtgärder.

Tillägget Planeringsoptimering gör det möjligt att utföra beräkningar som händer utanför Supply Chain Management och dess Azure SQL-databas. De fördelar som är kopplade till funktionerna för Planeringsoptimering omfattar förbättrad prestanda och minimal inverkan på SQL-databasen under huvudplaneringskörningen. Snabba planeringskörningar kan göras även under kontorstid, så att planerare omedelbart kan reagera på efterfrågan eller parameterändringar.

För mer information om Planeringsoptimering, se [Systemarkitektur för huvudplanering](master-planning-architecture.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Föråldring av befintlig huvudplaneringsmotor

Microsoft håller på att göra den inaktuella huvudplaneringsmotorn föråldrad i Planeringsoptimeringen. Den här ändringen påverkar alla molnmiljöer. Lokala installationer påverkas inte. I version 10.0.16 och senare visas ett felmeddelande om du kör den inaktuella huvudplaneringsmotorn utan att generera planerade tillverkningsorder. Huvudplaneringskörningen kommer dock att slutföras trots felmeddelandet.

Mer information om föråldrad för den inaktuella huvudplaneringsmotorn finns i meddelanden i [borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migrering, meddelanden och undantag

Ägare av befintliga miljöer som kör den inaktuella huvudplaneringsmotorn utan att generera planerade produktionsorder kommer att få ett e-postmeddelande som innehåller information om undantagsprocessen. Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till Planeringsoptimering.

Som nämnts får du ett felmeddelande i version 10.0.16 och senare om du kör den inaktuella huvudplaneringsmotorn utan att generera planerade produktionsorder. Det här felmeddelandet innehåller instruktioner om migrering och instruktioner för att begära ett undantag.

### <a name="new-deployments"></a>Nya distributioner

Planeringsoptimeringen ska behandlas som standard huvudplaneringsmotor för alla nya distributioner i molnet. Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen. Om en ny distribution beror på funktioner som inte stöds av Planeringsoptimering kan du begära ett undantag så att du kan fortsätta att använda den inaktuella huvudplaneringsmotorn.

### <a name="existing-deployments"></a>Befintliga distributioner

Ägare till befintliga molnbaserade distributioner som är beroende av huvudplaneringen ska migreras till Planeringsoptimering. Om din implementering beror på funktioner som inte stöds av Planeringsoptimering kan du begära ett undantag så att du kan fortsätta att använda den inaktuella huvudplaneringsmotorn.

För miljöer som för närvarande använder huvudplaneringsprocesser som görs gamla skickar Microsoft ett e-postmeddelande till administratören för miljön. Det här e-postmeddelandet innehåller information om de åtgärder som krävs för att migrera eller begära ett undantag.

## <a name="the-exception-process"></a>Undantagsprocessen

Du kan begära ett undantag om du måste fortsätta att använda den inaktuella huvudplaneringsmotorn, eftersom affärs processerna är beroende av minst en funktion som inte är implementerad i Planeringsoptimeringen. En lista över tillgängliga funktioner finns i [Bristanalys för Planeringsoptimering](planning-optimization/planning-optimization-fit-analysis.md).

För närvarande är undantag för migrering av Planeringsoptimering endast relevanta om din huvudplaneringsprocess inte inkluderar produktion (det vill säga planerade produktionsorder som genereras av huvudplanering) och du behöver den inaktuella huvudplaneringsmotorn utöver version 10.0.15 .

När de nödvändiga funktionerna blir tillgängliga kommer Microsoft att tillhandahålla en respitperiod tills undantaget upphör att gälla. Miljöadministratören kommer att informeras när de nödvändiga funktionerna har blivit tillgängliga och respitperiod har inletts.

Flödesschemat nedan sammanfattar informationen i denna artikel så att du snabbt kan ta reda på om du bör begära ett undantag. Om du behöver begära ett undantag kan du fylla i och skicka in enkäten [Planera optimeringsmigrering och undantag](https://go.microsoft.com/fwlink/?linkid=2144962). Produktgruppen ansvarar för att utvärdera och godkänna varje undantagsbegäran, så skicka din begäran direkt till produktgruppen med länken och skapa ingen supportbegäran för den. Om din begäran avvisas ska du inte skapa en supportbegäran eftersom Microsoft Support inte kan utvärdera eller bevilja undantag på nytt.

![Flödesschema för undantag.](media/exception-diagram.png "Flödesschema för undantag")

> [!NOTE]
> Du kan endast begära ett undantag för klientorganisationer som för närvarande inkluderar, eller kommer att omfatta, en produktionsmiljö, ej endast klientorganisationer med enbart sandbox-miljöer. Om du behöver inaktivera undantagsfelet för Planeringsoptimeringen i en infrastruktur som en service (IaaS) miljö med begränsat läge kör du SQL-frågeställningen i [begränsade miljöer](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Miljö i begränsade lägen

Kan jag använda inaktuella huvudplaneringsmotorn i min begränsade miljö? Behöver jag ett undantag?

**Svar:** undantag är normalt inte relevant för begränsade miljöer, eftersom undantagsfelet för Planeringsoptimering inte förhindrar att den inaktuella huvudplaneringsmotorn körs korrekt. Om felmeddelandet stör dig kan du emellertid inaktivera det på en IaaS (inte Service Fabric) för begränsade miljöer genom att köra följande fråga i databasen:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Lokala miljöer

Min miljö är lokal Behöver jag ett undantag?

**Svar:** Nej. Ett undantag krävs inte för lokala miljöer. Du kan fortsätta att använda den inaktuella huvudplaneringsmotorn. Din miljö administratör kommer att informeras om en åtgärd krävs.

### <a name="production-scenarios"></a>Produktionsscenarier

Vi använder planerade tillverkningsorder, men jag bekymrar mig om vad som kommer att hända när vi uppgraderar till version 10.0.16. Ska jag vidta några åtgärder?

**Svar:** du bör inte bekymra dig. Du kan fortsätta att använda den inaktuella huvudplaneringsmotorn i version 10.0.16. Vi rekommenderar dock att du utvärderar om migrering till Planeringsoptimering kan starta med den aktuella funktionen. Vi rekommenderar också att du fortsätter att informera dig om nya funktioner.

### <a name="email-from-microsoft"></a>E-post från Microsoft

Vår miljöadministratör har tagit emot ett e-postmeddelande från Microsoft. Det här e-posttillståndet som vi ska migrera till Planeringsoptimering eller begära ett undantag. Måste jag utföra några åtgärder?

**Svar:** Ja. Miljön kommer att påverkas om du inte följer instruktionerna i e-postmeddelandet. Du kan antingen migrera till Planeringsoptimering efter det angivna datumet eller begära ett undantag med hjälp av länken i e-postmeddelandet. Den här länken öppnar en enkät. När du har skickat och skickat in enkäten får du ett svar via e-post. Trots att den här processen är manuell svarar Microsoft att svara inom en vecka efter det att enkäten har skickats.

### <a name="error-messages"></a>Felmeddelanden

Jag använder version 10.0.16 eller senare och följande felmeddelande visas när jag kör huvudplaneringen. Är huvudplaneringen blockerad?

> Det här felmeddelandet visas eftersom den inaktuella huvudplaneringsmotorn användes för scenarier som stöds vid Planeringsoptimering. Du bör migrera till Planeringsoptimering nu eftersom den aktuella inaktuella huvudplaneringen är föråldrad. Observera att huvudplaneringskörningen slutfördes utan fel.
>
> Om migreringen har starka beroenden på väntande funktioner kan det krävas ett undantag till fortsatt användning av den inaktuella huvudplaneringsmotorn.
>
> Fyll i följande enkät för att komma igång och om relevant undantag från migreringen till Planeringsoptimering.

**Svar:** Nej, huvudplaneringen är inte blockerad. Huvudplaneringskörningen har slutförts och du kan använda resultatet på vanligt sätt. För att undvika att felmeddelandet visas under en framtida huvudplaneringskörning måste du emellertid migrera till Planeringsoptimering direkt eller begära ett undantag med hjälp av länken i felmeddelandet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
