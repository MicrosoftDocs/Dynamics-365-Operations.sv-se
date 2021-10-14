---
title: Registrera betalningar automatiskt för koncerninterna kundfakturor
description: Detta ämne förklarar hur du registrerar betalningar automatiskt för koncerninterna kundfakturor
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548545"
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
