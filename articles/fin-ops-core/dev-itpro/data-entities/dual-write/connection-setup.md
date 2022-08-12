---
title: Riktlinjer för att ställa in dubbelriktad skrivning
description: I den här artikeln beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111262"
---
# <a name="guidance-for-dual-write-setup"></a>Riktlinjer för att ställa in dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Du kan skapa en anslutning med dubbelriktad skrivning mellan en miljö för ekonomi och drift och en Dataverse-miljö.

+ En **miljö för ekonomi och drift** tillhandahåller den underliggande plattformen för **appar för ekonomi och drift** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Human Resources).
+ En **Dataverse-miljö** tillhandahåller den underliggande plattformen för **kundengagemangsappar** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> Personalmodulen i Dynamics 365 Finance har stöd för anslutningar för dubbelriktad skrivning men inte Dynamics 365 Human Resources-appen.

Installationsmekanismen varierar beroende på din prenumeration och miljön:

+ För nya instanser av appar för ekonomi och drift börjar konfigurationen av en anslutning med dubbel skrivning i Microsoft Dynamics Lifecycle Services (LCS). Om du har en licens för Microsoft Power Platform får du en ny Dataverse-miljö om ditt innehavare inte har någon.
+ För befintliga instanser av appar för ekonomi och drift börjar konfigurationen av en anslutning med dubbel skrivning i miljön för ekonomi och drift.

Innan du initierar dubbelriktad skrivning på en entitet kan du köra en inledande synkronisering för att hantera befintliga data på båda sidor: appar för ekonomi och drift samt kundengagemangsappar. Du kan hoppa över den inledande synkroniseringen om du inte behöver synkronisera data mellan de två miljöerna.

Vid en inledande synkronisering kan du kopiera befintliga data från ett program till en annan dubbelriktat. Det finns flera installationsscenarier beroende på vilka miljöer som du redan har och vilken typ av data som finns i dem.

Följande konfigurationsscenarier stöds:

+ [En ny appinstans för ekonomi och drift och en ny appinstans för kundengagemang](#new-new)
+ [En ny appinstans för Ekonomi och drift och en befintlig instans av kundengagemangsapp](#new-existing)
+ [En ny appinstans för Ekonomi och drift som har data och en ny instans av kundengagemangsapp](#new-data-new)
+ [En ny appinstans för Ekonomi och drift som har data och en befintlig instans av kundengagemangsapp](#new-data-existing)
+ [En ny appinstans för Ekonomi och drift och en befintlig instans av kundengagemangsapp](#existing-new)
+ [En ny appinstans för Ekonomi och en befintlig instans av kundengagemangsapp](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>En ny appinstans för Ekonomi och drift och en ny instans av kundengagemangsapp

Om du vill konfigurera en anslutning med dubbelriktad skrivning mellan en ny instans av en app för ekonomi och drift som inte har några data och en ny instans av kundengagemangsapp följer du stegen i [Konfigurera dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:

- En ny, tom miljö för Ekonomi och drift tillhandahålls.
- En ny, tom instans av en kundengagemangsapp etableras, där den primtal som CRM är installerad.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Tabellmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>En ny appinstans för ekonomi och drift och en befintlig instans av kundengagemangsapp

Om du vill konfigurera en anslutning med dubbelriktad skrivning mellan en ny instans av en app för ekonomi och drift som inte har några data och en befintlig instans av en kundengagemangsapp följer du stegen i [Konfigurera dubbelriktad skrivning från Lifecycle Services](lcs-setup.md). När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:

- En ny, tom miljö för Ekonomi och drift tillhandahålls.
- En dubbelriktad anslutning har upprättats för DAT företagsdata.
- Tabellmappningar aktiveras för direkt synkronisering.

De båda miljöerna är sedan klara för synkronisering av realtidsdata.

Om du vill synkronisera befintliga Dataverse-data till appen för ekonomi och drift följer du dessa steg.

1. Skapa ett nytt företag i appen för ekonomi och drift.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Dataverse data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.
4. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i [Exempel](#example) senare i den här artikeln.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>En ny appinstans för Ekonomi och drift som har data och en ny instans av kundengagemangsapp

Om du vill konfigurera en anslutning med dubbelriktad skrivning mellan en ny instans av en app för ekonomi och drift som har data och en ny instans av en kundengagemangsapp, följ stegen i [En ny appinstans för Ekonomi och drift och en ny kundengagemangsapp](#new-new) tidigare i denna artikel. När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.

1. Öppna appen för ekonomi och drift LCS-sidan, logga in och gå sedan till **Datahantering \> Dubbelriktad skrivning**.
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>En ny appinstans för Ekonomi och drift som har data och en befintlig instans av kundengagemangsapp

Om du vill konfigurera en anslutning med dubbelriktad skrivning mellan ny instans av en app för ekonomi och drift som har data och en befintlig instans av en kundengagemangsapp, följ stegen i [En ny appinstans för Ekonomi och drift och en ny kundengagemangsapp](#new-existing) tidigare i denna artikel. När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.

1. Öppna appen för ekonomi och drift LCS-sidan, logga in och gå sedan till **Datahantering \> Dubbelriktad skrivning**.
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Om du vill synkronisera befintliga Dataverse-data till appen för ekonomi och drift följer du dessa steg.

1. Skapa ett nytt företag i appen för ekonomi och drift.
2. Lägg till företaget i konfigurationen av dubbelriktad anslutning.
3. [Starta](bootstrap-company-data.md) Dataverse-data med en ISO-företagskod med tre bokstäver.
4. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>En befintlig appinstans för Ekonomi och drift och en ny instans av kundengagemangsapp

Konfigureringen av en anslutning med dubbelriktad skrivning mellan en befintlig instans av en app för ekonomi och drift och en ny instans av en kundengagemangsapp förekommer i Ekonomi och drift-miljön.

1. [Konfigurera anslutningen från appen för Ekonomi och drift](enable-dual-write.md).
2. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>En befintlig appinstans för ekonomi och drift och en befintlig instans av kundengagemangsapp

Inställningen för en anslutning med dubbelriktad skrivning mellan en befintlig instans av en app för ekonomi och drift och en befintlig instans av en kundengagemangsapp förekommer i miljön för ekonomi och drift.

1. [Konfigurera anslutningen från appen för Ekonomi och drift](enable-dual-write.md).
2. Om du vill synkronisera befintlig Dataverse-data till appen för ekonomi och drift, [starta då](bootstrap-company-data.md) Dataverse-data med en ISO-företagskod med tre bokstäver.
3. Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.

Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).

## <a name="example"></a>Exempel

Ett exempel finns i [Aktivera Customers V3 – kontakter tabellmappning](enable-entity-map.md#enable-table-map)

Om du vill ha en alternativ metod baserad på datavolymer i varje enhet som måste köra en inledande synkronisering, se [Att tänka på vid första synkroniseringen](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
