---
title: Övervaka försändelselagret med hjälp av leverantörssamarbete
description: I den här proceduren visas hur du använder leverantörssamarbete om du vill visa information om lagernivån för den produkt som du har placerat i försändelse med en kund.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f2e782bed4cd9f2f13e2ee45afffaef277279131
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020139"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Övervaka försändelselagret med hjälp av leverantörssamarbete

[!include [banner](../../includes/banner.md)]

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

