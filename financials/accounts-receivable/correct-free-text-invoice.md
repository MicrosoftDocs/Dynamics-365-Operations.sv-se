---
title: Korrigera en fritextfaktura
description: "Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: ab16c517abfd3fa2b59625fff04b7427ee3471bb
ms.lasthandoff: 03/31/2017


---

# <a name="correct-a-free-text-invoice"></a>Korrigera en fritextfaktura

Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.

Öppna bokförd fritextfaktura åtgärda en fritextfaktura som redan har bokförts. I den **fakturan** anger **Avbryt**, och välj sedan **fel faktura**. Välj en orsakskod, lägg till kommentarer och välj datum för ny korrigerad faktura. Du kan ändra den korrigerade fakturan och bokföra den. 

När du bokför den korrigerade fakturan skapas en annulleringsfaktura för ett kreditbelopp som är lika med det ursprungliga fakturabeloppet. Därför är det kombinerade saldot för den ursprungliga fakturan och annulleringsfakturan 0 (noll). Annulleringsfakturan kvittas mot den ursprungliga fakturan. 

När du har bokfört den korrigerade fakturan har du tre fakturor:

-   **Ursprunglig faktura** – Fakturan som innehåller informationen som du korrigerar.
-   **Annulleringsfaktura** – Den systemgenererade kreditfakturan som har skapats för att annullera fakturan som senast korrigerades.
-   **Korrigerad faktura** – Fakturan som innehåller den korrigerade fakturainformationen.

Du kan identifiera annullerings- och korrigeringsfakturor på två sätt:

-   Sidan **Alla fritextfakturor** innehåller kolumnen **Korrigering** där du ser vilka fakturor som är annulleringsfakturor och korrigerade fakturor.
-   Huvudet på fritextfakturan visas statusen **Cancelling fakturan '\[fakturanummer\]'** eller **korrigerade fakturan '\[fakturanummer\]'**.

> [!NOTE]
> Den här funktionen finns bara om den **ledig fakturan Textkorrigering** konfigurationsnyckeln har valts.


