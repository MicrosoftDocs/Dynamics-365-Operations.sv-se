---
title: "Omedelbar lagerpåfyllnad"
description: "Det här avsnittet beskriver hur du kan använda direkt påfyllnad för att fylla på lagret när ett platsdirektiv inte kan fördela lager."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a11a26df85647aa36cd30c42f81be4ec2af4409b
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="immediate-replenishment"></a>Omedelbar lagerpåfyllnad

[!include [banner](../includes/banner.md)]

Omedelbar lagerpåfyllnad gör det möjligt att fylla på lagret direkt efter att ett platsdirektiv för lagerställe misslyckas att tilldela lager. Påfyllningen baseras på en enkel rad i inställningarna av platsdirektivet. Om lagerbehållning inte finns är måttenheten som anges av den raden sker lagerpåfyllnad av den måttenheten omedelbart.

Omedelbar lagerpåfyllnad är ett alternativ till metoden där allokering av lagret baseras på flera rader i platsdirektivet och där efterfrågan summeras i slutet av allokeringen och fylls på i måttenheten som har angetts i formuläret sista raden i platsdirektivet.

Fördelarna med omedelbar lagerpåfyllnad är att lagerpåfyllnad kan begränsas av specifika enheter och kvantiteten kan dirigeras till specifika platser.

## <a name="business-scenario"></a>Affärsscenario

Exempelvis har du ett lagerställe som har separata plockområden för måttenheterna "ruta" och ”alla”. Om du vill optimera plockningsprocessen genom att välja så många rutor som möjligt och plockning av resterande kvantiteter som är mindre än en ruta från området ”alla”.

I det här fallet kan du använda omedelbar lagerpåfyllnad. I platsdirektiv kan du ange omedelbart lagerpåfyllnad för rutorna så att lagerpåfyllnad för efterfrågan används när det blir brist på rutor som kan plockas för efterfrågekvantiteten. På så sätt kan du optimera plockningsprocessen så att plockningen innehåller så många rutor som möjligt. Omedelbar lagerpåfyllnad genererar lagerpåfyllnad av rutor och efterfrågan kommer inte att skickas vidare så att kvantiteterna som plockas i måttenheten ”alla”. Med andra ord plockas endast den kvantitet som ska plockas i måttenheten ”alla” (dvs kvantiteter som är mindre än en ruta) från området ”alla”. Om brist visas i området ”ruta” kan du välja så många rutor som möjligt från den totala efterfrågan. De återstående kvantiteterna plockas sedan från området ”alla”.

## <a name="where-it-applies"></a>Tillämpning

Omedelbar påfyllning används under påfyllnadskörning om tilldelning misslyckas för en platsdirektivsrad som en påfyllnadsmall anges för.

## <a name="set-up-immediate-replenishment"></a>Ange omedelbar lagerpåfyllnad

- Gå till **lagerstyrning**\>**inställningar**\>**platsdirektiv**, och sedan till fliken **rader** i listan **omedelbar påfyllnadsmall** och välj en påfyllnadsmall för påfyllnadsbegäran.

Påfyllnadsmallen tillämpas om platsdirektivraden misslyckas att tilldelas en särskild måttenhet.

## <a name="troubleshooting"></a>Felsökning

Om omedelbar lagerpåfyllnad har valts för en platsdirektivrad men inget påfyllnadsarbete genereras när du använder mallar för begäran om lagerpåfyllnad för den platsdirektivraden måste två huvudorsaker undersökas:

- Kontrollera att påfyllnadsmallen för efterfrågan som används är konfigurerad till att använda rätt platsmallar och arbetsmallar för typen **Lagerpåfyllnad**.
- Kontrollera att det inte finns tillräcklig lagerbehållning på platser där lagerpåfyllnadsmallen för efterfrågan söker efter lagerbehållning för påfyllnad.

