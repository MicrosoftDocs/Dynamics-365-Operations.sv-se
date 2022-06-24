---
title: Optimera prestanda genom att tidsplanera batchjobb efter timmar
description: I den här artikeln beskrivs hur du löser prestandaproblem med Microsoft Dynamics 365 Human Resources genom att schemalägga långvariga batchjobb efter timmar.
author: twheeloc
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 6efb0a906bb948a47f03665dd6e7a8dd43434083
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896104"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optimera prestanda genom att tidsplanera batchjobb efter timmar


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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

   ![Ange upprepning.](media/talent-batch-history-cleanup-recurrence.png)

4. Under **Definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg. Välj **Inget slutdatum**. 

   ![Definiera startdatum och tid för upprepning.](media/talent-batch-history-cleanup-define-recurrence.png)

5. Välj **OK**.

6. Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

[Optimera prestanda med automatiska rensningsuppgifter](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
