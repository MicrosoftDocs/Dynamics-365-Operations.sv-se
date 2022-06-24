---
title: Registrera betalningar automatiskt för koncerninterna kundfakturor
description: Denna artikel förklarar hur du registrerar betalningar automatiskt för koncerninterna kundfakturor
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
ms.openlocfilehash: 4e8f784cd310026f0a647a0f509999e11ab26ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878799"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Registrera betalningar automatiskt för koncerninterna kundfakturor

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management skapar en kundtransaktion när en koncernintern kundfaktura bokförs. Denna kundtransaktion förblir öppen tills den kvittas, vilket innebär att den har betalats. När motsvarande koncerninterna inköpsorder är fakturauppdaterad skapas en leverantörstransaktion som matchar kundtransaktionen. Leverantörstransaktionen förblir också öppen tills den kvittas. För att minska risken för skillnader kan en betalningsjournal för kundreskontra skapas och bokföras automatiskt när betalningsjournalen för kundreskontra bokförs.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Om du vill konfigurera betalningar för koncerninterna kundreskontra på sidan **Koncernintern** för försäljningsorder väljer du länken **Försäljningsorderpolicyer**.
1. I fältet **Betalningsjournal** välj den betalningsjournal för kundreskontra som du vill registrera koncerninterna leverantörsbetalningar till. Du kan konfigurera detta på sidan **Parametrar för kundreskontra**.
1. Om du vill bokföra den här journalen automatiskt markerar du kryssrutan **Bokför journal automatiskt**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
