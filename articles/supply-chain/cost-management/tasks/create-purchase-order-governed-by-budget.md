---
title: Skapa en inköpsorder som omfattas av budget
description: Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8458fc1f47f929ac612acfb3a2d75a79c8fb7d6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671378"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Skapa en inköpsorder som omfattas av budget

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget. I den här inspelningen används demonstrationsföretaget USMF.


## <a name="review-the-budget-control-configuration"></a>Granska budgetkontrollkonfigurationen
1. Gå till Budgetering > Inställningar > Budgetkontroll > Budgetkontrollkonfiguration.
2. Klicka på fliken Budgetmedel är tillgängliga.
3. Klicka på fliken Dokument och journaler.
4. Klicka på fliken Definiera budgetkontrollregler.
5. Klicka på fliken Definiera budgetgrupper.
6. Stäng sidan.

## <a name="create-the-purchase-order-header"></a>Skapa inköpsorderrubriken
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Leverantörskonto.
4. Expandera avsnittet Allmänt.
5. Ställ in datumet i fältet Redovisning till "2016-01-01".
6. Klicka på OK.

## <a name="add-a-purchase-order-line"></a>Lägg till en inköpsorderrad
1. Ange eller välj ett värde i fältet Anskaffningskategori.
2. Ställ in kvantiteten till 2.
3. Ange eller välj ett värde i fältet Enhet.
4. Ställ in Enhetspris till "10 000".
5. Klicka på Ekonomi.
6. Klicka på Fördela belopp.
7. Ange värdet "601300-001-023--" i fältet Redovisningskonto.
8. Stäng sidan.

## <a name="perform-budget-checking"></a>Utför budgetkontroll
1. Klicka på Ekonomi.
2. Klicka på Utför budgetkontroll.
3. Klicka på Ekonomi.
4. Klicka på Fel eller varningar från budgetkontroll.
5. Klicka på Stäng.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]