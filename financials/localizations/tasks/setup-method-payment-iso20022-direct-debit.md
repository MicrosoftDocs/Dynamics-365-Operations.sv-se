--- 
title: "Ställ in en betalningsmetod för ISO20022-autogiro"
description: "I denna procedur visas hur du ställer in kundbetalningsmetoden ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16ff0cc28b272add80b08ae43b9fe5b8e7370b70
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a>Ställ in en betalningsmetod för ISO20022-autogiro

[!include[task guide banner](../../includes/task-guide-banner.md)]

I denna procedur visas hur du ställer in kundbetalningsmetoden ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering. 



Innan du slutför denna uppgift måste du skapa exportformatkonfigurationer och betalningskonton.



Proceduren har skapats med demodataföretaget DEMF.



Detta är den tredje av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.

1. Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Betalningsmetod med värdet "ELECTRONIC".
3. Klicka på Redigera.
4. Ange värdena "'DEMF OPER" i fältet Betalningskonto.
5. Expandera avsnittet Filformat.
6. Välj Ja i fältet Allmän elektronisk rapportering.
7. Ange eller välj ett värde i fältet Exportera formatkonfiguration.
    * Välj "ISO20022 Direct debit (DE)" i listan.  Om listan är tom innebär det att inga aktiva konfigurationer av exportformat för kundbetalning har importerats.  
8. Välj Ja i fältet kräv medgivande.
    * Välj parametern Require mandate för layouten för kundbetalningar som kräver inkludering av fullmaktsinformation i betalningsmeddelandet, exempelvis autogiro för SEPA.  
9. Klicka på Spara.


