--- 
title: "Skapa låneartiklar"
description: "Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 65655283c70c99b5d64289b319ecc69f6e414221
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-loan-items"></a>Skapa låneartiklar

[!include[task guide banner](../../includes/task-guide-banner.md)]

Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare. Varje fysisk artikel måste ha en motsvarande låneartikel. Varje låneartikelpost bör beskriva vad som lånas ut, vem som är ansvarig för lånet och antalet dagar som artikeln kan lånas ut. Du kan skapa flera låneartiklar samtidigt, till exempel nycklar, passerkort eller uniformer. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-loan-types"></a>Skapa lånetyper
1. Gå till Personal > Arbetare > Låneartiklar > Lånetyper.
2. Klicka på Ny.
3. Ange ett värde i fältet Lånetyp.
4. Ange ett värde i fältet Beskrivning.
5. Ange det antal dagar med vilket artiklar som tilldelats till den här lånetypen får ha förfallit. 
6. Klicka på Spara.
7. Stäng sidan.
8. Uppdatera sidan.

## <a name="create-loan-items"></a>Skapa låneartiklar
1. Gå till Personal > Arbetare > Låneartiklar > Låneartiklar.
2. Klicka på Skapa flera låneartiklar.
3. I kvant. fältet anger du ett tal.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lånetyp.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Ange det antal dagar som artikeln kan lånas ut.
    * Standardvärdet i fältet Planerad retur på sidan Lånad utrustning beräknas som dagens datum plus det här numret.  
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Ansvarig person.
10. Klicka på Välj.
11. Du måste ange ett nummer i fältet Startvärde.
12. Ange ett nummer i fältet Intervall.
13. Ange ett värde i fältet Format.
    * Om det högsta startnumret för en låneartikel är 10 anger du till exempel två nummersymboler i fältet Format.  
14. Klicka på OK.
15. Uppdatera sidan.

