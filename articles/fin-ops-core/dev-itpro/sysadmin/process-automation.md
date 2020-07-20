---
title: Processautomatisering
description: Det här avsnittet innehåller information om hur processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508195"
---
# <a name="process-automation"></a>Processautomatisering

[!include[banner](../includes/banner.md)]

Processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern. Med den uppdaterade kalendervyn av det schemalagda arbetet kan slutanvändare visa och vidta åtgärder för schemalagt och slutfört arbete.

## <a name="administration"></a>Administration

Sidan Central administration för alla automatiseringar av processer finns i modulen systemadministration på menyn **Inställningar**. Den här sidan visar alla automatiserade processer (serier) som är inställda i systemet. Du kan också lägga till nya processautomatiseringar direkt från den här sidan. När en serie har ställts in kan du hantera varje serie från den här listan. Du kan välja att redigera hela serien, ta bort den, visa alla förekomster i en listvy eller inaktivera serien om du vill pausa det schemalagda arbetet under en tidsperiod. 

## <a name="calendar-view"></a>Kalendervy 
En av huvudfördelarna med processautomatisering är möjligheten att se det schemalagda arbetet i en enkel kalendervy.  I den här vyn kan du se arbetet för en vecka i taget. Den här vyn visas till höger på sidan **Processautomatisering**. Den kommer att fyllas i med det schemalagda arbetet för den valda serien. 

[![Kalender för processautomatisering](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Förekomständringar
Varje förekomst kan ändras utan att påverka andra förekomster som har definierats i serien. Förekomster av schemalagt arbete kan redigeras i kalendervyn genom att du väljer knappen **Visa/redigera** och väljer **Förekomst**. På så sätt kan du komma åt alla inställningar som ursprungligen visades i guiden för serieinställningar och du kan göra en enstaka ändring för den valda förekomsten. Du kan också stänga av en förekomst av schemalagt arbete genom att välja knappen **Inaktivera** i kalendervyn. 

## <a name="developer-documentation"></a>Dokumentation för utvecklare 
Dokumentationen för utvecklare håller på att skrivas för att utvecklare ska kunna utöka processens automatiseringsramverk. I den här dokumentationen får du information om hur du kan skapa anpassade processer som du behöver köra av den batchservern som är schemalagd med guiden bearbeta automatisering och visas automatiskt i kalendervyn.
