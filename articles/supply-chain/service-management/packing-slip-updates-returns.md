---
title: "Följesedelsuppdateringar för returer"
description: "Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7532c5b1debdb498c2d6bab129208a412387c8fa
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

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

  



