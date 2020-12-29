---
title: Underhållsschema
description: I det här avsnittet beskrivs underhållsschema i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 351e088ece0512fee1bb5f9dad020f32f7728fe4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437699"
---
# <a name="maintenance-schedule"></a>Underhållsschema

[!include [banner](../../includes/banner.md)]

 

Underhållsschemat innehåller en lista över alla förväntade förebyggande underhållsplaner, underhållsbegäranden och underhållsomgångar som ska utföras. Vissa schemarader kan ha konverterats till arbetsorder.

De fyra vyerna för underhållsscheman skiljer sig något beroende på vilka underhållsschemarader du vill se.

| Menyalternativ                  | Beskrivning av innehåll                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alla underhållsscheman       | Alla underhållsschemarader visas.     |
| Min tidsplan för tillgången        | Alla underhållsschemarader innehåller tillgångar som är installerade på funktionsplatser som du är relaterad till som arbetare (ställs in i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md)) som visas i den här listan. |
| Öppna rader för underhållsschema | Underhållsschemarader med status "Skapad" – innebär att de ännu inte har konverterats till en arbetsorder eller kasserats – visas i den här listan.                                            |
| Öppna pooler för underhållsschema | Underhållsschemarader som hör till en arbetsorderpool visas i den här listan.                                                                                                                  |

>[!NOTE]
>Om en underhållsschemarad ingår i flera arbetsorderpooler (se [Arbetsorderpooler](../work-orders/work-order-pools.md)) visas en post för varje pool i **Öppna pooler för underhållsschema**. Detta görs för att optimera filtreringsalternativen för arbetsorderpooler.

Öppna ett underhållsschema:

1. Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema**.

2. Om du vill uppdatera underhållsschemat klickar du på **Underhållsplan** eller **Underhållsomgång**. 

3. Du kan redigera en underhållsschemarad genom att markera den och klicka på **Redigera**. Du kan till exempel enkelt uppdatera servicenivån eller den arbetare som är ansvarig för jobbet. Du kan bara redigera underhållsschemarader som ännu inte har kopplats till en arbetsorder.

4. Du kan ta bort en underhållsschemarad genom att markera den på listsidan och klicka på **Ta bort**.

5. Du kan ignorera en underhållsschemarad genom att markera den på listsidan och klicka på **Ignorera**. Den här funktionen är användbar om till exempel en tillgång har en underhållsplan på 2 000 km och en underhållsplan på 10 000 km. Sedan vill du kanske ignorera den rad som har skapats från underhållsplanen för 2 000 km när den sammanfaller med 10 000 km, 20 000 km, 30 000 km och så vidare. Om du tar bort en underhållsschemarad som är relaterad till en underhållsplan kommer den raden aldrig att visas när underhållsplanen planeras.

6. Du kan välja ett antal underhållsschemarader i **Alla underhållsplaner** och klicka på **Arbetsorderpool** om du vill att alla valda rader ska inkluderas i samma pool för arbetsorder.

7. Du kan välja ett antal underhållsschemarader i **Alla underhållsscheman** eller **Öppna underhållsschemarader** eller **Öppna pooler för underhållsschema** och klicka på **Justera schema** om du vill göra samma justeringar på flera rader. Du kan ändra förväntade start- och slutdatum, servicenivå och den ansvariga underhållsarbetargruppen eller ansvariga underhållsarbetaren relaterad till de valda underhållsschemaraderna.

- När en underhållsschemarad har relaterats till en arbetsorder visas arbetsorder-ID:t i fältet **Arbetsorder**.  
- I informationsvyn **Alla tillgångar** > snabbfliken **Underhållsplaner för tillgångar** kan du välja underhållsplaner för till gången. Om du senare tar bort en underhållsplanrad som är relaterad till en tillgång i **Alla tillgångar** tar du också automatiskt bort alla underhållsschemarader med status "Skapat" som har skapats baserat på den underhållsplanen. Se även [Skapa en tillgång](../objects/create-an-object.md).

På bilden nedan visas listsidan **Alla underhållsscheman**.

![Figur 1](media/16-preventive-maintenance.png)

