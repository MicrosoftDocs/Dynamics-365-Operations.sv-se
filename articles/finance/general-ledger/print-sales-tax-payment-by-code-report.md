---
title: Skriva ut rapporten för momsbetalning per kod
description: Det här avsnittet innehåller information om de inställningar och åtgärder som krävs för att skriva ut rapporten momsbetalning per kod i redovisnings- eller skattekodsvalutan.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7c863308d2efc442ad16973407fe1cb72fb68cf89204c20f4468a3c98f4740c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774339"
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

    ![Dialogrutan Momsbetalning per kod.](media/Sales-tax-payment-by-code.png)

Den följande bilden visar ett exempel på den rapport som genereras. Rapporten visar att rapporteringskoden **101** har valutan **EUR** om fältet **momsvaluta** anges till **EUR** för den momskod som rapportkoden är tilldelad till.

![Exempel på rapporten för momsbetalning per kod.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]