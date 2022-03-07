---
title: Bekräfta betalningsplaner för tillgångsleasing i en batch
description: I det här ämnet beskrivs hur du bekräftar flera betalningsplaner i en batch.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9a3bd7293fed4b8df5d7bd76edacbcae253aa1f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816086"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Bekräfta betalningsplaner för tillgångsleasing i en batch

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du bekräftar flera betalningsplaner i en batch. Betalningsplaner bekräftas antingen på leasing-till-leasing-basis eller via batchprocessen för bekräftelse. En journalpost kan bara bokföras mot en leasing som har en bekräftad betalningsplan. En bekräftelse av betalningsplanen fungerar som ett slutligt godkännande av den finansiella informationen för leasingen. Alla framtida ändringar av den ekonomiska informationen för leasingen, såsom betalningar och leasingperioden, utgör en leasingjustering och bör bearbetas på detta sätt.

Om du vill bekräfta flera betalningsplaner följer du dessa steg.

1. Gå till **Leasing av tillgångar \> Periodisk \> Bekräftelsebatch**.
2. På sidan **Bekräftelsebatch** väljer du **Bekräftelsebatch**.
3. I dialogrutan som visas filtrerar du fram de böcker du vill bekräfta.

    - Om du vill bekräfta alla böcker i en viss leasinggrupp väljer du gruppen i fältet **Leasinggrupp**.
    - Om du vill bekräfta vissa böcker väljer du böckerna i fältet **Bok-ID**.
    - Bekräfta alla böcker genom att aktivera parametern **För alla böcker**.

Information för de nyligen bekräftade böckerna visas på sidan **Bekräftade böcker**. När betalningsplanerna har bekräftats kan de ursprungliga redovisningsjournalposterna bokföras mot leasingarna.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]