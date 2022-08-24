---
title: Omklassificera anläggningstillgångar
description: Det här ämnet beskriver omklassificering av tillgångar. Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bd901b1709f0b006cecfbbf6d8c170b56f89d19
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284376"
---
# <a name="reclassify-fixed-assets"></a>Omklassificera anläggningstillgångar

[!include [banner](../../includes/banner.md)]

Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp. 

När en anläggningstillgång omklassificeras:

- Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången. All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången. Statusen för den ursprungliga anläggningstillgångens böcker är Stängd. 

- De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**. Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen. Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**. 

- De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.

- När en tillgång som har en överföringstransaktion har omklassificerats visas ett meddelande i **Åtgärdscentret** som anger att en överföringstransaktion inte slutförs i samband med omklassificeringen. Det är nödvändigt att slutföra en överföringstransaktion för att flytta de befintliga omklassificeringstransaktionerna till de relevanta ekonomiska dimensionerna. 

   Under omklassificeringsprocessen kör systemet följande åtgärder för att omklassificera tillgångssaldot från den ursprungliga tillgången till den nya tillgången. 
   
   - Omklassificeringsprocessen kopierar data från den ursprungliga anläggningstillgångsboken till den nya anläggningstillgångsboken.

   - Omklassificeringstransaktionen använder information från den ursprungliga bokförda anskaffningen som inkluderar information om den ekonomiska dimension som är inkluderad i anskaffningstransaktionen.  
   
   - Samtidigt återställer omklassificeringsprocessen den ursprungliga anskaffnings- och överföringstransaktionen av tillgångar. 

Följande diagram och procedur ger ett exempel på omklassificeringsprocessen. 

[![Diagram som visar omklassificeringsprocesser.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

Följ dessa steg för att omklassificera en anläggningstillgång:

1. Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.
2. I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.
3. I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.
4. I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.
    * Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie. I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**. Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.  
5. Ange ett datum i fältet **Omklassificeringsdatum**.
6. Ange eller välj ett värde i fältet **Verifikationsserie**.
7. Välj **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
