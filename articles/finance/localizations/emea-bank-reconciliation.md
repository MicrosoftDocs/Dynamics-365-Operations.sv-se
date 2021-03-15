---
title: Bankutdrag och betalningsavstämning för EU
description: Det här avsnittet innehåller en översikt över funktioner med vilka du kan stämma av betalningsinformation från banker i format som används av europeiska länder.
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7773a8557aa19169871102d72dee48677605c7d7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978288"
---
# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a>Bankutdrag och betalningsavstämning för EU

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över funktioner med vilka du kan stämma av betalningsinformation från banker i format som används av europeiska länder. Du kan importera transaktioner från banker och kvitta dessa transaktioner mot befintliga transaktioner. I Europa kan du göra detta i följande fall:

-   Importera bankutdrag
-   Importera betalningar
-   Importera returfiler

## <a name="bank-statements"></a>Bankutdrag
Ett *bankutdrag* eller *kontoutdrag* är en sammanfattning av finansiella transaktioner som har inträffat under en viss period på ett bankkonto som innehas av ett företag med ett finansinstitut. Du kan importera ett bankutdrag i Finance. Det är viktigt att kvitta importerade transaktioner mot befintliga transaktioner, samt att kontrollera inledande och avslutande saldon på bankkontona. Följande lista innehåller de europeiska format som stöds.

-   Avancerade europeiska format för bankavstämning. Mer information finns i [Översikt för avancerad bankavstämning](../cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Filformatet ISO 20022 camt.053 för bankutdragsmeddelanden.
-   CODA-filformat för bankutdrag. Mer information finns i [CODA-bankutdrag](emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Import- och returmeddelanden för kund- och leverantörsbetalningar
Förutom ett bankutdrag kan banker även tillhandahålla specifika meddelanden som innehåller information om kund- och leverantörsbetalningar, och som kan importeras till Finance och synkroniseras med kund-och leverantörstransaktioner. När ett företag måste ta emot information om inkommande kundbetalningstransaktioner från banken, kan importformaten användas. För företag som använder direktdebitering och kreditöverföring kan returmeddelanden tas emot för att uppdatera statusen för betalningar som tidigare har exporterats. Skillnaden mellan importformat och returformat är att returer oftast riktas mot att uppdatera redan skapade journalrader (dessa kan skapas när överföringar via autogiro eller kredit startas) istället för att skapa nya rader. Vissa komplexa importformat kan även innehålla returer. I följande exempel visas hur denna fördelning bör genomföras.

### <a name="import-formats"></a>Importformat

-   [ISO 20022 camt.054](emea-ISO20022-file-formats.md) bankmeddelande
-   [Nettoimportformat](emea-nor-nets-import-format.md) – Komplexa funktioner för norska betalningsformat
-   [Import av ESR-kundbetalningar](emea-che-esr-customer-payments-import.md) 
-   Importera betalningsformat för Sverige – BankGirot Max och BankGirot OCR-format

### <a name="return-formats"></a>Returformat

-   [ISO 20022 pain.002](emea-ISO20022-file-formats.md)-rapport för betalningsstatus
-   (DNK) BetalingsserviceBasis-returformat – Returformat för kundexportformatet Betalingsservice
-   [Importera betalningsformat för Sverige](emea-swe-payment-formats-import.md) – Bankgirot Autogiro returnerar
-   (SVERIGE) BankGirot retur – Returformat för leverantörsbetalningar som motsvarar exportformatet Bankgirot




[!INCLUDE[footer-include](../../includes/footer-banner.md)]