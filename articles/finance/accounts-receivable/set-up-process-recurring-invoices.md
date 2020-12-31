---
title: Ställa in och bearbeta återkommande fakturor
description: Det här avsnittet innehåller en beskrivning av hur du ställer in och bearbetar återkommande fakturor. Du kan använda återkommande fakturor om du måste fakturera kunder samma belopp regelbundet.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b443630d1612b5095fefa74b5ed6d057be534b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447906"
---
# <a name="set-up-and-process-recurring-invoices"></a>Ställa in och bearbeta återkommande fakturor

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du ställer in och bearbetar återkommande fakturor. Du kan använda återkommande fakturor om du måste fakturera kunder samma belopp regelbundet.

<a name="create-a-recurring-free-text-invoice-template"></a>Skapa en fritextmall för återkommande fakturor
---------------------------------------------

Om du regelbundet vill fakturera kunder för samma tjänster måste du definiera en fritextfakturamall som kan återanvändas för att skapa fakturorna. Mallen innehåller följande information:

-   Huvudinformation som momsgrupp, betalningsvillkor och betalningsmetod.
-   Radinformation som beskrivning, intäktskonton, enhetspris och fakturabelopp.
-   Avgifter för leverans eller hantering.
-   Redovisningsfördelningar tillsammans med information om ekonomisk dimension, exempelvis kostnadsställen och affärsenheter.

I praktiken skapar du en faktura och sparar den som en mall. Du kan ställa in mallar på sidan **Återkommande fakturor**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Koppla en fritextfakturamall till en kund och ange återkommande detaljer
När mallen har skapats, måste du koppla mallen till de kunderna som du vill fakturera. Dessutom måste du ange när och hur ofta fakturan ska användas. Du kan koppla mallar på fliken **Faktura** på sidan **Kunder**. Lägg till mallen i listan och uppdatera följande information:

-   Startdatum och eventuellt slutdatum för återkommande faktureringen.
-   Hur ofta den återkommande faktureringen ska göras (exempelvis varje dag eller en gång i månaden).
-   Det maximala faktureringsbeloppet (om denna information krävs).

En kund kan ha flera mallar med olika frekvenser.

## <a name="generate-the-recurring-invoices"></a>Generera de återkommande fakturorna
På sidan **Återkommande fakturor** finns en uppgift som bearbetar återkommande fakturamallar. Du anger fakturadatumet och vilken mall fakturorna ska genereras från. Fakturor skapas och kopplas till ett återkommande-id-nummer för varje grupp av fakturor som bearbetas.

<a name="post-recurring-free-text-invoices"></a>Bokföra återkommande fritextfakturor
---------------------------------

När återkommande fakturor har skapats, visas återkommande-id:na för fakturorna i en bokföringsuppgift på sidan **Återkommande fakturor**. Du kan visa alla av fakturor för ett återkommande-id genom att klicka på länken. När du granskar fakturorna för återkommande-id:t kan du ta bort enskilda fakturor. Kundens inställningar för återkommande fakturor återställs för mallen, så att den kan genereras igen senare. Du kan bokföra en, många eller alla fakturor för ett återkommande-id. Om arbetsflöden är aktiva, måste du klicka på **Skicka** innan du kan bokföra fakturor.

<a name="print-recurring-free-text-invoices"></a>Skriva ut återkommande fritextfakturor
----------------------------------

När återkommande fakturor bokförs kan du skriva ut fakturorna från sidan med en lista över fritextfakturor. Du kan skriva ut de fakturor som har valts, eller välja ett intervall med fakturor som ska skrivas ut.



