---
title: Synkronisera koncerninterna avgifter
description: Det här avsnittet innehåller information om synkronisering av koncerninterna avgifter
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2c7f60786743cf750b2bb17ccc0dadf71d859766
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678587"
---
# <a name="synchronize-intercompany-charges"></a>Synkronisera koncerninterna avgifter

[!include [banner](../../includes/banner.md)]

Avgifter synkroniseras endast mellan en koncernintern försäljningsorder och en koncernintern inköpsorder, och synkroniseringen genomförs alltid.

Om fältet **Tillåt prisredigering** har markerats på den koncerninterna inköpsordern eller den koncerninterna försäljningsordern kan du manuellt lägga till en avgift på försäljningsordern eller inköpsordern. Annars kan du inte.

Om fältet **Tillåt prisredigering** inte har markerats på den koncerninterna försäljningsordern kan du inte lägga till avgifter manuellt på försäljningsordern.

Om fältet **Tillåt prisredigering** inte har markerats på den koncerninterna inköpsordern kan du inte lägga till avgifter på inköpsordern.

Om fältet **Tillåt prisredigering** är aktiverat på både koncerninterna inköpsordern och koncerninterna försäljningsordern kan du lägga till avgifter manuellt på båda order. Detta kan dock leda till att många avgifter läggs till på fel sätt.

Den bästa metoden att undvika den här typen av konflikter är att tillåta att avgifter kan läggas till antingen på koncerninterna försäljningsorder eller på koncerninterna inköpsorder men inte på båda.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
