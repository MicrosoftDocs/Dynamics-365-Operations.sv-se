---
title: Ställ in leverantörer och leverantörsbankkonton för ISO20022-krediteringsöverföringar
description: I den här proceduren visas hur du ställer in den specifika information om leverantören och leverantörens specifika bankkonto som krävs för att generera ISO20022-kreditöverföringen eller någon annan fil för leverantörsbetalning.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a901591f9f3d1a892c29f92e59dc96c1f172143cae6bec571da33b4a50d274
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723729"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Ställ in leverantörer och leverantörsbankkonton för ISO20022-krediteringsöverföringar

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in den specifika information om leverantören och leverantörens specifika bankkonto som krävs för att generera ISO20022-kreditöverföringen eller någon annan fil för leverantörsbetalning. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.
Detta är den fjärde proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="set-up-bank-details"></a>Ställ in bankdetaljer
1. Gå till leverantörsreskontra > Leverantörer > Alla leverantörer.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Leverantörskonto med värdet "DE-001".
3. Klicka på DE-001 om du vill öppna leverantörsinformationen.
4. Klicka på Leverantör i åtgärdsfönstret.
5. Klicka på bankkonton.
6. Klicka på Redigera.
    * Om det inte finns något tillgängligt bankkonto, måste du skapa ett nytt.  
7. Skriv "COBADEFFXXX" i fältet SWIFT-kod.
8. Skriv "DE36200400000628808808" i fältet IBAN.
9. Stäng sidan.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Ställ in betalningsmetod för leverantören
1. Klicka på Redigera.
2. Visa eller dölj avsnittet Betalning.
3. I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.
4. I listan klickar du på länken på SEPA CT-raden.
5. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]