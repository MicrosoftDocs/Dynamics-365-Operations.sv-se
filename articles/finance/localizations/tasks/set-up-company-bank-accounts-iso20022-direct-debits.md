---
title: Ställ in företagets bankkonton för ISO20022-autogiron
description: I den här uppgiften går du igenom hur du ställer in den företagsspecifika bankkontoinformation som krävs för att generera kund-betalningsfiler.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 652d8aa8f78d9a12ee390d23904f2c94d9bcf684
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144883"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Ställ in företagets bankkonton för ISO20022-autogiron

[!include [banner](../../includes/banner.md)]

I den här uppgiften går du igenom hur du ställer in den företagsspecifika bankkontoinformation som krävs för att generera kund-betalningsfiler. I den här proceduren används formatet ISO 20022 för autogiro som exempel. Andra format kanske kräver ytterligare inställningsinformation som exempelvis företagets ID eller sorteringskod.



Uppgiften har skapats med demodataföretaget DEMF.



Detta är den andra av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.


## <a name="set-up-the-iban-and-swift-codes"></a>Ställ in IBAN- och SWIFT-koder
1. Gå till Kassa- och bankhantering > Bankkonton.
2. Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "DEMF OPER".
3. Klicka på länken på den valda raden i listan.
    * Klicka till exempel på "DEMF-OPER" för att öppna bankkontoinformationen.  
4. Klicka på Redigera.
5. Expandera eller komprimera avsnittet Ytterligare identifiering.
6. Ange ett värde i fältet IBAN.
    * Ange till exempel "DE89370400440532013000".  
7. Skriv ett värde i fältet SWIFT-kod.
    * Ange till exempel "DEUTDEFF".    Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.  
8. Klicka på Spara.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Ställ in ett bankkonto för den juridiska personen
1. Gå till Organisationsadministration > Organisationer > Juridiska personer.
2. Klicka på Redigera.
3. Expandera eller komprimera avsnittet Bankkontoinformation.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Bankkonto.
5. Klicka på länken på den valda raden i listan.
    * Välj till exempel bankkontot "DEMF OPER".  
6. Klicka på Spara.

