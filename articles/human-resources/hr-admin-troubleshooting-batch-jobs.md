---
title: Optimera prestanda genom att tidsplanera batchjobb efter timmar
description: I det här avsnittet beskrivs hur du löser prestandaproblem med Microsoft Dynamics 365 Human Resources genom att schemalägga långvariga batchjobb efter timmar.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a5aeaeb7311d87a154882b7058b6da430900bd56
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053477"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optimera prestanda genom att tidsplanera batchjobb efter timmar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Utfärda

Microsoft Dynamics 365 Human Resources kan uppleva prestandaproblem om långvariga batchjobb körs under normal arbetstid.

## <a name="resolution"></a>Upplösning

Tidsplanera följande batchjobb vid ledighet. Vi rekommenderar också att du granskar frekvensen av batchjobb som körs ofta. Minska om möjligt upprepningen av batchjobbet. I många fall är standardfrekvensen tillräcklig.

Följande batchjobb ska köras under nätter eller efter timmar. Kontrollera tids zonen för dessa återkommande batchjobb. Vissa batchjobb kan använda Pacific Standard Time (PST).

| Batchjobb | Standardförekomst |
| --- | --- |
| Rensa historik över batchjobb | 1 gång per månad |
| Exportera rensning av mellanlagring | 1 gång per dag |
| Common Data Service-integration, synkronisering av missad begäran | 1 gång per dag |
| Systemjobb för databaskomprimering som regelbundet måste köras på ledig tid | 1 gång per dag |
| Systemjobb för återskapa databasindex som regelbundet måste köras på ledig tid | 1 gång per dag |

1. I Personal, välj **Systemadministration**.

2. I fältet **Sök** söker du efter ett av batchjobben ovan.

3. Välj **kör i bakgrunden** och välj sedan **återkommande**.

   ![Ange upprepning](media/talent-batch-history-cleanup-recurrence.png)

4. Under **Definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg. Välj **Inget slutdatum**. 

   ![Definiera återkommande startdatum och tid](media/talent-batch-history-cleanup-define-recurrence.png)

5. Välj **OK**.

6. Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

[Optimera prestanda med automatiska rensningsuppgifter](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]