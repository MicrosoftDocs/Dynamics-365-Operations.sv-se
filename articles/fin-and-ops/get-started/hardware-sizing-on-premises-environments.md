---
title: "Krav för beräkning av maskinvara för lokala miljöer"
description: "Detta ämne listar krav för beräkning av maskinvara för lokala miljöer"
author: kfend
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: 5be9b195754d6c8315342c83451128092f64a241
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="hardware-sizing-for-on-premises-environments"></a>Beräkna maskinvara för lokala miljöer
Innan du påbörjar beräkningsprocessen för maskinvara och infrastruktur för en lokal miljö bör du bekanta dig med [systemkrav](system-requirements.md) och [instruktioner för installation och distribution](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md) för att få en djupare förståelse av underliggande infrastruktur. 

  **Obs!** Var mycket uppmärksam på systeminställninganas bästa metod för optimal prestanda. 

När du har granskat dokumentationen startar du processen för uppskattning av transaktionell och samtidig användarvolym och beräknar din miljö baserat på genomsnittlig grundläggande genomflödesberäkning.

## <a name="factors-that-affect-sizing"></a>Faktorer som påverkar beräkning
De faktorer som visas i följande illustration bidrar till beräkning. Ju mer detaljerad information som samlas in, desto mer exakt kan du bestämma beräkning. Maskinvaruberäknning utan stöddata blir sannorlikt felaktig. Absolut minimikravet för nödvändiga data är topptransaktionslinjens belastning per timme. 

[![Beräkna maskinvara för lokala miljöer](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Sett från vänster till höger, är den första och viktigaste faktorn som krävs för att uppskatta beräkning en transaktionsprofil eller transaktionsbeskrivning. Det är viktigt att alltid hitta den högsta transaktionella volymen per timme. Om det finns flera toppperioder, måste dessa perioder fastställas noggrant. 

När du förstår den belastning som påverkar din infrastruktur måste du också ta reda mer om dessa faktorer: 

- **Transaktioner** - Transaktioner har normalt vissa toppar under dagen/veckan. Detta beror oftast på transaktionstypen. Tids- och kostnadsposterna visar vanligtvis toppar en gång i veckan och försäljningsorderposter levereras ofta i bulk via integrering eller droppar in under dagen. 

- **Antalet samtidiga användare** – Antalet samtidiga användare är den näst viktigaste beräkningsfaktorn. Du kan inte tillförlitligt få beräkningsuppskattningar utifrån antalet samtidiga användare, så om detta är de enda data som finns, beräknar du ett ungefärligt nummer och ångrar detta om det finns mer data. En exakt samtidig användardefinition innebär: 
  - Namngivna användare är inte samtidiga användare.
  - Samtidiga användare är alltid en uppsättning namngivna användare. 
  - Högsta belastning definierar högsta samtidighet för beräkning.
 
- Kriterier för samtidiga användare är att användaren uppfyller följande kriterier: 
  - Har loggat in. 
  - Arbetar med transaktioner/förfrågningar vid tidpunkten för inventering. 
  - Inte en inaktiv session. 
 
- **Datasammansättning** – Detta är om hur datorn ställs in och konfigureras. Till exempel hur många juridiska personer som du har, hur många artiklar, hur många olika strukturlistenivåer och hur komplexa dina säkerhetsinställningar kommer att vara. Var och en av de faktorer som kan påverka lite på prestanda, så att dessa faktorer kan avräknas genom att använda avancerade alternativ när det gäller infrastruktur. 

- **Tillägg** – Anpassningar kan vara enkel eller komplex. Antalet anpassningar och komplexitet och användningen har olika påverkan på beräkningen av den infrastruktur som behövs. För komplexa anpassningar är det tillrådligt att genomföra en utvärdering av prestanda så att de inte bara testats för effektivitet utan också att förstå infrastrukturen som behövs. Detta är ännu mer viktigt när tillägg inte är kodade enligt bästa praxis för prestanda och skalbarhet. 

- **Rapportering och analyser** – Dessa faktorer inkluderar normalt körning av tunga frågor mot olika databaser i Finance and Operations-databassystem. Förstå och minska frekvensen när dyra rapporter körs som hjälper dig att förstå vilken inverkan. 

- **Tredjepartslösningar** – Dessa lösningar som t.ex. ISV, har samma konsekvenser och rekommendationer som tillägg. 

## <a name="sizing-your-finance-and-operations-environment"></a>Beräkna Finance and Operation-miljön
För att förstå dina beräkningskrav måste du veta högsta transaktionsvolymen du måste bearbeta. De kompletterande system som Management Reporter eller SSRS, är mindre verksamhetskritiska. Detta innebär att detta dokument innehåller typiska oftast AOS och SQL Server. 

**Anmärkning:** i allmänhet beräknas nivåer skala ut och ska ställas in på N+1-sätt, vilket innebär att om du uppskattar tre AOS, lägger du till ett fjärde AOS. Databasskiktet ska ställas in i en alltid på hög tillgänglighetsinställning. 


## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Beräkning

- 3K till 15K transaktionsrader per timme per kärna på databasserver.
- Typiska AOS-SQL-kärnförhållandet mellan 3:1 för den primära SQL-servern. Ytterligare kärnor krävs utifrån den valda konfigurationen med hög tillgänglighet. 
  - Behandling av databastunga åtgärder kan gå tillbaka till detta 2:1. 
- Följande faktorer påverkar varianter: 
  - Parameterinställningarna används. 
  - Tilläggsnivåer. 
  - Användning av flera funktioner, som t.ex. logg och varningar. Extrema databainloggning kommer att ytterligare minska per timme per kärna under 3K rader. 
  - Komplex datasammansättning – en enkel kontoplanen jämfört med mer detaljerad kontoplan har konsekvenser på genomflödet (exempelvis). 
  - Beskrivning av transaktionen.
  - 2 GB till 4 GB minne, för varje kärna. 
  - Extra databaser på en databasserver som t.ex. Management reporter och SSRS-databaser.
  - Temp DB = 15 % av storleken på DB, med så många filer som fysiska processorer. 
  - SAN-storlek och genomflöde baserat på total samtidig transaktionsvolym/användning. 

### <a name="high-availability"></a>Hög tillgänglighet 
Vi rekommenderar alltid att använda SQL Server i antingen ett kluster eller speglingsinställning. Den sekundära SQL-noden ska ha samma antal kärnor som den primära noden. 

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)
För beräkning av AD FS, se [AD FS serverkapacitetdokumentation](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Ett [beräkningskalkylblad](http://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) är tillgänglig för att planera antalet instanser i distributionen.

<a name="aos-online-and-batch"></a>AOS (Online och batch)
----------------------

### <a name="sizing"></a>Beräkning

- Beräkning efter transaktionsvolym/användning
  - 2K till 6K rader per kärna
  - 16 GB per instans
  - Standardruta – 4 till 24 kärnor
  - 10 till 15 företagsanvändare per kärna
  - 15 till 25 aktivitetsanvändare per kärna
  - 25 till 50 gruppmedlemmar per kärna
- Batch
   - 1 till 4 batchtrådar per kärna
   - Beräkning baserad på batchfönsterkarakterisering
- Observera att AOS, datahantering och batch är på samma roll i Service Fabric. Du behöver beräkna dessa arbetsbelastningar kombinerat, och inte dela dem som i Microsoft Dynamics AX 2012.
- Samma variantfaktorer för SQL Server gäller här.

### <a name="high-availability"></a>Hög tillgänglighet
- Kontrollera att du har minst 1 till 2 fler AOS tillgängliga än du uppskattar.
- Kontrollera att du har minst 3 till 4 virtuella värdar tillgängliga.

## <a name="management-reporter"></a>Management Reporter
I de flesta fall, om de inte används mycket, ska de rekommenderade minimikraven med två noder fungerar bra. I de fall där det inte används mycket behöver du fler än två noder. Ange skala efter behov.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services 
En SSRS-nod kan användas för normal tillgänglighet. Övervaka din SSRS-nod medan du testar och ökar antalet kärnor tillgängliga för SSRS på grundval av behov. Kontrollera att du har en tillgänglig förkonfigurerad sekundär nod på en virtuell värd som är en annan än SSRS VM. Detta är viktigt om det finns ett problem med den virtuella datorn som är värd för SSRS eller den virtuella värden. Om så är fallet behöver du byta ut dem. 

## <a name="environment-orchestrator"></a>Orchestrator-miljö
Orchestrator-tjänsten är en tjänst som hanterar distributionen och relaterad kommunikation med LCS. Denna tjänst används som primär Service Fabric-tjänst och kräver minst tre virtuella maskiner. Denna tjänst är samlokaliserad med Service Fabric-orchestrationtjänsterna. Detta bör beräknas till toppbelastning för klustret. Mer information finns i [Kapacitetsplanering för Service Fabric-kluster](/azure/service-fabric/service-fabric-cluster-capacity).  


## <a name="virtualization-and-oversubscription"></a>Virtualisering och överabonnemang
Missionskritiska tjänster som AOS bör finnas på virtuella värdar som har dedikerade resurser - kärnor, minne och disk.   


