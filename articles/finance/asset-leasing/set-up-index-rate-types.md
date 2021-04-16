---
title: Konfigurera indexräntor
description: Det här ämnet innehåller information om hur du konfigurerar indexräntor. Det krävs indexräntor om din organisation kopplar leasingbetalningsbelopp till en uppsättning indexräntor.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6424248e8d01d04720ad65e80aaa543b42abccc6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823033"
---
# <a name="set-up-index-rates"></a>Konfigurera indexräntor

[!include [banner](../includes/banner.md)]

Om leasingbetalningar är beroende av ett index, kan indexräntetyper läggas till och upprätthållas i systemet. Om du vill omvärdera leasingbetalningarna från sidan **Indexräntetyp**, använder ombedömningsprocessen för indexränta den senaste indexräntan från datumet för omvärderingen.

Följ stegen nedan om du vill lägga till indexräntetyper och indexräntor.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Indexräntetyper**.
2. Välj **Ny**.
3. I tillämpliga fält anger du räntetyp och namn på indexräntan.
4. Om du vill lägga till ett nytt värde för indexränta väljer du indexräntetyp och väljer sedan **Lägg till**.
5. Välj effektivt startdatum för räntan och välj räntevärdet.

Du måste välja antingen **Värdedifferens för indexränta** eller **Indexräntevärde** som indexräntemetod.

- Välj metoden **Värdedifferens för indexränta** för att beräkna en ny leasingbetalning, baserat på differensen mellan indexräntan på startdatumet och den senaste indexräntan. Indexräntan definieras i fältet **Indexränta (%)**.
- Välj metoden **Indexräntevärde** om du vill beräkna leasingbetalningen med hjälp av procentsatsen som anges i fältet **Indexränta (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]