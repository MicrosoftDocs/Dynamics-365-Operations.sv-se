---
title: " Betalningskonfigurationer för Retail-utdrag"
description: I den här proceduren visas konfigurationer för betalsätt för handel som påverkar hur handelsutdrag skapas och bokförs.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3c8c7678d88b3c01138aa098b8830336885e6445fb41931b19bcda2b95b86b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712367"
---
# <a name="payment-configurations-for-retail-statements"></a> Betalningskonfigurationer för Retail-utdrag

[!include [banner](../includes/banner.md)]

I den här proceduren visas konfigurationer för betalsätt för handel som påverkar hur handelsutdrag skapas och bokförs.

I den här registreringen används demonstrationsföretaget USRT.

1. Gå till Butik och handel > Kanaler > Butiker >Alla butiker.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Ställ in i åtgärdsfönstret.
5. Klicka på Betalsätt.
6. Utöka eller komprimera avsnittet Bokföring.
7. Klicka på Redigera.
    * Välj om de belopp som har tagits emot för denna betalningsmetod ska bokföras på ett huvudbokskonto eller bankkonto.  
    * Välj det konto som de belopp som tas emot för den här betalsättet ska bokföras till.  
    * Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det belopp som beräknas för betalsättet.  
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]