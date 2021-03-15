---
title: Felsöka åtgärder för utgående distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med utgående distributionslager i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 165ac8145ad75c2c6619764b9abe855b9d32eb46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993988"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Felsöka åtgärder för utgående distributionslager

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med utgående distributionslager i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Följande felmeddelande visas: "försäljningsordern kan inte frisläppas".

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan uppstå av flera orsaker. Till exempel är ordern i kredithanteringsspärr och inga försändelser kan skapas förrän en giltig postadress anges för alla försäljningsrader som är kopplade till en försäljningsorder. Alternativt finns det ett orderspärr som måste åtgärdas innan ordern kan frisläppas till lagerstället. Det här undantaget kan vara kundspecifikt, eller så kan det finnas på kundkontot.

### <a name="issue-resolution"></a>Problemlösning

Lägg till eller uppdatera adressen på försäljningsordern och orderraderna och släpp sedan ordern på lagerstället. Order kan bara frisläppas till lagerstället om de har en giltig leveransadress (per adressformats inställningar i modulen **organisationsadministration**).

Undersök orderspärren och åtgärda utleveranserna. Ta sedan bort spärren från ordern eller kunden och släpp ordern på lagerstället.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Följande meddelande visas: "försändelsen för inläsningen 1 % har bekräftats." Inga rader bokförs dock.

### <a name="issue-description"></a>Problembeskrivning

En leverans av en last har bekräftats, men ingen ytterligare bokföring utfördes.

### <a name="issue-resolution"></a>Problemlösning

Försändelsebekräftelse påverkar inte bokföring. Den uppdaterar bara försändelsen och laststatus. Bokföring måste ske i en separat process.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Följande felmeddelande visas: "direktleverans kan inte behandla för lagerställe 1 % eftersom lager styrning har aktiverats. Ange ett annat lagerställe som inte är aktiverat för lagerstyrning".

### <a name="issue-description"></a>Problembeskrivning

En artikel läggs till på en försäljningsrad för direktleverans från ett lagerställe som är aktiverat för lagerstyrning (WMS). Det här felmeddelandet visas när försäljningsraden uppdateras. 

### <a name="issue-resolution"></a>Problemlösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande stöder inte WMS direktleverans. Om du vill använda direktleverans måste du därför välja en icke-WMS artikel och lagerställe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]