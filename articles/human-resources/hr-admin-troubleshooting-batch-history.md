---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I detta avsnitt beskrivs hur du förbättrar prestandan i Microsoft Dynamics 365 Human Resources genom att rensa historiken för batchjobb.
author: twheeloc
ms.date: 08/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 47cd132c188c39c8700cae6035ae75d0ce71d841
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687231"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimera prestanda med automatiska rensningsuppgifter


[!INCLUDE [PEAP](../includes/peap-2.md)]

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
