---
title: Optimera prestanda genom att tidsplanera batchjobb efter timmar
description: I det här avsnittet beskrivs hur du löser prestandaproblem med Microsoft Dynamics 365 Human Resources genom att schemalägga långvariga batchjobb efter timmar.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 452a87cf5ba6c1ac73636584d75b2ec2ac555e02
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527775"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optimera prestanda genom att tidsplanera batchjobb efter timmar

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
