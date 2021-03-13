---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I det här avsnittet beskrivs hur du löser vissa prestandaproblem med Microsoft Dynamics 365 Human Resources genom att rensa historiken för batchjobb.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 97f6e310d3a69c870fe8ef03bd7a10cc7ab652e5
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114299"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimera prestanda med automatiska rensningsuppgifter

**Utleverans**

Microsoft Dynamics 365 Human Resources kan uppleva prestandaproblem om historiken för batchjobb blir för stor.

**Orsak**

Batchjobb som körs ofta kan leda till en hållbar tillväxt av historiken för batchjobb. Detta kan leda till prestandaproblem. 

**Upplösning**

Schemalägg en automatisk uppgift för att rensa historiken för batchjobb. Vi rekommenderar att du anger att aktiviteten ska köras varje vecka, men du kan behöva göra en rensning mer eller mindre ofta, beroende på din miljö. Följande procedur innehåller våra rekommenderade inställningar, men du kan ändra dem efter dina behov.

1. I Personal, välj **Systemadministration**.

2. I fätet **Sök**, ange **Rensa historik för batchjobb**.

   ![Sök efter rensa historik för batchjobb](media/talent-batch-history-cleanup-search-bar.png)

3. I **Historikgränser (dagar)**, ange **30**.

   ![Ange historikgräns till 30](media/talent-batch-history-cleanup-history-limit.png)

4. Välj **kör i bakgrunden** och välj sedan **återkommande**.

   ![Ange upprepning](media/talent-batch-history-cleanup-recurrence.png)

5. Under **definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg och välj sedan **INGET SLUTDATUM**. 

   ![Definiera återkommande startdatum och tid](media/talent-batch-history-cleanup-define-recurrence.png)

6. Under **ÅTERKOMMANDE MÖNSTER**, välj **dagar** och ange **UPPREPA EFTER ANGIVET INTERVALL** till **7**.

   ![Ställ in rensning för att upprepa veckovis](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Välj **OK**.

8. Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.

