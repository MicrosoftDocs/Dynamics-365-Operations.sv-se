---
title: Översikt över Dynamics 365 Human Resources infrastrukturkoppling
description: I den här artikeln beskrivs den sammanfogade Microsoft Dynamics 365 Human Resources infrastrukturkoppling.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e68b28bfde35b51605aa0b653265da6261b69a90
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819253"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Dynamics 365 Human Resources infrastrukturkoppling 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Human Resources 365

Microsoft Dynamics 365 Human Resources tillhandahåller verktyg som hjälper personalteam att öka organisationens flexibilitet, transformera medarbetarnas erfarenheter och optimera personalprogram för att skapa en arbetsplats där människor och företaget kan frodas. För mer information om Dynamics 365 Human Resources, se [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transformera medarbetarerfarenhet.** Behåll de främsta medarbetarna genom att ge chefer och medarbetare erfarenheter av uppkopplad självbetjäning som driver engagemang och tillväxt.
- **Optimera personalprogram.** Hjälp till att minska driftkostnaderna och skapa personcentrerade tjänstledighets- och frånvaroprogram samt tids-, förmåns- och kompensationshanteringsprogram.
- **Öka organisationens flexibilitet.** Gör det möjligt för personalavdelningen att använda den rörlighet som verksamheten kräver genom att använda Dataverse och Microsoft Power Platform för att centralisera personers data och enkelt utöka Dynamics 365 Human Resources.
- **Upptäcka personalinsikter.** Fatta datadrivna beslut genom att analysera och visualisera personers data på omfattande instrumentpaneler som är tillgängliga på alla enheter.

## <a name="human-resources-infrastructure-merge"></a>Sammanslagning av Human Resources-infrastruktur

Dynamics 365 Human Resources är ett fristående program som för närvarande använder olika infrastrukturer än ekonomi och drift-appar, t.ex. Dynamics 365 Finance eller Dynamics 365 Supply Chain Management. Infrastrukturkopplingen kommer att föra in Dynamics 365 Human Resources i samma infrastruktur som andra appar för ekonomi och drift.

Mer information om sammanslagning av Human Resources-infrastruktur finns i [Slå samman HR-erbjudanden](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Vanliga frågor och svar på vanliga frågor finns i [Vanliga frågor om sammanslagning av Human Resources-infrastruktur](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Kund migrering kontra kundsammanfogning

Som en del av infrastrukturkoppling har alla funktioner i Personal-appen gjorts tillgängliga i ekonomi- och driftsmiljöer. Kunder kan migrera sina personalmiljöer genom att använda migreringsverktyget som är tillgängligt i Microsoft Dynamics Lifecycle Services. De kan också sammanfoga data med befintliga ekonomi- och driftmiljöer. 

Kundmigrering och kundkoppling skiljer sig åt på följande sätt:

- **Kundmigrering** – Den automatiska migreringsverktyget används för att utföra en "Lift and Shift-migrering" (rörelse) av kunddatabasen från Personal-infrastruktur till ekonomi- och driftinfrastrukturen. Resultatet är en ny ekonomi- och driftmiljö som använder kundens Personal-databas. 
- **Sammanfoga kund** – Detta ytterligare steg du inte behöver av Microsoft. Det gör du efter kundens godtyckliga önskemål och i kundens egen tidslinje. Under det här steget flyttas kunddata till en befintlig miljö, till exempel en Ekonomi eller Project Operations-miljö. Den är oftast manuell och kan utföras med hjälp av ramverket för datahantering (DMF) dataentiteter. 

## <a name="planning-a-human-resources-environment-migration"></a>Planera en migreringsmiljö för Personal

Som en del av infrastrukturkoppling måste alla kunder flytta sina befintliga Personalmiljöer från den fristående infrastruktur. Vi rekommenderar att du använder den automatiska migreringsverktyget i Lifecycle Services för att flytta dina aktuella miljöer till den nya infrastrukturen. 

I följande avsnitt finns mer information om hur du använder Lifecycle Services-verktygen för att flytta en fristående Personal-miljö. 

Kunder som planerar en migrering kan ha följande förväntningar:

- Alla kunder måste migrera till en sandbox-miljö innan de kan migrera produktionsmiljön. 
- Med migreringsverktyg går det bara att migrera sandbox till sandbox och migrering av produktion till produktion. Därför bestämmer din miljötyp vilken miljö som kan migreras på rätt sätt. 
- Kunder kan migrera så många sandboxar som behövs innan de flyttar sin produktionsmiljö, förutsatt att det finns en sandbox-målplats. Kunder kan också ta bort en migrerad sandbox och migrera om flera gånger. 
- Om en sandbox-migrering misslyckas, eller om du vill börja om, kan du ta bort en miljö på den ekonomiska och driftinfrastrukturen och migrera om samma miljö.
- URL-adressen till din personalmiljö skiljer sig åt efter migreringen.
- Planera ett lämpligt antal driftstopp för migreringen av din produktionsmiljö. Den uppskattade tidsramen för att slutföra den automatiska migreringsprocessen är tre till fyra timmar. Tidsramen varierar beroende på organisationens data. Du ska validera den tid som krävs under migreringen av dina sandbox-miljöer och tillåta tid för eventuella manuella uppgifter som måste slutföras.

> [!IMPORTANT] 
> När en produktionsmiljö har migrerats till ekonomi- och driftsinfrastrukturen tas den fristående produktionsmiljön automatiskt bort. Du ska inte ta bort den migrerade produktionsmiljön. 

Migreringsprocessen är oftast automatisk. Dina affärsanvändare måste dock utföra några manuella steg och validering efter migreringen.

Följande manuella steg måste slutföras:

- Skapa ett nytt Lifecycle Services-projekt för migrering.
- Ändra eventuella integreringar i din gamla miljö till den nya miljön genom att peka på integrationen till de nya URL-adresserna/slutpunkterna, baserat på varje integrationskonfiguration.
- Uppdatera dataarkivet för inbäddade Power BI-rapporter.
- Uppdatera data entitetslistan från DMF-arbetsytan.
- Länk till Lifecycle Services för hjälp.
- Skapa räkenskapskalendrar.

Under den automatiska processen slutförs följande åtgärder och ska valideras:

- Data:

    - Konfigurationer
    - Säkerhetsroller (inklusive anpassade roller)
    - Arbetsflöden (inklusive aviseringar)
    - Anpassningar och sparade vyer
    - Transaktioner
    - Anpassade fält
    - Bilagor
    - Notifieringar

- Datahantering – Ta med din egen databas (BYOD).
- Funktionshantering – aktiverade/inaktiverade funktioner.
- Inbäddade Power Apps.
- Power Platform administratörscenter kopplad miljö (endast produktion).
- Batchjobb.
- En tom redovisning skapas för varje juridisk person. Standardväxelkurstypen och redovisningsvalutan för varje redovisning ställs in.
- En ny kontoplan skapas automatiskt och länkas till sidan **Redovisning** i varje juridisk enhet. De ekonomiska dimensionerna som konfigureras i personalmiljön läggs automatiskt till i en ny kontostruktur och kopplas till redovisningen. 

> [!NOTE]
> En redovisning krävs i infrastruktur för ekonomi och drift i Dynamics 365 Finance-produkten. Den anpassade dimensionskontrollant som fanns i det Dynamics 365 Human Resources fristående programmet ingen tillgänglig. Den sammanslagna infrastrukturen för Personal beror på Ekonomi-logiken för att visa finansiella dimensioner i modulen **Personal**. Mer information om kontoplanen och ekonomiska dimensioner finns [här](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Att tänka på

- Migrering till miljöer finns alltid i den senaste generellt tillgängliga versionen (GA). Beroende på din migrerings- och testplan bör du, om migreringsvalidering för miljön var i en annan version, validera en migrering av migrering på samma version som din produktionsmiljö. 
- Under migreringen placeras de migrerade miljön i samma region som käll fristående personalmiljöer.

## <a name="licensing"></a>Licensiering

Licenserna för Dynamics 365 Human Resources ändras inte i följande områden: 

- **Minsta licensinköpskrav**
- **Licenser till en produktionsmiljö och en sandbox-miljö** – Om du har befintliga fristående personallicenser som omfattar en produktionsmiljö och en sandbox-miljö, kommer samma antal licenser att vara tillgängliga i ekonomi- och driftinfrastrukturen utan ytterligare kostnader.
- **Ytterligare sandbox-licenser** – Om du har köpt ytterligare sandlådelicenser för den fristående Personal-appen är samma antal sandbox-licenser tillgängliga för en standardmiljö för acceptanstest (sandbox) på ekonomi- och driftsinfrastrukturen, utan extra kostnad. 
