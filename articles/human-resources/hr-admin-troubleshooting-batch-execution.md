---
title: Återställ batchjobb som fastnat
description: I det här ämnet beskrivs hur du löser problem med batchjobb som fastnat.
author: twheeloc
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: f1aa9f53e0d314edd920a664d18408019325d435
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2022
ms.locfileid: "8534033"
---
# <a name="reset-stuck-batch-jobs"></a>Återställ batchjobb som fastnat


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Utleverans

Microsoft Dynamics 365 Human Resources kan uppleva problem med batchjobb som sitter fast i antingen ett **Utförande** eller **Avbrytande** tillstånd och inte är fullständig.

## <a name="resolution"></a>Upplösning

När ett batchjobb har körts fast i läget **Utförande** eller **Avbrytande** kan du återställa statusen genom att framtvinga annulleringen av jobbet. När du har annullerat det kan du återställa batchjobbet genom att ange det till **Väntande** tillstånd. Den kommer då att hämtas igen för körning i nästa planerade batchkörning.

1. I arbetsytan **Systemadministration**, välj sidan **Länkar** och välj **Batch-jobb**.

2. I listsidan **Batch-jobb**, välj det jobb som behöver återställas.

3. Välj på åtgärdsmenyfliken **Tvinna annullering** och bekräfta åtgärden.

   > [!NOTE]
   > Åtgärden **Tvinga annullering** är bara tillgänglig när det valda batchjobbet har statusvärdet **Utföra** eller **Annullera** och inga batchkörnings- eller avbokningsprocesser körs för jobbet.

4. På åtgärdsmenyfliken väljer du **Ändra status**.

5. På sidan **Välj ny status**, välj **Väntar** och sedan **OK**.

   ![Välj en ny status för batchjobb.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Se även

[Optimera prestandan genom att schemalägga batchjobb efter kontorstid](hr-admin-troubleshooting-batch-jobs.md)<br>
[Optimera prestanda med automatiska rensningsuppgifter](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
