---
title: " Butikskonfigurationer för Retail-utdrag"
description: Den här proceduren går igenom konfigurationer för den butik som påverkar hur handelsutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: 4b73282abd2df92b3f466f7c1c6c210173001fd7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024044"
---
# <a name="store-configurations-for-retail-statements"></a> Butikskonfigurationer för Retail-utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom konfigurationer för den butik som påverkar hur handelsutdrag skapas och bokförs. Ekonomiska dimensioner för butiker hanteras i en annan procedur. I den här proceduren används demonstrationsföretaget USRT.

1. I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Kanaler > Butiker > Alla butiker**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på **Redigera**.
5. Inställningarna på snabbfliken **Utdrag/avstämning** påverkar skapandet av utdrag, validering och bokföringen för butiken. Expandera snabbfliken **Utdrag/avstämning**.  
6. I fältet **Utdragsmetod** väljer du den metod du vill använda för att gruppera utdragsrader.  
7. Välj Ja i **Ett utdrag per dag** om det ska finnas bara ett utdrag per dag när du skapar utdrag från batchjobbet för skapande av utdrag.  
8. Fältet **Beräkning av kassaavstämning** anger om kassaavstämningar ska läggas till tillsammans, eller om den sista ska användas.  
9. I fältet **Avrundning** välj huvudbokskontot för bokföring av avrundningsdifferenser.  
10. I fältet **Högsta avrundningsbelopp** kan du ange den största tillåtna avrundningsdifferensen.
11. I fältet **Bokföring** kan du ange den högsta totala tillåtna bokföringsdifferensen för ett utdrag.
12. I fältet **Skift** kan du ange den högsta totala tillåtna differensen i ett skift i ett utdrag.  
13. I fältet **Transaktion** kan du ange den högsta totala tillåtna differensen på en utdragsrad.  
14. I fältet **Stängningsmetod** kan du definiera om transaktioner som ska inkluderas i ett utdrag ska ingå i ett stängt skift eller om de kan vara transaktioner inom det angivna datum/tidintervallet.  
15. I fältet **Slut på vardagen** kan du ange en tidpunkt om transaktioner som inträffar efter midnatt borde ha bokförts föregående dag.  
16. Välj Ja i **Bokför som vardag** om transaktioner som inträffar efter midnatt borde ha bokförs som en del av föregående dag.  
17. Välj Ja i **Metoden dela efter utdrag** för att få utdrag skapade för varje definierad utdragsmetod. Det kan vara praktiskt om resultatet för bokföringen behöver förbättras för butiker med höga transaktionsvolymer, eftersom den skapar flera mindre utdrag som kan bearbetas parallellt.  
18. I fältet **Standardkund** på snabbfliken **Allmänt** kan du välja kundkontot som ska användas för försäljning till kunder som gör köp direkt i butiken.  

