---
title: Följesedelsuppdateringar för returer
description: Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 021cf6c0ff606e4b5a7139285fe7508283fb9fe2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675695"
---
# <a name="packing-slip-updates-for-returns"></a>Följesedelsuppdateringar för returer  

[!include [banner](../includes/banner.md)]


Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör. Liksom fakturauppdateringsprocessen är uppdateringen av den ekonomiska transaktionen, uppdateringen av följesedeln den fysiska uppdateringen av lagerposten, vilket innebär att det förbinder ändringar i lager. Vid returer implementeras stegen som tilldelas dispositionsåtgärden under uppdateringen av följesedeln.

Följesedelsuppdateringen kan genomföras antingen i artikelinförseljournalen eller returordern.

Som en del av bokföringsprocessen för följesedeln kan eventuellt referensnumret från kundens leveransdokument kopplas till orderraderna. Denna koppling är valfri och är endast för referens. Den skapar inga transaktionsuppdateringar.

Om inte alla förväntade returer har anlänt inkluderar du endast mottagen kvantitet i följesedelsuppdateringen. Lämna återstående artiklar på ordern tills resten av returleveransen anländer.

Om en artikel skickas tillbaka från karantänen till avdelningen för skeppning och inleverans, t.ex. när karantäninspektören inte vet var han eller hon ska placera artikeln i lagret, måste motsvarande följesedel uppdateras för att registreringen och hanteringen av dispositionskoden som har angetts som ett resultat av karantänen ska bli korrekt.

När du uppdaterar en följesedel för en returnerad artikel från ett försäljningsavtal uppdateras försäljningsavtalutfästelsen för artikeln automatiskt om du vill visa ändringarna i kvantiteten eller beloppet. 

## <a name="see-also"></a>Se även

[Utföra fakturauppdateringar för returer](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]