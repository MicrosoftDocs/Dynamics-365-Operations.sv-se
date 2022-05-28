---
title: Koncerninterna order och returorder
description: Detta ämne förklarar koncerninterna order och returorder
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 1c22c021adce5f892ccb6c2ff8735f9e647e8b81
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671854"
---
# <a name="intercompany-orders-and-return-orders"></a>Koncerninterna order och returorder

[!include [banner](../../includes/banner.md)]

Det här avsnittet beskriver hur koncerninterna inköpsorder, försäljningsorder, returorder, inköpsavtal och försäljningsavtal skapas och uppdateras.

## <a name="about-intercompany-orders"></a>Om koncerninterna order

När du skapar en koncernintern försäljningsorder skapar Microsoft Dynamics 365 Supply Chain Management motsvarande inköpsorder automatiskt. På samma sätt medför genereringen av en koncernintern inköpsorder att motsvarande koncerninterna försäljningsorder skapas automatiskt.

Detta gäller för tvåledade order (transaktioner mellan två relaterade företag) samt för de flesta treledade företag (då en koncernintern transaktion uppkommer genom en försäljningsorder från en extern kund).

## <a name="intercompany-order-example"></a>Exempel på koncerninterna order

Du har två relaterade företag. Företag A är ett försäljningsdotterbolag och Företag B är en distributionsenhet. Koncerninterna försäljningsorder och inköpsorder skapas automatiskt i följande scenarier:

- När Företag A skapar en inköpsorder och leverantören är Företag B, skapas en koncernintern försäljningsorder automatiskt i Företag B. Den tvåledade orderkedjan består av en inköpsorder i Företag A och en koncernintern försäljningsorder i Företag B.
- När Företag B skapar en försäljningsorder och leverantören är Företag A, skapas en koncernintern inköpsorder automatiskt i Företag A. Den tvåledade orderkedjan består av en försäljningsorder i Företag B och en koncernintern inköpsorder i Företag A.
- När Företag A skapar en försäljningsorder för en extern kund, kan en inköpsorder skapas automatiskt i Företag A, vilket i sin tur leder till automatisk generering av en koncernintern företagsorder i Företag B. Den treledade orderkedjan består av en försäljningsorder och en inköpsorder i Företag A, och en koncernintern försäljningsorder i Företag B.

## <a name="about-intercompany-return-orders"></a>Om koncerninterna returorder

Du kan returnera koncerninterna artiklar på samma sätt som vanliga returer. Men med koncerninterna artiklar skapar returordern från den externa kunden en koncernintern inköpsorder. Det, i sin tur, leder till automatiskt skapande av en koncernintern försäljningsreturorder. Du kan också returnera en koncernintern artikel utan en extern kundreturneraorder.

Koncerninterna returorder, liknande vanliga returorder, skapas på sidan **Skapa returorder**.

I Microsoft Dynamics 365 Supply Chain Management uppdateras koncerninterna försäljnings- och inköpsavtal automatiskt för att återspegla en returnerad artikel. Försäljnings- eller inköpsavtalsutfästelsen för artikeln justeras automatiskt för att visa ändringar av kvantitet eller belopp när en artikel returneras.

## <a name="intercompany-return-order-example"></a>Exempel på koncerninterna returorder

Företag A skapar en inköpsorder som är länkad till ett inköpsavtal för en koncernintern artikel. En koncernintern försäljningsorder skapas automatiskt i Företag B som är länkad till motsvarande försäljningsavtal. Inköpsavtalet och försäljningsavtalet är relaterade som koncerninterna avtal.

Företag A returnerar den koncerninterna artikeln till Företag B. Företag B skapar en returartikel för artikeln, och en inköpsreturorder skapas automatiskt i Företag A. Utfästelserna i inköpsavtalet och försäljningsavtalet som är länkade till de ursprungliga ordrarna justeras automatiskt för att återspegla ändringen i kvantitet eller belopp.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
