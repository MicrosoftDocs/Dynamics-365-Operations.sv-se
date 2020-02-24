---
title: Välj en dataintegreringsteknik
description: Den här artikeln innehåller vägledning om olika alternativ för integration med data som hanteras av personal och som beskriver egenskaperna hos olika integrationstekniker så att integrerare kan fatta välgrundade beslut om vilka tekniker som passar bäst deras behov.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029898"
---
# <a name="choose-a-data-integration-technology"></a>Välj en dataintegreringsteknik

Dynamics 365 Human Resources hanterar affärsdata som är användbara i en mängd olika affärsprocesser. Den här artikeln innehåller vägledning om olika alternativ för integration med data som hanteras av personal och som beskriver egenskaperna hos olika integrationstekniker så att integrerare kan fatta välgrundade beslut om vilka tekniker som passar bäst deras behov.

## <a name="data-integration-vision"></a>Dataintegreringsvision

Microsoft ser affärsdata som en nyckeltillgång som gör ditt företag unikt. Ditt företags data är mycket värdefulla. Data som samlas in och underhålls av en del av verksamheten relaterar till data som samlas in av en annan del av verksamheten och dessa relationer kan användas för att förbättra affärsprocesser och affärsstrategier i hela organisationen. Ger enkel, säker och stabil åtkomst till dina affärsdata, oavsett vilket system som "äger" informationen är en nyckelprincip för den vision vi har för dataintegrering med personal.

Historiskt sett har det varit svårt att integrera data mellan flera system.
Microsoft vidtar åtgärder för att underlätta dataintegrationen och ett stort steg mot det målet realiseras via [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Framöver gör personal Common Data Service till det föredragna offentliga gränssnittet för personaldata. Med tiden kan vi förvänta dig att alla de viktigaste data som hanteras av personalavdelningen kommer att visas i Common Data Service. Vi rekommenderar Common Data Service som den teknik som du väljer för de flesta integrerade program. Samtidigt som vi inser att inte alla data som programmet behöver finns i Common Data Service och att dina projekt tidslinjer kan kräva en alternativ teknik, kan du meddela oss när Common Data Service inte uppfyller dina integrationsbehov.

## <a name="integration-technologies"></a>Integrationstekniker

I följande avsnitt beskrivs de olika tekniker för dataintegrering som kan användas med personal.

### <a name="common-data-service-entities"></a>Common Data Service-entiteter

Common Data Service är det rekommenderade allmänna datagränssnittet för personal. Common Data Service är byggd på en mogen plattform som har vuxit ut ur Dynamics 365 "XRM"-plattformen, där [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement)-lösningarna är byggda.

Common Data Service tillhandahåller en plattform för data enheter och ett API för åtkomst till dessa enheter. När personal distribueras i din organisation är personal anslutna till en Common Data Service-instans och de enheter som underhåller de personal distribueras till den Common Data Service-instansen, vilket gör enheterna och deras data tillgängliga för alla program som kan ansluta till Common Data Service-instansen. Beroende på vilka typer av personalavdelning du använder, utför personaluppgifter antingen dataoperationer direkt mot Common Data Service-enheterna (detta är fallet för Attract och vara Onboard) eller synkroniserar data till/från Common Data Service-enheterna.

När de dataenheter som visar de data som dina integrationsprogram kräver finns i Common Data Service kan du använda [Common Data Service och API:er som den stöder](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Bland de API:er som stöds [Dynamics 365 webb-API](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), som tillhandahåller en OData-implementering av Common Data Service-data.

Common Data Service-enheterna och tillhörande API: er är det bästa alternativet för åtkomst till personal data från webbprogram, webb tjänster/API:er och andra program som ansluter till OData-feeds.

> [!NOTE]
> Med beslutet att göra Common Data Service till föredraget datagränssnittet för personal relativt nyligen kanske du upptäcker att de dataenheter för personal som du behöver för din integration ännu inte finns i Common Data Service<sup>1</sup>. Om de personalenheter som krävs för din integration ännu inte är tillgängliga, måste du vänta på att dataenheterna ska vara tillgängliga eller använda någon av de andra integrationstekniker som beskrivs nedan.
> 
> Som standard är Common Data Service-integrationen inaktiverad i nya miljöer som inte innehåller de tillhandahållna demodata. Som standard är den aktiverad i nya miljöer där demodata och miljöerna börjar synkronisera data när de är avsedda. När din miljö är redo att synkronisera data kan du aktivera integrationen.

<sup>1</sup>För en lista över personalenheter som är tillgängliga i Common Data Service finns i [personal och Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). För Attract och Onboard är alla enheter tillgängliga i Common Data Service.

### <a name="dmfdixf-entities"></a>DMF/DIXF-enheter

Personal som huvudsakligen används på samma plattform som Finance and Operations-program, tillhandahåller en [Data Management Framework (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), som ibland också kallas dataimport ramverket eller DIXF och en uppsättning data enheter som kan användas för import/export av data till/från personal. När Common Data Service enheter är prioriterade dataintegrering gränssnitt för personal, är DMF-enheterna fortfarande användbara i vissa fall, t.ex.:

- Common Data Service entiteter är inte tillgängliga än.

- Integrationen kräver bulkdata av dataimport- och exportfunktioner för hög prestanda.

DMF-enheterna innehåller för närvarande den mest kompletta datatäckningen för personal.

DMF är inte lämplig för real tids integration (t.ex. när direkt användar återrapportering i ett användargränssnitt krävs), eftersom paket operationer är schemalagda batchjobb och har ofta minst en fördröjning på 1-2 minuter innan batch-tjänsten hämtar jobbet för körning, plus vilken tid som krävs för att slutföra import- och exportåtgärden.

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

DMF har dessutom en kraftfull funktion (vanligen kallat [ta med din egen databas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) eller BYOD) som gör att personal kan exportera data till din egen Microsoft Azure SQL-databas. Detta ger en enorm flexibilitet eftersom när data finns i din egen SQL-databas kan du använda alla program eller mellanliggande program som kan ansluta till ett SQL-datalager.

BYOD bör i allmänhet betraktas som en skrivskyddad lösning. Även om du kan ändra och lagra alla data som du vill ha i Azure SQL-databasen (t.ex. för datamashup), kommer data som lagrats i Azure SQL-databasen inte att synkroniseras tillbaka till personal.

BYOD passar för rapporteringslösningar, dataintegrationer, datamashup, som datakälla för en [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/)-pipeline.

> [!NOTE]
> BYOD är inte tillgänglig för Attract och Onboard.

### <a name="odata-enabled-entities"></a>OData-aktiverade enheter

De flesta DMF-enheterna är också aktiverade för åtkomst via datatjänsten för pesonal (OData). Dokumentationen för tjänsten för [Finance and Operations OData-tjänst](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) är i allmänhet också tillämplig på personal, men dokumentation om att skapa egna OData-exponerade enheter kommer inte att tillämpas.

Medan implementeringen av Common Data Service och OData som ges av Common Data Service (via [Dynamics 365 webb-API](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) är föredraget framför datatjänsten för personal, har datatjänsten för personal för närvarande mer fullständig enhetstäckning för personaldata.

### <a name="excel-add-in"></a>Excel-tillägg

[Excel-tillägg](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) använder OData-aktiverade enheter under ytan. Det är ett bekvämt sätt för en slutanvändare att hämta och ändra personaldata via det välkända Excel-gränssnittet.

Excel-tillägget är lämpligt för import/export av ad hoc-data av företagsdomänexperter. För en återkommande dataintegrering som kräver programmeringsautomatisering är en annan integreringsteknik lämpligare.

### <a name="data-integrator"></a>Dataintegrerare

Administratörserfarenheten för Common Data Service ger [tjänsten dataintegrerare](https://docs.microsoft.com/powerapps/administrator/data-integrator) som kan användas för dataintegrering till/från Common Data Service. Dataintegreraren kan användas för att definiera integrationsprojekt (som ofta baseras på fördefinierade mallar som programutvecklare har anpassat för specifika integrationer). Integrationsprojekten kan schemaläggas att köras automatiskt på ett återkommande schema eller köras manuellt.

Dataintegrationsprojekt är lämpliga för Common Data Service batch-integreringar och utgör ett bra val för integration mellan programfamiljen Dynamics 365. Microsoft tillhandahåller t.ex. en standardmall för Dataintegrerare som kan användas för att integrera data från personal i Dynamics 365 Finance. Mer information finns i [Integration från Dynamics 365 Human Resources till Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Dataintegrerare stöder även [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (via dess [avancerade frågefunktion](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
Power Query innehåller kraftfull, flexibel datafiltrering och transformering, inklusive det rika M-formelspråket och kommer sannolikt att vara bekant för dem som har erfarenhet av att utveckla Power BI-rapporter.

## <a name="deciding-on-an-integration-technology"></a>Fatta beslut om integrationsteknik

Med så många olika integrationstekniker tillgängliga kan det vara överväldigande att välja vilken integrationsmetod som ska användas. Med tiden, och särskilt när datatäckningen i Common Data Service mognar, kommer beslutet att bli enklare där Common Data Service är det föredragna datagränssnittet i de flesta fall. Till dess kan du emellertid hitta det som Common Data Service ännu inte uppfyller dina behov. I följande tabell beskrivs några av nyckelegenskaperna i de olika alternativen för integrationsteknik.

| Teknik/verktyg/API    | Återkommande integrationer                   | Synkron/asynkron                    | Programmatisk åtkomst genom en API        | Lämpliga datavolymer                                   | Datatäckning                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Common Data Service-entiteter           | Ja, använda dataintegrerare eller mellanprogram | Sync Async, batch (via dataintegrerare) | Ja, via Dynamics 365 webb-API (OData) | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Förbättra<sup>2</sup>                       |
| DMF-entiteter           | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja, till DMF-paket REST API         | Hög (hundratusentals poster)                    | Högt                                |
| DMF-paket REST API   | Ja, schemalagda via mellanprogram        | Async, batch                                | Ja                                       | Hög (hundratusentals poster)                    | API stöder alla DMF-enheter       |
| BYOD                   | Ja, schemalagt av administratör i personal        | Async, batch                                | Nej<sup>3</sup>                                    | Hög (hundratusentals poster)                    | Stöder alla DMF-enheter           |
| OData-aktiverade enheter | Ja, använda mellanprogram                    | Synkronisering                                        | Ja, via datatjänst för personal (OData)  | Varierar med användningsfall (stöder sidindelning för interaktiv användning) | Högt                                |
| Excel-tillägg           | Nej                                       | Synkronisering                                        | Nej                                        | Mellan (tiotusentals poster)                      | Stöder alla OData-aktiverade enheter |
| Dataintegrerare        | Ja, schemalagd i dataintegrerare        | Async, batch                                | Nej                                        | Varierar med användningsfall                                       | Stöder alla Common Data Service-enheter           |

<sup>2</sup>Microsoft är till stor utsträckning att öka datatäckningen för Common Data Service-enheter och rekommenderar Common Data Service det som det bästa datagränssnittet när det finns täckning. För närvarande är Common Data Service datatäckning låg relativ till DMF- och OData-aktiverade entiteter.

<sup>3</sup>SQL-databasen kan öppnas programmässigt.

## <a name="summary"></a>Sammanfattning

Dina affärsdata är en värdefull tillgång, men dess värde kan minskas om det är svårt att använda informationen för dina specifika syfte (t.ex. rapportering, datamashup eller anpassade program). Dynamics 365 Human Resources ger flera tekniker för att arbeta med data utanför de personalprogrammet användargränssnitt (UI), så att det går att integrera programåtkomst till data. I det här avsnittet beskrivs tillgängliga integreringstekniker och några av deras nyckelegenskaper. Denna information ska hjälpa dig fatta bättre beslut om vilka metoder som gäller för integrationsprojekt.

