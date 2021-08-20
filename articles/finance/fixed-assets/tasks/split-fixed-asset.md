---
title: Dela en anläggningstillgång
description: Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.
author: saraschi2
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ac7bc9ae9040f9668c36c570be795ebeb7c6970049ff911b1caeadd06f31d0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779000"
---
# <a name="split-a-fixed-asset"></a>Dela en anläggningstillgång

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning. Här används revisorrollen och USMF-demonstrationdata.

## <a name="create-a-new-fixed-asset"></a>Skapa en ny anläggningstillgång

1. I navigeringsfönstret går du till **Moduler \> Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
2. Välj **Ny**.
3. Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.** Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.
4. I fältet **Namn** anger du ett värde.
5. Stäng formuläret.

## <a name="split-a-fixed-asset"></a>Dela en anläggningstillgång

Innan en helt avskriven tillgång delas upp, ska tillgångens bokningsstatus ändras manuellt från **stängd** till **öppen**. Det här steget är obligatoriskt eftersom bokföringsstatus måste vara **öppen** om du måste bokföra transaktioner för tillgången (t.ex. för en avyttrande försäljning). Du måste också aktivera parametern **Tillåt flera transaktioner inom en verifikation** på fliken **Allmänt** på sidan **Redovisningsparametrar**. När status för tillgångsboken har ändrats och flera transaktioner inom en verifikation har tillåtits, utför du följande steg för att dela upp tillgången.

1. Hitta och välj länken till den anläggningstillgång som ska delas i listan.
2. Välj **Räkenskapsböcker**. Välj räkenskapsboken för att dela till den nya tillgången.
3. Välj **Funktioner**.
4. Välj **Dela anläggningstillgång**.
5. Ange eller välj ett värde i fältet **Till anläggningstillgång**.
6. I fältet **Till räkenskapsbok** väljer du den nedrullningsbara knappen för att öppna sökningen.
7. I fältet **Transaktionsdatum**, ange ett datum.
8. Ange ett tal i fältet **Procent**.
9. Ange eller välj ett värde i fältet **Journalnamn**.
10. Välj **OK**.

## <a name="post-the-journal-transaction"></a>Bokför journaltransaktionen

1. I navigeringsfönstret går du till **Moduler \> Anläggningstillgångar \> Journalposter \> Journal för anläggningstillgångar**.
2. Välj den journal som skapats med delningsprocessen i listan.
3. Markera **rader**

    - Kontrollera de skapade journalraderna.
    - En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.
    - En anskaffningstransaktion skapas för den nya tillgången för samma belopp.

4. Vald **bokföring**


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]