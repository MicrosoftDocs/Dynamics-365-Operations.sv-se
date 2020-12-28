---
title: Sälj och returnera produkter som inte ingår i sortimentet för en butik
description: Med Dynamics 365 Commerce kan du sälja och returnera produkter utanför sortiment.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 86c6ecf9ef67ca3ac4ed3c44d930acaa965112b6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415913"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a>Sälj och returnera produkter som inte ingår i sortimentet för en butik

[!include [banner](includes/banner.md)]

Ett vanligt scenario för alla återförsäljare är att sälja produkter till sina kunder eller acceptera returer från kunderna, även om de inte saluför specialprodukter i sin butik (d.v.s. produkter som inte är utvalda till butiken).

Här följer några vanliga scenarier:

+ En återförsäljaren saluför inte alla sina produkter i en specifik butik. De återstående produkterna lagras i lagerstället. Butiksbiträdet kan hjälpa kunden genom att söka eller leta efter produkter på lagret, lägga dem i kundvagnen och slutföra utcheckningen genom att välja en leveransmetod, till exempel levereras till en adress från lagret eller låta kunden hämta produkten från den aktuella butiken eller från en annan butik.
+ En återförsäljare saluför inte specialprodukter i butiken eller har dem inte i lager i butiken som kunden besökte, men produkterna finns i andra butiker. Butiksbiträdet kan hjälpa kunden genom att söka eller leta efter produkterna i andra butiker, lägga till dem i kundvagnen och slutföra utcheckningen genom att välja en leveransmetod.
+ En återförsäljare har många butiker i och runt en viss ort eller ett visst postnummer och vill inte tvinga kunder att returnera produkter till samma butik som de köpts in i. I stället kan kunderna returnera sina produkter i valfri butik.

Dessa vanliga scenarier är tillgängliga för återförsäljare som använder Handel. Med Handel kan du:

+ Söka eller bläddra bland produkter i andra butiker.
+ Söka eller bläddra i alla frisläppta produkter.
+ Skapa cash-and-carry-transaktioner eller kundorder.
+ Välj leveransalternativ för kundorder.
+ Hämta produkter i den aktuella butiken eller i en annan butik.
+ Avbryt en order i den aktuella butiken eller i en annan butik.
+ Returnera en order med eller utan kvitt i den aktuella butiken eller i en annan butik.
