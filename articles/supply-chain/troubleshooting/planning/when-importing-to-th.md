---
title: Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar
description: Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049490"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar

KB-nummer: 4615588

## <a name="symptoms"></a>Symtom

I vissa situationer kanske du får följande meddelande när du öppnar sidan **Artikeldisponering** efter att du importerat artiklar via enheten *Artikeldisponering V2*:

> Vill du spara ändringarna innan du stänger?

Du får det här meddelandet även om du inte har gjort några ändringar.

## <a name="resolution"></a>Lösning

Sidan **Artikeldisponering** innehåller komplex standardlogik som kan medföra att meddelandet visas när direkta ändringar nyligen har gjorts i databasen, t.ex. genom enhetsimport. Till exempel ställs entitetsfältet `AREGENERALSETTINGSOVERRIDDEN` anges till *Nej*, men du importerar en fil som innehåller nya eller modifierade värden för fält som `PRODUCTCOVERAGEGROUPID` och/eller `VENDORACCOUNTNUMBER`. Eftersom fältet är inställt på `AREGENERALSETTINGSOVERRIDDEN` anges till *Nej*, värdena rensas automatiskt från fälten när du öppnar sidan **Artikeldisponering** för första gången efter importen. Om du sparar ändringarna så som meddelanderutan uppmanas, lagras de i databasen. I annat fall visas samma meddelande nästa gång du öppnar sidan.

Om du vill förhindra detta beteende, men även inkludera värden för fält som `PRODUCTCOVERAGEGROUPID`via enhetsimport, ställer du in `AREGENERALSETTINGSOVERRIDDEN` på *Ja* när du importerar.
