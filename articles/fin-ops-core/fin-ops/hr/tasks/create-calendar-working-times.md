---
title: Skapa kalendrar och generera arbetstider
description: Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser. Det här avsnittet förklarar för att definiera en arbetskalender som baseras på en arbetstidsmall.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1645dc42e3c7145feb3081b862c6069d9032913a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550943"
---
# <a name="create-calendars-and-generate-working-times"></a>Skapa kalendrar och generera arbetstider

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

