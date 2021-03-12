---
title: En verifikation med flera kund- eller leverantörsposter
description: Det här avsnittet innehåller en översikt över vad som händer när du bokför en enskild verifikation med flera kund- eller leverantörsposter. Den här funktionen ska annulleras i kommande versioner av Microsoft Dynamics 365 Finance och därför rekommenderar vi att inte använda denna metod för bokföring på grund av redovisningens inverkan på kvittningsbehandling.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01fd382a97f86e93e4ab91759d35c65fae7447c5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972018"
---
# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>En verifikation med flera kund- eller leverantörsposter

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över vad som händer när du bokför en enskild verifikation med flera kund- eller leverantörsposter. Den här funktionen ska annulleras i kommande versioner av och därför rekommenderar vi att inte använda denna metod för bokföring på grund av redovisningens inverkan på kvittningsbehandling. 

Några vanliga exempel där en verifikation används för flera kunder eller leverantörer inkluderar saldoöverföringar mellan kunder och netting av saldon mellan kunder och leverantörer i samma organisation. 

En verifikation som innehåller mer än en kund eller leverantör, kan anges med någon av följande metoder:

-   Om du vill använda en journal som endast har alternativet **Ett verifikationsnummer** markerat så att varje rad som läggs till journalen inkluderas på samma verifikation.
-   Med hjälp av verifikation av flera rader där det inte finns någon motkonto med mer än en kund eller leverantör.
-   Ange en verifikation med kontot och det motkonto som är leverantör/leverantör, kund/kund, leverantör/kund, eller kund/leverantör.

Det här avsnittet visar hur kvittningen kommer att bearbetas när en verifikation med flera kund- eller leverantörsposter bokförs. Dessutom ger det här avsnittet tillfälliga lösningar som hjälper dig att förstå hur du undviker att använda en verifikation med flera kunder eller leverantörer. I synnerhet finns det två exempel som illustrerar de två gemensamma kvittningscenarion som påverkas av användningen av en verifikation med flera kunder eller leverantörer:

-   Kassarabattbokföring
-   Ombedömningsbokföring

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Hur påverkar kvittning användning av enskild verifikation
När du bokför en verifikation som innehåller flera kund- eller leverantörsposter skapas en enskild redovisningsverifikation som innehåller flera kundreskontra- eller leverantörsreskontrasaldon. Under kvittningsprocessen används de ursprungliga redovisningsposterna för att skapa redovisningsposter för kassarabatten, orealiserad vinst och förlust, realiserad vinst och förlust och avdrag för originaldokumentets samlingskonto. Om till exempel en kassarabatt tas när du kvittar en leverantörsbetalning till en faktura måste kassarabattredovisningen bokföras till huvudboken för leverantörsreskontra från den ursprungliga fakturan. Om den ursprungliga fakturan bokfördes i en verifikation som innehåller flera leverantörsposter, sammanfattas den ursprungliga redovisningen. I det här fallet, eftersom det inte finns något sätt att få tillgång till den detaljerade redovisningsposten för varje leverantörstransaktion i den enkla verifikationen finns det inget sätt att bestämma hur användaren avsåg hur kassarabatten skulle redovisas.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>En verifikation med flera leverantörer och inverkan på kassarabattredovisning

I följande exempel registreras flera leverantörsfakturor i redovisningen på en och samma verifikation på sidan **Allmän journal**. Dessa fakturor fördelas över flera kontodimensioner.

| Verifikation | Kontotyp | Konto  | beskrivning | Debet | Kredit |
|-------------|------------------|--------------|-----------------|-----------|------------|
| GNJL001     | Leverantör           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Leverantör           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Leverantör           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Redovisning           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Redovisning           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Redovisning           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Redovisning           | 606300-004-- | INV3            | 300,00    |            |

Efter bokföringen skapas en verifikation.

| Verifikation | Konto  | Bokföringstyp | Belopp i transaktionsvaluta |
|-------------|--------------|------------------|------------------------------------|
| GNJL001     | 606300-001-- | Redovisningsjournal   | 50,00                              |
| GNJL001     | 606300-002-- | Redovisningsjournal   | 50,00                              |
| GNJL001     | 606300-003-- | Redovisningsjournal   | 200,00                             |
| GNJL001     | 606300-004-- | Redovisningsjournal   | 300,00                             |
| GNJL001     | 200110-001-  | Leverantörssaldo   | -100,00                            |
| GNJL001     | 200110-001-  | Leverantörssaldo   | -200,00                            |
| GNJL001     | 200110-001-  | Leverantörssaldo   | -300,00                            |

Observera att verifikationen innehåller tre poster för bokföringstypen för leverantörsaldo i den enkla verifikationen. Det finns inget sätt för att ange att 50,00 debet för 606300-001 och 50,00 debet 606300-002 är avsett att kompensera leverantörsaldoposten för 200110-001. Detta är eftersom användaren angav de olika leverantörsposterna i en enda verifikation.

Med det här exemplet kan du analysera påverkan som det har att använda en verifikation på en underordnad kvittningsredovisning. Anta att du betalar 197,00 för fakturan på 200,00 med en kassarabatt på 3,00. Observera att värdet för kassarabatt kontovärde fördelas mellan alla dimensioner från fakturaverifikationens utgiftskonton. Detta beror på att en verifikation används för att bokföra ovanstående faktura, utan att indikera hur användaren avsåg att kostnadsfördelningarna korrelerar till leverantörssaldot i den enkla verifikationen.

| Verifikation | Konto  | Bokföringstyp     | Debet | Kredit |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Leverantörssaldo       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-001-- | Leverantörskassarabatt |           | 0.25       |
| 14000056    | 520200-002-- | Leverantörskassarabatt |           | 0.25       |
| 14000056    | 520200-003-- | Leverantörskassarabatt |           | 1,00       |
| 14000056    | 520200-004-- | Leverantörskassarabatt |           | 1.50       |
| 14000056    | 200110-001-  | Leverantörssaldo       | 3,00      |            |

Om användaren missnöjd med kassarabatten som fördelas mellan alla kostnadsfördelningar från den ursprungliga fakturan, ska i stället för en verifikation, flera verifikationer användas för att bokföra fakturorna. Här är ett exempel på hur flera verifikationer kan bokföras i redovisningen, i stället för att använda en verifikation, som visas i början av det här exemplet.

| Verifikation | Kontotyp | Konto  | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL001     | Leverantör           | 1001         | INV1            |           | 100,00     | Redovisning          | &lt;tom&gt;      |
| GNJL001     | Redovisning           | 606300-001-- | INV1            |   50,00   |            | Redovisning          | &lt;tom&gt;      |
| GNJL001     | Redovisning           | 606300-002-- | INV1            |   50,00   |            | Redovisning          | &lt;tom&gt;      |
| GNJL002     | Leverantör           | 1001         | INV2            |           | 200,00     | Redovisning          | 606300-003--       |
| GNJL003     | Leverantör           | 1001         | INV3            |           | 300,00     | Redovisning          | 606300-004--       |

Nu när INV2 har betalats, kommer följande post att göras. Observera att kassarabattens ekonomiska dimensioner följer den associerade utgiftens ekonomiska dimensioner.

| Verifikation | Konto  | Bokföringstyp     | Debet | Kredit |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Leverantörssaldo       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-003-- | Leverantörskassarabatt |           | 3,00       |
| 14000056    | 200110-001-  | Leverantörssaldo       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>En verifikation med flera leverantörer och inverkan på redovisning av realiserad vinst/förlust

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Kontotyp | Konto  |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| GNJL001     | Leverantör           | 1001        | INV1            |           | 100,00     | Redovisning           | 606300-001-- |
| GNJL001     | Leverantör           | 1001        | INV2            |           | 200,00     | Redovisning           | 606300-002-- |

I följande exempel registreras flera leverantörsfakturor i redovisningen på en och samma verifikation på sidan **Allmän journal**. Dessa fakturor fördelas över flera kontodimensioner. Efter bokföringen skapas en verifikation.

| Verifikation | Konto  | Bokföringstyp | Belopp i transaktionsvaluta (EUR) | Belopp i redovisningsvaluta (SEK) |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| GNJL001     | 606300-001-- | Redovisningsjournal   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Redovisningsjournal   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Leverantörssaldo   | -100,00                                  | -114,00                                 |
| GNJL001     | 200110-001-  | Leverantörssaldo   | -200,00                                  | -228,00                                 |

Observera att verifikationen innehåller två poster för bokföringstypen för leverantörsaldo i den enkla verifikationen. Det finns inget sätt att ange att debet för 606300-001 är avsett att kompensera leverantörsaldoposten på 100,00 till 200110-001. Detta är eftersom användaren angav de olika leverantörsposterna i en enda verifikation. 

Med det här exemplet kan du analysera påverkan som det har att använda en verifikation på en underordnad kvittningsredovisning. Anta att din redovisningsvaluta är SEK och ovanstående transaktionerna bokfördes i en transaktionsvaluta i EUR. Anta att du helt betalar fakturan på 200,00 EUR men att det uppstår en realiserad förlust på grund av en skillnad i valutakursen mellan tiden för bokföring av fakturan och betalningen. Observera att värdet för realiserad förlustkonto fördelas mellan alla dimensioner från fakturaverifikationens utgiftskonton. I det här fallet fördelas både dimension 001 och 002, även om användarens föreställning kan vara att endast 002 tillhör utgiftskontot från den fakturan som kvittas. Detta beror på att en verifikation används för att bokföra ovanstående faktura, utan någon möjlighet att indikera hur användaren avsåg att kostnadsfördelningarna korrelerar till leverantörssaldot i den enkla verifikationen.

| Verifikation | Konto | Bokföringstyp   | Belopp i transaktionsvaluta (EUR) | Belopp i redovisningsvaluta (SEK) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Leverantörssaldo     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Kursförlust | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Kursförlust | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Leverantörssaldo     |                                          | -2,00                                   |

Om användaren missnöjd med den Kursförlust som fördelas mellan alla kostnadsfördelningar från den ursprungliga fakturan, ska i stället för en verifikation, flera verifikationer användas för att bokföra fakturorna. Här är ett exempel på hur flera verifikationer kan bokföras i redovisningen, i stället för att använda en verifikation, som visas i början av det här exemplet.

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL002     | Leverantör           | 1001        | INV1            |           | 100,00     | Redovisning          | 606300-001--       |
| GNJL003     | Leverantör           | 1001        | INV2            |           | 200,00     | Redovisning          | 606300-002--       |

Nu när INV2 har betalats, kommer följande post att göras. Observera att kursförlustens ekonomiska dimensioner följer den associerade utgiftens ekonomiska dimensioner.

| Verifikation | Konto | Bokföringstyp   | Belopp i transaktionsvaluta (EUR) | Belopp i redovisningsvaluta (SEK) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Leverantörssaldo     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Kursförlust | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Leverantörssaldo     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>En verifikation för saldoöverföringar och nettingscenarion
Två vanliga scenarier som använder en verifikation som innehåller flera kunder eller leverantörer, inkluderar saldoöverföringar från en kund/leverantör till en annan kund/leverantör och netting av en kund och leverantör som är samma organisation. Följande två exempel visar den metod som ska användas för att ange dessa scenarier som ett alternativ till att registrera dem i en verifikation. 

En *saldoöverföring* är en verifikation med flera kunder som har angetts för syftet att föra över saldot från en kund till en annan kund (densamma för leverantörer). Det här scenariot kan ske när ansvaret för att betala fakturan skiftar till en annan part, till exempel ett underordnat företag som skiftar ansvaret till ett moderbolag. 

Det här exemplet förutsätter en försäljning där kunden är berättigad till kassarabatt, om betalningen görs inom 10 dagar. Kunden i det här exemplet använder ett försäkringsbolag som ska vara ansvarig för att betala räkningen. Försäkringsbolaget anges som en annan kund i systemet. Den ursprungliga kundens saldo överförs till försäkringsbolaget, som betalar fakturan med en kassarabatt på 2 % för att den betalar inom rabattperioden. 

Anta att följande försäljning görs till kunden ACME. Följande redovisningsposter representerar försäljningen.

| Redovisningskonto | Bokföringstyp | Debet | Kredit |
|--------------------|------------------|-----------|------------|
| 401100-002-023-    | Intäkt          |           | 100        |
| 130100-002-        | Kundsaldo | 100       |            |

Därefter överför användaren förfallet saldo från ACME till försäkringsbolaget i en verifikation i Betalningsjournal för kundreskontra. Försäkringsföretaget ställs in som kundförsäkring.

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Kund         | ACME        | Överför        |           | 100,00     | Kund        | Försäkring          |

Observera att den här posten ingår i en verifikation. Den verifikation innehåller två kundposter. Följande verifikation, skapas när ovan redovisningposten bokförs.

| Verifikation | Konto | Bokföringstyp | Belopp i transaktionsvaluta |
|-------------|-------------|------------------|------------------------------------|
| ARPAYM001   | 130100-002- | Kundsaldo | 100,00                             |
| ARPAYM001   | 130100-002- | Kundsaldo | -100,00                            |

Anta att du tar emot en betalning från försäkringkunden för 98,00 och du väljer att kvitta betalningen till fakturan som skapas av saldoöverföringen. Detta leder det till att följande verifikation bokförs. Det kan finnas en förväntan att kvittningen använder ekonomiska dimensioner från den ursprungliga fakturan, men detta är inte möjligt eftersom det inte finns något fakturadokument för försäkringskunden. Onservera att fördelningdimensionerna på kassarabatt som standard kommer från kundtransaktionen som skapas från överföringen, inte från den ursprungliga fakturans intäktskonto. Standardinställningen är ett resultat av att använda en verifikation för att överföra saldona.

| Verifikation | Konto | Bokföringstyp | Debet | Kredit |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM002   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM002   | 130100-002- | Kundsaldo |           | 98.00      |

På den relaterade verifikationen för kassarabatt kommer standardinställningen för den ekonomiska dimensionen från kundtransaktionen som skapades från överföringen, eftersom överföringen har mer än en kund.

| Verifikation | Konto | Bokföringstyp       | Debet | Kredit |
|-------------|-------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002- | Kundkassarabatt | 2.00      |            |
| ARP-00001   | 130100-002- | Kundsaldo       |           | 2.00       |

Om användaren är missnöjd med standardinställningen för de ekonomiska dimensionerna för kassarabatten, kan i stället för en verifikation, flera verifikationer användas för att registrera saldoöverföringen. Detta scenario skulle åstadkommas genom att skapa en kreditnota för kunden som saldot att flyttas FRÅN en debetnota eller faktura som skapas för kunden som saldot flyttas TILL. Följande exempel visar hur flera verifikationer kan anges i betalningsjournalen för kundreskontra för att överföra saldot i stället för att använda en verifikation, som visas i det tidigare exemplet.

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Kund         | ACME        |                 |           | 100,00     | Redovisning          | 401100-002-023-    |
| ARPAYM002   | Kund         | Försäkring   |                 | 100,00    |            | Redovisning          | 401100-002-023-    |

Detta innebär att när försäkringskunden betalar 98,00 med verifikationen ARPAYM02, kommer korrekta ekonomiska dimensioner från verifikationen ARPAYM002-huvudbokskonto i redovisningen att användas.

| Verifikation | Konto | Bokföringstyp | Debet | Kredit |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM003   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM003   | 130100-002  | Kundsaldo |           | 98.00      |

På den relaterade verifikationen för kassarabatt kommer de ekonomiska dimensionerna från motbokning av intäktskontot som visas på ARPAYM002-verifikationen.

| Verifikation | Konto     | Bokföringstyp       | Debet | Kredit |
|-------------|-----------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002-023- | Kundkassarabatt | 2.00      |            |
| ARP-00001   | 130100-002-     | Kundsaldo       |           | 2.00       |

### 

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>En verifikation med en netting för flera kunder och leverantörer
Netting kan vara användbart när organisation köper och säljer till samma företag. Istället för att betala leverantörsfakturor och vänta på att ta emot betalning för fakturor, nettas leverantören och fakturor. Nettingtransaktionen kvittas mot utestående saldon. 

Anta att leverantör 1001 och kund US-008 är samma enhet, så din organisation vill netta saldo i skulder mot saldo i fodringar innan du betalar/mottar det återstående saldot. Anta att kundposten är skyldig 75,00 EUR och leverantörsposten är skyldig 100,00 EUR vilket innebär att du kan föredrar att netta saldon och bara betala leverantören 25,00 EUR. Anta vidare att redovisningsvalutan är SEK. I det här fallet anges en nettingtransaktion i en verifikation i betalningsjournalen för leverantörsreskontra.

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| APPAYM001   | Leverantör           | 1001        | Netting         |  75,00    |            | Kund        | US-008             |

För att undvika oönskade problem med framtida kvittningar för denna transaktion ska i stället för att använda en verifikation, flera verifikationer anges i journalen för att registrera nettingtransaktionen. Observera att kund- och leverantörssaldon motbokas med ett enskilt clearingkonto för att undvika använda en verifikation som innehåller flera kund- och leverantörssaldon.

| Verifikation | Kontotyp | Konto | beskrivning | Debet | Kredit | Avräkningstyp | Motkonto |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| 001         | Kund         | US-008      |                 |           |  75,00     | Redovisning          | 999999---          |
| 002         | Leverantör           | 1001        |                 |  75,00    |            | Redovisning          | 999999---          |





