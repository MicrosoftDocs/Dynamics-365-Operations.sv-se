---
title: Transaktioner går att bokföra på ett uppskjutet huvudbokskonto
description: Om en produktinleverans annulleras tillåter systemet att transaktionerna bokförs på avbrutna redovisningskonton även om huvudkontona är inaktiverade.
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
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477680"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>Transaktioner går att bokföra på ett uppskjutet huvudbokskonto

## <a name="symptoms"></a>Symtom

Om en produktinleverans annulleras tillåter systemet att transaktionerna bokförs på avbrutna redovisningskonton även om huvudkontona är inaktiverade.

## <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. På sidan **Parametrar för leverantörsreskontra** på fliken **Allmänt** se till att alternativet **Bokför produktinleverans i redovisning** anges till *Ja*.
1. Skapa en inköpsorder och lägg till en orderrad som har kvantiteten *1 000* för en produkt.
1. Bekräfta inköpsordern.
1. Bokför produktinleveransen och kontrollera verifikationerna.
1. Gör uppehåll för de relevanta huvudkontona *200140* och *140200*.
1. Annullera den bokförda produktinleveransen.
1. Lägg märke till att transaktioner kan bokföras på uppskjutna redovisningskonton.

## <a name="resolution"></a>Lösning

Transaktioner kan bokföras på uppskjutna redovisningskonton när produktinleveranser annulleras, eftersom detta möjliggör rätt bokföring.
