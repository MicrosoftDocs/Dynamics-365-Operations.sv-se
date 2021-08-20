---
title: Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg
description: Det här avsnittet beskriver sändningsfunktionen Tillägg.
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
ms.openlocfilehash: 8c9c435c9ef8f692551a216d72a76f8a71b4ce6dc03dc6b13c23364a0aa81662
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746709"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg

[!include [banner](includes/banner.md)]

Med sändningsfunktionen Tillägg i Commerce kan kundorder placeras i en butik och levereras från en annan butik.

Kundorder i butik klientstöd med flera utförandealternativ. Exempel på utförandealternativ är:

- Hämta från samma butik ett annat datum.
- Hämta från en annan butik samma datum eller ett annat datum.
- Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.

Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter. Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från. Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken. Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikslokaliserargrupp som tilldelats butiken.

Möjligheten att välja adresser ”leverans till” ändras inte.

Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser. Eftersom reglerna om giltiga leveranssätt hanteras i administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]