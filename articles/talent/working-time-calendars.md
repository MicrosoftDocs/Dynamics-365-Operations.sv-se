---
title: Arbetstidskalendrar
description: Det här avsnittet beskriver arbetstidskalendrar i Dynamics 365 for Talent -- Core HR liksom hur du ställer in kalendrar.
author: jcart1106
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 2465065d7db18a5468d7c979e0d6cb9c7e76f969
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306221"
---
# <a name="working-time-calendars"></a>Arbetstidskalendrar

[!include [banner](includes/banner.md)]

Arbetstidskalendern låter dig skapa en kalender med det antal timmar och dagar som medarbetarna arbetar i organisationen. Kalendrar effektiviserar ansökningsprocessen för ledig tid som standard i timmar eller dagar. När en medarbetare skickar en begäran om ledighet, behöver de inte bekymra sig om helgdagar och öppettider som hanteras åt dem via arbetstidskalendern.

## <a name="setting-up-a-working-time-calendar"></a>Ställa in en arbetstidskalender

Kalendrar innehåller information om generering, dagar och tider som du vill inkludera, dagar i kalendern, arbetstider för de dagarna och även registrerade medarbetare. 

Så här ställer du in en kalender:

1. På sidan **Organisationsadministration** klickar du på **kalendrar**.

2. I åtgärdsfönstret, välj **Ny** och ange ett namn och en beskrivning.

3. Välj arbetsdagar för ditt företag och ange arbetstid.

4. Lägg till helgdagar och öppettider med knappen **Lägg till**.

5. Ange namn och beskrivning för helger och öppettider till exempel amerikanska helger eller helgdagar. Ange datum för helgdagar och öppettider. Spara listan över helgdagar och öppettider och stäng sidan.

6. Välj listan över helgdagar och öppettider från rullgardinsmenyn.

7. Om dina medarbetare har arbetsfria tider, till exempel luncher eller raster, lägg till de också. Välj **Arbetsfria tider** och ange namnet och tidsintervall. Stäng sidan. 

8. Klicka på **Lägg till** för att lägga till arbetstiden i kalendern.

9. På fliken **dagar**, välj **generera** för att generera dagar i kalendern. Ange datumintervall för kalendern. Dagar och arbetstider skapas baserat på de arbetsdagar och tider som definieras i alternativ för generering tillsammans med de datum som valts.

10. För att tilldela en kalender till medarbetare, välj **tilldela medarbetare** i åtgärdsfönstret. Välj den medarbetare du vill tilldela till kalendern och klicka sedan på **tilldela**.

Anställda måste inte ha tilldelats kalendrar. Om det finns en definierad arbetstidskalender kommer lediga dagar automatiskt uteslutas från begäran. Antalet timmar eller dagar är som standard de arbetstider som anges i kalendern. Om medarbetaren inte har en kalender tilldelad är alla dagar tillgängliga för ledig tid och ledig tidsmängd är inte standard för begäran. 
