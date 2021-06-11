---
title: Välja en dataintegreringsteknik
description: Den här artikeln innehåller information om hur du integrerar med data som hanteras av personal. Här beskrivs olika integreringstekniker som hjälper dig att avgöra vilka tekniker som bäst passar dina behov.
author: andreabichsel
ms.date: 02/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9cfa29272e794b6eee62ae5dd404d8b6339b907c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055158"
---
# <a name="choose-a-data-integration-technology"></a>Välja en dataintegreringsteknik

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller information om hur du integrerar med data som hanteras av Dynamics 365 Human Resources. Här beskrivs olika integreringstekniker som hjälper dig att avgöra vilka tekniker som bäst passar dina behov.

## <a name="data-integration-background"></a>Bakgrund för dataintegrering

Affärsdata är en nyckeltillgång som gör ditt företag unikt. Ditt företags data är mycket värdefulla. Du kan använda relationerna mellan data som samlats in i ditt företag för att förbättra affärsprocesser och affärsstrategier i hela organisationen. Vi strävar efter att ge enkelt, säkert och stabil åtkomst till dina affärsdata oavsett vilket system de kommer från.

Historiskt sett har det varit svårt att integrera data mellan flera system.
Microsoft vidtar åtgärder för att underlätta dataintegrationen och ett stort steg mot det målet realiseras via [Dataverse](/powerapps/maker/common-data-service/data-platform-intro).

Personal gör Dataverse till det föredragna offentliga gränssnittet för personaldata. Med tiden kan vi förvänta dig att alla de viktigaste data som hanteras av personalavdelningen kommer att visas i Dataverse. Vi rekommenderar Dataverse som den teknik som du väljer för de flesta integrerade program.

Vi inser att Dataverse kanske inte redan innehåller alla data som programmet behöver. Vi kan även inse att ditt projekts tidslinje kanske kräver en alternativ teknik. Var noga med att tala om när Dataverse inte passar dina integrationsbehov.

## <a name="integration-technologies"></a>Integrationstekniker

I följande avsnitt beskrivs de olika tekniker för dataintegrering som kan användas med personal.

### <a name="dataverse-tables"></a>Dataverse-register

Dataverse är det rekommenderade allmänna datagränssnittet för personal. Det sammanfaller med Dynamics 365 XRM-plattformen, som används av [Dynamics 365 Customer Engagement](/dynamics365/?panel=customer-engagement#pivot=business-apps)-lösningar.

Dataverse tillhandahåller en plattform och API för dataregister. När du distribuerar personal ansluts den till en Dataverse-instans. Enheterna för personaldata som ska användas i den Dataverse-instansen. Registren och deras data är tillgängliga för alla program som kan ansluta till Dataverse-instansen. Personal synkroniserar data till och från Dataverse-registren.

> [!NOTE]
> Personal-entiteter motsvarar Dataverse-register. Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

När de dataregister som krävs av de integrerande apparna finns i Dataverse, kan du använda [Dataverse och de API:er det stöder fullt ut](/powerapps/?panel=developer#pivot=home). Bland de API:er som stöds [Dynamics 365 webb-API](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), som tillhandahåller en OData-implementering av Dataverse-data.

Dataverse-register och tillhörande API:er är det bästa alternativet för åtkomst till Personal-data från webbprogram, webbtjänster/API:er samt andra program som ansluter till OData-feeds.

> [!NOTE]
> Med beslutet att göra Dataverse till föredraget datagränssnittet för personal relativt nyligen kanske du upptäcker att de dataenheter för personal som du behöver för din integration ännu inte finns i Dataverse.
> </br>
> För en lista över personalenheter som är tillgängliga i Dataverse, se [personal och Dataverse](/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Om de personalenheter som krävs för din integration ännu inte är tillgängliga, måste du vänta på att dataenheterna ska vara tillgängliga eller använda någon av de andra integrationstekniker som beskrivs nedan.
> </br>
> Som standard är Dataverse-integrationen inaktiverad i nya miljöer som inte innehåller de tillhandahållna demodata. Som standard är den aktiverad i nya miljöer där demodata och miljöerna börjar synkronisera data när de är avsedda. När din miljö är redo att synkronisera data kan du aktivera integrationen.

### <a name="dmfdixf-entities"></a>DMF/DIXF-enheter

Personal som huvudsakligen är baserade på samma plattform som Finance and Operations-program, tillhandahåller en [Data Management Framework (DMF)](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json). DMF kallas också för Data Import Export Framework (DIXF). Personal innehåller en uppsättning dataentiteter som du kan använda för att importera och exportera information om personaldata. Medan Dataverse-register är det föredragna dataintegreringsgränssnittet för Personal, är DMF-entiteterna fortfarande användbara i vissa fall, t. ex.:

- Dataverse-register är ännu inte tillgängliga.

- Integrationen kräver bulkdata av dataimport- och exportfunktioner för hög prestanda.

> [!NOTE]
> Personal-entiteter motsvarar Dataverse-register. Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

DMF-entiteterna innehåller för närvarande den mest kompletta datatäckningen för Personal-data.

DMF är inte lämplig för integration i realtid, t.ex. när du behöver omedelbar feedback från användare i ett användargränssnitt. Paketåtgärder är schemalagda batchjobb och har ofta minst en 1-2 minuter lång fördröjning innan batch-tjänsten hämtar jobbet för körning, plus vilken tid som krävs för att slutföra import- och exportåtgärden.

DMF kan vara det bästa alternativet när högt dataflöde krävs (t.ex. en planerad import/export på natten av många tusentals poster).

> [!NOTE]
> DMF är inte tillgänglig för Attract och Onboard.

### <a name="dmf-package-rest-api"></a>DMF-paket REST API

DMF tillhandahåller ett [REST-API](/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) för hantering av datapaket. Detta API kan användas för att programmässigt samverka med DMF och tillåta åtgärder som t.ex.:

- Importera datapaket.

- Exportera datapaket.

- Kontrollera status för en import- och exportåtgärd.

REST API för DMF-paket stöds fullt i Personal.

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

DMF har dessutom en kraftfull funktion (kallat [ta med din egen databas](/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) eller BYOD) som gör att personal kan exportera data till din egen Microsoft Azure SQL-databas. Den här funktionen ger enorm flexibilitet. När data finns i din egen SQL-databas kan du använda alla program eller mellanliggande program som kan ansluta till ett SQL-datalager.

BYOD är i huvudsak en skrivskyddad lösning. Även om du kan ändra och lagra alla data som du vill ha i Azure SQL-databasen (t.ex. för datamashup), kommer data som lagrats i Azure SQL-databasen inte att synkroniseras tillbaka till personal.

BYOD passar för rapporteringslösningar, dataintegrationer, datamashup, som datakälla för en [Azure Data Factory](/azure/data-factory/)-pipeline.

> [!NOTE]
> BYOD är inte tillgänglig för Attract och Onboard.

### <a name="odata-enabled-entities"></a>OData-aktiverade enheter

De flesta DMF-enheterna är också aktiverade för åtkomst via datatjänsten för pesonal (OData). Dokumentationen för [Finance and Operations OData-tjänsten](/dynamics365/unified-operations/dev-itpro/data-entities/odata) gäller för personal, förutom för att skapa egna OData-exponerade enheter.

Medan implementeringen av Dataverse och OData som ges av Dataverse (via [Dynamics 365 webb-API](/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) är föredraget framför datatjänsten för personal, har datatjänsten för personal för närvarande mer fullständig enhetstäckning för personaldata.

### <a name="excel-add-in"></a>Excel-tillägg

[Excel-tillägg](/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json) använder OData-aktiverade enheter under ytan. Det är ett bekvämt sätt för en slutanvändare att hämta och ändra personaldata via det välkända Excel-gränssnittet.

Excel-tillägget är lämpligt för import/export av ad hoc-data av företagsdomänexperter. För en återkommande dataintegrering som kräver programmeringsautomatisering är en annan integreringsteknik lämpligare.

### <a name="data-integrator"></a>Dataintegrerare

Du kan använda [Dataintegrerartjänsten](/powerapps/administrator/data-integrator) för att integrera data till och från Dataverse. Dataintegreraren låter dig definiera integrationsprojekt som ofta baseras på fördefinierade mallar som programutvecklare har anpassat för specifika integrationer. Du kan schemalägga integrationsprojekten kan schemaläggas att köras automatiskt på ett återkommande schema eller köras manuellt.

Dataintegrerarprojekt är lämpliga för Dataverse batch-integration. De är ett bra val för integration mellan programfamiljen Dynamics 365. Microsoft tillhandahåller t.ex. en mall för Dataintegrerare för att integrera data från personal i Dynamics 365 Finance. Du kan lära dig mer om mallen i [integration från Dynamics 365 Human Resources till Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Dataintegrerare stöder [Power Query](/power-query/power-query-what-is-power-query) via dess [avancerade frågefunktion](/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query innehåller kraftfull, flexibel datafiltrering och transformering, inklusive det rika M-formelspråket. Power Query är förmodligen bekant om du har utvecklat Power BI-rapporter.

## <a name="deciding-on-an-integration-technology"></a>Fatta beslut om integrationsteknik

Med så många olika integrationstekniker tillgängliga kan det vara överväldigande att välja vilken integrationsmetod som ska användas. När datatäckningen i Dataverse mognar, kommer beslutet att bli enklare där Dataverse är det föredragna datagränssnittet i de flesta fall. Till dess kan du emellertid hitta det som Dataverse ännu inte uppfyller dina behov. I följande tabell beskrivs några av nyckelegenskaperna i de olika alternativen för integrationsteknik.

| Teknik/verktyg/API    | Återkommande integrationer                   | Synkron/asynkron                    | Programmatisk åtkomst genom en API        | Lämpliga datavolymer                                   | Datatäckning                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Dataverse-register           | Ja, använda dataintegrerare eller mellanprogram | Sync Async, batch (via dataintegrerare) | Ja, via Dynamics 365 webb-API (OData) | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Förbättra<sup>2</sup>                       |
| DMF-entiteter           | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja, till DMF-paket REST API         | Hög (hundratusentals poster)                    | Högt                                |
| DMF-paket REST API   | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja                                       | Hög (hundratusentals poster)                    | API stöder alla DMF-enheter       |
| BYOD                   | Ja, schemalagt av administratör i personal        | Async, batch                                | Nej<sup>3</sup>                                    | Hög (hundratusentals poster)                    | Stöder alla DMF-enheter           |
| OData-aktiverade enheter | Ja, använda mellanprogram                    | Synkronisering                                        | Ja, via datatjänst för personal (OData)  | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Högt                                |
| Excel-tillägg           | Nej                                       | Synkronisering                                        | Nej                                        | Mellan (tiotusentals poster)                      | Stöder alla OData-aktiverade enheter |
| Dataintegrerare        | Ja, schemalagd i dataintegrerare        | Async, batch                                | Nr                                        | Varierar med användningsfall                                       | Stöder alla Dataverse-register           |

<sup>2</sup>Microsoft investerar mycket i att öka datatäckningen för Dataverse-register. Vi rekommenderar att du använder Dataverse när täckning är tillgängligt. För närvarande är Dataverse datatäckning låg jämfört med DMF- och OData-aktiverade entiteter.

<sup>3</sup>SQL-databasen kan öppnas programmässigt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]