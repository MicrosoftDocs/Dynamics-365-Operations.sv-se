---
title: Korrigera en fritextfaktura
description: "Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a143a373a63ab145ee4c25bb1abfab777cca6619
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="correct-a-free-text-invoice"></a>Korrigera en fritextfaktura

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.

Öppna bokförd fritextfaktura för att åtgärda en fritextfaktura som redan har bokförts. På sidan **Faktura**, välj **Avbryt** och sedan **Korrigera faktura**. Välj en orsakskod, lägg till kommentarer och välj datum för ny korrigerad faktura. Du kan ändra den korrigerade fakturan och bokföra den. 

När du bokför den korrigerade fakturan skapas en annulleringsfaktura för ett kreditbelopp som är lika med det ursprungliga fakturabeloppet. Därför är det kombinerade saldot för den ursprungliga fakturan och annulleringsfakturan 0 (noll). Annulleringsfakturan kvittas mot den ursprungliga fakturan. 

När du har bokfört den korrigerade fakturan har du tre fakturor:

-   **Ursprunglig faktura** – Fakturan som innehåller informationen som du korrigerar.
-   **Annulleringsfaktura** – Den systemgenererade kreditfakturan som har skapats för att annullera fakturan som senast korrigerades.
-   **Korrigerad faktura** – Fakturan som innehåller den korrigerade fakturainformationen.

Du kan identifiera annullerings- och korrigeringsfakturor på två sätt:

-   Sidan **Alla fritextfakturor** innehåller kolumnen **Korrigering** där du ser vilka fakturor som är annulleringsfakturor och korrigerade fakturor.
-   Sidhuvudet på fritextfakturan anger statusen **Annullerar faktura "\[fakturanummer\]"'** eller **Korrigerad faktura "\[fakturanummer\]"**.

> [!NOTE]
> Den här funktionen är bara tillgänglig om konfigurationsnyckeln **Korrigering av fritextfaktura** markeras.



