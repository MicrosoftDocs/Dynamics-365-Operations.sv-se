---
title: "Uppgradera övergångstestning"
description: "Det här avsnittet beskriver hur du kan testa de aktiviteter som inträffar efter att du har stängt av AX 2012, men innan du aktiverar Dynamics 365 för Finance and Operations, Enterprise edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: sv-se
ms.lasthandoff: 06/15/2017

---

# Uppgradera övergångstestning
<a id="upgrade-cutover-testing" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Övergång* är den term som vi använder för slutliga processen för att publicera ett nytt system. Övergångsprocessen består av de aktiviteter som inträffar efter att Microsoft Dynamics AX 2012 har inaktiverats, men innan Microsoft Dynamics 365 för Finance and Operations, Enterprise edition har aktiveras. Syftet med övergångstestning av uppgraderingen är att öva på övergångsprocessen för att garantera en smidig erfarenhet för alla som är involverade under den faktiska övergången till publicering.

Det finns två huvudsakliga arbetsflöden under en övergång:

- **Tekniskt arbetsflöde** – den här arbetsflödet inkluderar datauppgraderingens körningsprocess. Din affärsverksamhet kommer att tvinga fram en gräns för hur långt driftstopp som kan tillåtas. Under driftstoppet kommer varken AX 2012 eller Finance and Operations att vara tillgängliga. Det här arbetsflödet behöver kanske justera datauppgraderingsprocessen så att den uppfyller företagets driftstoppsgräns.
- **Funktionellt arbetsflöde** – det här arbetsflödet innehåller konfigurationsåtgärder som har utförts efter att datauppgraderingen har slutförts. Alla dessa uppgifter skall dokumenteras och kvantifieras och en resurs måste tilldelas dem, eftersom både det funktionella arbetsflödet och det tekniska måste passa in inom företagets driftstoppsgräns.

I följande illustration visas den övergripande processen för övergången till publiceringen som uppstår i produktionsmiljön.

![Övergångsprocess](./media/cutover_1.png)

Den här övergångsprocessen skiljer sig från en uppgradering av grundläggande data i en avgränsad miljö på följande sätt:

- AX 2012-databasen kopieras inte utan säkerhetskopieras enbart och därefter ändras den ursprungliga databasen. Den här metoden är snabbare och säkerhetskopian ger återställning om återställning krävs.
- Eftersom produktionsmiljön för Finance and Operations har begränsad åtkomst utförs de uppgifter som tidigare utfördes på den begränsade instansen av programobjektservern (AOS) nu av Microsoft DSE-team. I dessa uppgifter ingår att hämta och importera bacpac-filen och köra paketet MajorversionDataUpgrade.zip.
- Vi har lagt till följande uppgifter:

    - Utför ett röktest.
    - Utför programmets inställningsuppgifter. Det här steget kan vara stort, beroende på de funktioner som används. I det här steget konfigurerar det funktionella teamet nya programfunktioner så att de är färdiga att användas i det uppgraderade systemet.
    - Tillåt användare igen. Meddela din användarbas att uppgraderingen är slutförd och att de använda systemet igen.

## Tekniskt arbetsflöde
<a id="technical-workstream" class="xliff"></a>

Olika tekniska teammedlemmar ingår i det tekniska arbetsflödet: databasadministratören (DBA), systemadministratören för AX 2012, serveradministratörer och utvecklare som känner till AX 2012 och Finance and Operations. Det här avsnittet förklarar vilka uppgifter som berör de olika rollerna.

Under övergångstestning fokuserar det tekniska teamet på prestanda och tillförlitlighetstestning av datauppgraderingsprocessen för att säkerställa att det uppfyller företagets driftstoppsgräns. Många delar av maskin- och programvarorna är inblandade i processen. Vissa av dessa element är lokala, medan andra finns i Microsoft-molnet. Dessutom omfattas många delar av den anpassade programkoden och standardkoden. Resultatet av detta test bör vara att övergångsprocessen för din miljö är tillförlitlig.

### Inaktivera AX 2012 AOS-instanserna
<a id="turn-off-the-ax-2012-aos-instances" class="xliff"></a>

Denna uppgift omfattar AX 2012-systemadministratören och serveradministratörerna.

Följande områden måste valideras:

- **Batchjobb som körs under övergången** – ett långvarigt batchjobb som redan har börjat köras förhindrar att systemet stoppas. Planera framåt, så att du kan stoppa AOS-instanser vid önskat tillfälle. Du kan behöva schemalägga batcher så att de slutförs en stund innan du inaktiverar AX 2012.
- **Integrerade system** – du kan ha andra system som är integrerad med AX 2012-miljön. Du måste räkna med de här systemen i planen för att inaktivera AX 2012. Du kan behöva inaktivera integrerade system en stund innan du inaktiverar själva AX 2012, så att eventuella återstående pågående transaktioner kan slutföras. Kraven för integrerade system kan variera mycket från företag till företag. Därför måste expertteamet planera för detta separat.

### Skapa en säkerhetskopia av AX 2012-databasen.
<a id="create-a-backup-of-the-ax-2012-database" class="xliff"></a>

Den här uppgiften involverar DBA. Säkerhetskopian ska användas om en återställning krävs. Den används också som en referenspunkt som sparas under en period och visar systemets tillstånd vid tidpunkten för övergången.

Följande områden måste valideras:

- Hämta konkreta tidsinställningar för säkerhetskopieringen.
- Ändra de alternativ för säkerhetskopiering som används (t.ex. komprimering mot icke-komprimering), för att garantera snabbast möjliga säkerhetskopiering.

### Exportera databasen till bacpac
<a id="export-the-database-to-bacpac" class="xliff"></a>

Den här uppgiften involverar DBA. Resultatet av åtgärden är den exportfil som kommer att överföras till Microsoft Azure för det nya systemet.

Följande områden måste valideras:

- Hämta konkreta tidsinställningar för säkerhetskopieringen.
- Optimera exporten för att garantera snabbast möjliga erfarenhet. Optimering kan kräva följande:

    - Mätsystemresurser vid export såsom CPU, i/o-disk och minne.
    - Om flaskhalsar påträffas, skapa en plan för att begränsa dem. Vanligtvis ska du begränsa dessa flaskhalsar genom att tilldela fler av de resurser som krävs.

### Överföra bacpac-filen till Azure-lagring
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

Detta berör DBA eller serveradministratörerna. Under den här uppgiften överförs bacpac-filen till Azure.

Följande områden måste valideras:

- Välj den dator som ska användas för överföring och se till att utforskningsverktyget för Azure Storage är konfigurerat och färdigt att användas.
- Hämta konkreta tidsinställningar för överföringen genom att mäta dem flera gånger. Överföringstider varierar beroende på hastigheten på din Internetanslutning och det geografiska läget i förhållande till Azure-datacentret.

### Hämta och importera bacpac-filen till Azure SQL-databasen
<a id="download-and-import-the-bacpac-file-to-the-azure-sql-database" class="xliff"></a>

När den här uppgiften publiceras utförs den av Microsoft DSE-teamet. Under överföringstestet berörs dock din databasadministratör. Resultatet av åtgärden är den exportfil som kommer att överföras till Azure för det nya systemet.

Följande områden måste valideras:

- Hämta konkreta tidsinställningar för importen.
- Optimera exporten för att garantera snabbast möjliga erfarenhet. Optimering kan kräva följande:

    - Mät systemresurser vid exporten. Nedan följer några exempel:

        - **På AOS-datorn:** CPU, diskens i/o och minne
        - **På Azure SQL-databasinstansen:** genomflöde av SQL-databasen (DTU). Du kan övervaka Azure SQL DTU från Microsoft SQL Server Management Studio på AOS-maskinen genom att titta på systemvyn sys.dm_resource_stats.

    - Om flaskhalsar påträffas, skapa en plan för att begränsa dem. Vanligtvis ska du begränsa dessa flaskhalsar genom att tilldela fler av de resurser som krävs. Eftersom Microsoft är värd för den här datorn måste du skicka en begäran till Microsoft för att öka resurser om du har identifierat dem som en flaskhals.

### Köra paketet MajorVersiondataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

När den här uppgiften publiceras utförs den av Microsoft DSE-teamet. Under överföringstestet berörs dock utvecklarna. I den här uppgiften omvandlas den gamla databasstrukturen till strukturen för det nya systemet.

Databassynkroniseringen körs som en del av den här uppgiften. Databassynkroniseringen kan ta lång tid i vissa situationer, t ex när ett grupperat index har ändrats i en tabell eftersom åtgärden är en kostsam åtgärd i SQL.

Vi rekommenderar starkt att du först utför analysen och felsökningsprocessen i en utvecklingsmiljö. I en avgränsad miljö är alternativen för felsökning och analys mer begränsad. Målet är att ha få eller inga problem som måste lösas när du utför övergångstestning.

Följande områden måste valideras:

- Hämta konkreta tidsinställningar för importen.
- Optimera processen för att garantera snabbast möjliga erfarenhet. Optimering kan kräva följande:

    - Övervaka prestanda för enskilda uppgraderingsskript via tabellen ReleaseUpdateScriptsExecution.
    - Justera skript om du vill optimera prestandan. Uppgiften kanske kräver att du anpassar ett skripts X++-kod för att optimera den för din datauppsättning.
    - Övervaka Azure SQL DTU genom att använda Microsoft Dynamics Lifecycle Services (LCS)-övervakning eller sys.dm_resources_stats-systemvyn i Management Studio. Om resurser är utmaximerade kan du behöva begära en högre databasnivå från Microsoft DSE-team.

### Återställa till AX 2012
<a id="roll-back-to-ax-2012" class="xliff"></a>

Målet med den här uppgiften är att återställa databasen med hjälp av den säkerhetskopia som skapades när AX 2012 var inaktiverat och sedan aktivera AX 2012 på nytt. Statusen för integrerade system kan också behöva återställas. Eftersom integrerade system varierar från företag till företag, måste du planera för det här scenariot separat, baserat på dina specifika omständigheter. Även om det är osannolikt att du måste återställa är det mycket viktigt att du har en testad process om du skulle behöva det.

## Funktionellt arbetsflöde
<a id="functional-workstream" class="xliff"></a>

När data har uppgraderats krävs flera konfigurationsåtgärder i den nya miljön. Målet med det här arbetsflödet är att dokumentera och kvantifiera alla konfigurationsåtgärder och tilldela en resurs till varje uppgift för att garantera att dessa uppgifter kan utföras tillsammans med det tekniska arbetsflödet under driftstoppstiden.

Vanligtvis omfattas funktionella uppgifter en ändring av värden för specifika systemparametrar eller andra konfigurationsdata. Dessa uppgifter identifieras via det fullständiga funktionella testpasset som en separat aktivitet från övergångstestningen. När en uppgift av den här typen identifierats ska den granskas tillsammans med den funktionella resursen och utvecklaren.

Större ändringar kanske kräver att ett nytt anpassat datauppgraderingsskript skrivs för att uppdatera data under datauppgraderingen. Den funktionella resursen kan dock köra mindre ändringar manuellt genom det nya systemet efter datauppgraderingen.

Större ändringar med nya datauppgraderingsskript måste testas. Därför måste en eller flera extra upprepningar av paketet MajorVersionDataUpgrade.zip köras. Det är viktigt att du jämför kostnaden för att köra paketet igen med kostnaden för manuell inmatning.

För varje manuell ändring måste en aktivitet läggas till i dokumentet med planen för övergången. Den här uppgiften måste visa följande information:

-   Vad är uppgiften och vad måste göras?
-   Vem måste göra detta?
-   Hur lång tid tar det?

