--- 
title: Garantitransaktion
description: "I den här proceduren förklaras processen för garanti."
author: kweekley
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c2e215f1ae16f907c8b64ea1f05cf67bfb0a04b6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="letter-of-guarantee-transaction"></a>Garantitransaktion

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

## <a name="process-letter-of-guaranteerequest"></a>Bearbeta garanti_begäran
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

## <a name="process-letter-of-guaranteesubmit-to-bank"></a>Bearbeta garanti_Skicka till bank
1. Gå till Kassa- och bankhantering > Garanti > Garanti.
2. Hitta och markera önskad post i listan.
3. Klicka på Skicka till bank för att öppna dialogrutan.
4. Ange eller välj ett värde i fältet Bankkonto.
5. Klicka på länken på den valda raden i listan.
6. Klicka på OK.

## <a name="process-letter-of-guaranteereceive-from-bank"></a>Bearbeta garanti_Ta emot från bank
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

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a>Bearbeta garanti_Ge till mottagare
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

## <a name="process-letter-of-guaranteeincrease-value"></a>Bearbeta garanti_Öka värde
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

## <a name="process-letter-of-guaranteeliquidate"></a>Bearbeta garanti_Likvidera
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


