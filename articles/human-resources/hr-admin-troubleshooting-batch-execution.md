---
title: Återställ batchjobb som fastnat
description: I det här ämnet beskrivs hur du löser problem med batchjobb som fastnat.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 906a391b3c28d15445f6ddf0fc547ebcf842ba19
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881770"
---
# <a name="reset-stuck-batch-jobs"></a>Återställ batchjobb som fastnat

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

   ![Välj ett nytt batchjobbstatus](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Se även

[Optimera prestandan genom att schemalägga batchjobb efter kontorstid](hr-admin-troubleshooting-batch-jobs.md)<br>
[Optimera prestanda med automatiska rensningsuppgifter](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
