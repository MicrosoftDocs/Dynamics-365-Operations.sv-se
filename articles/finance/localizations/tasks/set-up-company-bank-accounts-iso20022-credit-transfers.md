---
title: Ställ in företagets bankkonton för ISO20022-kreditöverföringar
description: I den här proceduren visas hur du ställer in företagsspecifik bankkontoinformation som krävs för att generera betalningsfilen.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a3ddcae4a53fffa07bd386174811c12150f2f162
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819490"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Ställ in företagets bankkonton för ISO20022-kreditöverföringar

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in företagsspecifik bankkontoinformation som krävs för att generera betalningsfilen. Du ställer in information som krävs för att skapa format för ISO 20022-kreditöverföring, men beroende på formatet kan annan information krävas, till exempel företags-ID eller sorteringskod. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.

Detta är den andra proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="set-up-iban-and-swift-code"></a>Ställ in IBAN- och SWIFT-koden
1. Gå till Kassa- och bankhantering > Bankkonton.
2. Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "DEMF OPER".
3. Klicka på DEMF OPER för att öppna bankkontoinformationen.
4. Klicka på Redigera.
5. Expandera avsnittet Additional identification section.
6. Skriv "DE89370400440532013000" i fältet IBAN.
7. Skriv "DEUTDEFF" i fältet SWIFT-kod.
    * Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.  
8. Klicka på Spara.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Ställ in bankkonto för den juridiska personen
1. Gå till Organisationsadministration > Organisationer > Juridiska personer.
2. Klicka på Redigera.
3. Expandera avsnittet Bankkontoinformation.
4. Ange eller välj ett värde i fältet Bankkonto.
5. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]