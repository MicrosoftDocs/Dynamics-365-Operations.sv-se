---
title: Ställ in ett betalsätt för ISO20022-kreditöverföringar
description: I denna procedur visas hur du ställer in leverantörbetalsättet för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92bc314e69628f2a287ba7c9a7c2d3d73a0bfd33
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988112"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Ställ in ett betalsätt för ISO20022-kreditöverföringar

[!include [banner](../../includes/banner.md)]

I denna procedur visas hur du ställer in leverantörbetalsättet för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil. 

Innan du slutför denna uppgift måste du exportera formatkonfigurationer och skapa betalningskonton.

Uppgiften har skapats med DEMF-demodataföretaget.

Detta är den tredje proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till Leverantörsreskontra > Betalningsinställning > Betalsätt.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]