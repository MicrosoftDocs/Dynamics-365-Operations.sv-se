---
title: Frågeställningar och svar om publicering
description: Det här avsnittet innehåller en lista med vanliga frågeställningar om hur du arbetar med ett Dynamics 365 Human Resources implementeringsprojekt.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e5b0f58c7ebf03466805d20806316f6f1c32e4a4
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695372"
---
# <a name="go-live-faq"></a>Frågeställningar och svar om publicering 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Det här avsnittet innehåller en lista med vanliga frågeställningar om hur du arbetar med ett Dynamics 365 Human Resources implementeringsprojekt. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>När kan jag konfigurera och begära produktionsmiljön? 

Vanligtvis distribueras en produktionsmiljö när följande kriterier är uppfylla:

- Alla anpassningar är kodslutförda.
- Testning av användargodkännande (UAT) har slutförts.
- Kunden har signerat lösningen.
- Det finns inga blockeringsproblem för publicering. 

När kvalificerade kunder är på det här stadiet arbetar Microsoft FastTrack-teamet med projektgruppen för att utföra en publiceringsutvärdering. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Vilka förutsättningar är nödvändiga för att driftsätta en produktionsmiljö? 

En lista med förutsättningar finns i  [förbereda för publicering](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>Vad är en publiceringsutvärdering?  

Publiceringsutvärdering är en del av  [Microsoft FastTrack-programmet](/dynamics365/fasttrack/). Under den här recensionen bedömer en lösningsarkitekt om ett implementeringsprojekt är klart för en lyckad övergång och publicering. Den här recensionen är obligatorisk för varje implementationsprojekt innan du kan begära att bli aktivt i en produktionsmiljö. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>Våra begränsade miljöer distribueras i det centrala amerikanska datacentret. Vi vill att våra produktionsmiljöer distribueras i det västra amerikanska datacentret. Kan jag välja västra USA som datacenter i min produktionskonfiguration? 

LCS begränsar dig inte från att välja ett annat datacenter när du distribuerar Personal-miljöer, men vi rekommenderar att du inte väljer ett annat datacenter.  

Om du vill att din produktionsmiljö ska finnas i det västra amerikanska datacentret bör du först omdistribuera begränsade miljön till det västra amerikanska datacentret, testa dem och sedan godkänna. 

Information om hur du väljer rätt datacenter finns i [nätverkskrav](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Vilken åtkomstnivå till Azure-resurserna för mina Personal-miljöer?  

Åtkomst till Personal-miljöer är begränsad. Du kan inte komma åt den virtuella datorn (VM) eller Microsoft Internet Information Services (IIS). Du kan inte heller komma åt databasen via Microsoft SQL Server Management Studio. 

Även om du inte kan komma åt dina Azure-resurser eller din Dynamics 365 Human Resources-miljö direkt, finns det fler funktioner som du kan använda för att komma åt dina data:

- Du kan distribuera en Azure SQL-databas i din egen Azure-klient och använda funktionen ta med din egen databas (BYOD) för att synkronisera data. Mer information finns i [ta din egen databas (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).

- Du kan använda Dataverse-integrering för att synkronisera valda enheter i Dataverse-databasen. Mer information finns i [Dataverse-tabeller](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>Hur ofta säkerhetskopieras min produktionsdatabas? 

Databaser skyddas med automatiska säkerhetskopieringar enligt följande frekvenser:

| Typ av säkerhetskopiering | Frekvens |
| --- | --- |
| Fullständig säkerhetskopia av databaser | Varje vecka |
| Säkerhetskopiering av differentiella databaser | Var 12-24 timme |
| Säkerhetskopiering av transaktionslogg | Var 5 till 10 minuter |

Microsoft behåller tillräckliga säkerhetskopior för att tillåta återställning till tidpunkt (PITR) under de senaste 14 dagarna. 

Mer information finns i  [Läs mer om automatisk säkerhetskopiering av SQL databaser](/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>Kan jag begära en kopia av säkerhetskopian av min produktionsdatabas? 

Nr Du kan skicka en servicebegäran om databasuppdatering för att kopiera din produktionsmiljö till miljö i begränsat läge. Du kan distribuera en Azure SQL-databas i din egen Azure-klient och använda BYOD-funktionen för att synkronisera data från din egen produktionsmiljö. Mer information finns i [ta din egen databas (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Hur flyttar jag min miljö i begränsat läge till produktion för publicering? 

Eftersom en kopieringsfunktion inte är tillgänglig för att flytta din miljö från en miljö i begränsat läge till en produktionsmiljö, måste du använda datapaket för att flytta data till din produktionsmiljö.  

Vi rekommenderar att du underhåller en rensad lista med enheter som har konfigurerats i din miljö med begränsat läge i hela projektet. Testa sedan processen för övergång och migrering av alla datapaket som behövs för din publicering. Du måste manuellt flytta alla datapaket till produktionsmiljön när du är redo att publicera. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>Vad ska jag göra om min produktionsmiljö är ur drift? 

Om du vill rapportera ett produktionsavbrott följer du processen som beskrivs i  [rapportera ett produktionsavbrott](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md). 

 ## <a name="see-also"></a>Se även

 [Förbereda publicering](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
