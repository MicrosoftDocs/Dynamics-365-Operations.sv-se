---
title: Garanti
description: "Det här avsnittet innehåller information om garanti. I en garanti förbinder sig en bank att betala ett visst belopp till en person om en av bankens kunder inte betalar fakturan eller skulden till den personen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: fa27a5a2b2edb73875b74572bc467cd20a3e7ec8
ms.lasthandoff: 03/31/2017


---

# <a name="letters-of-guarantee"></a>Garanti

Det här avsnittet innehåller information om garanti. I en garanti förbinder sig en bank att betala ett visst belopp till en person om en av bankens kunder inte betalar fakturan eller skulden till den personen. 

En bankgaranti är ett avtal med en bank (garanten) om att betala ett belopp som till en person (mottagare) om en bankkund (gäldenär) inte gör en betalning eller uppfyller en skyldighet gentemot mottagaren. Garantier är inte överlåtbara. De gäller endast mottagaren som anges i avtalet. Gäldenären kan begära en ökning eller minskning en värdet på en garanti, i enlighet med villkoren för avtalet. 

Om du vill likvidera en garanti måste mottagaren skicka den ursprungliga garantin och informera banken om att gäldenären inte har betalat före utgångsdatumet. Banken betalar sedan det utestående beloppet till mottagarens konto, enligt villkoren i garantin. Banken tar en procentandel av betalningen som marginal. Procentandelen överenskoms och anges i villkoren för avtalet. 

Du kan skapa en kod för att följa syftet med en garanti. Du kan även ange de orsaker som kan kopplas till en garanti när garantin annulleras. Du kan visa syftekoderna och bankorsakerna på sidorna **Syfteskoder för betalning** och **Bankorsaker** . 

Du kan använda sidan **Garanti** för att utföra följande uppgifter:

-   Skapa korrekta redovisningsposter och eliminera manuell registrering.
-   Registrera alla monetära och icke-monetära transaktioner följa upp saldon för garantier.
-   Registrera och följa upp status och förfallotidpunkten för garantier.
-   Generera en rapport som visar banker som har garantier.

I tabellen nedan beskrivs vilka åtgärder du kan utföra i samband med en garanti.

| Åtgärd              | Syfte                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Skicka till bank      | Skicka en begäran till banken att utfärda en garanti.                                                                       |
| Ta emot från bank   | När banken har gått med på att begäran, får du garantin från banken.                            |
| Ge till mottagare | När du har fått garantin från banken ger du den till mottagaren.              |
| Öka värde      | Om mottagaren och gäldenären är överens kan det monetära värdet ökas.                                                  |
| Minska värde      | Om mottagaren och gäldenären är överens kan det monetära värdet minskas.                                                  |
| Utöka              | När du har gett garantin till mottagaren går det att förlänga giltighetstiden om det är nödvändigt. |
| Avbryt              | När syftet med garantin inte längre finns kan du avsluta avtalet.                  |
| Likvidera           | När mottagaren presenterar garantin för banken betalas garantin.                      |




