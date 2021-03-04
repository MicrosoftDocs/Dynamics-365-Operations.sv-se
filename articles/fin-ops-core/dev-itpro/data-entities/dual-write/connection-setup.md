---
title: Riktlinjer för att ställa in dubbelriktad skrivning
description: I det här avsnittet beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 47c07dd0e2f311b61297340a48a5a31cb1de3903
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685675"
---
# <a name="guidance-for-dual-write-setup"></a>Riktlinjer för att ställa in dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Du kan skapa en dubbelriktad anslutning mellan en Finance and Operations-miljö och en Dataverse-miljö.

+ En **Finance and Operations-miljö** tillhandahåller den underliggande plattformen för **Finance and Operations-appar** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Human Resources).
+ En **Dataverse-miljö** tillhandahåller den underliggande plattformen för **kundengagemangsappar i Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> Personalmodulen i Dynamics 365 Finance har stöd för anslutningar för dubbelriktad skrivning men inte Dynamics 365 Human Resources-appen.

Installationsmekanismen varierar beroende på din prenumeration och miljön:

+ För nya instanser av Finance and Operations-appar börjar konfigurationen av en dubbelriktad anslutning i Microsoft Dynamics Lifecycle Services (LCS). Om du har en licens för Microsoft Power Platform får du en ny Dataverse-miljö om ditt innehavare inte har någon.
+ När det gäller Finance and Operations-appar i befintliga instanser börjar konfigurationen av dubbelriktad anslutning i Finance and Operations-miljön.

Innan du startar dubbelriktad skrivning på en enhet kan du köra en inledande synkronisering för att hantera befintliga data på båda sidor av Finance and Operations-appar och kundengagemangsappar. Du kan hoppa över den inledande synkroniseringen om du inte behöver synkronisera data mellan de två miljöerna.

Vid en inledande synkronisering kan du kopiera befintliga data från ett program till en annan dubbelriktat. Det finns flera installationsscenarier beroende på vilka miljöer som du redan har och vilken typ av data som finns i dem.

Följande konfigurationsscenarier stöds:

+ [En ny Finance and Operations-appinstans och en ny instans av kundengagemangsapp](#new-new)
+ [En ny Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp](#new-existing)
+ [En ny Finance and Operations-appinstans som har demodata och en ny instans av kundengagemangsapp](#new-data-new)
+ [En ny Finance and Operations-appinstans som har demodata och en befintlig instans av kundengagemangsapp](#new-data-existing)
+ [En befintlig Finance and Operations-appinstans och en ny instans av kundengagemangsapp](#existing-new)
+ [En befintlig Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>En ny Finance and Operations-appinstans och en ny instans av kundengagemangsapp

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en ny instans av kundengagemangsapp följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:

- En ny, tom Finance and Operations-miljö etableras.
- En ny, tom instans av en kundengagemangsapp etableras, där den primtal som CRM är installerad.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Tabellmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>En ny Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en befintlig instans av kundengagemangsapp följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:

- En ny, tom Finance and Operations-miljö etableras.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Tabellmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

Om du vill synkronisera befintliga Dataverse data till Finance and Operations-appen följer du dessa steg.

1. Skapa ett nytt företag i Finance and Operations-appen.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Dataverse data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.
4. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i [Exempel](#example) senare i det här avsnittet.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>En ny Finance and Operations-appinstans som har demodata och en ny instans av kundengagemangsapp

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har data och en ny instans av en kundengagemangsapp, följ stegen i [En ny Finance and Operations-appinstans och en ny kundengagemangsapp](#new-new) tidigare i detta avsnitt. När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.

1. Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>En ny Finance and Operations-appinstans som har demodata och en befintlig instans av kundengagemangsapp

Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har data och en befintlig instans av en kundengagemangsapp, följ stegen i [En ny Finance and Operations-appinstans och en befintlig kundengagemangsapp](#new-existing) tidigare i detta avsnitt. När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.

1. Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Om du vill synkronisera befintliga Dataverse data till Finance and Operations-appen följer du dessa steg.

1. Skapa ett nytt företag i Finance and Operations-appen.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Dataverse-data med en ISO-företagskod med tre bokstäver.
4. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>En befintlig Finance and Operations-appinstans och en ny instans av kundengagemangsapp

Inställningen dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en ny instans av en kundengagemangsapp förekommer i Finance and Operation-miljön.

1. [Ställ in anslutningen från Finance and Operations-appen](enable-dual-write.md).
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>En befintlig Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp

Inställning av dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en befintlig instans av en kundengagemangsapp sker i Finance and Operation-miljön.

1. [Ställ in anslutningen från Finance and Operations-appen](enable-dual-write.md).
2. Om du vill synkronisera befintlig Dataverse data till Finance and Operations-app, [starta](bootstrap-company-data.md) Dataverse data med en ISO-företagskod med tre bokstäver.
3. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="example"></a>Exempel

Ett exempel finns i [Aktivera Customers V3 – kontakter tabellmappning](enable-entity-map.md#enable-table-map)

Om du vill ha en alternativ metod baserad på datavolymer i varje enhet som måste köra en inledande synkronisering, se [Att tänka på vid första synkroniseringen](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]