---
title: Organisationer och organisationshierarkier – översikt
description: Organisationshierarkier representerar relationerna mellan de organisationer som finns i företaget.
author: sericks007
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efd34b01ab414b2282fd08d8d9329ae7f9a801ce
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747645"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>Organisationer och organisationshierarkier – översikt

[!include [banner](../includes/banner.md)]

En organisation är en grupp personer som arbetar tillsammans för att utföra ett arbete eller uppnå ett mål. Organisationshierarkier representerar relationerna mellan de organisationer som finns i företaget.

## <a name="organizations"></a>Organisationer

Du kan definiera följande typer av interna organisationer: juridiska personer, driftenheter och team.

Alla interna organisationer är typer av enheten **Part**. Därför använder dessa organisationer adressboken för att lagra adress - och kontaktinformation. En part, som kan vara antingen en person eller en organisation, kan tillhöra en eller flera adressböcker.

### <a name="legal-entities"></a>Juridiska personer

En juridisk person är en organisation som har en registrerad eller lagstiftad juridisk struktur. Juridiska personer kan ingå juridiska kontrakt och måste förbereda utdrag som rapporterar deras resultat.

Ett företag är en sorts juridisk person. För närvarande är företag den enda typ av juridisk person som du kan skapa, och varje juridisk person associeras med ett företags-ID. Denna koppling finns eftersom vissa funktionella områden i programmet använder ett företags-ID eller DataAreaId, i deras datamodeller. I dessa funktionella områden används företag som en gräns för datasäkerhet. Användarna kan endast komma åt data för de företag som de är inloggade på.

### <a name="operating-units"></a>Driftenheter

En driftenhet är en organisation som används för skilja kontrollen av ekonomiska resurser och processer kunskap i ett företag. Personer i en driftenhet har en skyldighet att maximera användningen av knappa resurser, att förbättra processer och att redovisa deras resultat.

Typerna av driftenheter innehåller kostnadsställen, affärsenheter, värdeströmmar, avdelningar och handelskanaler. I följande tabell finns mer information om varje typ av driftenhet.

| Typ av driftenhet | Beskrivning | Syfte |
|---------------------|-------------|---------|
| Kostnadsställe         | En driftenhet där chefer är ansvariga för budgeterade och faktiska omkostnader. | Används för hantering och driftskontrollen av affärsprocesser som sträcker sig över juridiska personer. |
| Affärsenhet       | En halvautonom driftenhet som skapas för att uppfylla strategiska affärsmål. | Används för den ekonomiska rapporteringen som baseras på de branscher eller produktserier som organisationen använder oberoende av juridiska personer. |
| Värdeström        | En driftenhet som kontrollerar ett eller flera produktionsflöden. | Används vanligtvis i lean manufacturing för att kontrollera de aktiviteter och flöden som krävs för att tillhandahålla en produkt eller tjänst till kunderna. |
| Avdelning          | En driftenhet som representerar en kategori eller en funktionell del av en organisation som utför en viss uppgift, till exempel försäljning eller redovisning. | Används för att rapportera om funktionsområden. En avdelning kan ha ansvar för vinster och förluster och kan bestå av en grupp av kostnadsställen. |
| Handelskanal      | En driftenhet som representerar en fysisk butik, en onlinebutik eller en onlinemarknadsplats. | Används för hantering och den driftskontrollen av en eller flera butiker inom eller mellan juridiska personer. |

### <a name="teams"></a>Team

Ett team är en organisation i vilken medlemmarna delar ett gemensamt ansvarsområde, intresse eller mål. Team kan inte användas i organisationens hierarkier.

## <a name="organizational-hierarchies"></a>Organisationshierarkier

Ställa in organisatoriska hierarkier för att visa och rapportera utifrån olika perspektiv av verksamheten. Du kan till exempel skapa en hierarki av juridiska personer för momsrapportering, juridisk rapportering eller lagstadgad rapportering. Ställa in en hierarki som baseras på driftenheter för att rapportera ekonomisk information som inte krävs enligt lag, men som används för intern kontroll. Du kan till exempel skapa en inköpshierarki för att kontrollera inköpspolicyer, regler och arbetsprocesser.

Varje hierarki tilldelas ett syfte. Syftet med en hierarki bestämmer vilka typer av organisationer som kan inkluderas i hierarkin. Syftet avgör också de programscenarier som en hierarki kan användas i.

Organisationer i en hierarki kan dela parametrar, policyer och transaktioner. En organisation kan ärva eller åsidosätta parametrarna för dess överordnade organisation. Delade huvuddata, till exempel produkter och adressböcker, gäller däremot för hela organisationen och kan inte åsidosättas för enskilda organisationer. När du skapar organisationer och hierarkier krävs det noga planering. Mer information om hierarkidesignern finns i [Planera organisationshierarkin](plan-organizational-hierarchy.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]