--- 
title: "Skapa en plan för en plats"
description: "Produktionstadsplaneraren beräknar material- och kapacitetsbehov för att producera en specifik artikel."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1452c5d6f5dd8d0dd4cb08eb5cc9a48fd8f875f9
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-plan-for-a-site"></a>Skapa en plan för en plats

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


