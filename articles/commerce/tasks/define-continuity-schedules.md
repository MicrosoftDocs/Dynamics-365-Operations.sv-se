---
title: Definiera kontinuitetstidsplaner
description: I denna artikel beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order).
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: faa55c844c8ee8742fbb0868b55a520cec6686aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885094"
---
# <a name="define-continuity-schedules"></a>Definiera kontinuitetstidsplaner

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order). Denna artikel använder företaget USRT i demonstrationsdatan.


## <a name="create-continuity-program"></a>Skapa ett kontinuitetsprogram
1. Gå till Butik och handel > Kontinuitet > Kontinuitetsprogram.
2. Klicka på Ny.
3. Ange ID för kontinuitetstidsplan i fältet Schedule ID.
4. I fältet Order start väljer du "First event".
    * Om en kund lägger en ny order för kontinuitetsprogrammet finns det två alternativ för vilken produkten levereras: 1. Första händelse: den första produkten i kontinuitetsprogrammet ska levereras.  2. Aktuell händelse: den aktuella produkten skickas. Till exempel: tre månader efter programmets början får kunden den tredje i programmet.  
5. Välj ”Yes” om du vill efterfråga orderstartdatumet.
6. Klicka på Lägg till rad.
7. I fältet Item number anger du artikelnumret för den första produkten ("0013").
8. Ange "CP".
9. Ange det datum då den första produkten finns tillgänglig för order.
10. Klicka på Lägg till rad.
11. Skriv 0014 i fältet Artikelnummer.
12. I fältet för datumintervallskod rensar du värdet så att fältet står tomt.
    * Rensa datumintervallet för denna procedur. Du anger datumet som inkrementellt från startdatum för den första artikeln.  
13. Här kan du ange det intervallet då produkterna skickas. Ange "30".
    * För att ett månatligt program ska du ange 30 dagar för intervallet.  
14. Klicka på Lägg till rad.
15. Skriv 0015 i fältet Artikelnummer.
16. Ange "End".
17. Klicka på Spara.

## <a name="assign-to-continuity-item"></a>Tilldela till en kontinuitetsartikel
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Välj artikel "0016".
    * För den här proceduren väljer du artikel nummer 0016. Normalt har du skapat en frisläppt produkt som har ytterligare tillämpad kontinuitetsaffärslogik när den läggs på en försäljningsorder hos kundtjänsten.  
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Expandera eller komprimera sälja avsnitt.
6. Här kan du ange det kontinuitetsprogram som denna artikel representerar. Ange det tidsplans-ID som du skapade tidigare.
    * När artikeln säljs hos en kundtjänst tillämpas affärslogik från det valda kontinuitetsprogrammet.  
7. Klicka på Spara.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]