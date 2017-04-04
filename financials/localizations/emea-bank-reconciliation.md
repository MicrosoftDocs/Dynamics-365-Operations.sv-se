---
title: "Bank-uttryck och betalning avstämning – översikt för EU"
description: "Det här avsnittet innehåller en översikt över funktioner kan du stämma av betalningsinformation från banker i format som används av europeiska länder."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267994
ms.assetid: 2bfb8ecc-e850-43cb-9a96-deb11716a391
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 22d93d7b3618d4f5931c6a7e39d681173734b0b9
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-and-payment-reconciliation-overview-for-the-eu"></a>Bank-uttryck och betalning avstämning – översikt för EU

Det här avsnittet innehåller en översikt över funktioner kan du stämma av betalningsinformation från banker i format som används av europeiska länder.

Du kan importera transaktioner från banker och kvittar dessa transaktioner mot befintliga transaktioner i Microsoft Dynamics 365 för operationer. I Europa är gör det du i följande fall:

-   Importera bankutdrag
-   Import av betalningar.
-   Returnerad importering.

## <a name="bank-statements"></a>Bankutdrag
A *bankutdraget* eller *konto uttrycket* är en sammanfattning av finansiella transaktioner som har inträffat under en viss period på ett bankkonto som innehas av ett företag med ett finansiellt institut. Du kan importera ett bankutdrag i Dynamics 365 för operationer. Det är viktigt att kvitta importerade transaktioner med befintliga transaktioner samt kontrollera inledande och avslutande saldot på bankkontona. Följande lista innehåller de europeiska format som stöds.

-   Avancerad avstämning Europeiska filformat. Mer information finns i [avancerade bank-avstämning översikt](../cash-bank-management/advanced-bank-reconciliation-overview.md).
-   ISO 20022 camt.053 meddelande filen bankutdragsformat
-   Filformatet för bank CODA-utdraget. Mer information finns i [CODA-bankutdrag](emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Kund- och leverantörsbetalningar importera och felmeddelanden
Förutom ett bankutdrag kan banker ge specifika meddelanden som innehåller information om kund- och leverantörsbetalningar som kan importeras till Dynamics 365 för operationer och synkroniseras med kund-och leverantörstransaktioner. När ett företag måste ta emot information om inkommande kundtransaktioner betalningar från banken, kan importera format användas. För företag som använder direktdebitering och betalning kan returnerade meddelanden tas emot om du vill uppdatera status för betalningar som tidigare har exporterats. Skillnaden mellan Importformat och RETUR-format är att returnerar riktar oftast om du vill uppdatera skapat journalrader (skapas när direkt inleddes överföringen debet eller kredit) istället för att skapa nya rader. Vissa komplexa Importformat kan även innehålla returer. I följande exempel visas hur denna fördelning bör genomföras.

##### <a name="import-formats"></a>Importformat

-   ISO 20022 camt.054 bank-meddelande
-   [Nätredskap importformatet](emea-nor-nets-import-format.md) -komplexa funktioner för norska betalningsformat
-   Importera ESR kundbetalningar
-   Importera betalningsformat för Sverige - BankGirot Max och BankGirot OCR-format

##### <a name="return-formats"></a>Returnera format

-   ISO 20022 pain.002 betalning statusrapport
-   (DNK) BetalingsserviceBasis returformat – returnerade format för kund Betalingsservice exportformat
-   [Importera betalningsformat för Sverige](emea-swe-payment-formats-import.md) -returnerar Bankgirot Autogiro
-   (SVERIGE) BankGirot RETUR – returnera leverantörsbetalningar format som motsvarar Bankgirot exportformat

