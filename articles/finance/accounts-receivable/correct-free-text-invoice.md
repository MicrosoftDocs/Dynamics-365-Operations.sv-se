---
title: Korrigera en fritextfaktura
description: Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f04e70c9afb66be015ce18cebebd711f00d764b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827588"
---
# <a name="correct-a-free-text-invoice"></a>Korrigera en fritextfaktura

[!include [banner](../includes/banner.md)]

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
> Den här funktionen är bara tillgänglig om konfigurationsnyckeln **Korrigering av fritextfaktura** markeras. Mer information om hur du aktiverar konfigurationsnycklar finns i avsnittet Aktivera (eller inaktivera) konfigurationsnycklar i avsnittet [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]