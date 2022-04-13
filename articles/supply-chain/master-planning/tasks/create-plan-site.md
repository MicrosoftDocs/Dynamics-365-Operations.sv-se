---
title: Skapa en plan för en plats
description: Produktionstadsplaneraren beräknar material- och kapacitetsbehov för att producera en specifik artikel.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8330fc15074eb59762dac73d0b176bd7faadc
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469517"
---
# <a name="create-a-plan-for-a-site"></a>Skapa en plan för en plats

[!include [banner](../../includes/banner.md)]

Produktionstadsplaneraren beräknar material- och kapacitetsbehov för att producera en specifik artikel. När anskaffningsförslagen har skapats, hittar han order på siten för vilken han planerar och bekräftar order med start från de mest brådskande. De mest brådskande order är de som måste bekräftas på det aktuella datumet. Använd demonstrationdataföretaget USMF för att utföra dessa uppgifter.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Skapa material och kapacitetsplan för en artikel
1. Klcka på Huvudplanering.
    * Du måste navigera till Standardinstrumentpanelen.  
2. Klicka på Kör.
3. Expandera avsnittet Poster som ska ingå.
4. Klicka på Filter.
5. Markera vald rad i listan.
6. Ange ett värde i fältet Kriterier.
    * Exempel: D0001  
7. Klicka på OK.
8. Klicka på OK.
    * Detta kan ta några minuter.  
9. Uppdatera sidan.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identifiera brådskande planerade order för artikeln
1. Öppna artikelnummerkolumnfiltret.
2. Använd ett filter för fältet ”artikelnummer”, med värdet ”D0001", med hjälp av filteroperatorn ”börjar med”.
3. Öppna Kolumnfilter för orderdatum.
4. Tillämpa ett filter i fältet ”Orderdatum", med ett värde av aktuellt datum med filteroperatorn "Är exakt".

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Bekräfta alla brådskande planerade order för artikeln
1. Markera eller avmarkera alla rader i listan.
2. Klicka på Bekräfta.
3. Klicka på OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]