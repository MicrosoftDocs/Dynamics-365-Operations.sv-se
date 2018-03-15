--- 
title: " Betalningskonfigurationer för Retail-utdrag"
description: "I den här proceduren visas konfigurationer för betalningsmetoder för butik som påverkar hur detaljhandelsutdrag skapas och bokförs."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 0ffd6dc5fff6d27ec3cfdcd68c53b2299c4100b9
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="payment-configurations-for-retail-statements"></a> Betalningskonfigurationer för Retail-utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren visas konfigurationer för betalningsmetoder för butik som påverkar hur detaljhandelsutdrag skapas och bokförs.

I den här registreringen används demonstrationsföretaget USRT.

1. Gå till butik och handel > Kanaler > butiker > Alla butiker.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Ställ in i åtgärdsfönstret.
5. Klicka på Betalningsmetoder.
6. Utöka eller komprimera avsnittet Bokföring.
7. Klicka på Redigera.
    * Välj om de belopp som har tagits emot för denna betalningsmetod ska bokföras på ett huvudbokskonto eller bankkonto.  
    * Välj det konto som de belopp som tas emot för den här betalningsmetoden ska bokföras till.  
    * Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det belopp som beräknas för betalningsmetoden.  
    * I det här fältet kan du ange ett konto att styra när avvikelsebeloppet ska bokföras på ett annat differenskonto. Du kan använda det här alternativet för att spåra stora differenser.  
    * Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det beräknade beloppet, när de överskrider det värde som har definierats i fältet Högsta avvikelsebelopp.  
    * Välj Ja om du vill bokföra de belopp som sätts in på bank på ett separat konto.  
    * I det här fältet kan du välja om de belopp som sätts in på bank ska bokföras på ett huvudbokskonto eller ett bankkonto.  
    * Välj det konto du vill bokföra de belopp som sätts in på bank på.  
    * Välj den banktransaktionstyp som ska användas när du bokför belopp som sätts in på bank på bankkontot.  
    * Välj Ja om du vill bokföra de belopp som lämnats i kassaskåp på ett separat konto.  
    * I det här fältet kan du välja om de belopp som lämnats i kassaskåp ska bokföras på huvudbokskontot eller bankkontot.  
    * Välj det konto du vill bokföra de belopp som lämnats i kassaskåp på.  
8. Klicka på Spara.


