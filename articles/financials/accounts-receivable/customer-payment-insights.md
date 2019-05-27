---
title: Kundbetalningsinsikter (förhandsgranskning)
description: Det här avsnittet beskriver hur insikter om kundbetalningar kan hjälpa till att förutsäga när en faktura ska betalas och hjälpa organisationer att optimera strategier som förbättrar sannolikheten att få betalt i tid.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566268"
---
# <a name="customer-payment-insights-preview"></a>Kundbetalningsinsikter (förhandsgranskning)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Denna funktion ingår i en målinriktad uppdatering och är bara tillgänglig för användare som har valt privat förhandsvisning. Denna funktion kommer att ingå i en kommande, allmänt tillgänglig version.

# <a name="overview"></a>Översikt

Organisationer finner det ofta svårt att förutsäga när en kund betalar sina fakturor. Denna brist på insyn kan leda till felaktiga kassaflödesprognoser, ineffektiva inkasseringsprocesser och risken att order levereras till kunder som kan utgöra en kreditrisk. Insikter om kundbetalningar (förhandsgranskning) använder maskininlärning för att förutsäga när en faktura betalas. Den innehåller även optimeringsstrategier som kan skräddarsys för att maximera sannolikheten att kunderna betalar i tid.

## <a name="predictions"></a>Förutsägelser

Betalningsprognoser gör att organisationer kan förbättra sina affärsprocesser genom att:

-   Enkelt identifiera de fakturor som bedöms kan komma att betalas för sent.
-   Vidta lämpliga åtgärder för att öka sannolikheten för att få betalt i tid.

Insikter om kundbetalningar (förhandsgranskning) använder maskininlärning för att förutsäga när en faktura betalas. Här används historiska data om faktura, betalning och kund i syfte att skapa en modell för maskininlärning som används för att förutsäga när en faktura kommer att betalas.

Kundbetalningsinsikter (förhandsgranskning) förutsäger tre sannolikheter för betalning för respektive faktura:

-  Sannolikheten för betalning i tid (senast på fakturans förfallodatum).
-  Sannolikheten för betalning inom 30 dagar efter fakturans förfallodatum.
-  Sannolikheten för betalning efter 30 dagar efter fakturans förfallodatum.

Sannolikheten för betalningar kan visas i avsnittet om prognoser.

[![Betalningsprognoser](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

Varje faktura kopplas även till en primär betalningssannolikhet enligt någon av de tre beräknade sannolikheter för betalning enligt ovan. Scenariot med bäst sannolikhet till betalning är vinnande scenario.


Låt oss till exempel anta att förutsägelsen för en faktura anger 71 procents sannolikhet att fakturan ska betalas i tid, 13 procents sannolikhet att fakturan ska betalas inom 30 dagar efter förfallodatum, och 16 procents sannolikhet att fakturan betalas efter 30 dagar efter förfallodatum. Den största sannolikheten visar att fakturan ska ingå i scenariot "i tid", varför fakturan kommer att märkas med sannolikheten att betalas i tid.

[![Betalningsförutsägelser](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Optimeringsstrategier

Utöver betalningsprognoser kan kundbetalningsinsikter (förhandsgranskning) optimera strategier för att öka risken för att få betalt i tid. Detta gör det möjligt för organisationer att utföra "tänk om"-analyser genom att göra det möjligt för användare att justera faktura- kundparametrar och sedan jämföra motsvarande effekt baserat på möjligheten att få fakturainbetalningar i tid.

En organisation kanske exempelvis vill utvärdera effekten av att uppdatera kassarabatten på fakturor baserat på sannolikheten att erhålla betalningen i tid. När fakturorna optimeras för att använda den nya rabatten kan användarna studera effekten av att tillämpa rabatten baserat på sannolikheten för att ta emot betalningar för dessa fakturor i tid. Om kostnaden för att tillämpa rabatten är minimal i jämförelse med förmånen att få betalt i tid, kan organisationen välja att tillämpa vald rabatt på alla framtida, öppna order.

> [!NOTE] 
> För närvarande finns endast rabatt som en optimeringsstrategi för insikter om kundbetalningar (förhandsgranskning).

[![Optimerade prognoser](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Hur du får insikter om kundbetalningar (förhandsgranskning)

Om du är intresserad av att testa insikter om kundbetalningar (förhandsgranskning), e-posta då [Förhandsgranskningsteamet för finansiella insikter](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Sekretessmeddelande

Förhandsgranskning lagrar kunddata i USA. Förhandsgranskningar (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 for Finance and Operations de (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.
