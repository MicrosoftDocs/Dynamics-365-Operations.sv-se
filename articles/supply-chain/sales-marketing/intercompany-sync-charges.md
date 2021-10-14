---
title: Synkronisera koncerninterna avgifter
description: Det här avsnittet innehåller information om synkronisering av koncerninterna avgifter
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c4854b698c8046fc603454c4d9d7059c938c70b3
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548542"
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
