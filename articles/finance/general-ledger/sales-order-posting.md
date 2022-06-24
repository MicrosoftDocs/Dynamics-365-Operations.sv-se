---
title: Bokföring av försäljningsorder
description: Den här artikeln ger information om fliken Försäljningsorder på sidan med lagerbokföringsprofil.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5ea1c3c90b32d18243615e3ff283e1e818ac23b6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886325"
---
# <a name="sales-order-posting"></a>Bokföring av försäljningsorder

Fliken **Försäljningsorder** på sidan **Lagerbokföringsprofiler** används för att styra hur försäljningsorder bokförs i redovisningen. Två huvudaktiviteter bokförs i huvudboken för en försäljningsorder: 

- Följesedel
- Faktura

För att en fysisk transaktion (följesedel) ska bokföras i redovisningen för en försäljningsorder måste följande villkor uppfyllas:

- På sidan **Parametrar för hantering av lager och lagerstyrning** måste kryssrutan **Bokför följesedel i redovisningen** vara markerad.
- På sidan **Artikelmodellgrupp** för artikeln som valts på försäljningsorderraden måste kryssrutan **Bokför fysiskt lager i redovisningen** vara markerad.
- På sidan **Lagerbokföringsprofil** måste huvudkontona anges för följande bokföringstyper:
  - Kostnaden för enheter, levererade
  - Kostnad för sålda varor, levererade

För att en ekonomisk transaktion (faktura) ska bokföras i redovisningen för en försäljningsorder måste följande villkor uppfyllas:

- På sidan **Artikelmodellgrupp** för artikeln som valts på försäljningsorderraden måste kryssrutan **Bokför ekonomiskt lager i redovisningen** vara markerad.
- Huvudkontona måste anges på sidan **Lagerbokföringsprofil** för följande bokföringstyper:
  - Kostnad för enheter, fakturerad
  - Kostnad för sålda varor, fakturerad
  - Intäkter
  - Rabatt\*

> [!NOTE]
> Rabattkontot är valfritt. Många redovisningsregler, som GAAP och IFRS, kräver att rabatter minskar försäljningsintäkterna och därför används inte dessa konton i många scenarier. Om lokala regler tillåter ska du använda ett separat huvudkonto för att bokföra den del av försäljningspriset som är rabatterat.

Om du vill bokföra det uppskjutna (uppskattade) intäktsvärdet i redovisningen när du genererar en följesedel för en försäljningsorder, måste följande villkor uppfyllas:

- På sidan **Artikelmodellgrupp** för artikeln som valts på försäljningsorderraden måste kryssrutan **Bokför fysiskt lager i redovisningen** vara markerad.
- På sidan **Artikelmodellgrupp** måste kryssrutan **Bokför på konto för uppskjuten intäkt vid försäljningsleverans** vara markerad.
- På sidan **Parametrar för hantering av lager och lagerstyrning** måste kryssrutan **Bokför följesedel i redovisningen** vara markerad.
- På sidan **Parametrar för hantering av lager och lagerstyrning** måste kryssrutan **Bokför fysisk moms** vara markerad.
- På sidan **Parametrar för kundreskontra** måste kryssrutan **Bokför följesedel i redovisningen** vara markerad.
- På sidan **Lagerbokföringsprofil** måste huvudkontona anges för följande bokföringstyper:
  - Uppskjuten intäkt vid leverans
  - Uppskjuten intäkt förskjuts vid leverans
  - Uppskjuten moms vid leverans

> [!NOTE]
> Vi rekommenderar vanligtvis att du aktiverar alternativen **Bokför fysiskt lager** och **Bokför följesedel i redovisningen**. Om du aktiverar de här alternativen kan det hjälpa till att påskynda procedurerna för månadsstängning, eftersom inga uppskjutningar behöver beräknas och bokföras manuellt. Boksluten återspeglar dessutom de uppskjutna beloppen automatiskt utan manuell inblandning.

> [!IMPORTANT]
> Alternativet **Bokför på konto för uppskjuten intäkt vid försäljningsleverans** används inte med intäktsredovisning. Mer information om intäktsredovisning finns i [Översikt över intäktsredovisning](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Exempel på konfiguration av bokföringsprofil 

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar:
 
- Kolumnen **Clearingkonto** visar att bokföringstypen är ett clearingkonto. Beloppet som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs. 
- Kolumnen **P/F** (F/E) anger **P** för fysisk bokföring och **F** för ekonomisk bokföring. 
- Kolumnen **Följ** visar om huvudkontot för en viss bokföringstyp normalt är samma som en annan bokföringstyp. Värdet i kolumnen visar den bokföringstyp som används vanligtvis.

> [!NOTE]
> De här huvudkontona och huvudkontonamnen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.


| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debit/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Kostnaden för enheter, levererade | 140100</br>140101 | Materiallager</br>Levererade material, inte fakturerade | Tillgång | Kredit | Ja | P | Kostnad för enheter, fakturerad | Används när följesedeln för en försäljningsorder bokförs. Motbokningen till kontot är Kostnader för sålda varor, levererad. Beloppet på detta konto återförs när en försäljningsorderfaktura bokförs. Du kanske vill använda ett Levererade material, inte fakturerade-konto för att representera det fysiska lagret och reservera Materiallager-kontot för den ekonomiska uppdateringen. |
| Kostnad för sålda varor, levererade | 500150 | Uppskjuten KSV | Utgift | Debet | Ja | P  | Används när följesedeln för en försäljningsorder bokförs. Motbokningen till kontot är Kostnaden för enheter, levererade. Beloppet på detta konto återförs när en försäljningsorderfaktura bokförs. |
| Kostnad för enheter, fakturerad | 140100 | Materiallager | Tillgång | Kredit | Nej | F | Kostnaden för enheter, levererade | Används när en försäljningsorderfaktura bokförs. Motbokningen till kontot är Kostnad för sålda varor, fakturerad. Detta konto representerar lagret i balansräkningen. |
| Kostnad för sålda varor, fakturerad | 500100 | KSV-material | Utgift | Debet | Nej | F  | Används när en försäljningsorderfaktura bokförs. Motbokningen till kontot är Kostnad för enheter, fakturerad. Detta konto representerar KSV på ditt resultatutdrag. |
| Intäkt (Försäljningsorderintäkt*) | 400100 | Intäkt material | Intäkter | Kredit | Nej | F   | Används när en försäljningsorderfaktura bokförs. Motbokningen till detta konto är Sammanfattning-kontot (Kundsaldo*) på **bokföringsprofilen för kundreskontra**. |
| Provision (Försäljning, provision*) | 602150 | Provisionsutgift | Utgift | Debet | Nej | F  | Används när provision har aktiverats och beräknats för en försäljning och bokförts under processen för försäljningsorderfaktura. Motkontot till detta konto är Utgående provision. |
| Provisionsmotkonto (Försäljning, provision motkonto*) | 201110 | Utgående provisioner | Skulder | Kredit | Ja | F | Används när provision har aktiverats och beräknats för en försäljning och bokförts under processen för försäljningsorderfaktura. Motkontot till detta konto är Provisionsutgift. |
| Uppskjuten intäkt vid leverans (Försäljning - följesedel intäkt*) | 401400 | Upplupen försäljning | Intäkter | Kredit | Ja | P  | Används när Uppskjuten intäkt vid leverans är aktiverat och bokförs när du bearbetar en följesedel för försäljningsorder. Motkontot är det här kontot är Uppskjuten intäkt. Beloppen på detta konto återförs automatiskt när du bokför försäljningsorderfakturan. |
| Uppskjuten intäkt förskjuts vid leverans (Försäljning - följesedel intäkt motkonto)* | 130400 | Kundreskontra – faktureras ej | Tillgång | Debet | Ja | P  | Används när Uppskjuten intäkt vid leverans är aktiverat och bokförs när du bearbetar en följesedel för försäljningsorder. Motkontot är det här kontot är Uppskjuten intäkt vid leverans. Beloppen på detta konto återförs automatiskt när du bokför försäljningsorderfakturan. |
| Uppskjuten moms vid leverans (Försäljning, följesedelsskatt*) | 250500 | Uppskjuten moms | Skulder | Kredit | Ja | P  | Används när Uppskjuten intäkt vid leverans aktiveras och Bokför fysisk moms har aktiverats. Momsbeloppet bokförs när du bearbetar en följesedel för försäljningsorder. |

\*Värden inom parentes i den här tabellen representerar det värde som används i fältet **Bokföringstyp** på sidan **Verifikationstransaktioner**. Du kan visa **Bokföringstyp** på sidan **Verifikationstransaktioner** på fliken **Allmänt**.

## <a name="sales-category-posting"></a>Bokföring av försäljningskategori

Ett alternativ till att ställa in lagerbokföring för alla artiklar, en artikelgrupp eller en enskild artikel är att ställa in kategorier och kontrollera redovisningsbokföringen efter försäljningskategorier. Mer information om hur du konfigurerar en kategorihierarki och tilldelar kategorier till produkter finns i [Skapa en produktklassificeringshierarki](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) och [Klassificera en produkt med hjälp av kategorihierarkier](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

När du har skapat en kategorihierarki måste du tilldela hierarkin till en eller flera typer. Om du vill använda en kategorihierarki på försäljningsorder måste du tilldela kategorin till typen Försäljningskategorihierarki. Mer information finns i [Om kategorihierarkier](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Skapa intäktsbokföring per försäljningskategori

Gör på följande sätt om du vill tilldela redovisningsbokföring för en försäljningsorder baserat på en försäljningskategori:

1. Gå till **Lagerhantering** > **Inställningar** > **Bokföring** > **Bokföring**.
2. Välj fliken **Försäljning**.
3. Välj alternativknappen för den bokföringstyp som du vill konfigurera (t.ex. **Intäkt**).
4. Välj **Ny**.
5. Välj **Kategori** i fältet **Artikelkod**.
6. Använd fältet **Kategorirelation** för att välja kategori för bokföringsprofilen.
7. I fältet **Kontokod** väljer du ett alternativ för **Tabell**, **Grupp** eller **Alla**. Om du till exempel vill använda bokföringsprofilen för alla kunder väljer du **Alla**.
   - Om du väljer **Tabell** i steg 6 väljer du **Leverantörsnummer** för bokföringsprofilen i fältet **Kontorelation**.
   - Om du väljer **Grupp** i steg 6 väljer du **Leverantörsgrupp** för bokföringsprofilen i fältet **Kontorelation**.
   - Om du väljer **Alla** i steg 6 lämnas fältet **Kontorelation** tomt.

8. Om du vill associera en viss momsgrupp som har den valda bokföringstypen, väljer du en **momsgrupp**. Om du lämnar det här fältet tomt gäller bokföringstypen för alla befintliga momsgrupper. Bokföring som anges för momsgrupper gäller bara transaktioner för försäljning och inköp.

9. I fältet **Huvudkonto** anger du kontonumret som kontotypen ska bokföras på. Markera ett av de befintliga kontonumren i kontoplanen.
