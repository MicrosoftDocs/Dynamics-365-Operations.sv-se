---
title: Inställningen Bokför till debiteringskonto i redovisning är inte aktiverad
description: Det här problemet uppstår när en inköpsorder faktureras, om alternativet Bokför till debiteringskonto i redovisning är aktiverat på fliken Faktura på sidan Parametrar för leverantörsreskontra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477652"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Inställningen Bokför till debiteringskonto i redovisning är inte aktiverad

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när en inköpsorder faktureras, om alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**.

## <a name="reproduce-the-issue"></a>Återskapa problemet

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

## <a name="resolution"></a>Lösning

Detta beror på parameterinställningarna för fakturor och fakturagrupper. Mer information finns i följande blogginlägg: [Redovisning av inköpsavgift och lagervariation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
