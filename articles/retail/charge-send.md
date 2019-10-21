---
title: Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg
description: Det här avsnittet beskriver sändningsfunktionen Tillägg.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 088f55e5605c99f69852b4d6811b5c5504f267a2
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019472"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg

[!include [banner](includes/banner.md)]

Med sändningsfunktionen Tillägg i Retail kan kundorder placeras i en butik och levereras från en annan butik.

Kundorder i butik klientstöd med flera utförandealternativ. Exempel på utförandealternativ är:

- Hämta från samma butik ett annat datum.
- Hämta från en annan butik samma datum eller ett annat datum.
- Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.

Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter. Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från. Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken. Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikslokaliserargrupp som tilldelats butiken.

Möjligheten att välja adresser ”leverans till” ändras inte.

Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser. Eftersom reglerna om giltiga leveranssätt hanteras i Retail-administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad.
