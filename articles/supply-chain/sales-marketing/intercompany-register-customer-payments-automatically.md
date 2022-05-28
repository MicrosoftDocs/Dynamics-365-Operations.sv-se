---
title: Registrera betalningar automatiskt för koncerninterna kundfakturor
description: Detta ämne förklarar hur du registrerar betalningar automatiskt för koncerninterna kundfakturor
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
ms.openlocfilehash: dbd06b21d736d1e247cd087e5bb86fbe641352e6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669444"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Registrera betalningar automatiskt för koncerninterna kundfakturor

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management skapar en kundtransaktion när en koncernintern kundfaktura bokförs. Denna kundtransaktion förblir öppen tills den kvittas, vilket innebär att den har betalats. När motsvarande koncerninterna inköpsorder är fakturauppdaterad skapas en leverantörstransaktion som matchar kundtransaktionen. Leverantörstransaktionen förblir också öppen tills den kvittas. För att minska risken för skillnader kan en betalningsjournal för kundreskontra skapas och bokföras automatiskt när betalningsjournalen för kundreskontra bokförs.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Om du vill ställa in betalningar för koncerninterna kundreskontra på sidan **Koncernintern** för försäljningsorder väljer du länken **Försäljningsorderpolicyer**.
1. I fältet **Betalningsjournal** välj den betalningsjournal för kundreskontra som du vill registrera koncerninterna leverantörsbetalningar till. Du kan ställa in detta på sidan **Parametrar för kundreskontra**.
1. Om du vill bokföra den här journalen automatiskt markerar du kryssrutan **Bokför journal automatiskt**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
