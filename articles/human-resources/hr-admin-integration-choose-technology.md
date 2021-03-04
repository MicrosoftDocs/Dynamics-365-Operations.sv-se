---
title: Välja en dataintegreringsteknik
description: Den här artikeln innehåller information om hur du integrerar med data som hanteras av personal. Här beskrivs olika integreringstekniker som hjälper dig att avgöra vilka tekniker som bäst passar dina behov.
author: andreabichsel
manager: AnnBe
ms.date: 02/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9e6eeac66cff24d193e30aa942039707fc0aed52
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528351"
---
# <a name="choose-a-data-integration-technology"></a>Välja en dataintegreringsteknik

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller information om hur du integrerar med data som hanteras av Dynamics 365 Human Resources. Här beskrivs olika integreringstekniker som hjälper dig att avgöra vilka tekniker som bäst passar dina behov.

## <a name="data-integration-background"></a>Bakgrund för dataintegrering

Affärsdata är en nyckeltillgång som gör ditt företag unikt. Ditt företags data är mycket värdefulla. Du kan använda relationerna mellan data som samlats in i ditt företag för att förbättra affärsprocesser och affärsstrategier i hela organisationen. Vi strävar efter att ge enkelt, säkert och stabil åtkomst till dina affärsdata oavsett vilket system de kommer från.

Historiskt sett har det varit svårt att integrera data mellan flera system.
Microsoft vidtar åtgärder för att underlätta dataintegrationen och ett stort steg mot det målet realiseras via [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Personal gör Common Data Service till det föredragna offentliga gränssnittet för personaldata. Med tiden kan vi förvänta dig att alla de viktigaste data som hanteras av personalavdelningen kommer att visas i Common Data Service. Vi rekommenderar Common Data Service som den teknik som du väljer för de flesta integrerade program.

Vi inser att Common Data Service kanske inte redan innehåller alla data som programmet behöver. Vi kan även inse att ditt projekts tidslinje kanske kräver en alternativ teknik. Var noga med att tala om när Common Data Service inte passar dina integrationsbehov.

## <a name="integration-technologies"></a>Integrationstekniker

I följande avsnitt beskrivs de olika tekniker för dataintegrering som kan användas med personal.

### <a name="common-data-service-entities"></a>Common Data Service-entiteter

Common Data Service är det rekommenderade allmänna datagränssnittet för personal. Det sammanfaller med Dynamics 365 XRM-plattformen, som används av [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement)-lösningar.

Common Data Service tillhandahåller en plattform och API för dataenheter. När du distribuerar personal ansluts den till en Common Data Service-instans. Enheterna för personaldata som ska användas i den Common Data Service-instansen. Enheterna och deras data är tillgängliga för alla program som kan ansluta till Common Data Service-instansen. Personal synkroniserar data till och från Common Data Service-entiteterna.

När de dataentiteter som krävs av de integrerande appar är i Common Data Service, kan du använda dem fullt ut [Common Data Service och de API:er de stöder](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Bland de API:er som stöds [Dynamics 365 webb-API](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), som tillhandahåller en OData-implementering av Common Data Service-data.

Common Data Service-enheterna och tillhörande API:er är det bästa alternativet för åtkomst till personal data från webbprogram, webb tjänster/API:er och andra program som ansluter till OData-feeds.

> [!NOTE]
> Med beslutet att göra Common Data Service till föredraget datagränssnittet för personal relativt nyligen kanske du upptäcker att de dataenheter för personal som du behöver för din integration ännu inte finns i Common Data Service.
</br>
> För en lista över personalenheter som är tillgängliga i Common Data Service, se [personal och Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Om de personalenheter som krävs för din integration ännu inte är tillgängliga, måste du vänta på att dataenheterna ska vara tillgängliga eller använda någon av de andra integrationstekniker som beskrivs nedan.
> </br>
> Som standard är Common Data Service-integrationen inaktiverad i nya miljöer som inte innehåller de tillhandahållna demodata. Som standard är den aktiverad i nya miljöer där demodata och miljöerna börjar synkronisera data när de är avsedda. När din miljö är redo att synkronisera data kan du aktivera integrationen.

### <a name="dmfdixf-entities"></a>DMF/DIXF-enheter

Personal som huvudsakligen är baserade på samma plattform som Finance and Operations-program, tillhandahåller en [Data Management Framework (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json). DMF kallas också för Data Import Export Framework (DIXF). Personal innehåller en uppsättning dataentiteter som du kan använda för att importera och exportera information om personaldata. När Common Data Service enheter är prioriterade dataintegrering gränssnitt för personal, är DMF-enheterna fortfarande användbara i vissa fall, t.ex.:

- Common Data Service entiteter är inte tillgängliga än.

- Integrationen kräver bulkdata av dataimport- och exportfunktioner för hög prestanda.

DMF-enheterna innehåller för närvarande den mest kompletta datatäckningen för personal.

DMF är inte lämplig för integration i realtid, t.ex. när du behöver omedelbar feedback från användare i ett användargränssnitt. Paketåtgärder är schemalagda batchjobb och har ofta minst en 1-2 minuter lång fördröjning innan batch-tjänsten hämtar jobbet för körning, plus vilken tid som krävs för att slutföra import- och exportåtgärden.

DMF kan vara det bästa alternativet när högt dataflöde krävs (t.ex. en planerad import/export på natten av många tusentals poster).

> [!NOTE]
> DMF är inte tillgänglig för Attract och Onboard.

### <a name="dmf-package-rest-api"></a>DMF-paket REST API

DMF tillhandahåller ett [REST-API](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) för hantering av datapaket. Detta API kan användas för att programmässigt samverka med DMF och tillåta åtgärder som t.ex.:

- Importera datapaket.

- Exportera datapaket.

- Kontrollera status för en import- och exportåtgärd.

DMF-paket REST API stöds fullt i personal: Core HR.

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

DMF har dessutom en kraftfull funktion (kallat [ta med din egen databas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) eller BYOD) som gör att personal kan exportera data till din egen Microsoft Azure SQL-databas. Den här funktionen ger enorm flexibilitet. När data finns i din egen SQL-databas kan du använda alla program eller mellanliggande program som kan ansluta till ett SQL-datalager.

BYOD är i huvudsak en skrivskyddad lösning. Även om du kan ändra och lagra alla data som du vill ha i Azure SQL-databasen (t.ex. för datamashup), kommer data som lagrats i Azure SQL-databasen inte att synkroniseras tillbaka till personal.

BYOD passar för rapporteringslösningar, dataintegrationer, datamashup, som datakälla för en [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/)-pipeline.

> [!NOTE]
> BYOD är inte tillgänglig för Attract och Onboard.

### <a name="odata-enabled-entities"></a>OData-aktiverade enheter

De flesta DMF-enheterna är också aktiverade för åtkomst via datatjänsten för pesonal (OData). Dokumentationen för [Finance and Operations OData-tjänsten](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) gäller för personal, förutom för att skapa egna OData-exponerade enheter.

Medan implementeringen av Common Data Service och OData som ges av Common Data Service (via [Dynamics 365 webb-API](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) är föredraget framför datatjänsten för personal, har datatjänsten för personal för närvarande mer fullständig enhetstäckning för personaldata.

### <a name="excel-add-in"></a>Excel-tillägg

[Excel-tillägg](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) använder OData-aktiverade enheter under ytan. Det är ett bekvämt sätt för en slutanvändare att hämta och ändra personaldata via det välkända Excel-gränssnittet.

Excel-tillägget är lämpligt för import/export av ad hoc-data av företagsdomänexperter. För en återkommande dataintegrering som kräver programmeringsautomatisering är en annan integreringsteknik lämpligare.

### <a name="data-integrator"></a>Dataintegrerare

Du kan använda [Dataintegrerartjänsten](https://docs.microsoft.com/powerapps/administrator/data-integrator) för att integrera data till och från Common Data Service. Dataintegreraren låter dig definiera integrationsprojekt som ofta baseras på fördefinierade mallar som programutvecklare har anpassat för specifika integrationer. Du kan schemalägga integrationsprojekten kan schemaläggas att köras automatiskt på ett återkommande schema eller köras manuellt.

Dataintegrerarprojekt är lämpliga för Common Data Service batch-integration. De är ett bra val för integration mellan programfamiljen Dynamics 365. Microsoft tillhandahåller t.ex. en mall för Dataintegrerare för att integrera data från personal i Dynamics 365 Finance. Du kan lära dig mer om mallen i [integration från Dynamics 365 Human Resources till Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Dataintegrerare stöder [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) via dess [avancerade frågefunktion](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query innehåller kraftfull, flexibel datafiltrering och transformering, inklusive det rika M-formelspråket. Power Query är förmodligen bekant om du har utvecklat Power BI-rapporter.

## <a name="deciding-on-an-integration-technology"></a>Fatta beslut om integrationsteknik

Med så många olika integrationstekniker tillgängliga kan det vara överväldigande att välja vilken integrationsmetod som ska användas. När datatäckningen i Common Data Service mognar, kommer beslutet att bli enklare där Common Data Service är det föredragna datagränssnittet i de flesta fall. Till dess kan du emellertid hitta det som Common Data Service ännu inte uppfyller dina behov. I följande tabell beskrivs några av nyckelegenskaperna i de olika alternativen för integrationsteknik.

| Teknik/verktyg/API    | Återkommande integrationer                   | Synkron/asynkron                    | Programmatisk åtkomst genom en API        | Lämpliga datavolymer                                   | Datatäckning                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Common Data Service-entiteter           | Ja, använda dataintegrerare eller mellanprogram | Sync Async, batch (via dataintegrerare) | Ja, via Dynamics 365 webb-API (OData) | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Förbättra<sup>2</sup>                       |
| DMF-entiteter           | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja, till DMF-paket REST API         | Hög (hundratusentals poster)                    | Högt                                |
| DMF-paket REST API   | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja                                       | Hög (hundratusentals poster)                    | API stöder alla DMF-enheter       |
| BYOD                   | Ja, schemalagt av administratör i personal        | Async, batch                                | Nej<sup>3</sup>                                    | Hög (hundratusentals poster)                    | Stöder alla DMF-enheter           |
| OData-aktiverade enheter | Ja, använda mellanprogram                    | Synkronisering                                        | Ja, via datatjänst för personal (OData)  | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Högt                                |
| Excel-tillägg           | Nej                                       | Synkronisering                                        | Nej                                        | Mellan (tiotusentals poster)                      | Stöder alla OData-aktiverade enheter |
| Dataintegrerare        | Ja, schemalagd i dataintegrerare        | Async, batch                                | Nej                                        | Varierar med användningsfall                                       | Stöder alla Common Data Service-enheter           |

<sup>2</sup>Microsoft investerar mycket i att öka datatäckningen för Common Data Service-enheter. Vi rekommenderar att du använder Common Data Service när täckning är tillgängligt. För närvarande är Common Data Service datatäckning låg jämfört med DMF- och OData-aktiverade entiteter.

<sup>3</sup>SQL-databasen kan öppnas programmässigt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]