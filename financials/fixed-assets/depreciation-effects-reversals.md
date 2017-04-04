---
title: "Avskrivningseffekter med återföringar"
description: "Det här avsnittet behandlar potentiella konsekvenser vid återföring av en anläggningstillgångstransaktion."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: 292186b17406851e40917225cf0c1b8c8e98c654
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-effects-with-reversals"></a>Avskrivningseffekter med återföringar

Det här avsnittet behandlar potentiella konsekvenser vid återföring av en anläggningstillgångstransaktion. 

Du kan återföra transaktioner för anläggningstillgångar och transaktionerna som är kopplade till en anläggningstillgång. Du kan även återkalla en återförd transaktion. 

Du kan återställa eller återkalla en transaktion som inte är den senaste transaktionen som bokfördes i tillgångsboken. Du bör först fastställa om några avskrivningstransaktioner bokfördes efter den transaktion som du återför. Detta eftersom avskrivning inte räknas om när du återför en transaktion. Därför blir avskrivningen ofta för hög eller för låg efter återföringen, vilket exemplen visar. 

Om du vill vara säker på att avskrivningen är korrekt när du återför en transaktion, gå inte vidare med återföringen om du får ett meddelande om att avskrivningen inte räknas om. Återför istället först avskrivningstransaktionen som bokfördes efter att den transaktion som du försökte du återföra och fortsätt sedan med återföringen. Du varnas inte om omberäkningar av avskrivning och du kan gå vidare med återföringen. 

Följande exempel visar de omberäkningar som genomförs om du fortsätter utan att beakta meddelandet att först återföra avskrivningstransaktionerna.

## <a name="example-1-depreciation-is-overstated"></a> Exempel 1: Avskrivningen är för hög
En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder). I det här exemplet blir avskrivningen för hög.
#### <a name="asset-transaction-history"></a>Tillgångens transaktionshistorik

| Datum       | Transaktionstyp                                                          | Belopp                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1 januari  | Anskaffning                                                               | 59 000,00                                 |
| 1 januari  | Anskaffningsjustering                                                    | 1 000,00                                  |
| 31 januari | Avskrivning (skapad med ett förslag på en avskrivningsperiod) | 1 000,00 Beräkning: Bokfört värde (59 000 + 1 000) / antal kvarstående avskrivningsperioder (60) |

#### <a name="reversal-action"></a>Återföringsåtgärd

| Datum      | transaktionstyp                | Belopp    |
|-----------|---------------------------------|-----------|
| 1 januari | Återföring av anskaffningsjustering | -1 000,00 |

#### <a name="depreciation-effect"></a>Avskrivningseffekt

| Datum        | transaktionstyp        | Belopp                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 februari | Avskrivning (förslag) | 983,05 Beräkning: Bokfört värde (59 000 - 1 000 avskrivning) / antal kvarstående avskrivningsperioder (59) |

Avskrivningens värde är 16,95 för högt (1 000 – 983,05).

## <a name="example-2-depreciation-is-understated"></a> Exempel 2: Avskrivningen är för låg
En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder). I det här exemplet blir avskrivningen för låg.
#### <a name="asset-transaction-history"></a>Tillgångens transaktionshistorik

| Datum       | transaktionstyp                                                          | Belopp                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1 januari  | Anskaffning                                                               | 59 000,00                                   |
| 1 januari  | Nedskrivning                                                     | 1 000,00                                    |
| 31 januari | Avskrivning (skapad med ett förslag på en avskrivningsperiod) | 966,67 Beräkning: Bokfört värde (59 000 - 1 000) / antal kvarstående avskrivningsperioder (60) |

#### <a name="reversal-action"></a>Återföringsåtgärd

| Datum      | transaktionstyp               | Belopp    |
|-----------|--------------------------------|-----------|
| 1 januari | Återföring av nedskrivningsjustering | -1 000,00 |

#### <a name="depreciation-effect"></a>Avskrivningseffekt

| Datum        | transaktionstyp        | Belopp                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 februari | Avskrivning (förslag) | 983,62 Beräkning: Bokfört värde (59 000 - 966,67 avskrivning) / antal kvarstående avskrivningsperioder (59) |

Avskrivningens värde är 16,95 för lågt (983,62 – 966,67).



<a name="see-also"></a>Se även
--------

[Fixed asset depreciation](fixed-asset-depreciation.md)


