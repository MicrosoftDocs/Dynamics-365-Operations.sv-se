---
title: Kostnadsredovisningar
description: När du ställer in kostnadsredovisning har du två mål. För det första ska du definiera visningsformatet för information om kostnader för sålda varor för en tillverkad artikel eller tillverkningsorder. Den formaterade visningen kallas för kostnadsredovisning. För det andra ska du definiera grunden för hur indirekta kostnader beräknas. Inställningarna för kostnadsredovisningen bygger på kostnadsgruppsfunktionen för visningsinformation och på beräkningsformler för indirekta kostnader. De två målen med inställningarna för kostnadsredovisning beskrivs i den här artikeln.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostSheetDesigner, CostSheetCalculationFactor
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f83c18bb8700e274bcf8cb369a7436a17450bf7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437954"
---
# <a name="costing-sheets"></a>Kostnadsredovisningar

[!include [banner](../includes/banner.md)]

När du ställer in kostnadsredovisning har du två mål. För det första ska du definiera visningsformatet för information om kostnader för sålda varor för en tillverkad artikel eller tillverkningsorder. Den formaterade visningen kallas för kostnadsredovisning. För det andra ska du definiera grunden för hur indirekta kostnader beräknas. Inställningarna för kostnadsredovisningen bygger på kostnadsgruppsfunktionen för visningsinformation och på beräkningsformler för indirekta kostnader. De två målen med inställningarna för kostnadsredovisning beskrivs i den här artikeln. 

En kostnadsredovisning är en formaterad visning av information om kostnaden för varor som är sålda för en tillverkad artikel eller tillverkningsorder. När du ställer in en kostnadsredovisning definierar du formatet för informationen och även basen för beräkning av indirekta kostnader. Inställningarna för kostnadsredovisningen bygger på kostnadsgruppsfunktionerna för visningsinformation och de formler som används för att beräkna indirekta kostnader. Här följer mer information om de två målen för inställningar för kostnadsredovisning:
-   **Definiera formatet för kostnadsredovisningen.** Det användardefinierade formatet för en kostnadsredovisning identifierar segmenteringen av kostnaderna som innehåller en tillverkad artikels kostnad för sålda varor. T.ex. informationen om kostnader för sålda varor kan segmenteras till material, arbete och omkostnader som baseras på kostnadsgrupper. Dessa kostnadsgrupper har tilldelats artiklar, kostnadskategorier för flödesoperationer och formler för indirekt kostnadsberäkning. Formatet för kostnadsredovisningen kräver normalt mellanliggande summor när flera kostnadsgrupper har definierats. Du kan till exempel lägga till flera kostnadsgrupper som är relaterade till material. Definitionen av en kostnadsredovisning är valfri, men kostnadsredovisningsformatet måste definieras om indirekta kostnader ska beräknas.
-   **Definiera grunden för beräkning av indirekta kostnader.** Indirekta kostnader återspeglar tillverkningsomkostnader som associeras med produktionen av en tillverkad artikel. En beräkningsformel för indirekta kostnader kan uttryckas som ett tillägg eller en tariff. Ett tillägg representerar ett procentvärde, medan en tariff representerar ett belopp per timme för en flödesoperation. En kostnadsgrupp definierar grunden för beräkningsformeln, till exempel 100 procents tillägg för en arbetskostnadsgrupp eller 500 kronors timtaxa för en maskinkostnadsgrupp. Om du vill definiera en beräkningsformel och dess kostnadsgruppsgrunder, kräver inställningarna för kostnadsredovisningen att du identifierar kostnadsgruppen som representerar omkostnaden och att du väljer att använda tillägg eller tariff.

Varje beräkningsformel måste anges som en kostnadspost. Kostnadsposten består av en angiven kostnadsredovisningsversion, en tilläggsprocent eller ett tariffbelopp, kostnadsgruppsgrunden, ett statusvärde och ett giltighetsdatum. När en artikelkostnadspost först registreras har den status **Väntande** och ett giltighetsdatum. När kostnadsposten aktiveras uppdateras status så att posten är den aktuella aktiva posten och giltighetsdatumet uppdateras till aktiveringsdatumet. Kostnadsposten kan även ange en site för en sitespecifik beräkningsformel. Alternativt kan du lämna fältet **Plats** tomt om du vill ange att beräkningsformeln är en företagsomfattande formel. Kostnadsposten kan också bestå av en angiven artikel eller en artikelgrupp när beräkningsformeln har markerats som en formel per artikel. 

De aktuella aktiva kostnadsposterna för beräkningsformler för indirekta kostnader används för uppskattning av produktionsorderkostnader. De används också för beräkning av faktiska kostnader som hör till verklig förbrukningen av tid och material. De pågående kostnadsposterna används i strukturlisteberäkningar för ett framtida datum. 

Två spärrprinciper för en kostnadsversion bestämmer om väntande kostnader kan underhållas och om väntande kostnader kan startas Använd spärrprinciperna när du vill tillåta dataunderhåll, och sedan för att förhindra dataunderhåll för kostnadsdata i en kostnadsversion. 

När du har definierat kostnadsredovisningsformatet och beräkningar för indirekta kostnader måste du utföra ett separat steg för att validera och spara informationen. Kostnadsredovisningen innebär att informationen om kostnader för sålda varor visas på ett enhetligt sätt i hela företaget. 

Kostnadsredovisningen visas på sidan **Beräkna artikelkostnad**. Kostnadsredovisningen kan visas för en tillverkad artikels beräknade kostnadspost på sidan **artikelpris** eller för en orderspecifik beräkningspost på sidan **Resultat från strukturlisteberäkningar**. Den kan också visas som en del av sidan **Prisberäkningen** för en produktionsorder.





