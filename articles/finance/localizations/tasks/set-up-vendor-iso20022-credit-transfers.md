---
title: Ställ in leverantörer och leverantörsbankkonton för ISO20022-krediteringsöverföringar
description: I den här proceduren visas hur du ställer in den specifika information om leverantören och leverantörens specifika bankkonto som krävs för att generera ISO20022-kreditöverföringen eller någon annan fil för leverantörsbetalning.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4809a352f87cc3d88429461a06dfe36189ed5f31
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447834"
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

