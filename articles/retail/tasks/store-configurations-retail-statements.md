---
title: " Butikskonfigurationer för Retail-utdrag"
description: Den här proceduren går igenom konfigurationer för den butik som påverkar hur butiksutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fddeb8434d916df1613d61da88110dec8fb4465
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563654"
---
# <a name="store-configurations-for-retail-statements"></a> Butikskonfigurationer för Retail-utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom konfigurationer för den butik som påverkar hur butiksutdrag skapas och bokförs. Ekonomiska dimensioner för butiker hanteras i en annan procedur. I den här proceduren används demonstrationsföretaget USRT.

1. Gå till butik och handel > Kanaler > butiker > Alla butiker.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Inställningarna i avsnittet Utdrag/avstämning påverkar skapandet av utdrag, validering och bokföringen för butiken.  Öppna avsnittet Utdrag/avstämning.  
    * Välj den metod du vill använda för att gruppera utdragsraderna efter.  
    * Välj Ja om det ska finnas bara ett utdrag per dag när du skapar utdrag från batchjobbet för skapande av utdrag.  
    * Fältet Beräkning av kassaavstämning anger om kassaavstämningar ska läggas till tillsammans, eller om den sista ska användas.  
    * Välj huvudbokskontot för bokföring av avrundningsdifferenser.  
    * I fältet Högsta avrundningsbelopp kan du ange den största tillåtna avrundningsdifferensen.  
    * I fältet Bokföring kan du ange den högsta totala tillåtna bokföringsdifferensen för ett utdrag.  
    * I fältet Skift kan du ange den högsta totala tillåtna differensen i ett skift i ett utdrag.  
    * I fältet Transaktion kan du ange den högsta totala tillåtna differensen på en utdragsrad.  
    * I fältet Stängningsmetod kan du definiera om transaktioner som ska inkluderas i ett utdrag ska ingå i ett stängt skift eller om de kan vara transaktioner inom det angivna datum/tidintervallet.  
    * I fältet Slut på vardagen kan du ange en tidpunkt om transaktioner som inträffar efter midnatt borde ha bokförts föregående dag.  
    * Välj Ja om transaktioner som inträffar efter midnatt borde ha bokförs som en del av föregående dag.  
    * Välj Ja för att få utdrag skapade för varje definierad utdragsmetod. Det kan vara praktiskt om resultatet för bokföringen behöver förbättras för butiker med höga transaktionsvolymer, eftersom den skapar flera mindre utdrag som kan bearbetas parallellt.  
    * I fältet Standardkund kan du välja kundkontot som ska användas för försäljning till kunder som gör köp direkt i butiken.  

