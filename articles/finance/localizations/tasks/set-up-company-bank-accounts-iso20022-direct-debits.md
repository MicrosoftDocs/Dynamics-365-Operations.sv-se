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
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8079dadd09f3e781bcfde21974882cdd59dec809
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256606"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]