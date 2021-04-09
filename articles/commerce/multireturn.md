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
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796907"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Returnera artiklar för flera kunder, order och fakturor

[!include [banner](includes/banner.md)]


I den här artikeln beskrivs två funktioner som optimerar kundorderreturer för flera fakturor. 

## <a name="enable-refunds-over-multiple-captures"></a>Aktivera återbetalningar för flera poster

Den här funktionen aktiverar flera kopplade återbetalningar mot samma kundorder. 

1. Gå till arbetsytan **Funktionshantering** och sök efter **Aktivera återbetalningar för flera poster**.
2. Välj **Aktivera återbetalningar för flera order** och klicka sedan på **Aktivera**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Aktivera korrekt momsberäkning för returer med delkvantitet

Med hjälp av den här funktionen kan du se till att momsen blir lika med det momsbelopp som ursprungligen debiterades när en order returneras med hjälp av flera fakturor. 

1. Gå till arbetsytan **Funktionshantering** och sök efter **Aktivera korrekt momsberäkning för returer med delkvantitet**.
2. Välj **Aktivera korrekt momsberäkning för returer med delkvantitet** och klicka sedan på **Aktivera**. 


## <a name="process-returns"></a>Bearbeta returer

När dessa funktioner har aktiverats och ändringarna synkroniserats till butikerna, kan kassören i butiken välja flera försäljningsorder för en kund och göra returer.

När ordern har valts visas en lista över alla produkter på alla fakturor som kan returneras för ordern. Kassören kan sedan välja vilka produkter som ska returneras. En enda returorder skapas för alla valda produkter.

Om ordern har returnerats till fullo kommer momsbeloppet som har returnerats till kunden att vara lika med det momsbelopp som ursprungligen debiterades.



[!INCLUDE[footer-include](../includes/footer-banner.md)]