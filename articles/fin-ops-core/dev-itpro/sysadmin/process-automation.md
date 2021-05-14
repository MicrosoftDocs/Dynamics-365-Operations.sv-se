---
title: Processautomatisering
description: Det här avsnittet innehåller information om hur processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: a8722adfe410f15bc379f9b550f0618c881f067d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920839"
---
# <a name="process-automation"></a>Processautomatisering

[!include[banner](../includes/banner.md)]

Processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern. Med den uppdaterade kalendervyn av det schemalagda arbetet kan slutanvändare visa och vidta åtgärder för schemalagt och slutfört arbete.

## <a name="administration"></a>Administration

Sidan Central administration för alla automatiseringar av processer finns i modulen systemadministration på menyn **Inställningar**. Den här sidan visar alla automatiserade processer (serier) som är inställda i systemet. Du kan också lägga till nya processautomatiseringar direkt från den här sidan. När en serie har ställts in kan du hantera varje serie från den här listan. Du kan välja att redigera hela serien, ta bort den, visa alla förekomster i en listvy eller inaktivera serien om du vill pausa det schemalagda arbetet under en tid. 

Alla processer som inaktiveras i funktionshanteringen visas inte när funktionen är inaktiverad. Dessutom kommer schemaläggningsmotorn för processautomation inte att schemalägga några händelser eller bakgrundsprocesser för en inaktiverad funktion. Om du aktiverar funktionen igen kommer schemalagda förekomster eller bakgrundsprocesser tidigare att kunna köras omedelbart. Planeringsmotorn för processautomatisering använder sig av systemets batchjobb **Systemjobb för processautomatiseringssökning** för att kunna köras. Jobbet bör aldrig ändras eller modifieras. 

## <a name="calendar-view"></a>Kalendervy

En av huvudfördelarna med processautomatisering är möjligheten att se det schemalagda arbetet i en enkel kalendervy.  I den här vyn kan du se arbetet för en vecka i taget. Den här vyn visas till höger på sidan **Processautomatisering**. Den kommer att fyllas i med det schemalagda arbetet för den valda serien. 

[![Kalender för processautomatisering](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Förekomständringar

Varje förekomst kan ändras utan att påverka andra förekomster som har definierats i serien. Förekomster av schemalagt arbete kan redigeras i kalendervyn genom att du väljer knappen **Visa/redigera** och väljer **Förekomst**. Denna sida gör att du kan komma åt alla inställningar som ursprungligen visades i guiden för serieinställningar och du kan göra en enstaka ändring för den valda förekomsten. Du kan också stänga av en förekomst av schemalagt arbete genom att välja knappen **Inaktivera** i kalendervyn.

## <a name="developer-documentation"></a>Dokumentation för utvecklare

Med processens automatiseringsramverk kan utvecklare utöka processens automatiseringsramverk. [Ramverket för processautomatisering](../process-automation/process-automation-framework.md) dokumentationen får du information om hur du kan skapa anpassade processer som du behöver köra av den batchservern som är schemalagd med guiden bearbeta automatisering och visas automatiskt i kalendervyn.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
