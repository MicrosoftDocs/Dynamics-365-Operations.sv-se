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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 3a884837ab0b5a1f4211532969619b54206bbef4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a>Ställ in en betalningsmetod för ISO20022-autogiro

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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


