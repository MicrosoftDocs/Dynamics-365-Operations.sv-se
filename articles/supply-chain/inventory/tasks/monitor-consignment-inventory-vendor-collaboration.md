---
title: "Övervaka försändelselagret med hjälp av leverantörssamarbete"
description: "I den här proceduren visas hur du använder leverantörssamarbete om du vill visa information om lagernivån för den produkt som du har placerat i försändelse med en kund."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 567be29bd9989b3471b22d5a970ed0e51e4549ec
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Övervaka försändelselagret med hjälp av leverantörssamarbete

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du använder leverantörssamarbete om du vill visa information om lagernivån för den produkt som du har placerat i försändelse med en kund. Du kan även övervaka lagerförbrukningen när kunden tar över ägarskapet för lagret. Du kan använda den här proceduren i demonstrationsdataföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.


## <a name="view-consumed-inventory"></a>Visa förbrukat lager
1. Gå till Leverantörssamarbete > Försändelselager > Mottagna produkter från försändelselager.
    * I listan visas produktinleveransraderna som genererades när ägarskapet för försändelselagret ändrades från leverantör till kund. Du kanske måste rulla åt höger för att se kvantiteter och annan information. Du kan använda informationen i den här listan om du vill generera fakturor för kunden. Du kan även exportera datan till Microsoft Excel.   
2. Klicka på View purchase order.
3. Expandera avsnittet Radinformation.
    * Raden har markerats som Consignment (leverans), och huvudavsnittet visar att inköpsordern har statusen Received (mottagen).  
4. Stäng sidan.

## <a name="view-on-hand-inventory"></a>Visa lagerbehållning
1. Gå till Leverantörssamarbete > Försändelselager > Behållning i försändelselager.
    * Lagersidan för behållningsförsändelse (On-hand consignment inventory) visar det lager som du äger på kundens lagerställe. Du kan visa ytterligare dimensioner, till exempel plats och lagerställe, genom att klicka på fliken Display dimensions.   

