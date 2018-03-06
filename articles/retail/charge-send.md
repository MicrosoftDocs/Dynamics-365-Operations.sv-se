---
title: "Leverera en order från en annan butik"
description: "Det här avsnittet beskriver sändningsfunktionen Tillägg."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 986ec7835dac52c326085c47313205d08b1bafa8
ms.openlocfilehash: d217bc31ad9d93c5440e5329f7b7327d089137f4
ms.contentlocale: sv-se
ms.lasthandoff: 10/10/2017

---

# <a name="ship-an-order-from-a-different-store"></a>Leverera en order från en annan butik

[!include[banner](includes/banner.md)]

Med sändningsfunktionen Tillägg i Dynamics 365 for Retail kan kundorder placeras i en butik och levereras från en annan butik. Kundorder i butik klientstöd med flera utförandealternativ. Exempel på utförandealternativ är:
-   Hämta från samma butik ett annat datum.
-   Hämta från en annan butik samma datum eller ett annat datum.
-   Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.

Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter. Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från. Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken. Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikslokaliserargrupp som tilldelats butiken. 

Möjligheten att välja adresser ”leverans till” ändras inte. 

Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser. Eftersom reglerna om giltiga leveranssätt hanteras i Retail-administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad. 


