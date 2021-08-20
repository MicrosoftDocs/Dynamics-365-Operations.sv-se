---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I det här avsnittet beskrivs hur du löser vissa prestandaproblem med Microsoft Dynamics 365 Human Resources genom att rensa historiken för batchjobb.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 767358705e6f43322c819116d47f4f348ca0966c7859c9f6f22a0f8004615319
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744856"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimera prestanda med automatiska rensningsuppgifter

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

Microsoft Dynamics 365 Human Resources kan uppleva prestandaproblem om historiken för batchjobb blir för stor.

**Orsak**

Batchjobb som körs ofta kan leda till en hållbar tillväxt av historiken för batchjobb. Detta kan leda till prestandaproblem. 

**Upplösning**

Schemalägg en automatisk uppgift för att rensa historiken för batchjobb. Vi rekommenderar att du anger att aktiviteten ska köras varje vecka, men du kan behöva göra en rensning mer eller mindre ofta, beroende på din miljö. Följande procedur innehåller våra rekommenderade inställningar, men du kan ändra dem efter dina behov.

1. I Personal, välj **Systemadministration**.

2. I fätet **Sök**, ange **Rensa historik för batchjobb**.

   ![Sök efter historikrensning för batchjobb.](media/talent-batch-history-cleanup-search-bar.png)

3. I **Historikgränser (dagar)**, ange **30**.

   ![Ange historikgräns till 30.](media/talent-batch-history-cleanup-history-limit.png)

4. Välj **kör i bakgrunden** och välj sedan **återkommande**.

   ![Ange upprepning.](media/talent-batch-history-cleanup-recurrence.png)

5. Under **definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg och välj sedan **INGET SLUTDATUM**. 

   ![Definiera startdatum och tid för upprepning.](media/talent-batch-history-cleanup-define-recurrence.png)

6. Under **ÅTERKOMMANDE MÖNSTER**, välj **dagar** och ange **UPPREPA EFTER ANGIVET INTERVALL** till **7**.

   ![Ställ in rensning att upprepas veckovis.](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Välj **OK**.

8. Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]