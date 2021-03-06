---
title: Skapa låneartiklar
description: Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11c81e37952c59325c4f7dd46fd19599fbf8390f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056838"
---
# <a name="create-loan-items"></a>Skapa låneartiklar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]