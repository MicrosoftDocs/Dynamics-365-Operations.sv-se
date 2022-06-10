---
title: Entiteten behållaraktiviteter
description: Det här ämnet ger information om behållaraktiviteter, som används för att spåra förloppet för leveransbehållare.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 7bb2b97e8885e3b1265f0c93585873c8a64f1dfb
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813095"
---
# <a name="container-activities-entity"></a>Entiteten behållaraktiviteter

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Behållaraktiviteter används för att spåra förloppet för leveransbehållare. En post skapas för varje del som tilldelas resemallen som väljs när en fraktbehållare skapas. Poster skapas också när fraktbehållare skapas via en dataenhet.

Information om förloppet för en fraktbehållare under transport tas ofta emot från en extern källa. Med hjälp av enheten för behållaraktiviteter kan en extern källa, till exempel en fraktspeditör, uppdatera posten direkt. Därför krävs ingen manuell uppdatering av data.

## <a name="container-activities-itmcontaineractivityentity"></a>Behållaraktiviteter (ITMContainerActivityEntity)

Du kan använda enheten för behållaraktiviteter (`ITMContainerActivityEntity`) för att skapa ytterligare aktivitetsposter. Alternativt kan en fraktspeditör skicka uppdateringar för ett bekräftat värde för **Faktiskt slutdatum**.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Faktiskt slutdatum | ITMContainerActivityTable.ActualEndDate | DatumTid | Nej | Nej |
| Leveranssätt | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | Nej | Nej |
| Uppskattat slutdatum | ITMContainerActivityTable.EsimatedDate | DatumTid | Nej | Nej |
| Radnummer | ITMContainerActivityTable.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Anteckningar | ITMContainerActivityTable.Notes | nvarchar(MAX) | Nej | Nej |
| Aktivitet | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | Nej | **Ja** |
| Fraktcontainer | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Ja** | **Ja** |
| Sjötransport | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Ja** | **Ja** |
| Etapp | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | Nej | **Ja** |
| Tjänstleverantör | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | Nej | Nej |
| Temperatur | ITMContainerActivityTable.ShipTemperature | Numerisk(32, 6) | Nej | Nej |
| Fartyg | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | Nej | Nej |
| Startdatum | ITMContainerActivityTable.StartDate | DatumTid | Nej | Nej |

## <a name="tracking-control"></a>Spårningskontroll

Med spårningskontrollcentret kan en uppdatering av ett angivet källfält utlösas genom en uppdatering av ett angivet målfält. Om både värdet i källfältet och värdet i målfältet uppdateras med hjälp av enheten för behållaraktiviteter, visar målfältet enhetsvärdet. Detta har att göra med spårningskontrollposter som har värdet **Skapa typ** av *Ledtid*.

För kostnadsområden som har ett värde på **Skapa typ** för *Statusuppdatering* eller *Tom* (som är ett användardefinierat värde), kommer systemet att uppdatera färdstatus eller målfält enligt spårningskontrollkonfigurationen.

## <a name="calculated-fields"></a>Beräknade fält

Värdena i följande fält i en behållaraktivitetspost beräknas baserat på värdena i andra fält. Även om dessa beräknade fält inte inkluderas i dataenheten ställs de in om fälten som beräkningarna baseras på tillhandahålls.

- **Uppskattade dagar** = **Uppskatt slutdatum** – **Startdatum**
- **Faktiskt dagar** = **Faktiskt slutdatum** – **Startdatum**
