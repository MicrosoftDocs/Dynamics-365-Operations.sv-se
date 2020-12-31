---
title: Skriva ut rapporten för momsbetalning per kod
description: Det här avsnittet innehåller information om de inställningar och åtgärder som krävs för att skriva ut rapporten momsbetalning per kod i redovisnings- eller skattekodsvalutan.
author: anasyash
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7033999f7258e9ddd1d01620f9ad416e94ef3111
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448018"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Skriva ut rapporten för momsbetalning per kod 

[!include [banner](../includes/banner.md)]

Om du vill skriva ut rapporten **momsbetalning per kod** gå till **moms** \> **förfrågningar och rapporter** \> **momsrapporter** \> **momsbetalning per kod**. Som standard genereras rapportbelopp i den juridiska personens redovisningsvaluta för alla rapportkoder som har ställts in på sidan **momsrapporteringskoder**.

Du kan också generera rapporten så att den visar momsbetalningsbeloppen i valutorna för momskoderna för alla rapportkoder som har tilldelats momskoderna på sidan **momskoder**.

## <a name="turn-on-the-feature"></a>Aktivera en funktion

I arbetsytan **funktionshantering** aktivera följande funktion: **Generera momsbetalningen per kodrapport i valutan för momsbetalningskod**.

## <a name="run-the-report"></a>Köra rapporten

1. Gå till **Skatt** \> **Förfrågningar och rapporter** \> **Momsrapporter** \> **Momsbetalning per kod**.
2. I fältet **rapportvaluta**, välj ett av följande värden:

    - **Redovisningsvaluta** – Skriv ut rapportbeloppen i redovisningsvalutan.
    - **Momskodvaluta** – Skriv ut rapportbeloppen i momskodernas valutor.

    ![Dialogrutan momsbetalning per kod](media/Sales-tax-payment-by-code.png)

Den följande bilden visar ett exempel på den rapport som genereras. Rapporten visar att rapporteringskoden **101** har valutan **EUR** om fältet **momsvaluta** anges till **EUR** för den momskod som rapportkoden är tilldelad till.

![Exempel på rapporten för momsbetalning per kod](media/Sales-tax-payment-by-code-2.png)
