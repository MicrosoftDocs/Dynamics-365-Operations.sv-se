---
title: Skapa betalningsblankettformat för projektfakturor
description: Företag bifogar ofta betalningsblanketter till fakturor för att hjälpa kunder och ange en betalningsreferens för bokföring och kvittning.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4671e1df3bc86361736b5882d67e6b160b4c5644
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848729"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Skapa betalningsblankettformat för projektfakturor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Företag bifogar ofta betalningsblanketter till fakturor för att hjälpa kunder och ange en betalningsreferens för bokföring och kvittning. Betalningsblanketten kan användas för projekt - eller tjänstfakturor, kravbrev, räntefakturor och kontoutdrag, utöver försäljningsfakturor och fritextfakturor. Om du vill bearbeta betalningsblanketter, ställ först in betalningsmottagarens identifieringsnummer och formaten för den bifogade betalningsblanketten.

I den här proceduren används demonstrationsföretaget DEMF. 

Den här funktionen är bara tillgänglig för juridiska personer som har den primära adressen i Danmark.


## <a name="set-up-a-creditor-id-number"></a>Ställ in en betalningsmottagares identifieringsnummer
1. Gå till Organisationsadministration > Organisationer > Juridiska personer.
2. Expandera eller komprimera avsnittet Bankkontoinformation.
3. Klicka på Redigera.
4. Skriv ett värde i fältet ID för FI-kreditgivare.
5. Klicka på Spara.
6. Stäng sidan.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Ställ in ett betalningsblankettformat för fakturor, anteckningar, brev och utdrag
1. Gå till Kundreskontra > Inställningar > Formulär > Formulärinställningar.
2. Klicka på fliken Faktura.
3. I fältet Associerad betalningsbilaga för kundfaktura, välj ett alternativ.
    * Ingen – skriv inte ut någon betalningsblankett. Välj det här alternativet om betalningsbeloppet är i en annan valuta än danska kroner (DKK).   FIK 751 – Skriv ut ett FIK 751-betalningskvitto om du tänker skriva betalningsbeloppet och förfallodatumet manuellt på betalningskvittot.   FIK 752 – skriv ut ett betalningskvitto för FIK 752, om du tänker använda en betalningskvitto som har ett fördefinierad betalningsbelopp och förfallodatum.  
4. Klicka på Spara.
5. Klicka på fliken Fritextfaktura.
6. I fältet Associerad betalningsbilaga på fritextfaktura, välj ett alternativ.
    * Ingen – skriv inte ut någon betalningsblankett. Välj det här alternativet om betalningsbeloppet är i en annan valuta än danska kroner (DKK).   FIK 751 – skriv ut ett betalningskvitto för FIK 751 om du tänker skriva betalningsbeloppet och förfallodatumet manuellt på betalningskvittot.   FIK 752 – skriv ut ett betalningskvitto för FIK 752, om du tänker använda en betalningskvitto som har ett fördefinierad betalningsbelopp och förfallodatum.  
7. Klicka på Spara.
8. Klicka på fliken Räntefaktura.
9. I fältet Associerad betalningsbilaga på räntefaktura, välj ett alternativ.
    * Ingen – skriv inte ut någon betalningsblankett. Välj det här alternativet om betalningsbeloppet är i en annan valuta än danska kroner (DKK).   FIK 751 – skriv ut ett betalningskvitto för FIK 751 om du tänker skriva betalningsbeloppet och förfallodatumet manuellt på betalningskvittot.   FIK 752 – skriv ut ett betalningskvitto för FIK 752, om du tänker använda en betalningskvitto som har ett fördefinierad betalningsbelopp och förfallodatum.  
10. Klicka på Spara.
11. Klicka på fliken Kravbrev.
12. I fältet Associerad betalningsbilaga i kravbrev, välj ett alternativ.
    * Ingen – skriv inte ut någon betalningsblankett. Välj det här alternativet om betalningsbeloppet är i en annan valuta än danska kroner (DKK).   FIK 751 – skriv ut ett betalningskvitto för FIK 751 om du tänker skriva betalningsbeloppet och förfallodatumet manuellt på betalningskvittot.   FIK 752 – skriv ut ett betalningskvitto för FIK 752, om du tänker använda en betalningskvitto som har ett fördefinierad betalningsbelopp och förfallodatum.  
13. Klicka på Spara.
14. Klicka på fliken Kontoutdrag.
15. I fältet Associerad betalningsbilaga på kontoutdrag, välj ett alternativ.
    * Ingen – skriv inte ut någon betalningsblankett. Välj det här alternativet om betalningsbeloppet är i en annan valuta än danska kroner (DKK).   FIK 751 – skriv ut ett betalningskvitto för FIK 751 om du tänker skriva betalningsbeloppet och förfallodatumet manuellt på betalningskvittot.   FIK 752 – skriv ut ett betalningskvitto för FIK 752, om du tänker använda en betalningskvitto som har ett fördefinierad betalningsbelopp och förfallodatum.  
16. Klicka på Spara.
17. Stäng sidan.

