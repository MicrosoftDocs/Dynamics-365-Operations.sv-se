--- 
title: "Ställ in företagets bankkonton för ISO20022-kreditöverföringar"
description: "I den här proceduren visas hur du ställer in företagsspecifik bankkontoinformation som krävs för att generera betalningsfilen."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
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
ms.openlocfilehash: 4e55a4727555f781b6880103abb1a38c5d0d5b78
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Ställ in företagets bankkonton för ISO20022-kreditöverföringar

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

