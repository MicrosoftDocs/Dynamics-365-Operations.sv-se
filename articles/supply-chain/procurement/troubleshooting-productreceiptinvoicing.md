---
title: Felsök produktinleveranser och fakturering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinleveranser och fakturering.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 22b1abec0c6dd5f571e604c5c07379b397b8bdaa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999063"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Felsök produktinleveranser och fakturering

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinleveranser och fakturering.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Jag kan inte bokföra fler än en faktura för en inköpsorderrad som har kategoribaserade artiklar.

En kvantitet är obligatorisk om du vill bokföra fakturor. Om hela kvantiteten av en rad endast har fakturerats för ett delbelopp, kan du alltså inte fakturera resten av beloppet på en annan faktura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Jag får felmeddelandet "objektreferensen har inte angetts" vid en inköpsorderbekräftelse, eller ett undantag har utlösts av målet för ett anropsundantag uppstår under bokföringen av leverantörsfakturan.

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Jag kan inte konsolidera flera produktinleveranser till en enda inköpsorder.

Du kan inte konsolidera flera produktinleveranser till en enda inköpsorder om de olika produktinleveranser raderna har olika redovisningsdatum.

I tidigare versioner av Microsoft Dynamics 365 Supply Chain Management var konsolideringen tillåten i den här situationen. Men övningen är benägen för fel. Redovisningsdatumet på inköpsorderraderna som skapas ska inte skilja sig från redovisningsdatumet på de produktinleveranser som dessa inköps orderrader skapades från. (Redovisningsdatumet på inköpsorderraderna matchar redovisningsdatumet i inköpsorderrubriken.) Därför är konsolideringen av flera produktinleveranser i en enskild inköpsorder inte längre tillåten.

Redovisningsdatumet används till exempel för budgetreservationer och inteckning. Därför bör den behållas under övergången från produktinleverans till inköpsorder.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>När produktinleveranser annulleras kan transaktioner bokföras till ett uppskjutet redovisningskonto.

### <a name="issue-description"></a>Problembeskrivning

Om en produktinleverans annulleras tillåter systemet att transaktionerna bokförs på avbrutna redovisningskonton även om huvudkontona är inaktiverade.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. På sidan **Parametrar för leverantörsreskontra** på fliken **Allmänt** se till att alternativet **Bokför produktinleverans i redovisning** anges till *Ja*.
1. Skapa en inköpsorder och lägg till en orderrad som har kvantiteten *1 000* för en produkt.
1. Bekräfta inköpsordern.
1. Bokför produktinleveransen och kontrollera verifikationerna.
1. Gör uppehåll för de relevanta huvudkontona *200140* och *140200*.
1. Annullera den bokförda produktinleveransen.
1. Lägg märke till att transaktioner kan bokföras på uppskjutna redovisningskonton.

### <a name="issue-resolution"></a>Problemlösning

Transaktioner kan bokföras på uppskjutna redovisningskonton när produktinleveranser annulleras, eftersom detta möjliggör rätt bokföring.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Ett verifikationsnummer för produktinleverans förbrukas även om ingen ekonomisk verifikation genereras vid produktinleverans.

Om alternativet **Periodisera skulder vid produktinleverans** anges till *Nej* för artikelmodellgruppen görs inga bokföringar i redovisningen. En fysisk händelse registreras emellertid i syfte att bokföras i redovisningen och den händelsen kräver ett verifikationsnummer. Detta verifikationsnummer är det verifikationsnummer som refereras i lagertransaktionerna.

Vi rekommenderar att du ställer in alternativet **Periodisera skulder vid produktinleverans** till *Ja*, vilket beskrivs i följande blogginlägg: [Bokför tillägg vid inleverans av produkten](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Bokför till debiteringskonto i redovisningsinställningen är inte aktiverat.

### <a name="issue-description"></a>Problembeskrivning

Det här problemet uppstår när en inköpsorder faktureras, om alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
1. På fliken **faktura** ange alternativet **Bokför till debiteringskonto i redovisning** till *Ja*.
1. Gå till **Lagerhantering \> Inställningar \> Bokföring \> Bokföring**.
1. På fliken **Inköpsorder** ser du till att du har tagit bort alla rader i inköpsutgifterna för produkten.
1. Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.
1. Skapa en inköpsorder På fältet **leverantörskonto** välj *1001 Acme kontorsmaterial*.
1. Lägg till en inköpsorderrad med följande inställningar:

    - **Artikelnummer:** *D0011 laserprojektor*
    - **Plats:** *1*
    - **Lagerställe:** *11*
    - **Kvantitet:** *4*

1. I Åtgärdsfönstret, på fliken **inköp**, i gruppen **åtgärd**, markerar du **bekräfta**.
1. I åtgärdsfönstret, på fliken **Inleverera** i gruppen **Generera**, markerar du **Produktinleverans**.
1. I dialogrutan **Bokför produktinleverans** i fältet **Produktinleverans** ange ett godtyckligt nummer och välj sedan **OK**.
1. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
1. I fältet **Nummer** ange ett godtyckligt nummer som fakturanummer.
1. Uppdatera matchningsstatus och bokför.
1. Observera att du nu får följande fel när du genererar en faktura från en inköpsorder: "Kontonummer för transaktionstyp Inköpsutgifter för produkten finns inte."

### <a name="issue-resolution"></a>Problemlösning

Detta beror på parameterinställningarna för fakturor och fakturagrupper. Mer information finns i följande blogginlägg: [Redovisning av inköpsavgift och lagervariation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
