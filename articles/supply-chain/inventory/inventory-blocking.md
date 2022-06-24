---
title: Lagerspärr
description: Det här avsnittet ger en översikt över lagerspärren, som är en del av kvalitetsinspektionsprocessen i Supply Chain Management. Du kan använda lagerspärr för att förhindra att artiklar bearbetas eller förbrukas.
author: yufeihuang
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7a16c41b56b30098945a6fbdb02577624b6e173
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857820"
---
# <a name="inventory-blocking"></a>Lagerspärr

[!include [banner](../includes/banner.md)]

Det här avsnittet ger en översikt över lagerspärren, som är en del av kvalitetsinspektionsprocessen i Supply Chain Management. Du kan använda lagerspärr för att förhindra att artiklar bearbetas eller förbrukas.

Du kan spärra lagerartiklar på fäljande sätt:

- Manuellt
- Genom att skapa en kvalitetsorder
- Genom att använda en process som genererar en kvalitetsorder
- Genom att använda lagerstatusspärr

## <a name="blocking-items-manually"></a>Spärra artiklar manuellt

Du kan spärra en kvantitet för en artikel, genom att skapa en transaktion på sidan **Lagerspärr**. Endast artiklar som finns i lager kan spärras manuellt. För manuellt spärrade kvantiteter måste du bestämma om plancerade aktiviteter inkluderar förväntade inleveranser som förväntad lagerbehållning. Förväntad inleveranser är spärrade artiklar som förväntas vara tillgängliga som lagerbehållning efter inspektion. Du kan behålla de förväntade datumet. Som standard väljs alternativet **Förväntade inleveranser** för artiklar som är spärrade via en kvalitetsorder. Du kan avbryta en manuell blockering för en kvantitet, genom att radera transaktionen på sidan **Lagerspärr**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Spärra artiklar genom att skapa en kvalitetsorder

Du kan ange artiklar som måste kontrolleras, genom att skapa en kvalitetsorder på sidan **Kvalitetsorder**. När du skapar en kvalitetsorder, spärras kvantiteten för en artikel som du anger. Samplingsplanen som är kopplad till n kvalitetsorder kontrollerar bara kvantiteten av artiklarna som måste kontrolleras, inte kvantiteten som har spärrats. Oavsett vilken kvantitet som skickas på inspektion, är den kvantitet som spärras den kvantitet av artikeln som anges på kvalitetsordern.

> [!NOTE]
> Att använda både batchens utgångsdatum och spärr av lagerstatusfunktioner stöds inte av huvudplaneringen. Detta kan resultera i dubbel uteslutning av lagerbehållning, som kan inträffa under huvudplaneringen. Vi rekommenderar att du använder koder för batchdispositionskod, i stället för lagerstatus, för spärr av utgångna batchar.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Spärra artiklar med en process som genererar en kvalitetsorder

Om en kvalitetsprocess anger att en artikel måste inspekteras kommer en kvantitet av artikeln att spärras automatiskt. Så när en kvalitetsorder genereras automatiskt kontrollerar den artikelsamplingsprovsplan som hör till kvalitetsordern både kvantiteten av artiklar som är spärrade och kvantiteten som ska kontrolleras. Om alternativet **Fullständig spärr** på sidan **Artikelsampling** har markerats är den fullständiga kvantiteten på till exempel en inköpsorderrad spärrad under inspektion oavsett artikelsamplingskvantiteten.

### <a name="example"></a>Exempel

I följande exempel skapas en kvalitetsorder när en följesedel för inköpsorder bokförs. På sidan **Kvalitetsassociationer** anger du att bokföring av en följesedel för inköpsorder som den process som aktiverar kvalitetsordern.

|Inställningar |Användaråtgärd |Resultat |
|----|---|---|
| En kvalitetsassociation anger att en kvalitetsorder måste genereras vid bokföringen av en följesedel för inköpsorder. Artikelsamplingsinställningar för kvalitetsordern anger att 10 % av inköpsorderradkvantiteten måste kontrolleras. Eftersom alternativet **Fullständig spärr** är markerad i artikelsamplingsinställningarna måste hela kvantiteten för inköpsorderraden vara spärrad vid inspektion oavsett kvantiteten som skickas för inspektion. | Följesedeln bokförs. | En kvalitetsorder genereras. 10 % av inköpsorderkvantiteten för artikeln skickas för inspektion. Den fullständiga kvantiteten på inköpsorderraden är spärrad. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Spärra artiklar med lagerstatusspärr

Du kan ange vilka sorters lagerstatus som är spärrar genom att använda parametern **Lagerspärr** på sidan **Lagerstatus**. Du kan inte använda lagerstatus som spärrstatus för tillverkningsorder, försäljningsorder, överföringsorder, utgående transaktioner eller projektintegreringer. För utgående arbete, använd artiklar med tillgänglig lagerstatus. Om det finns artiklar med statusen **bruten** och huvudplaneringen körs på dessa artiklar, betraktas artiklarna saknade, och lagret fylls automatiskt på.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Var försiktig vid spärr av artiklar där både lagerstatusspärr och kvalitetsorderspärr används

Du kan skapa en kvalitetsorder som är associerad med lager med lagerstatus där dess parameter för **lagerspärr** är aktiverad. I det här fallet skapas en ny lagerspärrpost på kvalitetsordern, utöver den som skapats av lagerstatusen. Eftersom lagerspärrningen för kvalitetsorder aktiveras parametern **Förväntade inleveranser** skapar detta en extra *beställd lager* transaktion som också är blockerad av dess lagerstatus. Den här kombinationen kan göra att du förstår vad genererade lagertransaktioner betyder, eftersom det ser ut som om den totala spärrade kvantiteten överstiger den totala tillgängliga kvantiteten. Låt oss undersöka transaktionerna på ett exempel på en inleverans av 10 enheter av artikel A0001 med en kvalitetsorder som genererats för prov 1 styck. Hur beteendet fungerar beror på om alternativet **Reservera beställda artiklar** är aktiverat på sidan **Hantering av lager och lagerställen**.

>[!NOTE]
>Om du använder lagerstatusblockering och kvalitetsorder tillsammans rekommenderar vi starkt att du har alternativet **Reservera beställda artiklar** aktiverat.

### <a name="example-with-reserve-ordered-items-enabled"></a>Exempel när "Reservera beställda artiklar" är aktiverat

När **Reservera beställda artiklar** aktiveras, har alla lagerspärrtransaktioner statusvärdet *Reserverat fysiskt* eller *Reserverat beställt*.

| Lagertransaktionsreferens | Inleverans | Utleverans | Kvantitet | Site | Lagerställe | Lagerstatus | Plats | ID-nummer | Kommentar |
|---|---|---|---|---|---|---|---|---|---|
| Inköpsorder | Inköpt | | 10 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | | 
| Lagerspärr | | Fysiskt reserverat | -9 stycken | 2 | 24 | Spärr | | | Transaktion som skapas av spärr av lagerstatus |
| Lagerspärr | | Fysiskt reserverat | -1 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | Transaktion som genereras av samplingsspärren för kvalitetsorder |
| Lagerspärr | Beställt | | 1 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | Förväntade inleveranser från samplingsspärren för kvalitetsorder |
| Lagerspärr | | Reserverat beställt | 1 stycken | 2 | 24 | Spärr | | | Transaktion som skapas av spärr av lagerstatus

### <a name="example-with-reserve-ordered-items-disabled"></a>Exempel när "Reservera beställda artiklar" är inaktiverat

När **Reservera beställda artiklar** inaktiveras, kan de förväntade inleveranserna inte reserveras eftersom de har status *Beställt*, så en del spärrningar lämnas i status *Har beställts*.

| Lagertransaktionsreferens | Inleverans | Utleverans | Kvantitet | Site | Lagerställe | Lagerstatus | Plats | ID-nummer | Kommentar |
|---|---|---|---|---|---|---|---|---|---|
| Inköpsorder | Inköpt | | 10 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | |
| Lagerspärr | | Fysiskt reserverat | -9 stycken | 2 | 24 | Spärr | | | Transaktion som skapas av spärr av lagerstatus |
| Lagerspärr | | Fysiskt reserverat | -1 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | Transaktion som genereras av samplingsspärren för kvalitetsorder |
| Lagerspärr | Beställt | | 1 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | Förväntade inleveranser från samplingsspärren för kvalitetsorder |
| Lagerspärr | | Har beställts | 1 stycken | 2 | 24 | Spärr | RECV | receiptLp1 | Transaktion som skapas av spärr av lagerstatus

Observera skillnaden i transaktionsstatus och dimensioner mellan de två ärendena. Därför rekommenderar vi att du aktiverar alternativet **Reservera beställda artiklar**.

### <a name="disable-expected-receipts-from-quality-orders-that-sample-blocked-inventory-feature"></a>Inaktivera förväntade inleveranser från kvalitetsorder som ger exempel på funktionen blockerat lager

För att förenkla lagertransaktionerna när det gäller kvalitetsorder som innehåller spärrat lager som en förfallen lagerstatus, innehåller systemet en funktion som inaktiverar förväntade inleveranser från sådana kvalitetsorder. Eftersom den förväntade inleveransen är omedelbart blockerad av lagerstatusspärr finns ingen reducering av lagerbehållningen på grund av den här ändringen.

Den här funktionen är inaktiverad som standard. Administratörer kan aktivera eller inaktivera det genom att söka efter funktionen *Inaktivera förväntade kvitton från kvalitetsorder som provar blockerat lager* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa och underhålla en lagerblockering](tasks/create-maintain-inventory-blocking.md)

[Kvalitetshanteringsprocesser](quality-management-processes.md)

[Kontrollera kvaliteten på varor](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]