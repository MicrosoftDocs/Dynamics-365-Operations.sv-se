---
title: "Organisationer och organisationshierarkier (grundläggande om handel)"
description: "Grundläggande om handel har tre olika typer av interna organisationer som du kan definiera för att hjälpa en organisation att utföra en affärsprocess eller uppnå ett mål."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 50d29b6552cf7af5f2d9296b1d70b838a8edd637
ms.contentlocale: sv-se
ms.lasthandoff: 04/26/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organisationer och organisationshierarkier (grundläggande om handel)

[!include[banner](includes/banner.md)]


Grundläggande om handel har tre olika typer av interna organisationer som du kan definiera för att hjälpa en organisation att utföra en affärsprocess eller uppnå ett mål. 

En organisation är en grupp personer som arbetar tillsammans för att utföra ett arbete eller uppnå ett mål. En organisationshierarki representerar relationerna mellan de affärsenheter som finns i organisationen.

## <a name="organizations"></a>Organisationer
I Grundläggande om handel kan du definiera dessa typer av interna organisationer: juridiska personer, driftenheter och team. I Microsoft Dynamics AX är alla interna organisationer typer av enheten Part. Därför använder dessa organisationer en adressbok för att lagra adressen och annan kontaktinformation. En part kan vara antingen en person eller en organisation och den kan tillhöra en eller flera adressböcker.
### <a name="legal-entities"></a>Juridiska personer

En juridisk person är en organisation som har en registrerad eller lagstiftad juridisk struktur. Juridiska personer kan ingå juridiska kontrakt och måste förbereda utdrag som rapporterar deras resultat. Ett företag är en typ av juridisk person i  Microsoft Dynamics AX och varje juridisk person associeras med ett företags-ID. Denna association finns, eftersom ett företags-ID eller DataAreaId används i några produktmodeller där företag används som en gräns för datasäkerhet. Användarna kan endast komma åt data för de företag som de är inloggade på.

### <a name="operating-units"></a>Driftenheter

En driftenhet är en organisation som används för skilja kontrollen av ekonomiska resurser och processer kunskap i ett företag. Personer i en driftenhet har en skyldighet att maximera användningen av knappa resurser, att förbättra processer och att redovisa deras resultat. I Grundläggande om handel innehåller typerna av driftenheter kostnadsställen, affärsenheter, värdeströmmar, avdelningar och butikskanaler. I följande tabell finns mer information om varje typ av driftenhet.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Typ av driftenhet** | **Beskrivning**                                                                         | **Syfte**                                                                                                                                 |
| Affärsenhet           | En halvautonom driftenhet som skapas för att uppfylla strategiska affärsmål. | Använd affärsenheter för den ekonomiska rapporteringen som baseras på de branscher eller produktserier som organisationen använder mellan juridiska personer. |
| Butikskanal          | En driftenhet som representerar en fysisk butik.                             | Används för att hantera och kontrollera en eller flera butiker inom eller mellan juridiska personer.                                                               |

## <a name="organizational-hierarchies"></a>Organisationshierarkier
I Grundläggande om handel tilldelas varje hierarki tilldelas ett syfte. Syftet med en hierarki bestämmer vilka typer av organisationer som kan inkluderas i hierarkin. Syftet avgör också de programscenarier som en hierarki kan användas i. En butikshierarki kan exempelvis användas för att köpa och sälja produkter i en butik. Organisationer i en hierarki kan dela parametrar, policyer och transaktioner. En organisation kan ärva eller åsidosätta parametrarna för dess överordnade organisation. Delade huvuddata, till exempel produkter och adressböcker, gäller däremot för hela organisationen och kan inte åsidosättas för enskilda organisationer.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Regelverk för att ställa in en organisation i en hierarki

Tänk på följande när du implementerar en organisationshierarki:
-   Skapa en avdelning för att ange skärningspunkten mellan en juridisk person och en affärsenhet. Du kan sedan rulla upp data från en avdelning till en juridisk person för lagstadgad rapportering och från en avdelning till en affärsenhet för intern rapportering.
-   I en enskild juridisk person ska du inte ställa in flera hierarkier för samma hierarkisyfte.
-   Skapa inte en hierarki för varje syfte. Vanligtvis kan du skapa en hierarki för flera syften. En hierarki med driftenheter kan till exempel tilldelas till alla policyrelaterade syften.
-   Skapa balanserade hierarkier. I en hierarki definieras alla noder som är på samma avstånd från rotnoden som en nivå. I en balanserad hierarki kan endast en typ av driftenhet inträffa vid varje nivå, och avståndet från rotnoden till varje nivå är konsekvent. Om det finns mellanstadier mellan en avdelning och en juridisk person eller en affärsenhet, kan platshållareorganisationer krävas för att skapa en allsidig hierarki.
-   Ställ inte in en separat hierarki med driftenheter om strukturen för juridiska personer också är din driftstruktur. En blandad hierarki med juridiska personer och driftenheter kan uppfylla båda syftena.
-   Innan du ställer in stora omstruktureringsscenarier använder du hierarkins giltighetsdatum för att utföra en följdanalys och ett valideringstest.
-   Spara en hierarki som utkast, om du kan komma att ändra en hierarki, innan du publicerar den.
-   Begränsa antalet personer som har behörighet att lägga till eller ta bort organisationer från en hierarki i en produktionsmiljö. Ett lägre antal minskar risken för kostsamma misstag och behovet av korrigeringar.

## <a name="retail-store-management"></a>Butikshantering
I tabellen nedan beskrivs de Grundläggande om handel-scenarier där organisationshierarkier kan användas.
| Uppgift                                                                           | Beskrivning                                                                                                                                                                                                                                                                                                | Hierarkisyfte    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Hantera butikssortiment                                                      | Identifiera de produkter som är tillgängliga i varje butik.                                                                                                                                                                                                                                             | Butikssortiment    |
| Hantera butikspåfyllnad                                                    | Gruppera butiker för att fylla på lagret baserat på påfyllnadsregler.                                                                                                                                                                                                                                          | Butikspåfyllnad |
| Rapportdata för butiker                                                         | Gruppera butiker för rapportering.                                                                                                                                                                                                                                                                                | Butiksrapportering     |
| Bokföra lager, beräkna utdrag eller bokföra utdrag för en grupp av butiker | Skapa en grupp av butiker som kan tilldelas till ett batchjobb. När du definierar ett batchjobb för att bokföra lager, beräkna utdrag eller bokföra utdrag, kan du ange hierarkin som gäller för jobbet. När butiker läggs till eller raderas från hierarkin, behöver du inte ändra batchjobbet. | Bokföring för Retail POS   |






