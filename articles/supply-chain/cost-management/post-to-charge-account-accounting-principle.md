---
title: Bokföringsprincip för att bokföra på debiteringskonto
description: Denna artikel ger en översikt över principen för bokföring till debiteringskonto.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: c03109baaa341b25af70840b791ddf04f692fb1a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016577"
---
# <a name="post-to-charge-account-accounting-principle"></a>Bokföringsprincip för att bokföra på debiteringskonto

Med bokföringsprincipen *bokför på debiteringskonto* kan du redovisa och enklare stämma av eventuella skillnader som uppstår i enhetspriset mellan en fysisk bokföring och ekonomisk bokföring, indirekta kostnader för inköpta artiklar och avgifter på en inköpsorder.

Två konfigurationer för koder för leverantörsreskontraavgifter på sidan **Kod för avgifter** (**Leverantörsreskontra \> Ställa in avgifter \> Kod för avgifter**) kan leda till att en inköpsorder påverkar värderingen av lagertillgångar:

- För avgiftskoder där fältet **Debettyp** har inställningen *Artikel* och fältet **Kredittyp** har inställningen *Redovisningskonto*, fungerar redovisningskontot som valts som absorptionskonto som ett lagervariationskonto.
- För avgiftskoder där fältet **Debettyp** har inställningen *Artikel* och fältet **Kredittyp** har inställningen *Kund/Leverantör*, redovisas avgiften som materialkostnad och artikelns lagervariationskonto används.

## <a name="european-special-accounting-rule"></a>Särskild redovisningsregel för Europa

I Europa används ofta redovisningsprincipen *bokför på debiteringskonto* för att lägga till en särskild redovisningsregel. En av följande metoder används till exempel vanligtvis för att ta hänsyn till lagerändringar:

- **Kostnad för försäljning-metod** – Standardkonfigurationen av lagerbokföringsprofilen stöder den här metoden. Bokföringsprincipen *bokför på debiteringskonto* är inte obligatorisk.
- **Typ av utgift-metod** – Mindre organisationer använder ofta den här metoden. Den omfattar normalt följande steg:

    1. Varor eller tjänster kostnadsförs helt vid tidpunkten för inleveransen.
    2. I slutet av perioden utförs en cykelräkning.
    3. En manuell justering för kvantitet och värde bokförs till lagret. (Motkontot är ett lagervariationskonto som motbokar utgiften som bokfördes i steg 1. Variationen i lagervärdet visas alltså bara på detta konto.)

Med principen *bokför på debiteringskonto* kan du automatisera de två bokföringarna helt. På det här sättet kan du eliminera en manuell bokföring av periodstängningsjustering.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Aktivera bokföringsprincipen att bokföra på debiteringskonto

Gör på följande sätt när du vill aktivera bokföringsprincipen *bokför på debiteringskonto*.

1. Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2. På fliken **Faktura** på snabbfliken **Faktura** anger du **Bokför på debiteringskonto i redovisningsmodulen** som *Ja*.
3. Stäng sidan.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Förutsättningar och rekommenderade parametrar för bokföringsprincipen bokför på debiteringskonto

Om du tänker ta hänsyn till inköpsavgifter och lagervariationer måste följande förutsättningar uppfyllas:

- På fliken **Faktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Konfigurera \> Parametrar för leverantörsreskontra**), måste **Bokför på debiteringskonto i redovisningsmodulen** vara *Ja*.
- På sidan **Artikelmodellgrupper** (**Kostnadshantering \> Ställ in policyer för lagerredovisning \> Artikelmodellgrupper**) måste alla alternativ ha inställningen *Ja* för varje relevant modellgrupp som innehåller artiklar som är inkluderade i en inköpsorder:

    - Bokför fysiskt lager
    - Bokför ekonomiskt lager
    - Periodisera skulder vid produktinleverans

- På fliken **Leverans** på sidan **Anskaffnings- och källparametrar** (**Anskaffning och källa \> Konfigurera \> Anskaffnings- och källparametrar**) måste **Generera avgifter för produktinleverans** ha inställningen *Ja*.
- På fliken **Lagerredovisning** på sidan **Parametrar för hantering av lager och lagerstyrning** (**Lagerhantering \> Konfigurera \> Parametrar för hantering av lager och lagerstyrning**) måste **Bokför följesedel i redovisningen** ha inställningen *Ja*.
- På fliken **Inköpsorder** på sidan **Bokför** (**Lagerhantering \> Konfigurera \> Bokför \> Bokför**) måste huvudkonton som gäller alla relevanta artiklar anges för var och en av följande bokföringstyper:

    - Inköpsomkostnad, ej fakturerad
    - Inköpsomkostnad för produkt
    - Lagervariation

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Exempelscenario 1: Förändring av självkostnaden per enhet

Exempelscenariot har följande förutsättningar:

- Först in, först ut (FIFO) kostnadsmodell

Följande procedur innehåller ett exempel som visar vad som händer när du ändrar självkostnaden per enhet för en inköpsorder.

1. Skapa en inköpsorder för en kvantitet på 1 av en artikel som har ett enhetspris på 100,00.
2. Bekräfta inköpsordern.
3. Bokför produktinleverans för inköpsordern.
4. Validera verifikationen på produktinleveransen. Följande tabell visar en exempelverifikation:

    | Bokföringstyp | Huvudkonto | Huvudkontonamn | Kontotyp | Debet/kredit? | Clearingkonto | Fysisk/ekonomisk? | Belopp |
    |---|---|---|---|---|---|---|---|
    | Inköp, lagervariation | 600170 | Lagervariationsmaterial | Utgift | Kredit | Nej | Fysiskt | -100,00 |
    | Kostnad för inköpt material som inlevererats | 140100 | Materiallager | Tillgång | Debet | Ja | Fysiskt | 100.00 |
    | Inköpsomkostnad, ej fakturerad | 600180 | Materialinleveranser | Utgift | Debet | Ja | Fysiskt | 100.00 |
    | Inköp, periodisering | 200140 | Upplupna inköp | Skulder | Kredit | Ja | Fysiskt | -100,00 |

5. Bokför fakturan för inköpsordern med det uppdaterade enhetspriset 110,00.
6. Validera verifikationen på fakturan. Följande tabell visar en exempelverifikation:

    | Bokföringstyp | Huvudkonto | Huvudkontonamn | Kontotyp | Debet/kredit? | Clearingkonto | Fysisk/ekonomisk? | Belopp |
    |---|---|---|---|---|---|---|---|
    | Inköp, lagervariation | 600170 | Lagervariationsmaterial | Utgift | Kredit | Nej | Ekonomi | -10.00 |
    | Kostnad för inköpt material som inlevererats | 140100 | Materiallager | Tillgång | Debet | Ja | Ekonomi | -100,00 |
    | Inköpsomkostnad, ej fakturerad | 600180 | Materialinleveranser | Utgift | Debet | Ja | Ekonomi | -100,00 |
    | Inköp, periodisering | 200140 | Upplupna inköp | Skulder | Kredit | Ja | Ekonomi | 100.00 |
    | Kostnad för inköpt material som fakturerats | 140100 | Materiallager | Tillgång | Debet | Nej | Ekonomi | 110.00 |
    | Inköpsomkostnad för produkt | 600180 | Materialinleverans | Utgift | Kredit | Nej | Ekonomi | 110.00 |
    | Leverantörssaldo | 211000 | Leverantörsreskontrahandel | Skulder | Kredit | Nej | Ekonomi | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Exempel 2: Avgifter och indirekta kostnader på inköpsordern

Exempelscenariot har följande förutsättningar:

- FIFO-kostnadsmodell
- **Avgiftskod 1:** Debitera artikel och kreditera redovisningskonto för 10 %
- **Avgiftskod 2:** Debitera artikel och kreditera kund/leverantör för 10,00 proportionellt
- **Indirekt kostnad:** 2,00 % läggs till inköpspriset

Följande procedur innehåller ett exempel som visar vad som händer när du inkluderar avgifter och indirekta kostnader självkostnaden på en inköpsorder.

1. Skapa en inköpsorder för en kvantitet på 1 av en artikel som har ett enhetspris på 100,00.
2. Lägg till en avgiftskod på 10 procent som debiterar artikeln och krediterar redovisningen.
3. Lägg till en avgiftskod på 10,00 som debiterar artikeln och krediterar kunden/leverantören.
4. Allokera avgifterna på inköpsorderraderna.
5. Bekräfta inköpsordern.
6. Bokför produktinleverans för inköpsordern.
7. Validera verifikationen på produktinleveransen. Följande tabell visar en exempelverifikation:

    | Bokföringstyp | Huvudkonto | Huvudkontonamn | Kontotyp | Debet/kredit? | Clearingkonto | Fysisk eller ekonomisk | Belopp |
    |---|---|---|---|---|---|---|---|
    | Inköp, lagervariation | 600170 | Lagervariationsmaterial | Utgift | Kredit | Nej | Fysiskt | -110,00 |
    | Beräknad indirekt kostnad som förbrukats | 600520 | Absorberade indirekta kostnader | Utgift | Kredit | Ja | Fysiskt | -2,40 |
    | Inköpsfrakt | 600120 | Frakt/transportkostnader | Utgift | Kredit | Nej | Fysiskt | -10.00 |
    | Kostnad för inköpt material som inlevererats | 140100 | Materiallager | Tillgång | Debet | Ja | Fysiskt | 122.40 |
    | Inköpsomkostnad, ej fakturerad | 600180 | Materialinleveranser | Utgift | Debet | Ja | Fysiskt | 110.00 |
    | Inköp, periodisering | 200140 | Upplupna inköp | Skulder | Kredit | Ja | Fysiskt | -110,00 |

8. Bokför fakturan för inköpsordern.
9. Validera verifikationen på fakturan. Följande tabell visar en exempelverifikation:

    | Bokföringstyp | Huvudkonto | Huvudkontonamn | Kontotyp | Debet/kredit? | Clearingkonto | Fysisk/ekonomisk? | Belopp |
    |---|---|---|---|---|---|---|---|
    | Inköp, lagervariation | 600170 | Lagervariationsmaterial | Utgift | Kredit | Nej | Ekonomi | 0,00 |
    | Beräknad indirekt kostnad som förbrukats | 600520 | Absorberade indirekta kostnader | Utgift | Debet | Ja | Ekonomi | 2.40 |
    | Indirekt kostnad som förbrukats | 600520 | Absorberade indirekta kostnader | Utgift | Debet | Nej | Ekonomi | -2,40 |
    | Kostnad för inköpt material som inlevererats | 140100 | Materiallager | Tillgång | Kredit | Ja | Ekonomi | -110,00 |
    | Inköpsomkostnad, ej fakturerad | 600180 | Materialinleveranser | Utgift | Kredit | Ja | Ekonomi | -110,00 |
    | Inköp, periodisering | 200140 | Upplupna inköp | Skulder | Debet | Ja | Ekonomi | 110.00 |
    | Kostnad för inköpt material som fakturerats | 140100 | Materiallager | Tillgång | Debet | Nej | Ekonomi | 110.00 |
    | Inköpsomkostnad för produkt | 600180 | Materialinleverans | Utgift | Kredit | Nej | Ekonomi | 110.00 |
    | Leverantörssaldo | 211000 | Leverantörsreskontrahandel | Skulder | Kredit | Nej | Ekonomi | -110,00 |
