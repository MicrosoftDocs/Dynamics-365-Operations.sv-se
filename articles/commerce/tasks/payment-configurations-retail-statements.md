---
title: " Betalningskonfigurationer för Retail-utdrag"
description: I den här proceduren visas konfigurationer för betalningsmetoder för handel som påverkar hur handelsutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 390ccdfde3f9bb93770d456af7532a42e81955a1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140817"
---
# <a name="payment-configurations-for-retail-statements"></a> Betalningskonfigurationer för Retail-utdrag

[!include [banner](../includes/banner.md)]

I den här proceduren visas konfigurationer för betalningsmetoder för handel som påverkar hur handelsutdrag skapas och bokförs.

I den här registreringen används demonstrationsföretaget USRT.

1. Gå till Butik och handel > Kanaler > Butiker >Alla butiker.
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
