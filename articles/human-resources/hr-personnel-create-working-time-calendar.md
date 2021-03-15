---
title: Skapa kalendrar och generera arbetstider
description: Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser. Det här avsnittet förklarar för att definiera en arbetskalender som baseras på en arbetstidsmall.
author: andreabichsel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fd297d9368472138fbe2db5a2133719cb1a9f18
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130311"
---
# <a name="create-calendars-and-generate-working-times"></a>Skapa kalendrar och generera arbetstider



Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser. Det här avsnittet förklarar för att definiera en arbetskalender som baseras på en arbetstidsmall. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.

1. På startsidan väljer du **Livscykelhantering för resurs**.
2. Välj **kalendrar**.
3. Välj **Ny**.
4. I fältet **kalender** klassificerar du kalender. Detta är id:t för kalendern, som används som referens när du kopplat kalendrar, till exempel till en verksamhetsresurs eller en resursgrupp.  
5. Ange sedan ett namn i fältet **Namn** för din kalender.
6. Ange ett värde i fältet **Standardarbetsdag i timmar**.
7. Kontrollera att raden är markerad och välj **arbetstider** i åtgärdsfönstret.
8. Välj **Sammanställ arbetstider**. Skapa arbetstid för varje dag under perioden där du vill kunna planera arbetet. Efter hand kan du skapa arbetstider för ytterligare perioder.  
9. I fältet **Från datum** anger du ett datum. Detta är den första dagen som kalendern måste vara öppen.  
10. I fältet **Till datum**, anger du ett datum. Detta är den sista dagen som kalendern är öppen.  
11. Ange eller välj ett värde i fältet **Arbetstidsmall**. Arbetstidmallen definierar arbetstiden för varje veckodag.  
12. Välj **OK**.
13. Stäng sidan.



[!INCLUDE[footer-include](../includes/footer-banner.md)]