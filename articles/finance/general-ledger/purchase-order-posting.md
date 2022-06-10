---
title: Bokföring av inköpsorder
description: Det här ämnet beskriver fliken Inköpsorder på sidan Lagerbokföringsprofiler.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 4b36ab9da22da7d4f3e62bd2d2aba2a2ec80e60f
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8803033"
---
# <a name="purchase-order-posting"></a>Bokföring av inköpsorder

Fliken **Inköpsorder** på sidan **Lagerbokföringsprofiler** används för att styra hur inköpsorder bokförs i redovisningen. Två huvudaktiviteter bokförs till huvudboken för en inköpsorder: 

- Produktinleverans
- Faktura

För att en fysisk transaktion (produktinleverans) ska kunna bokföras till huvudboken på en inköpsorder, måste följande kryssrutor vara markerade:

- Kryssrutan **Bokför produktinleverans i redovisning** checkbox on the sidan **Parametrar för hantering av lager och lagerstyrning**.
- Kryssrutorna **Bokför fysiskt lager** och **Periodisera skulder vid produktinleverans** på sidan **Artikelmodellgrupper**.

Huvudkontona måste anges på sidan **Lagerbokföringsprofil** för följande bokföringstyper:

- Kostnad för inköpt material som inlevererats
- Inköpsomkostnad, ej fakturerad
- Inköp, periodisering

För att en ekonomisk transaktion (faktura) ska bokföras i redovisningen för en inköpsorder måste följande villkor uppfyllas:

- Kryssrutan **Bokför ekonomiskt lager** måste markeras på sidan **Artikelmodellgrupper** för den artikel som valts på inköpsorderraden.
- Huvudkontona måste anges på sidan **Lagerbokföringsprofil** för följande bokföringstyper:
  - Kostnad för inköpt material som fakturerats
  - Inköpsomkostnad för produkt
  - Inköpsomkostnad för utgift
  - Rabatt (valfritt)

## <a name="fixed-receipt-price-posting"></a>Bokföring av fast inleveranspris

Du kan använda fast kvittopris som standardkostnad för en produkt som ett alternativ till att välja **Standardkostnad** i fältet **Lagermodell** på sidan **Artikelmodellgrupper** för en artikel. Den största skillnaden när du använder **Fast inleveranspris**, det aktuella självkostnadspriset kommer att användas för artikeln när lagerinleveransen bokförs. Det finns ingen kostnadsomvärderingsprocess **Fast inleveranspris**; när en ekonomisk uppdatering bokförs används aktuellt självkostnadspris vid bokföringstillfället. Om det finns en skillnad mellan det självkostnadspris som används vid mottagandet och fakturan, kommer avvikelsen att bokföras på det fasta inleveransprisets vinst- och förlustkonton.

Om du vill använda ett fast inleveranspris för en produkt måste du konfigurera följande:

- På sidan **Artikelmodellgrupper**, välj kryssrutorna **Bokför fysiskt lager** och **Fast inleveranspris**. 
- På sidan **Parametrar för hantering av lager och lagerstyrning** välj kryssrutan **Bokför följesedel i redovisningen**.
- På sidan **Bokföringsprofil för lager**, ange huvudkonton för följande bokföringstyper:
  - Fast inleveransprisdifferens (+)
  - Fast inleveransprisdifferens (-)
  - Motkonto för fast inleveranspris

Mer information finns i [Fast inleveranspris](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Bokföring av inköpsavgifter och lagervariationer

Om du tänker ta hänsyn till inköpsavgifter och lagervariationer, gör följande:

- På sidan **Parametrar för leverantörsreskontra** på fliken **Faktura**, välj kryssrutan **Bokföra på debiteringskonto i redovisningsmodulen**.
- På sidan **Artikelmodellgrupper** för den artikel som valts på inköpsorderraden, markera kryssrutorna **Bokför fysiskt lager**, **Bokför ekonomiskt lager** och **Periodisera skulder vid produktinleverans**.
- På sidan **Anskaffnings- och inköpsparametrar** markerar du kryssrutan **Generera avgifter för produktinleverans**.
- På sidan **Parametrar för hantering av lager och lagerstyrning** välj kryssrutan **Bokför följesedel i redovisningen**.

På sidan **Lagerbokföringsprofil** måste du ange huvudkontona för följande bokföringstyper:

- Inköpsomkostnad, ej fakturerad
- Inköpsomkostnad för produkt
- Lagervariation

> [!NOTE]
> Bokföringstypen **Avgift** används inte när parametern **Bokföra på debiteringskonto i redovisningsmodulen** har valts.

För mer information, gå till [Bokföringsprincip för att bokföra på debiteringskonto](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Exempel på konfiguration av bokföringsprofil

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar:

- Kolumnen **Clearingkonto** visar att bokföringstypen är ett clearingkonto. Beloppet som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs. 
- Kolumnen **P/F** (F/E) anger **P** för fysisk bokföring och **F** för ekonomisk bokföring. 
- Kolumnen **Följ** visar om huvudkontot för en viss bokföringstyp normalt är samma som en annan bokföringstyp. Värdet i kolumnen visar den bokföringstyp som används vanligtvis.

> [!NOTE]
> De här huvudkontona och huvudkontonamnen är bara förslag. Vi rekommenderar<!--note from editor: Via Writing Style Guide.--> att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.


| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debit/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Kostnad för inköpt material som inlevererats | 140100</br>140101 | Materiallager</br>Levererade material, inte fakturerade | Tillgång | Debet | Ja | P | Kostnad för inköpt material som fakturerats | Används när en inköpsorder för produktinleverans bokförs. Motbokningen till kontot är Inköpsomkostnad, ej fakturerad. Beloppet på detta konto återförs när en inköpsorderfaktura bokförs. |
| Inköpsomkostnad, ej fakturerad | 600180 | Materialinleveranser | Utgift | Debet | Ja | P | |Används när en inköpsorder för produktinleverans bokförs. Två verifikationer skapas för inleveransen för att spåra inköpsprisavvikelser när standardkostnad används. Motbokningen till kontot på den första verifikationen är periodisering av inköp. Motbokningen på den andra verifikationen är summan av kontona Kostnad för inköpt material som inlevererats och Redovisningskonton för inköpsprisavvikelser.. Beloppen som bokfördes på detta konto återförs när en inköpsorderfaktura bokförs. |
| Kostnad för inköpt material som fakturerats | 140100 | Materiallager | Tillgång | Debet | Nej | F  |Kostnad för inköpt material som inlevererats | Används när en inköpsorderfaktura bokförs. Motbokningen till kontot är Inköpsomkostnad för produkt. Detta konto representerar lagret i balansräkningen. Kontot som används är normalt samma konto som används för Kostnader för levererade enheter och Kostnader för enheter som fakturerats för försäljningsorder. |
| Inköpsomkostnad för produkt | 600180 | Materialinleverans | Utgift | Kredit | Nej | F  | |Används när en inköpsorderfaktura bokförs. Motbokningen till detta konto är Kostnad för inköpt material. Detta konto representerar lagret i balansräkningen. |
| Fast inleveransprisvinst (Inköp, fast inleveransprisvinst*) | 510310 | Inköpsprisavvikelse | Utgift | Kredit | Nej | F | Fast inleveransprisdifferens (-) | Används när en inköpsorderfaktura bokförs och det finns en skillnad mellan det fakturerade priset och standardkostnaden för artikeln. Det här kontot används när differensen är högre. Motkontot är det här kontot är Motkonto för fast inleveranspris. |
| Fast inleveransprisdifferens (Inköp, fast inleveransprisförlust*) | 510310 | Inköpsprisavvikelse | Utgift | Debet | Nej | F | Fast inleveransprisdifferens (+) | Används när en inköpsorderfaktura bokförs och det finns en skillnad mellan det fakturerade priset och standardkostnaden för artikeln. Det här kontot används när differensen är lägre. Motkontot är det här kontot är Motkonto för fast inleveranspris. |
| Motkonto för fast inleveranspris (Inköp, motkonto för fast inleveranspris*) | 140900 | Lagervariation | Tillgång | Båda | Nej | F  | |Används när en inköpsorderfaktura bokförs och det finns en skillnad mellan det fakturerade priset och standardkostnaden för artikeln. Detta konto är motkonto till resultaträkningen för fast kvittopris. |
| Tillägg | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Detta konto används inte längre. Använd i stället lagervariationen. |
| Lagervariation | 600170 | Lagervariation | Utgift | Kredit | Nej | Båda | | Det här kontot används när: <ul><li>Det finns en skillnad i enhetspriset mellan produktinleverans och faktura.</li><li>Tillägg bokförs på artikeln.</li><li>Indirekta kostnader har<!--note from editor: Edit okay?--> lagts till de inköpta artiklarna. </li><li>Motbokningen till kontot är Inköpsomkostnad, ej fakturerat konto.</li></ul> |
| Inköp, periodisering | 200140 | Upplupna inköp | Skulder | Kredit | Y | P | |Används när ett inköpsorderproduktkvitto bokförs och alternativet att samla inköpsbelopp är aktiverat. |
| Uppskjuten moms vid inleverans | 250500 | Upplupen moms | Skulder | Kredit | Y | Båda  | |Det här kontot används när du väljer alternativet **Bokför fysisk moms** på **Parametrar för hantering av lager och lagerstyrning** och du har en inköpsorder med moms. Beloppet bokförs när du uppdaterar inköpsordern fysiskt (produktinleverans) och återförs när du bokför inköpsordern ekonomiskt (faktura). |
| Inleverans av anläggningstillgång (Debet för anläggningstillgång*) | 180100 | Materiell anläggningstillgång | Tillgång | Debet | N | Båda | Båda | Det här kontot används när du väljer alternativet på inköpsorderraden för Anläggningstillgångar. Inköpsorderintegrationen har konfigurerats för att anskaffa anläggningstillgången vid produktinleverans eller faktura. Mer information om integrering av inköpsorder för anläggningstillgångar finns i [Anskaffa tillgångar genom anskaffning](/fixed-assets/acquire-assets-procurement). |
| Inköpsomkostnad för utgift | 618900 | Diverse utgifter | Utgift | Debet | N | Båda | |Används vid bokföring av en produktinleverans eller faktura för en inköpsorder där artiklarna inte finns i lager, eller när en anskaffningskategori används. |
| Förskottsbetalning | 132190 | Förutbetalda kostnader | Tillgång | Debet | N | Båda | | Används vid bearbetning av en förskottsbetalningsfaktura på en inköpsorder. |


\*Värden inom parentes representerar det värde som används i fältet **Bokföringstyp** på sidan **Verifikationstransaktioner**. Du kan visa **Bokföringstyp** på sidan **Verifikationstransaktioner** på fliken **Allmänt**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Bokföring av anläggningstillgång med inköpsorder

Om du använder modulen **Anläggningstillgångar** och planerar att köpa anläggningstillgångar genom inköpsorder, måste du konfigurera bokföringstyper **Inleverans av anläggningstillgång** på fliken **Inköpsorder** på sidan **Bokföringsprofil för lager**. Mer information finns i [Integrering av anläggningstillgångar](/fixed-assets/fixed-asset-integration.md) och [Skapa och anskaffa tillgångar från leverantörsreskontra](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Förskottsbetalning inköpsorder fakturabokning

Om du tänker använda funktionen **förskottsbetalningsfaktura** för inköpsorder måste bokföringstypen **förskottsbetalningen** måste väljas på fliken **Inköpsorder** på sidan **Bokföringsprofil för lager**. Mer information finns i [Förskottsfakturor kontra förskottsbetalningar](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Inköpsrekvisition och inköpsorder bekräftelsebokning

Inköpsrekvisitioner och inköpsorderbekräftelser kan också konfigureras för att bokföra förinteckningar och inteckningar i redovisningen. Dessa bokföringar styrs av en bokföringsdefinition. Mer information finns i [Om inköpsorderinteckningar](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Bokföring av anskaffningskategori

Ett alternativ till att ställa in lagerbokföring för alla artiklar, en artikelgrupp eller en enskild artikel är att ställa in kategorier och kontrollera redovisningsbokföringen efter anskaffningskategorier. Mer information om hur du ställer in kategorier och tilldelar dem till produkter finns i [Exempel på bokföringsprofilkonfiguration](#sample-posting-profile-configuration) tidigare i det här avsnittet.

När du använder kategorier med inköpsorder eller leverantörsfakturor måste kategorihierarkin tilldelas till typen **Anskaffningskategorihierarki** på sidan **Rolltilldelningar för kategorihierarki**.

### <a name="vendor-invoices-with-procurement-categories"></a>Leverantörsfaktura med anskaffningskategorier

Om din organisation använder inköpsorder för vissa inköp och inte för andra, kan du bearbeta fakturor som inte är inköpsorderrelaterade på flera olika sätt. Detta inkluderar att använda journaler i **Leverantörsreskontra** eller av sidan **Väntande leverantörsfakturor** som används för att generera fakturor för inköpsorder. När du skapar fakturor för icke inköpsorderrelaterade fakturor måste du skapa anskaffningskategorier för varje typ av utgift. Du måste mappa kategorin till rätt utgiftskonto på sidan **Lagerbokföringsprofiler**.

Det exakta antalet kategorier varierar baserat på antalet utgiftskonton som du använder för att bokföra fakturorna. Du behöver minst en anskaffningskategori för varje huvudkonto som du utgift för icke-inköpsorderfakturor till. Många kategorier kan användas för ett enda huvudkonto. Den kan vara användbar för användarvänlighet, sökbarhet och rapportering av de utgiftstyper som du använder.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Fördelar med anskaffningskategorier för leverantörsfakturor

Några fördelar med att använda anskaffningskategorier för leverantörsfakturor inkluderar:

- Konsekvent användarupplevelse: När du konfigurerar inköpskategorier för alla icke-inköpsorderrelaterade utgifter, kan användarna tränas i en process för fakturering genom att använda sidan **Väntande leverantörsfakturor**.
- Förbättrad rapporteringserfarenhet: När du konfigurerar anskaffningskategorier för alla artiklar och alla icke-inköpsorderrelaterade utgifter, analyseras anskaffningskostnaden per leverantör, kategori med mera.
- Konsekvent arbetsflöde: När du använder **pågående leverantörsfakturor** för att bearbeta alla fakturor kan du skapa ett konsekvent arbetsflöde och en konsekvent godkännandeprocess med ett enda arbetsflöde.

## <a name="consignment-inventory-posting"></a>Bokföring av försändelselager

Försändelselager använder samma redovisningsbokföring som andra inköpta artiklar. Den största skillnaden är att när lagret tas emot registreras inga redovisningstransaktioner. Att överföra äganderätten till organisationen när en journal för **Lagerägarskapsändring** bokförs, genereras en verifikation för att registrera kostnaden för artikeln. Mer information finns i [Ställ in försändelse](/supply-chain/inventory/consignment.md).
