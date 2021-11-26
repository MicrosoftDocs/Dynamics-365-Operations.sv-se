---
title: Skapa låneartiklar
description: Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a812887f20a8ae5ae3b677ac452a498230c244a
ms.sourcegitcommit: 1cc56643160bd3ad4e344d8926cd298012f3e024
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731746"
---
# <a name="create-loan-items"></a>Skapa låneartiklar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare. Varje fysisk artikel måste ha en motsvarande låneartikel. Varje låneartikelpost bör beskriva vad som lånas ut, vem som är ansvarig för lånet och antalet dagar som artikeln kan lånas ut. Du kan skapa flera låneartiklar samtidigt, till exempel nycklar, passerkort eller uniformer. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-loan-types"></a>Skapa lånetyper
1. Gå till **Personal** > **Medarbetare** > **Låneartiklar** > **Lånetyper**.
2. Klicka på **Ny**.
3. Ange ett ävrde i fältet **Lånetyp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Ange det antal dagar med vilket artiklar som tilldelats till den här lånetypen får ha förfallit. 
6. Klicka på **Spara**.
7. Stäng sidan.
8. Uppdatera sidan.

## <a name="create-loan-items"></a>Skapa låneartiklar
1. Gå till **Personal** > **Medarbetare** > **Låneartiklar** > **Låneartiklar**.
2. Klicka på **Skapa låneartiklar**.
3. I fältet **Kvant.** anger du ett nummer.
4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Lånetyp** klickar du på knappen i listrutan för att öppna sökningen.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Ange det antal dagar som artikeln kan lånas ut.
    * Standardvärdet i fältet Planerad retur på sidan Lånad utrustning beräknas som dagens datum plus det här numret.  
9. I fältet **Ansvarig person** klickar du på knappen i listrutan för att öppna sökningen.
10. Klicka på **Välj**.
11. Ange ett värd ei fältet **Startvärde**.
12. Ange ett värde i fältet **Intervall**.
13. Ange ett värde i fältet **Format**.
    * Om det högsta startnumret för en låneartikel är 10 anger du till exempel två nummersymboler i fältet **Format**.  
14. Klicka på **OK**.
15. Uppdatera sidan.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
