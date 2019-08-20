---
title: Räkenskapskalendrar, räkenskapsår och perioder
description: Det här avsnittet behandlar räkenskapskalendrar, räkenskapsår och perioder och hur du använder dem för juridiska personer, anläggningstillgångar och budgetering.
author: aprilolson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b23b152ed6348b8f20b5deccf94394de6fbe85d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835056"
---
# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Räkenskapskalendrar, räkenskapsår och perioder

[!include [banner](../includes/banner.md)]

Det här avsnittet behandlar räkenskapskalendrar, räkenskapsår och perioder och hur du använder dem för juridiska personer, anläggningstillgångar och budgetering.

Räkenskapskalendrar ger ett ramverk för den ekonomiska aktiviteten i en organisation. Varje räkenskapskalender innehåller ett eller flera räkenskapsår och varje räkenskapsår innehåller flera perioder. Räkenskapskalendrar kan baseras på kalenderår från 1 januari till 31 december eller på datum som du väljer. En del organisationer väljer till exempel en räkenskapskalender som börjar den 1 juli ett år och slutar den 30 juni följande år. 

Det finns ingen gräns för antalet räkenskapskalendrar som du kan skapa, och ingen gräns för antalet räkenskapsår som kan skapas för en räkenskapskalender. Varje räkenskapskalender är oberoende av organisation och kan användas av flera juridiska personer i organisationen. En organisation har till exempel åtta avdelningar och varje avdelning är en separat juridisk person. Fem av dessa delar samma räkenskapskalender och tre använder andra räkenskapskalendrar. Du kan skapa en rapporteringsgrupp kalender för de fem juridiska personerna, med samma räkenskapsårets kalender, och sedan skapar separata räkenskapsårets kalendrar för de övriga juridiska personerna.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Skapa räkenskapskalendrar, räkenskapsår och perioder
Du kan skapa och ta bort räkenskapskalendrar, räkenskapsår och perioder på sidan Räkenskapskalendrar. Du kan också dela upp befintliga perioder och skapa stängningsperioder som kan användas för att stänga ett räkenskapsår. 

En bokslutsperiod används för att separera redovisningstransaktioner som genereras när ett räkenskapsår stängs. När det finns UB-transaktioner i en räkenskapsperiod är det enklare att skapa bokslut inklusive eller utan olika typer av bokslutsposter. Om ett räkenskapsår delas upp i 12 räkenskapsperioder är bokslutsperioden vanligtvis den 13:e perioden. Men en bokslutsperiod kan skapas från en period som har statusen Öppen. 

När du skapar en bokslutsperiod väljer du en period som har statusvärdet Öppen och har de datum som du vill använda. Den nya bokslutsperioden ska kopiera start- och slutdatum från den befintliga perioden. Den ursprungliga perioden fortsätter finnas kvar. Du väljer till exempel Period 12, som är den sista perioden under räkenskapsåret och har datumen 1 augusti till och med 31 augusti. Du anger ett namn för bokslutsperioden, till exempel Stäng. När du har skapat den nya bokslutsperioden har du nu den ursprungliga perioden och bokslutsperioden. Båda har datum som börjar med 1 augusti och slutar på 31 augusti.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Välj räkenskapskalendrar för redovisningar, anläggningstillgångar och budgetcykler
Räkenskapskalendrar används vid avskrivning av anläggningstillgångar, ekonomiska transaktioner och budgetcykler. När du skapar en räkenskapskalender kan du använda den för flera syften. Du kan välja en räkenskapskalender för en förteckning över anläggningstillgångar för att göra den till en kalender för anläggningstillgångar. Du kan välja en räkenskapskalender för en redovisning och göra den till redovisningskalender. Och du kan välja en räkenskapskalender för en budgetcykel för att skapa en budgetkalender. Du kan använda samma räkenskapskalender för alla dessa.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Välj en räkenskapskalender för din juridiska person.

Välj den räkenskapskalender som du vill använda för redovisningen för din juridiska person i redovisningsformuläret. En räkenskapskalender måste väljas på sidan Redovisning för varje juridisk person. När en räkenskapskalender har valts kan du ställa in periodstatus och behörigheter på sidan Redovisningskalender för någon av de perioder som är en del av räkenskapsåret.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Välj en räkenskapskalender för anläggningstillgångar

Du kan välja en räkenskapskalender för en förteckning över anläggningstillgångar och den räkenskapskalendern ska användas av de anläggningstillgångar som använder den valda förteckningen.+ Du kan välja bland alla räkenskapskalendrar som definieras på sidan Räkenskapskalendrar.

### <a name="define-budget-cycle-time-spans"></a>Definiera tidsrymder för budgetcykel

Budgetcykler är den tidsperiod som en budget används. Budgetcykler kan vara en del av ett räkenskapsår eller flera räkenskapsår, till exempel en tvåårig budgetcykel eller en treårig budgetcykel. Tidsrymden för budgetcykel definierar antalet perioder som ingår i budgetcykeln. Använd sidan Tidsrymder för budgetcykel för att ange tidsrymden för budgetcykeln.

## <a name="maintain-periods-for-your-organization"></a>Underhåll perioder för din organisation
Du kan använda sidan Redovisningskalender om du vill visa information om räkenskapskalendern, räkenskapsår och perioder som används i din organisation. Du kan även ändra status för perioderna och markera vilka användare kan bokföra redovisningstransaktioner till perioder. Till exempel i början av en ny period kan du ange att en grupp användare som du vill ska slutföras att bokföra ekonomiska transaktioner i föregående period, medan övriga grupper endast arbetar i den nya perioden.





