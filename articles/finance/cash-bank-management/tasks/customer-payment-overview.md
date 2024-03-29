---
title: Översikt över kundbetalning
description: Denna procedur går igenom olika metoder som används för att ange kundbetalningar.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b90b7f200133cfb0d30b335aca20c328856fba5
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778133"
---
# <a name="customer-payment-overview"></a>Översikt över kundbetalning

[!include [banner](../../includes/banner.md)]

Denna procedur går igenom olika metoder som används för att ange kundbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till **navigeringsfönstret > Moduler > Kundreskontra > Betalningar > Betalningsjournal**.
2. Klicka på **Ny**.
3. Välj den betalningsjournal där kundbetalningarna sparas.
4. Välj journalen eller ange den manuellt.
5. I **åtgärdsfönstret**, klicka på **Ange kundbetalningar**. Ange kundbetalningar används för att registrera en kundbetalning åt gången. Du anger betalningsinformationen överst och sedan kan du markera fakturorna som har betalats med betalningen, alla från samma sida.  
6. Ange den kund från vilken du har tagit emot betalningen. Om du inte känner till kunden, men känner till en transaktion som har betalats, kan du använda fältet **Transaktion** för att ange betalningen. Ange eller välj fakturan i fältet **Transaktion**. Kunden hämtas som standard automatiskt när du har valt transaktionen.
7. Ange en betalningsreferens i fältet **Betalningsreferens**. Betalningsreferensen kan vara kundens checknummer eller en referens eller från kundens elektroniska betalning. Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.  
8. Välj om betalningen ska inkluderas på ett insättningskvitto i fältet **insättningskvitto**. 
9. Ange kundbetalningens belopp i fältet **Belopp**. Betalningsbeloppet hämtas inte som standard. Det måste anges manuellt. 
10. Markera fakturorna som betalades av kunden. Om betalningen är en förskottsbetalning behöver du inte välja några fakturor för kvittning. Betalningen kan fortfarande sparas och bokföras. Kvittningen till en faktura kan utföras vid ett senare tillfälle.
11. Ange beloppet för den betalning som ska kvittas mot den markerade fakturan. Det här fältet kan användas när betalningen gäller en delbetalning. Om du inte anger något belopp kommer kvittningsbeloppet bestämmas automatiskt för dig.
12. Klicka på **Spara i journal**. Kontrollera att motkontot har definierats innan du sparar betalningen till journalen. Om du använder **Spara i journalen** sparas betalningen och flyttas till journalen. Du kan sedan fortsätta och ange nästa betalning.
13. Stäng sidan.
14. Klicka på **Rader** i **åtgärdsfönstret**. När du öppnar **rader** visas alla betalningar som du har registrerat på sidan **Ange kundbetalningar** och sparat i journalen. Du kan också använda den här sidan för att ange nya kundbetalningar eller redigera en befintlig kundbetalning innan den bokförs.
15. Klicka på **Ny** för att skapa en annan betalning. 
16. Välj den kund från vilken du har tagit emot betalningen. Om du inte känner till kunden, men känner till en faktura som betalas med betalningen, använder du fältet **Faktura** för att ange eller välja fakturan manuellt. Kunden hämtas som standard efter att fakturan har valts.  
17. Klicka på **Kvitta transaktioner** för att markera fakturor som har betalats. Du måste inte att kvitta betalningen mot några fakturor. Om det är en förskottsbetalning eller om du inte vet vilken faktura som har betalats kan du ange och bokföra betalningen. Betalningen kan kvittas mot en faktura vid en senare tidpunkt.  
18. Markera fakturorna som har betalats med betalningen. 
19. Ange beloppet för den betalning som ska kvittas mot fakturan i fältet **Belopp**.
20. Klicka på **OK**.
21. Ange en betalningsreferens i fältet **Betalningsreferens**. Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.  
22. I **åtgärdsfönstret**, klicka på **bokföra** om du vill bokföra kundbetalningarna. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
