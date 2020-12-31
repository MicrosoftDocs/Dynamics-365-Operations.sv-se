---
title: Konfigurera indexräntor
description: Det här ämnet innehåller information om hur du konfigurerar indexräntor. Det krävs indexräntor om din organisation kopplar leasingbetalningsbelopp till en uppsättning indexräntor.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16b83102aa76f46473138f89ea487e71668a188c
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448204"
---
# <a name="set-up-index-rates"></a>Konfigurera indexräntor

[!include [banner](../includes/banner.md)]

Om leasingbetalningar är beroende av ett index, kan indexräntetyper läggas till och upprätthållas i systemet. Om du vill omvärdera leasingbetalningarna från sidan **Indexräntetyp**, använder omvärderingsprocessen för indexränta den senaste indexräntan från datumet för omvärderingen.

Följ stegen nedan om du vill lägga till indexräntetyper och indexräntor.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Indexräntetyper**.
2. Välj **Ny**.
3. I tillämpliga fält anger du räntetyp och namn på indexräntan.
4. Om du vill lägga till ett nytt värde för indexränta väljer du indexräntetyp och väljer sedan **Lägg till**.
5. Välj effektivt startdatum för räntan och välj räntevärdet.

Du måste välja antingen **Värdedifferens för indexränta** eller **Indexräntevärde** som indexräntemetod.

- Välj metoden **Värdedifferens för indexränta** för att beräkna en ny leasingbetalning, baserat på differensen mellan indexräntan på startdatumet och den senaste indexräntan. Indexräntan definieras i fältet **Indexränta (%)**.
- Välj metoden **Indexräntevärde** om du vill beräkna leasingbetalningen med hjälp av procentsatsen som anges i fältet **Indexränta (%)**.
