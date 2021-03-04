---
title: Migrering till planeringsoptimering för huvudplanering
description: Det här avsnittet innehåller information om den nya huvudplaneringsmotorn, planeringsoptimering och migrering från den befintliga motorn.
author: ChristianRytt
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 94e5668da45c524ed9ab9eef10b40d0fb5336a65
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646006"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migrering till planeringsoptimering för huvudplanering

[!include [banner](../includes/banner.md)]

Den inbyggda huvudplaneringsmotorn är schemalagd att göras föråldrad (inaktuell). Det ersätts med tillägget planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management. I det här avsnittet finns information om påverkan på nya och befintliga distributioner. Den innehåller information om obligatoriska åtgärder.

Tillägget planeringsoptimering gör det möjligt att utföra beräkningar som händer utanför Supply Chain Management och dess Azure SQL-databas. De fördelar som är kopplade till funktionerna för planeringsoptimering omfattar förbättrad prestanda och minimal inverkan på SQL-databasen under huvudplaneringskörningen. Snabba planeringskörningar kan göras även under kontorstid, så att planerare omedelbart kan reagera på efterfrågan eller parameterändringar.

För mer information om planeringsoptimering, se [planeringsoptimering - översikt](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Föråldring av befintlig huvudplaneringsmotor

Microsoft håller på att göra den inbyggda planeringsmotorn föråldrad i planeringsoptimeringen. Den här ändringen påverkar alla molnmiljöer. Lokala installationer påverkas inte. I version 10.0.16 och senare visas ett felmeddelande om du kör den inbyggda huvudplaneringen utan att generera planerade tillverkningsorder. Huvudplaneringskörningen kommer dock att slutföras trots felmeddelandet.

Mer information om föråldrad för den inbyggda planeringsmotorn finns i meddelanden i [borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migrering, meddelanden och undantag

Ägare av befintliga miljöer som kör den inbyggda huvudplaneringsmotorn utan att generera planerade produktionsorder kommer att få ett e-postmeddelande som innehåller information om undantagsprocessen. Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till planeringsoptimering.

Som nämnts får du ett felmeddelande i version 10.0.16 och senare om du kör den inbyggda huvudplaneringen utan att generera planerade produktionsorder. Det här felmeddelandet innehåller instruktioner om migrering och instruktioner för att begära ett undantag.

### <a name="new-deployments"></a>Nya distributioner

Planeringsoptimeringen ska behandlas som standard huvudplaneringsmotor för alla nya distributioner i molnet. Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen. Om en ny distribution beror på funktioner som inte stöds av planeringsoptimering kan du begära ett undantag så att du kan fortsätta att använda den inbyggda huvudplaneringsmotorn.

### <a name="existing-deployments"></a>Befintliga distributioner

Ägare till befintliga molnbaserade distributioner som är beroende av huvudplaneringen ska migreras till planeringsoptimering. Om din implementering beror på funktioner som inte stöds av planeringsoptimering kan du begära ett undantag så att du kan fortsätta att använda den inbyggda huvudplaneringsmotorn.

För miljöer som för närvarande använder huvudplaneringsprocesser som görs gamla skickar Microsoft ett e-postmeddelande till administratören för miljön. Det här e-postmeddelandet innehåller information om de åtgärder som krävs för att migrera eller begära ett undantag.

## <a name="the-exception-process"></a>Undantagsprocessen

Du kan begära ett undantag om du måste fortsätta att använda den inbyggda huvudplaneringsmotorn, eftersom affärs processerna är beroende av minst en funktion som inte är implementerad i planeringsoptimeringen. En lista över tillgängliga funktioner finns i [Bristanalys för planeringsoptimering](planning-optimization/planning-optimization-fit-analysis.md).

För närvarande är undantag för migrering av planeringsoptimering endast relevanta om din huvudplaneringsprocess inte inkluderar produktion (det vill säga planerade produktionsorder som genereras av huvudplanering) och du behöver den inbyggda huvudplaneringsmotorn utöver version 10.0.15 .

När de nödvändiga funktionerna blir tillgängliga kommer Microsoft att tillhandahålla en respitperiod tills undantaget upphör att gälla. Miljöadministratören kommer att informeras när de nödvändiga funktionerna har blivit tillgängliga och respitperiod har inletts.

> [!NOTE]
> Du kan bara begära ett undantag för produktionsmiljöer, inte för begränsade miljöer. Om du behöver inaktivera undantagsfelet för planeringsoptimeringen i en infrastruktur som en service (IaaS) miljö med begränsat läge kör du SQL-frågan i [begränsade miljöer](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Miljö i begränsade lägen

Kan jag använda inbyggd huvudplanering i min begränsade miljö? Behöver jag ett undantag?

**Svar:** undantag är normalt inte relevant för begränsade miljöer, eftersom undantagsfelet för planeringsoptimering inte förhindrar att den inbyggda huvudplaneringsmotorn körs korrekt. Om felmeddelandet stör dig kan du emellertid inaktivera det på en IaaS (inte Service Fabric) för begränsade miljöer genom att köra följande fråga i databasen:

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

**Svar:** Nej. Ett undantag krävs inte för lokala miljöer. Du kan fortsätta att använda den inbyggda huvudplaneringen. Din miljö administratör kommer att informeras om en åtgärd krävs.

### <a name="production-scenarios"></a>Produktionsscenarier

Vi använder planerade tillverkningsorder, men jag bekymrar mig om vad som kommer att hända när vi uppgraderar till version 10.0.16. Ska jag vidta några åtgärder?

**Svar:** du bör inte bekymra dig. Du kan fortsätta att använda den inbyggda huvudplaneringen i version 10.0.16. Vi rekommenderar dock att du utvärderar om migrering till planeringsoptimering kan starta med den aktuella funktionen. Vi rekommenderar också att du fortsätter att informera dig om nya funktioner.

### <a name="email-from-microsoft"></a>E-post från Microsoft

Vår miljöadministratör har tagit emot ett e-postmeddelande från Microsoft. Det här e-posttillståndet som vi ska migrera till planeringsoptimering eller begära ett undantag. Måste jag utföra några åtgärder?

**Svar:** Ja. Miljön kommer att påverkas om du inte följer instruktionerna i e-postmeddelandet. Du kan antingen migrera till planeringsoptimering efter det angivna datumet eller begära ett undantag med hjälp av länken i e-postmeddelandet. Den här länken öppnar en enkät. När du har skickat och skickat in enkäten får du ett svar via e-post. Trots att den här processen är manuell svarar Microsoft att svara inom en vecka efter det att enkäten har skickats.

### <a name="error-messages"></a>Felmeddelanden

Jag använder version 10.0.16 eller senare och följande felmeddelande visas när jag kör huvudplaneringen. Är huvudplaneringen blockerad?

> Det här felmeddelandet visas eftersom den inbyggda huvudplaneringsmotorn användes för scenarier som stöds vid planeringsoptimering. Du bör migrera till planeringsoptimering nu eftersom den aktuella inbyggda huvudplaneringen är föråldrad. Observera att huvudplaneringskörningen slutfördes utan fel.
>
> Om migreringen har starka beroenden på väntande funktioner kan det krävas ett undantag till fortsatt användning av den inbyggda huvudplaneringsmotorn.
>
> Fyll i följande enkät för att komma igång och om relevant undantag från migreringen till planeringsoptimering.

**Svar:** Nej, huvudplaneringen är inte blockerad. Huvudplaneringskörningen har slutförts och du kan använda resultatet på vanligt sätt. För att undvika att felmeddelandet visas under en framtida huvudplaneringskörning måste du emellertid migrera till planeringsoptimering direkt eller begära ett undantag med hjälp av länken i felmeddelandet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]