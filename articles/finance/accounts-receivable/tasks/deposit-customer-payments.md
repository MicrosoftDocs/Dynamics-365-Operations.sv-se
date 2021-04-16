---
title: Sätta in kundbetalningar
description: Insättning av kundbetalningar.
author: ShivamPandey-msft
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bf44570a0eaceab94765b100bdd8b4d507a0f54
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822381"
---
# <a name="deposit-customer-payments"></a>Sätta in kundbetalningar

[!include [banner](../../includes/banner.md)]

Insättning av kundbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till **navigeringsfönstret > Moduler > Kundreskontra > Betalningar > Betalningsjournal**.
2. Välj **Ny**.
3. I fältet **Namn**, välj **CustPay** i den nedrullningsbara menyn.
4. Markera **rader**
5. Ange kund som du har tagit emot en betalning för i fältet **Konto**.
6. Ange betalningens belopp i fältet **Kredit**. Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.  
7. Skriv ett värde i fältet **Betalningsreferens**. Betalningsreferensen kan vara checknumret för en betalning som du anger. Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.  
8. Välj rutan Använd ett insättningskvitto. Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.  
9. Välj **Ny**.
10. I fältet **Konto** välj kund för nästa betalning.
11. Ange betalningsbeloppet i fältet **Kredit**.
12. Skriv ett värde i fältet **Betalningsreferens**.
13. Välj rutan **Använd ett insättningskvitto**.
14. Vald **bokföring** Betalningar måste bokföras, för insättningskvittot kan genereras. Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.  
15. Välj **Funktioner**.
16. Välj **Insättningskvitto**.
17. Välj **OK**. Den första sidan används för att skapa insättningskvittot.  
18. Välj **OK**. I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]