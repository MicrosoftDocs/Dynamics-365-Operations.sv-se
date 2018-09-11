--- 
title: Definiera resurskunskaper
description: "Resurskapaciteter beskriver vad verksamhetsresurser kan göra."
author: sorenva
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-resource-capabilities"></a>Definiera resurskunskaper

[!include [task guide banner](../../includes/task-guide-banner.md)]

Resurskapaciteter beskriver vad verksamhetsresurser kan göra. Vid tidsplanering matchas kraven för varje jobb och operation mot kapaciteter hos de tillgängliga resurserna. Den här uppgiftsguiden hjälper dig att skapa en resurskapacitet och tilldela den till en resurs. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.


## <a name="create-a-resource-capability"></a>Skapa en ny resurskapacitet
1. Gå till Resurskunskaper.
2. Klicka på Ny.
3. Ange ID för resurskapaciteten i fältet Kapacitet.
    * Använd kapacitets-ID för en viss operation för att ange att resurser som måste ha denna kapacitet för att utföra operationen.  
4. I fältet Beskrivning anger du en kort beskrivning av kapaciteten.

## <a name="assign-capability-to-a-resource"></a>Tilldela kapaciteten till en resurs
1. Klicka på Lägg till.
2. Ange ID för resursen i fältet Resurs.
    * En resurskapacitet kan tilldelas till en eller flera resurser.  
3. I fältet Utgång anger du datum.
    * Du kan använda det här fältet om du vill ange att en resurs har kapacitet i bara en begränsad tid.  
4. Välj ett tal i fältet Prioritet.
    * När du planerar jobb och operationer kan du ange om du vill välja resurser efter prioritet. Om du väljer att göra detta och fler än en resurs kan utföra jobbet eller operationen per det begärt datumet, väljs resursen som har lägst prioritet med avseende på den begärda kapaciteten.  
5. Välj ett tal i fältet Nivå.
    * När du anger att ett jobb eller en operation kräver en viss kapacitet, kan du också ange den lägsta nivån som krävs. Använd kapacitetsnivån för att skilja mellan resurser som kan utföra samma jobb, men med olika hastighet, styrka, storlek osv.  


