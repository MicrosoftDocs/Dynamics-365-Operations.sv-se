---
title: Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg
description: Denna artikel beskriver sändningsfunktionen Tillägg.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: d73a21bfe9a284bd6e222e73bb0250648912b230
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863523"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg

[!include [banner](includes/banner.md)]

Med sändningsfunktionen Tillägg i Commerce kan kundorder placeras i en butik och levereras från en annan butik.

Kundorder i butik klientstöd med flera utförandealternativ. Exempel på utförandealternativ är:

- Hämta från samma butik ett annat datum.
- Hämta från en annan butik samma datum eller ett annat datum.
- Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.

Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter. Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från. Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken. Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikssökargrupp som tilldelats butiken.

Möjligheten att välja adresser ”leverans till” ändras inte.

Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser. Eftersom reglerna om giltiga leveranssätt hanteras i administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]