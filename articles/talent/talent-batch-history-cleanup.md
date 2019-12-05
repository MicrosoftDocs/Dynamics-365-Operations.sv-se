---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I det här avsnittet beskrivs hur du löser vissa prestandaproblem med Microsoft Dynamics 365 Talent genom att rensa historiken för batchjobb.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a053c9094151f4e12e4aadc533dd272258779540
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832592"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimera prestanda med automatiska rensningsuppgifter

[!include [banner](includes/banner.md)]

**Utleverans**

Microsoft Dynamics 365 Talent kan uppleva prestandaproblem om historiken för batchjobb blir för stor.

**Orsak**

Batchjobb som körs ofta kan leda till en hållbar tillväxt av historiken för batchjobb. Detta kan leda till prestandaproblem. 

**Upplösning**

Schemalägg en automatisk uppgift för att rensa historiken för batchjobb. Vi rekommenderar att du anger att aktiviteten ska köras varje vecka, men du kan behöva göra en rensning mer eller mindre ofta, beroende på din miljö. Följande procedur innehåller våra rekommenderade inställningar, men du kan ändra dem efter dina behov.

1. Välj **systemadministration** i Talent.

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

