---
title: Ställ in ett betalsätt för ISO20022-autogiro
description: I denna procedur visas hur du ställer in kundbetalsättet ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 127d5402abfedcce124b39b76a6c1036a6c818a7c1318aaeabdb0688b50f738e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779771"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Ställ in ett betalsätt för ISO20022-autogiro

[!include [banner](../../includes/banner.md)]

I denna procedur visas hur du ställer in kundbetalsättet ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering. 



Innan du slutför denna uppgift måste du skapa exportformatkonfigurationer och betalningskonton.



Proceduren har skapats med demodataföretaget DEMF.



Detta är den tredje av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.

1. Gå till Kundreskontra > Betalningsinställning > Betalsätt.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]