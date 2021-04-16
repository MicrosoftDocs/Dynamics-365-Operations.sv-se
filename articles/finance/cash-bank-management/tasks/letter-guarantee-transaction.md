---
title: Garantitransaktion
description: I den här proceduren förklaras processen för garanti.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 089515287fc5706983b10614f69b4b1cd90178c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834726"
---
# <a name="letter-of-guarantee-transaction"></a>Garantitransaktion

[!include [banner](../../includes/banner.md)]

I den här proceduren förklaras processen för garanti.



Följande uppgifter måste slutföras innan du avslutar den här proceduren:

- Ställ in bankkreditlimiter och bokföringsprofiler för garanti.

- Skapa ett kreditlimitavtal för en garanti.



I den här proceduren används demonstrationsföretaget USMF.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Skapa försäljningsorder med garanti
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
4. Expandera avsnittet Allmänt.
5. Ange eller välj ett värde i fältet Plats.
6. Klicka på länken på den valda raden i listan.
7. Ange eller välj ett värde i fältet Lagerställe.
8. Klicka på länken på den valda raden i listan.
9. Välj Garanti i fältet Bankdokumenttyp.
10. Klicka på OK.
11. Ange eller välj ett värde i fältet Artikelnummer.
12. Ange ett tal i fältet Enhetspris.
13. Expandera avsnittet Radinformation.
14. Klicka på fliken Leverans.
    * Obs! Välj Leveransdatumkontroll = Ingen.  
15. I fältet Begärt transportdatum, ange ett datum.
16. I fältet Bekräftat transportdatum, ange ett datum.

## <a name="process-letter-of-guarantee_request"></a>Bearbeta garanti_begäran
1. Klicka på Hantera i åtgärdsfönstret.
2. Klicka på Garanti.
3. I fönstret Åtgärd, klicka på Garanti.
4. Klicka på Begäran om du vill öppna dialogrutan.
5. Ange eller välj ett värde i fältet Typ.
6. Klicka på länken på den valda raden i listan.
7. Ange ett nummer i fältet Värde.
8. I fältet Utgångsdatum anger du datum och tid.
9. Klicka på OK.
10. Stäng sidan.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Bearbeta garanti_Skicka till bank
1. Gå till Kassa- och bankhantering > Garanti > Garanti.
2. Hitta och markera önskad post i listan.
3. Klicka på Skicka till bank för att öppna dialogrutan.
4. Ange eller välj ett värde i fältet Bankkonto.
5. Klicka på länken på den valda raden i listan.
6. Klicka på OK.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Bearbeta garanti_Ta emot från bank
1. Klicka på Ta emot från bank för att öppna dialogrutan.
2. I fältet Banknummer, skriv ett värde.
    * Kontrollera värdena i de beräknade marginal- och utgiftsfälten.  
3. Klicka på OK.
4. Expandera avsnittet Åtgärder.
    * Kontrollera posten Ta emot från bank.  
5. Klicka för att följa länken i fältet Journalbatchnummer.
6. Klicka på Rader.
    * Kontrollera bokföringen av journalposter.  
7. Stäng sidan.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Bearbeta garanti_Ge till mottagare
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på länken på den valda raden i listan.
3. Klicka på Hantera i åtgärdsfönstret.
4. Klicka på Garanti.
5. I fönstret Åtgärd, klicka på Garanti.
6. Klicka på Ge till mottagare för att öppna dialogrutan.
7. Klicka på OK.
8. Gå till Kassa- och bankhantering > Garanti > Garanti.
9. Hitta och markera önskad post i listan.
10. Klicka på Ge till mottagare för att öppna dialogrutan.
11. Klicka på OK.
12. Expandera avsnittet Åtgärder.
    * Validera posten Ge till mottagare.  

## <a name="process-letter-of-guarantee_increase-value"></a>Bearbeta garanti_Öka värde
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på länken på den valda raden i listan.
3. Klicka på Hantera i åtgärdsfönstret.
4. Klicka på Garanti.
5. I fönstret Åtgärd, klicka på Garanti.
6. Klicka på Öka värde för att öppna dialogrutan.
7. I fältet Värde att lägga till, ange ett värde.
8. Klicka på OK.
9. Gå till Kassa- och bankhantering > Garanti > Garanti.
10. Hitta och markera önskad post i listan.
11. Klicka på Öka värde för att öppna dialogrutan.
12. Klicka på OK.
13. Expandera avsnittet Åtgärder.
    * Kontrollera posten Öka värde.  
14. Hitta och markera önskad post i listan.
15. Klicka för att följa länken i fältet Journalbatchnummer.
16. Klicka på Rader.
    * Kontrollera de bokförda journalposterna.  

## <a name="process-letter-of-guarantee_liquidate"></a>Bearbeta garanti_Likvidera
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på länken på den valda raden i listan.
3. Klicka på Hantera i åtgärdsfönstret.
4. Klicka på Garanti.
5. I fönstret Åtgärd, klicka på Garanti.
6. Klicka på Likvidera för att öppna dialogrutan.
7. Klicka på OK.
8. Gå till Kassa- och bankhantering > Garanti > Garanti.
9. Hitta och markera önskad post i listan.
10. Klicka på Likvidera för att öppna dialogrutan.
11. Klicka på OK.
12. Expandera avsnittet Åtgärder.
    * Kontrollera posten Likvidera.  
13. Hitta och markera önskad post i listan.
14. Klicka för att följa länken i fältet Journalbatchnummer.
15. Klicka på Rader.
    * Kontrollera de bokförda journalposterna.  
16. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]