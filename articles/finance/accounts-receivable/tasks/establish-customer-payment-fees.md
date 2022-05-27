---
title: Upprätta avgifter för kundbetalning
description: Skapa betalningsavgifter för kundbetalningar.
author: ShivamPandey-msft
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc02da71ef6edbf1b88395a52c3fcbfca62cc82f
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714437"
---
# <a name="establish-customer-payment-fees"></a>Upprätta avgifter för kundbetalning

[!include [banner](../../includes/banner.md)]

Skapa betalningsavgifter för kundbetalningar.

I den här uppgiften används demonstrationsföretaget USMF.

1. I **navigeringsfönstret**, gå till **Moduler > Kundreskontra > Betalningsinställning > Betalningsavgift**.
2. Klicka på **Ny**.
3. Ange avgifts-ID i fältet **Avgifts-ID**. Avgifts-ID visas i betalningsjournaler, vilket gör det beskrivande så att du förstår vilken avgiften som åläggs.  
4. Ange ett avgiftsnamn i fältet **Namn**.
5. Ange en beskrivning av avgiften i fältet **Avgiftsbeskrivning**.
6. I fältet **Tillägg**, välj om avgiften ska debiteras kunden eller ett huvudbokskonto. Välj Kund om kunden ska debiteras avgiften. Om avgiften ska åläggas din organisation som en utgift, välj redovisning. Markera kunden för denna uppgift.  
7. I fältet **Journaltyp** väljer du den typ av journal som kan använda den här betalningsavgiften. Om dessa tillägg används för kundbetalningar, kommer journaltypen troligen vara kundbetalning.  
8. Klicka på **Spara**.
9. Klicka på **Betalningsavgiftsinställning**. Betalningsavgiftinställningar används för att definiera villkoren för betalningsavgiften, när ska bedömas.  Du kan till exempel definiera som avgiften beräknas, om företaget är USMF OPER, och betalsättet är check.  
10. I fältet **Grupperingar**, välj Register, Grupp eller Alla när du vill definiera vilka bankkonton ska bedömas den avgiften. Om du väljer Alla, kan alla bankkonton åläggas avgiften.  Om du väljer Register, kan bara det bankkonto som du valt åläggas avgiften. Om du väljer Grupp, kan bara bankkontona i den markerade bankgruppen åläggas avgiften.  
11. I fältet **Bankrelation** väljer du antingen en bankgrupp eller ett bankkonto. Om du väljer Register, visar sökningen bankkonton. Om du väljer Grupp, visar sökningen bankgrupper.  
12. Klicka på länken på den valda raden i listan.
13. I fältet **Betalningsmetod**, välj det betalsätt som avgiften ska bedömas för. Du kan till exempel ålägga en avgift till kunden om de skickar betalningar som en check, snarare än som en elektronisk betalning.  
14. Hitta och markera önskad post i listan.
15. Ange vid behov en betalningsvaluta i fältet **Betalningsvaluta**. Betalningvalutan används som villkor för om avgift ska åläggas.  Anta att din bank läsa in en ytterligare avgift för betalningar som tas emot i USD, eftersom de normalt bara arbetar med EUR-valuta.  
16. Välj om tillägget ska vara procent, ett belopp eller ett intervall.
17. I fältet **Procent/Belopp**, ange procentandel eller belopp för avgiften. Om procentsatsen/beloppsfält är procentvärde anges värdet som en procentsats. Om procentsatsen/beloppsfält är belopp, anges värdet som en procentsats. Om procentsatsen/beloppsfält är intervall, ska du använda intervallfliken för att definiera nivåerna.  
18. Välj valuta för avgiften i fältet **Avgiftsvaluta**. Detta är den valuta som avgiften ska skapas i.  
19. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
