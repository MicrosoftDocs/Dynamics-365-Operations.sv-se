---
title: Det går inte att avreservera lager på en försäljningsorderrad
description: Om det finns öppet arbete mot en försäljningsrad och du försöker avreservera lager på raden visas ett felmeddelande. Slutför eller radera arbete för att frigöra reservationen.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477641"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Det går inte att avreservera lager på en försäljningsorderrad

## <a name="symptoms"></a>Symtom

Om det finns öppet arbete mot en försäljningsorderrad och du försöker avreservera lager på raden visas följande felmeddelande.

> Du kan inte ta bort reservationer eftersom det finns skapade arbetsuppgifter som är beroende av reservationerna.

## <a name="resolution"></a>Lösning

Undersök om öppna förpackningsgrupparbete finns för att hämta artikeln från en förpackningsstation till en annan plats (t.ex. *Baydoor*). Granska posterna på sidorna för **Loggen över arbetsskapande** och **Arbetsinformation** för att avgöra vad som fysiskt reserverar inventeringen och sedan slutföra eller ta bort arbetet för att frigöra reservationen.
