---
title: Returnera artiklar för flera kunder, order och fakturor
description: I det här avsnittet beskrivs funktionen som gör det möjligt att returnera via flera kundorder och fakturor i Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c36fe4c8376ad0364516c0268965c798e20436c6
ms.sourcegitcommit: 3a9599e9b9458434c0e44d295eabd2304c5650be
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "6334435"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Returnera artiklar för flera kunder, order och fakturor

[!include [banner](includes/banner.md)]


Returer kan göras för flera order och fakturor. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Konfigurera Commerce så att det går att göra returer för flera kundorder och fakturor

1. Gå till **Commerce-parametrar \> Kundorder**.
1. Aktivera parametern **Aktivera returer för flera order**. 

## <a name="process-returns"></a>Bearbeta returer

När parametern är aktiverad och ändringarna synkroniserats till butikerna, kan kassören i butiken välja flera försäljningsorder för en kund och göra returer.

När ordern har valts visas en lista över alla produkter på alla fakturor som kan returneras för ordern. Kassören kan sedan välja vilka produkter som ska returneras. En enda returorder skapas för alla valda produkter.
