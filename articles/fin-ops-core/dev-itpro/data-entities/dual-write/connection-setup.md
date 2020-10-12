---
title: Scenarier som stöds för inställningen dubbelriktad skrivning
description: I det här avsnittet beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818606"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Scenarier som stöds för inställningen dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Du kan skapa en dubbelriktad anslutning mellan en Finance and Operations-miljö och en Common Data Service-miljö.

+ En **Finance and Operations-miljö** tillhandahåller den underliggande plattformen för **Finance and Operations-appar** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management och Dynamics 365 Retail).
+ En **Common Data Service-miljö** tillhandahåller den underliggande plattformen för **modellstyrda appar i Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).

>[!IMPORTANT]
>Personal i Finance and Operations stöder anslutningar med dubbla skrivfunktioner med inte Dynamics 365 Human Resources-appen.

Installationsmekanismen varierar beroende på din prenumeration och miljön.

+ För nya instanser av Finance and Operations-appar börjar konfigurationen av en dubbelriktad anslutning i Microsoft Dynamics Lifecycle Services (LCS). Om du har en licens för Power Platform får du en ny Common Data Service-miljö om ditt innehavare inte har någon.
+ När det gäller Finance and Operations-appar i befintliga instanser börjar konfigurationen av dubbelriktad anslutning i Finance and Operations-miljön.

Följande konfigurationsscenarier stöds:

+ [En ny Finance and Operations-appinstans och en ny modellstyrd appinstans](#new-new)
+ [En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans](#new-existing)
+ [En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans](#new-demo-new)
+ [En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans](#new-demo-existing)
+ [En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>En ny Finance and Operations-appinstans och en ny modellstyrd appinstans

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en ny instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:

- En ny, tom Finance and Operations-miljö etableras.
- En ny, tom instans av en modellstyrd app etableras, där den primtal som CRM är installerad.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Entitetsmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en befintlig instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:

- En ny, tom Finance and Operations-miljö etableras.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Entitetsmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.

1. Skapa ett nytt företag i Finance and Operations-appen.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Common Data Service data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.

Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en ny instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en ny modellstyrd appinstans](#new-new) tidigare i det här ämnet. När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.

1. Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.
2. Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en befintlig instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans](#new-existing) tidigare i det här ämnet. När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.

1. Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.
2. Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.

Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.

1. Skapa ett nytt företag i Finance and Operations-appen.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Common Data Service-data med en ISO-företagskod med tre bokstäver.

Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans

Inställningen dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en ny eller befintlig instans av en modellstyrd app i Dynamics 365 inträffar i Finance and Operation-miljön.

1. Ställ in anslutningen från Finance and Operations-appen.
2. Om du vill synkronisera befintlig Common Data Service data till Finance and Operations-app, [starta](bootstrap-company-data.md) Common Data Service data med en ISO-företagskod med tre bokstäver.

Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.
