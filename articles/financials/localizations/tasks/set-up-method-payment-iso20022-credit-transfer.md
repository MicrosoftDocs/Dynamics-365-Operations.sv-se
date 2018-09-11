--- 
title: "Ställ in en betalningsmetod för ISO20022-kreditöverföringar"
description: "I denna procedur visas hur du ställer in leverantörbetalningsmetoden för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil."
author: mrolecki
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bed51f8749dfa0264ad39f51f9ceb295ac46fe93
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Ställ in en betalningsmetod för ISO20022-kreditöverföringar

[!include [task guide banner](../../includes/task-guide-banner.md)]

I denna procedur visas hur du ställer in leverantörbetalningsmetoden för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil. 

Innan du slutför denna uppgift måste du exportera formatkonfigurationer och skapa betalningskonton.

Uppgiften har skapats med DEMF-demodataföretaget.

Detta är den tredje proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Betalningsmetod med värdet "SEPA CT ".
3. Klicka på Redigera.
4. Välj "Summa" i fältet period.
5. Välj "Elektronisk betalning" i fältet Betalningstyp.
6. Expandera avsnittet Filformat.
7. Välj Ja i fältet Allmän elektronisk rapportering.
8. Ange eller välj ett värde i fältet Exportera formatkonfiguration.
    * Välj krediteringsöverföringen för värde ISO20022 (DE) i listan. Om listan är tom innebär det att inga aktiva konfigurationer av exportformat för leverantörsbetalning har importerats.  
9. Välj "Bank" i fältet Kontotyp.
10. Ange värdena "'DEMF OPER" i fältet Betalningskonto.
11. Klicka på Spara.


